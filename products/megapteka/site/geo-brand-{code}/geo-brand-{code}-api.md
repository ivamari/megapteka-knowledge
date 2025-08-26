## Страница сайта /geo/brand/{code}

### PagesGeoBrandService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/pages/geo/brand
  - **Описание:** Данные аптечной сети (бренд): название, рейтинг, логотип, список связанных сетей, характеристики.
  - **Параметры (data):** brand_code

### PagesGeoBrandAbcService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/pages/geo/brand/abc
  - **Описание:** Списки городов по буквам для данной сети и активная буква.
  - **Параметры (data):** brand_code, from (буква, опц.)

### brandResolver
- Делает forkJoin( fetchPage, fetchAbc ).
- Заполняет signals BrandService.brand и BrandService.abc.

### BrandService.fetchPage
- Вызывает PagesGeoBrandService.get({brand_code}).
- Маппит brands[] в {name,url:/geo/brand/{code}}.
- Устанавливает SEO (title/description) через MetaTagService.

### BrandService.fetchAbc
- Вызывает PagesGeoBrandAbcService.get({brand_code, from}).
- Преобразует abc[] в {name,checked,link,linkParam} и cities[] в {name,url:/{city.code}/geo/city}.

### SEO
- Title: "Аптеки {ИмяСети}: Поиск и наличие лекарств - Мегаптека" (коррекция префикса "Аптеки").
- Description: "{ИмяСети}: Адреса аптек, график работы, поиск и наличие лекарств - Мегаптека".

### Навигация (breadcrumbs)
/geo → /geo/brands → /geo/brand/{code}

### Пример запросов
GET ma/site/v1/pages/geo/brand?data={"brand_code":"rigla"}
GET ma/site/v1/pages/geo/brand/abc?data={"brand_code":"rigla","from":"a"}

