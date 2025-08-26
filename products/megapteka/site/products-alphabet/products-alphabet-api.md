## Страница сайта /products/alphabet/{abc}

### ProductsAlphabetService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/products/alphabet
  - **Описание:** Получение списка товаров по букве алфавита (from, page, count передаются в JSON параметре data; city_id добавляется автоматически)

### TradeBrandsService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/trade-brands
  - **Описание:** Получение списка торговых марок (используется резолвером для дополнения страницы алфавита)

