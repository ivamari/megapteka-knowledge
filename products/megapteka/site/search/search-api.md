## Страница сайта /search

### SearchItemsService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v4/search/items
  - **Описание:** Получение результатов поиска (items, products, теги, краткая информация) по параметрам запроса

### SearchAnalyticsService
- **Метод:** post
  - **HTTP:** POST
  - **URL:** ma/site/v3/search/analytics
  - **Описание:** Отправка аналитики поиска (наличие результатов, запрос пользователя)

### SearchClickService
- **Метод:** post
  - **HTTP:** POST
  - **URL:** ma/site/v1/search/click
  - **Описание:** Отправка события клика по результату поиска (позиция, тип события)

### SearchCautionService
- **Метод:** post
  - **HTTP:** POST
  - **URL:** ma/site/v1/search/caution
  - **Описание:** Отправка предупреждения о достижении зоны догрузки результатов (scroll tracking)

