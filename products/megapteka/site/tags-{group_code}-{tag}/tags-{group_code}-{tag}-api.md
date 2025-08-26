## Страница сайта /tags/{group_code}/{tag}

### PagesSectionsService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/pages/sections
  - **Описание:** Получение структуры разделов и проверка, является ли текущий раздел конечным (is_last)

### GroupsElementsService (условно, если is_last === true)
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v3/groups/elements
  - **Описание:** Получение списка товарных элементов группы (paging, sorting, tags) при конечном разделе

### GroupsTagsService (условно, если is_last === true)
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v2/groups/tags
  - **Описание:** Получение списка тэгов для группы (используется для фильтрации и отображения)

### TagsDetailService (условно, если присутствует параметр {tag})
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/tags/detail
  - **Описание:** Детальная информация о тэге (seo, описание) для выбранного тега в группе

