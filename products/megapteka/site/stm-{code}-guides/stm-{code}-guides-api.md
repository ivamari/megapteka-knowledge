## Страница сайта /stm/{code}/guides

### ApiStmGuidesService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/stm/guides
  - **Описание:** Получение списка гайдов STM (пагинация, сортировка, фильтры)

### ApiStmGuideFiltersService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/stm/guide-filters
  - **Описание:** Получение доступных фильтров для гайдов STM

### ApiStmItemFiltersService (косвенно при переключении режима контента)
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/stm/item-filters
  - **Описание:** Загрузка фильтров товарных позиций (используется вспомогательным сервисом)

