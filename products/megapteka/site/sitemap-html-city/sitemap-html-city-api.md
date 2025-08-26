## Страница сайта /:city/sitemap-html

### PagesSitemapGeoCityBrandsService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/pages/sitemap/geo/city/brands
  - **Описание:** Список аптечных сетей для конкретного города (city_code добавляется автоматически из CityService).

### Роуты (вложенные)
- /:city/sitemap-html — секции
- /:city/sitemap-html/brands — бренды (использует PagesSitemapGeoCityBrandsService)
- /:city/sitemap-html/metro — станции метро (на текущий момент отдельный HTTP сервис не найден; вероятно статический или общий источник)
- /:city/sitemap-html/store — аптеки (отдельный HTTP сервис не найден; возможно реиспользование geo/store)

### Параметры запроса
- city_code: подставляется автоматически
- Доп. параметры в data отсутствуют (по текущей реализации)

### Пример запроса
GET ma/site/v1/pages/sitemap/geo/city/brands?data={"city_code":"moskva"}

### Примечания
Если появятся сервисы для metro или store в sitemap-html, дополнить документ.

