## Страница сайта /specials

### SpecialsService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/specials
  - **Описание:** Список публикаций «Мегасоветы» (пагинация page/count, поиск по query; параметры передаются как JSON в query параметре data)

### TagsSpecialsService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/tags/specials
  - **Описание:** Список публикаций по конкретному тегу (tag_code обязательный; пагинация page/count). Параметры в JSON (query param data).

### GroupsSpecialsService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/groups/specials
  - **Описание:** Список публикаций по группе тегов (group_code обязательный; добавляется city_id автоматически). Параметры в JSON (query param data).

### Параметры (общие поля пагинации Page)
- page: номер страницы (>=1)
- count: размер страницы
- query: строка поиска (только для общего списка)
- tag_code: код тега (для TagsSpecialsService)
- group_code: код группы (для GroupsSpecialsService)
- city_id: добавляется GroupsSpecialsService автоматически

### Роутинг /specials
- /specials — общий список
- /specials/tag_<tag_code> — список по тегу (распознаётся PageMatcher по префиксу tag_)
- /specials/:specials_code — детальная публикация (см. отдельный файл specials-{specials_code}-api)

### Поведение
- listResolver формирует параметры (query → page=1) и вызывает ListService.getListSpecials (обёртка над SpecialsService.get с мержем локальных params).
- При page>1 происходит дозагрузка и конкатенация list.
- Для адресов с tag_ используется TagsSpecialsService (через Section/специализированные компоненты) — аналогичная пагинация.
- Для групп (например раздел каталога «specials») используется GroupsSpecialsService (city_id).

### Используемые сервисы (косвенно)
- ListService (агрегация и склейка страниц)
- SpecialsSearchService (хранение строки поиска query)
- TagsSpecialsService / GroupsSpecialsService (варианты выборки по тегу / группе)

### Примеры
- GET ma/site/v1/specials?data={"page":1,"count":9}
- GET ma/site/v1/specials?data={"page":1,"count":9,"query":"витамины"}
- GET ma/site/v1/tags/specials?data={"tag_code":"immunity","page":1,"count":9}
- GET ma/site/v1/groups/specials?data={"group_code":"season","page":1,"count":9,"city_id":<auto>}
