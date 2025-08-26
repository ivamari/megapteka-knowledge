## Страница сайта /{product_code} и /{city}/{product_code}

### ApiProductsService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v3/products
  - **Описание:** Базовая информация о продукте (name, seo, redirect...). code + city_id (авто) в JSON параметре data. withCredentials: true.

### ProductsItemsService (детализация товарных позиций)
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v4/products/items
  - **Описание:** Список товарных SKU продукта (фильтры, сортировка). product_code + city_id.

### ProductAnalogItemsService (аналоги)
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v4/products/analog-items
  - **Описание:** Аналогичные товары (product_code + city_id).

### ProductsFeedbackService (отзывы)
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v3/products/feedback
  - **Описание:** Отзывы и рейтинги (product_code + city_id). withCredentials: true.

### ProductsItemsTopService (популярные товары / топ)
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v2/products/items/top
  - **Описание:** Топовые предложения по продукту (product_code + city_id).

### Роутинг вложенный
- /{product_code} — деталь (detailResolver)
- /{product_code}/reviews — отзывы (reviewsResolver)
- /{product_code}/analogues — аналоги (analoguesResolver)
- /{product_code}/video — видео вкладка (videoResolver, без HTTP)
- /{product_code}/:filter_code — устаревший формат, выполняется 301 на query ?filter= (detailResolver)

### productResolver
- Ждет CityService.loading$ == true, затем ApiProductsService.get({code}).
- Если нет result.name => 404 (RedirectV2Inject._404()).
- Если есть result.redirect => 301 (подставляет city в url через #city#).

### detailResolver
- Собирает параметры через ItemFilterListService.getParams.
- Если присутствует filter_code в path => 301 на ?filter=.
- Вызывает ProductsItemsService. Если items пусты при наличии filter_code => 410.

### analoguesResolver
- Перенос старых URL с городом: если есть :city => 410.
- Загружает ProductAnalogItemsService; если items пусты => 404.

### reviewsResolver
- Если в отзывов list.length == 0 => 404.
- Загружает одновременно ProductsFeedbackService.get + ProductsItemsTopService.get.

### videoResolver
- Возвращает true (нет отдельного HTTP вызова).

### Основные параметры JSON data
- code / product_code
- page, count (для отзывов / списков)
- city_id (автоматически добавляется сервисами)
- фильтры (зависят от ItemFilterListService)

### Примеры запросов
- GET ma/site/v3/products?data={"code":"aspirin","city_id":123}
- GET ma/site/v4/products/items?data={"product_code":"aspirin","city_id":123}
- GET ma/site/v4/products/analog-items?data={"product_code":"aspirin","city_id":123}
- GET ma/site/v3/products/feedback?data={"code":"aspirin","page":1,"count":10,"city_id":123}
- GET ma/site/v2/products/items/top?data={"product_code":"aspirin","city_id":123}

