## Страница сайта /brand/{code}/guides

### ApiBrandGuidesService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/brand/guides
  - **Описание:** Получение списка гайдов бренда (пагинация, сортировка, фильтры)

### ApiBrandGuideFiltersService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/brand/guide-filters
  - **Описание:** Получение доступных фильтров для гайдов бренда

### ApiBrandItemFiltersService (косвенно при загрузке фильтров для переключения в режим items)
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/brand/item-filters
  - **Описание:** Загрузка фильтров товарных позиций (используется вспомогательным сервисом при смене типа контента)

