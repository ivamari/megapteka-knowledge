## Страница сайта /geo и /:city/geo

### PagesGeoStoreService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/pages/geo/store
  - **Описание:** Детальная страница конкретной аптеки (store_id)

### PagesGeoBrandService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/pages/geo/brand
  - **Описание:** Посадочная аптечной сети (code)

### PagesGeoBrandAbcService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/pages/geo/brand/abc
  - **Описание:** Списки аптечных сетей по букве (abc)

### Роуты
- /geo
- /geo/city, /geo/city/:abc
- /geo/brands, /geo/brands/:abc
- /geo/brand/:code
- /geo/store/:store_id
- /geo/metro/:code

### Резолверы / Guards
- geoResolver — минимальная задержка (оптимизация INP)
- brandResolver — загрузка данных сети (PagesGeoBrandService / PagesGeoBrandAbcService)
- storeResolver — загрузка данных аптеки (PagesGeoStoreService)

### Параметры
Передаются в JSON параметре data (code, store_id, abc и т.п.).

### См. также (детализированные документы)
- geo-brand-{code}/geo-brand-{code}-api.md — подробности страницы сети (/geo/brand/{code})
- geo-store-{store_id}/geo-store-{store_id}-api.md — подробности страницы аптеки (/geo/store/{store_id})

(Подробные поля ответа, SEO и breadcrumbs вынесены в отдельные файлы выше.)
