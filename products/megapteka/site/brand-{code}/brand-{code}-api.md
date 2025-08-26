## Страница сайта /brand/{code}

### ApiBrandService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/brand
  - **Описание:** Детальная информация о бренде (seo, описания, параметры страницы)

### ApiBrandItemsService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v2/brand/items
  - **Описание:** Список товарных позиций бренда (пагинация, сортировка, фильтры в query JSON)

### ApiBrandItemFiltersService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/brand/item-filters
  - **Описание:** Доступные фильтры для товарных позиций бренда

### ApiBrandGuidesService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/brand/guides
  - **Описание:** Список гайдов (статей/подборок) по бренду (пагинация, сортировка, фильтры)

### ApiBrandGuideFiltersService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/brand/guide-filters
  - **Описание:** Список фильтров для гайдов бренда

(Внутренние резолверы brandStmResolver / brandStmItemsResolver / brandStmGuidesService выбирают конкретный сервис и не выполняют собственных HTTP запросов напрямую.)

