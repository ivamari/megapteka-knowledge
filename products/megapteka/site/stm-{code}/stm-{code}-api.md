## Страница сайта /stm/{code}

### ApiStmService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/stm
  - **Описание:** Детальная информация о собственной торговой марке (seo, описание, настройки)

### ApiStmItemsService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v2/stm/items
  - **Описание:** Список товарных позиций STM (пагинация, сортировка, фильтры)

### ApiStmItemFiltersService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/stm/item-filters
  - **Описание:** Фильтры для списка товаров STM

### ApiStmGuidesService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/stm/guides
  - **Описание:** Список гайдов (подборок) STM

### ApiStmGuideFiltersService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/stm/guide-filters
  - **Описание:** Фильтры для гайдов STM

(Резолверы brandStmResolver / brandStmItemsResolver / brandStmGuidesService выбирают нужный набор сервисов.)

