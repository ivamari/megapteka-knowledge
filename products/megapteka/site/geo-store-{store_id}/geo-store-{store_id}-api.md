## Страница сайта /geo/store/{store_id}

### PagesGeoStoreService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/pages/geo/store
  - **Описание:** Детальная страница аптеки: основной объект store, ближайшие аптеки, бренд, город, отзывы, SEO.
  - **Параметры (data):** store_id

### storeResolver
- Валидирует наличие store_id.
- Вызывает StoreService.fetch(store_id).
- Если нет данных или отсутствует store → 404.
- Сохраняет результат в StoreService.data сигнал.

### StoreService.fetch
- Вызывает PagesGeoStoreService.get({store_id}).
- Преобразует stores_nearest в массив точек карты stores_map.
- Генерирует brands[] ссылки: /{city.code}/geo/brand/{brand.code}/

### SEO
- Title / Description устанавливаются через setSeo(title, description) (из ответа seo).

### Навигация (breadcrumbs)
/geo → /geo/city → /{cityCode}/geo/city → /{cityCode}/geo/brand/{brand_code} → /geo/store/{store_id}

### Map interaction
- onClickMapName(id) навигирует на /geo/store/{id}.

### Пример запроса
GET ma/site/v1/pages/geo/store?data={"store_id":12345}

