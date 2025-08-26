## Страница сайта /specials/{specials_code}

### SpecialsDetailService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v2/specials/detail
  - **Описание:** Детальная публикация «Мегасоветы» по коду (code в JSON параметре data; автоматически добавляется city_id из CityService).

### Параметры запроса
- code: string (обязательный)
- city_id: number (добавляется автоматически)

### Основные поля ответа (SpecialsDetailOutGet)
- id, code
- title — заголовок
- author_name / author_code / author_photo_url — данные автора
- detail_image_url / detail_image_alt
- preview_descr — краткое описание
- seo_title / seo_description
- warning_text — предупреждение (опц.)
- tags[]: {code,name,group_code}
- blocks[]: контентные блоки (id, name, sort, type_id, value)
  - type_id: 1|2|3|4|5|6|7|8|222 (разные типы контента; 222 — спец. тип)
- date_publish (строка) / date_publish_ts (unix)
- is_index: boolean
- editor_*: данные редактора (description, name, photo_url, url)
- seo_links: {title, links[]:{href,text}} | null
- redirect: string (если нужно 301)
- is_guide: boolean
- podcast: {title,text} | null

### Поведение
- detailResolver ожидает загрузку города (CityService.loading$) и вызывает SpecialsDetailService.get({code}).
- Если в ответе есть redirect — выполняется RedirectV2Inject._301(redirect).
- Если ответ пустой — выполняется RedirectV2Inject._404().
- Иначе в компонент прокидывается полученный SpecialsDetailOutGet.

### Используемые сервисы (косвенно)
- CityService (добавление city_id)
- RedirectV2Inject (обработка 301 / 404)

### Пример запроса
GET ma/site/v2/specials/detail?data={"code":"vitaminy-dlya-detey","city_id":<auto>}
