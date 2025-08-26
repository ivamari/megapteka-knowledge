## Страница сайта /tags/{group_code}

### PagesSectionsService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/pages/sections
  - **Описание:** Получение структуры подразделов и признака конечного раздела (is_last) по коду группы

(Условно, если раздел конечный is_last === true):

### GroupsElementsService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v3/groups/elements
  - **Описание:** Список товарных элементов конечного раздела (paging, sorting)

### GroupsTagsService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v2/groups/tags
  - **Описание:** Список доступных тегов для раздела (для фильтрации и отображения)

(В этом варианте без параметра {tag} не вызывается TagsDetailService.)

