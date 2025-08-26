## Страница сайта /what-if/{topic_id}

### WhatIfDetailService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/what-if/detail
  - **Описание:** Детальная страница "Что делать, если?" по topic_id (передаётся в JSON параметре data)

### WhatIfDetailResolver
- Валидирует topic_id (число). При ошибке 404 через RedirectV2Inject._404().
- В случае успеха добавляет seo.title и breadcrumb в route.data.

### Структура ответа (WhatIfDetailOutGet)
- sections[]: {title, image_url, blocks[]:{type_id, value{text}}}
- seo: {title, h1, description, json-ld?}

### Пример запроса
GET ma/site/v1/what-if/detail?data={"topic_id":123}

