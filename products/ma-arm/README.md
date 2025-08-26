# База знаний

Это централизованная база знаний для административной панели "Мегаптека". Здесь вы найдете документацию по всем основным страницам и функциональным модулям приложения.

## Структура документации

Каждая страница ARM имеет соответствующий `.md` файл в этой директории, который описывает её назначение, URL, функциональность и другие важные детали.

---

### 1. Авторизация
- **URL**: `/auth`
- **Файл документации**: [auth.component.md](./pages/auth.component.md)
- **Описание**: Страница входа в систему.
- **Функциональность**: Аутентификация пользователя по логину и паролю.

### 2. Клиенты: Черный список
- **URL**: `/clients/blacklist`
- **Файл документации**: [clients-blacklist.component.md](./pages/clients-blacklist.component.md)
- **Описание**: Управление заблокированными клиентами.
- **Функциональность**: Просмотр, добавление и удаление клиентов из черного списка.

### 3. Клиенты: Смена пароля
- **URL**: `/clients/password`
- **Файл документации**: [clients-password.component.md](./pages/clients-password.component.md)
- **Описание**: Смена пароля для клиентских аккаунтов.
- **Функциональность**: Поиск клиента и установка нового пароля.

### 4. Контент: SEO - Редактирование города
- **URL**: `/content/cities-seo/edit/:id`
- **Файл документации**: [content-cities-seo-edit.component.md](./pages/content-cities-seo-edit.component.md)
- **Описание**: Редактирование SEO-атрибутов для конкретного города.
- **Функциональность**: Изменение мета-тегов, заголовков и описаний.

### 5. Контент: SEO - Список городов
- **URL**: `/content/cities-seo`
- **Файл документации**: [content-cities-seo-list.component.md](./pages/content-cities-seo-list.component.md)
- **Описание**: Список городов для SEO-оптимизации.
- **Функциональность**: Поиск и навигация к странице редактирования SEO-атрибутов города.

### 6. Контент: Отзывы - Добавление
- **URL**: `/content/feedback/items/add`
- **Файл документации**: [content-feedback-items-add.component.md](./pages/content-feedback-items-add.component.md)
- **Описание**: Создание нового отзыва.
- **Функциональность**: Добавление отзыва от имени пользователя.

### 7. Контент: Отзывы - Редактирование
- **URL**: `/content/feedback/items/edit/:id`
- **Файл документации**: [content-feedback-items-edit.component.md](./pages/content-feedback-items-edit.component.md)
- **Описание**: Редактирование существующего отзыва.
- **Функциональность**: Изменение текста, рейтинга и статуса отзыва.

### 8. Контент: Отзывы - Список
- **URL**: `/content/feedback/items`
- **Файл документации**: [content-feedback-items-list.component.md](./pages/content-feedback-items-list.component.md)
- **Описание**: Просмотр и управление всеми отзывами.
- **Функциональность**: Фильтрация, поиск и модерация отзывов.

### 9. Контент: Партнеры - Редактирование
- **URL**: `/content/partners/edit/:id`
- **Файл документации**: [content-partners-edit.component.md](./pages/content-partners-edit.component.md)
- **Описание**: Редактирование информации о партнере.
- **Функциональность**: Обновление данных партнера.

### 10. Контент: Партнеры - Список
- **URL**: `/content/partners`
- **Файл документации**: [content-partners-list.component.md](./pages/content-partners-list.component.md)
- **Описание**: Список всех партнеров системы.
- **Функциональность**: Просмотр и поиск партнеров.

### 11. Дашборд
- **URL**: `/dashboard`
- **Файл документации**: [dashboard.component.md](./pages/dashboard.component.md)
- **Описание**: Главная страница с основной статистикой.
- **Функциональность**: Отображение ключевых метрик и виджетов.

### 12. Товары: Проверка резервирования (ATC)
- **URL**: `/items/atc-check`
- **Файл документации**: [items-atc-check.component.md](./pages/items-atc-check.component.md)
- **Описание**: Инструмент для проверки доступности товаров для добавления в корзину.
- **Функциональность**: Проверка статуса резервирования товаров.

### 13. Товары: Наличие в городе
- **URL**: `/items/availability/city`
- **Файл документации**: [items-availability-city.component.md](./pages/items-availability-city.component.md)
- **Описание**: Проверка наличия товаров в аптеках города.
- **Функциональность**: Поиск и просмотр остатков.

### 14. Товары: Наличие рядом
- **URL**: `/items/availability/near`
- **Файл документации**: [items-availability-near.component.md](./pages/items-availability-near.component.md)
- **Описание**: Поиск товаров в ближайших аптеках.
- **Функциональность**: Поиск на карте и по адресу.

### 15. Товары: Создание
- **URL**: `/items/create`
- **Файл документации**: [items-create.component.md](./pages/items-create.component.md)
- **Описание**: Форма создания новой товарной позиции.
- **Функциональность**: Добавление товаров в каталог.

### 16. Товары: Проверка запретов
- **URL**: `/items/disable-check`
- **Файл документации**: [items-disable-check.component.md](./pages/items-disable-check.component.md)
- **Описание**: Проверка, почему товар может быть запрещен к продаже.
- **Функциональность**: Анализ запретов на разных уровнях.

### 17. Товары: Запреты на устройствах
- **URL**: `/items/disable-devices/edit`
- **Файл документации**: [items-disable-devices-edit.component.md](./pages/items-disable-devices-edit.component.md)
- **Описание**: Управление запретами на продажу с определенных устройств.
- **Функциональность**: Настройка правил запрета.

### 18. Товары: Запреты в сетях
- **URL**: `/items/disable-networks/edit/:id`
- **Файл документации**: [items-disable-networks-edit.component.md](./pages/items-disable-networks-edit.component.md)
- **Описание**: Редактирование правил запрета для аптечных сетей.
- **Функциональность**: Управление запретами на уровне сети.

### 19. Товары: Список запретов в сетях
- **URL**: `/items/disable-networks`
- **Файл документации**: [items-disable-networks-list.component.md](./pages/items-disable-networks-list.component.md)
- **Описание**: Просмотр всех сетей с настроенными запретами.
- **Функциональность**: Навигация к редактированию запретов.

### 20. Товары: Запреты в аптеках
- **URL**: `/items/disable-stores/edit/:id`
- **Файл документации**: [items-disable-stores-edit.component.md](./pages/items-disable-stores-edit.component.md)
- **Описание**: Управление запретами на продажу в конкретных аптеках.
- **Функциональность**: Настройка индивидуальных запретов.

### 21. Товары: Список запретов в аптеках
- **URL**: `/items/disable-stores`
- **Файл документации**: [items-disable-stores-list.component.md](./pages/items-disable-stores-list.component.md)
- **Описание**: Список аптек с настроенными запретами.
- **Функциональность**: Поиск и навигация к редактированию.

### 22. Товары: Редактирование
- **URL**: `/items/edit/:id`
- **Файл документации**: [items-edit.component.md](./pages/items-edit.component.md)
- **Описание**: Редактирование карточки товара.
- **Функциональность**: Изменение всех атрибутов товара.

### 23. Товары: Исключения
- **URL**: `/items/exceptions`
- **Файл документации**: [items-exceptions-list.component.md](./pages/items-exceptions-list.component.md)
- **Описание**: Список товаров-исключений из правил.
- **Функциональность**: Просмотр и управление исключениями.

### 24. Товары: Новое исключение
- **URL**: `/items/exceptions/new`
- **Файл документации**: [items-exceptions-new.component.md](./pages/items-exceptions-new.component.md)
- **Описание**: Создание нового исключения для товара.
- **Функциональность**: Добавление товара в список исключений.

### 25. Товары: Товары бренда
- **URL**: `/items/from-brand`
- **Файл документации**: [items-from-brand.component.md](./pages/items-from-brand.component.md)
- **Описание**: Просмотр всех товаров, принадлежащих бренду.
- **Функциональность**: Поиск по бренду.

### 26. Товары: Выведенные из ассортимента
- **URL**: `/items/gone`
- **Файл документации**: [items-gone-list.component.md](./pages/items-gone-list.component.md)
- **Описание**: Список товаров, снятых с продажи.
- **Функциональность**: Просмотр архива товаров.

### 27. Товары: Редактирование группы
- **URL**: `/items/goods/edit/:id`
- **Файл документации**: [items-goods-edit.component.md](./pages/items-goods-edit.component.md)
- **Описание**: Управление товарными группами.
- **Функциональность**: Редактирование атрибутов группы.

### 28. Товары: Список групп
- **URL**: `/items/goods`
- **Файл документации**: [items-goods-list.component.md](./pages/items-goods-list.component.md)
- **Описание**: Иерархический список товарных групп.
- **Функциональность**: Навигация по каталогу групп.

### 29. Товары: Создание несовместимости
- **URL**: `/items/incompatibility/create`
- **Файл документации**: [items-incompatibility-create.component.md](./pages/items-incompatibility-create.component.md)
- **Описание**: Указание несовместимых друг с другом товаров.
- **Функциональность**: Создание правил несовместимости.

### 30. Товары: Список несовместимостей
- **URL**: `/items/incompatibility`
- **Файл документации**: [items-incompatibility-list.component.md](./pages/items-incompatibility-list.component.md)
- **Описание**: Просмотр всех правил несовместимости.
- **Функциональность**: Поиск и управление правилами.

### 31. Товары: Проверка наценки
- **URL**: `/items/markup-check`
- **Файл документации**: [items-markup-check.component.md](./pages/items-markup-check.component.md)
- **Описание**: Инструмент для проверки правил наценки.
- **Функциональность**: Расчет и отображение наценки для товара.

### 32. Товары: Объединение по штрих-коду
- **URL**: `/items/merge/check-barcode`
- **Файл документации**: [items-merge-items-check-barcode.component.md](./pages/items-merge-items-check-barcode.component.md)
- **Описание**: Поиск и объединение дублей товаров по штрих-коду.
- **Функциональность**: Сканирование и слияние карточек.

### 33. Товары: Проверка объединения
- **URL**: `/items/merge/check`
- **Файл документации**: [items-merge-items-check.component.md](./pages/items-merge-items-check.component.md)
- **Описание**: Ручная проверка и объединение товаров.
- **Функциональность**: Поиск дублей и их слияние.

### 34. Товары: Создание лимита на заказ
- **URL**: `/items/order-limit/create`
- **Файл документации**: [items-order-limit-create.component.md](./pages/items-order-limit-create.component.md)
- **Описание**: Установка ограничений на количество товара в заказе.
- **Функциональность**: Создание правил лимитов.

### 35. Товары: Список лимитов на заказ
- **URL**: `/items/order-limit`
- **Файл документации**: [items-order-limit-list.component.md](./pages/items-order-limit-list.component.md)
- **Описание**: Просмотр всех действующих лимитов.
- **Функциональность**: Управление лимитами.

### 36. Товары: Паттерны для удаления
- **URL**: `/items/patterns-to-delete`
- **Файл документации**: [items-patterns-to-delete-list.component.md](./pages/items-patterns-to-delete-list.component.md)
- **Описание**: Управление паттернами для автоматического удаления товаров.
- **Функциональность**: Создание и редактирование правил.

### 37. Товары: Связи цен
- **URL**: `/items/prices-connections`
- **Файл документации**: [items-prices-connections.component.md](./pages/items-prices-connections.component.md)
- **Описание**: Управление связями цен между товарами.
- **Функциональность**: Настройка зависимостей цен.

### 38. Товары: Редактирование продукта
- **URL**: `/items/products/edit/:id`
- **Файл документации**: [items-products-edit.component.md](./pages/items-products-edit.component.md)
- **Описание**: Редактирование основного продукта (эталона).
- **Функциональность**: Изменение атрибутов эталонного товара.

### 39. Товары: Список продуктов
- **URL**: `/items/products`
- **Файл документации**: [items-products-list.component.md](./pages/items-products-list.component.md)
- **Описание**: Список всех эталонных товаров.
- **Функциональность**: Поиск и навигация к редактированию.

### 40. Товары: Рекомендации для продуктов
- **URL**: `/items/products/recommendations`
- **Файл документации**: [items-products-recommendations-list.component.md](./pages/items-products-recommendations-list.component.md)
- **Описание**: Управление рекомендованными товарами для продуктов.
- **Функциональность**: Настройка связей рекомендаций.

### 41. Товары: Объединение поиска
- **URL**: `/items/search-union`
- **Файл документации**: [items-search-union.component.md](./pages/items-search-union.component.md)
- **Описание**: Инструмент для объединения поисковых запросов.
- **Функциональность**: Создание синонимов и связей для поиска.

### 42. Товары: Создание раздела
- **URL**: `/items/sections/create`
- **Файл документации**: [items-sections-create.component.md](./pages/items-sections-create.component.md)
- **Описание**: Создание нового раздела в каталоге.
- **Функциональность**: Добавление разделов в иерархию.

### 43. Товары: Редактирование раздела
- **URL**: `/items/sections/edit/:id`
- **Файл документации**: [items-sections-edit.component.md](./pages/items-sections-edit.component.md)
- **Описание**: Изменение названия и атрибутов раздела.
- **Функциональность**: Редактирование разделов каталога.

### 44. Товары: Список разделов
- **URL**: `/items/sections`
- **Файл документации**: [items-sections-list.component.md](./pages/items-sections-list.component.md)
- **Описание**: Просмотр иерархии разделов каталога.
- **Функциональность**: Управление структурой каталога.

### 45. Товары: Рекомендации для разделов
- **URL**: `/items/sections/recommendations`
- **Файл документации**: [items-sections-recommendations-list.component.md](./pages/items-sections-recommendations-list.component.md)
- **Описание**: Управление рекомендованными товарами для разделов.
- **Функциональность**: Настройка рекомендаций на уровне разделов.

### 46. Товары: Редактирование подписок
- **URL**: `/items/subscriptions/edit/:id`
- **Файл документации**: [items-subscriptions-edit.component.md](./pages/items-subscriptions-edit.component.md)
- **Описание**: Управление подписками на уведомления о товарах.
- **Функциональность**: Редактирование статуса подписок.

### 47. Товары: Список подписок
- **URL**: `/items/subscriptions`
- **Файл документации**: [items-subscriptions-list.component.md](./pages/items-subscriptions-list.component.md)
- **Описание**: Просмотр всех активных подписок.
- **Функциональность**: Поиск и фильтрация подписок.

### 48. Товары: Список тегов
- **URL**: `/items/tags`
- **Файл документации**: [items-tags-list.component.md](./pages/items-tags-list.component.md)
- **Описание**: Управление тегами для товаров.
- **Функциональность**: Создание, редактирование и удаление тегов.

### 49. Товары: Без эталона
- **URL**: `/items/without-etalon`
- **Файл документации**: [items-without-etalon.component.md](./pages/items-without-etalon.component.md)
- **Описание**: Список товаров, не привязанных к эталону.
- **Функциональность**: Поиск и привязка к эталонам.

### 50. Уведомления: Архив Push
- **URL**: `/notifications/push/archive`
- **Файл документации**: [notifications-push-archive.component.md](./pages/notifications-push-archive.component.md)
- **Описание**: Архив отправленных Push-уведомлений.
- **Функциональность**: Просмотр истории уведомлений.

### 51. Уведомления: Новое Push
- **URL**: `/notifications/push/new`
- **Файл документации**: [notifications-push-new.component.md](./pages/notifications-push-new.component.md)
- **Описание**: Создание и отправка нового Push-уведомления.
- **Функциональность**: Настройка и рассылка уведомлений.

### 52. Уведомления: Установка SMS
- **URL**: `/notifications/sms/install`
- **Файл документации**: [notifications-sms-install.component.md](./pages/notifications-sms-install.component.md)
- **Описание**: Настройка SMS-уведомлений для установки приложения.
- **Функциональность**: Управление шаблонами SMS.

### 53. Уведомления: Ручная отправка SMS
- **URL**: `/notifications/sms/manual`
- **Файл документации**: [notifications-sms-manual.component.md](./pages/notifications-sms-manual.component.md)
- **Описание**: Ручная отправка SMS-сообщений.
- **Функциональность**: Отправка кастомных SMS.

### 54. Заказы: Активные
- **URL**: `/orders/active`
- **Файл документации**: [orders-active.component.md](./pages/orders-active.component.md)
- **Описание**: Список всех текущих заказов.
- **Функциональность**: Просмотр, фильтрация и управление заказами.

### 55. Заказы: Архив
- **URL**: `/orders/archive`
- **Файл документации**: [orders-archive.component.md](./pages/orders-archive.component.md)
- **Описание**: Архив завершенных и отмененных заказов.
- **Функциональность**: Поиск и просмотр истории заказов.

### 56. Заказы: Редактирование
- **URL**: `/orders/edit/:id`
- **Файл документации**: [orders-edit.component.md](./pages/orders-edit.component.md)
- **Описание**: Детальная страница заказа.
- **Функциональность**: Редактирование состава и статуса заказа.

### 57. Заказы: Новый
- **URL**: `/orders/new`
- **Файл документации**: [orders-new.component.md](./pages/orders-new.component.md)
- **Описание**: Создание нового заказа вручную.
- **Функциональность**: Формирование заказа от имени клиента.

### 58. Фарм-мониторинг: Создание вендора
- **URL**: `/pharmacy-monitoring/vendor/create`
- **Файл документации**: [pharmacy-monitoring-vendor-create.component.md](./pages/pharmacy-monitoring-vendor-create.component.md)
- **Описание**: Добавление нового вендора для мониторинга.
- **Функциональность**: Регистрация вендора в системе.

### 59. Фарм-мониторинг: Детали вендора
- **URL**: `/pharmacy-monitoring/vendor/:id`
- **Файл документации**: [pharmacy-monitoring-vendor-detail.component.md](./pages/pharmacy-monitoring-vendor-detail.component.md)
- **Описание**: Просмотр детальной информации о вендоре.
- **Функциональность**: Отображение данных и статистики.

### 60. Фарм-мониторинг: Список вендоров
- **URL**: `/pharmacy-monitoring/vendors`
- **Файл документации**: [pharmacy-monitoring-vendors.component.md](./pages/pharmacy-monitoring-vendors.component.md)
- **Описание**: Список всех вендоров в системе мониторинга.
- **Функциональность**: Поиск и навигация.

### 61. Отчеты: Отмененные заказы
- **URL**: `/reports/cancel-orders`
- **Файл документации**: [reports-cancel-orders.component.md](./pages/reports-cancel-orders.component.md)
- **Описание**: Отчет по причинам отмены заказов.
- **Функциональность**: Анализ и выгрузка данных.

### 62. Отчеты: Номенклатура
- **URL**: `/reports/nomenclature`
- **Файл документации**: [reports-nomenclature.component.md](./pages/reports-nomenclature.component.md)
- **Описание**: Отчет по товарной номенклатуре.
- **Функциональность**: Генерация и экспорт отчета.

### 63. Отчеты: Вознаграждения
- **URL**: `/reports/reward`
- **Файл документации**: [reports-reward.component.md](./pages/reports-reward.component.md)
- **Описание**: Отчет по начисленным вознаграждениям.
- **Функциональность**: Анализ бонусной программы.

### 64. Отчеты: Топовые товары
- **URL**: `/reports/top-items`
- **Файл документации**: [reports-top-items.component.md](./pages/reports-top-items.component.md)
- **Описание**: Отчет о самых продаваемых товарах.
- **Функциональность**: Анализ популярности товаров.

### 65. Поиск: Создание исключения
- **URL**: `/search/ignore/create`
- **Файл документации**: [search-ignore-create.component.md](./pages/search-ignore-create.component.md)
- **Описание**: Добавление слова в список исключений поиска.
- **Функциональность**: Создание правил игнорирования.

### 66. Поиск: Список исключений
- **URL**: `/search/ignore`
- **Файл документации**: [search-ignore-list.component.md](./pages/search-ignore-list.component.md)
- **Описание**: Просмотр всех поисковых исключений.
- **Функциональность**: Управление списком.

### 67. Поиск: Создание синонима
- **URL**: `/search/synonyms/create`
- **Файл документации**: [search-synonyms-create.component.md](./pages/search-synonyms-create.component.md)
- **Описание**: Добавление нового синонима для поисковых запросов.
- **Функциональность**: Создание связей между словами.

### 68. Поиск: Список синонимов
- **URL**: `/search/synonyms`
- **Файл документации**: [search-synonyms-list.component.md](./pages/search-synonyms-list.component.md)
- **Описание**: Управление всеми синонимами в системе.
- **Функциональность**: Поиск и редактирование.

### 69. Поиск: Создание синонима для названия
- **URL**: `/search/synonyms-name/create`
- **Файл документации**: [search-synonyms-name-create.component.md](./pages/search-synonyms-name-create.component.md)
- **Описание**: Создание синонимов специально для названий товаров.
- **Функциональность**: Управление синонимами названий.

### 70. Поиск: Список синонимов для названий
- **URL**: `/search/synonyms-name`
- **Файл документации**: [search-synonyms-name-list.component.md](./pages/search-synonyms-name-list.component.md)
- **Описание**: Просмотр синонимов для названий.
- **Функциональность**: Поиск и управление.

### 71. Поиск: Создание транслитерации
- **URL**: `/search/synonyms-translit/create`
- **Файл документации**: [search-synonyms-translit-create.component.md](./pages/search-synonyms-translit-create.component.md)
- **Описание**: Добавление правил транслитерации для поиска.
- **Функциональность**: Создание правил.

### 72. Поиск: Список транслитераций
- **URL**: `/search/synonyms-translit`
- **Файл документации**: [search-synonyms-translit-list.component.md](./pages/search-synonyms-translit-list.component.md)
- **Описание**: Управление правилами транслитерации.
- **Функциональность**: Просмотр и редактирование.

### 73. Спецпредложения: Активные
- **URL**: `/specials/active`
- **Файл документации**: [specials-active.component.md](./pages/specials-active.component.md)
- **Описание**: Список текущих акций и спецпредложений.
- **Функциональность**: Просмотр и управление.

### 74. Спецпредложения: Архив
- **URL**: `/specials/archive`
- **Файл документации**: [specials-archive.component.md](./pages/specials-archive.component.md)
- **Описание**: Архив прошедших акций.
- **Функциональность**: Поиск и просмотр.

### 75. Спецпредложения: Авторы
- **URL**: `/specials/authors`
- **Файл документации**: [specials-authors.component.md](./pages/specials-authors.component.md)
- **Описание**: Управление авторами статей и акций.
- **Функциональность**: Создание и редактирование авторов.

### 76. Спецпредложения: Авторы деталей
- **URL**: `/specials/detail/:id/authors`
- **Файл документации**: [specials-detail-authors.component.md](./pages/specials-detail-authors.component.md)
- **Описание**: Привязка авторов к конкретному спецпредложению.
- **Функциональность**: Управление авторами акции.

### 77. Спецпредложения: Детали
- **URL**: `/specials/detail/:id`
- **Файл документации**: [specials-detail.component.md](./pages/specials-detail.component.md)
- **Описание**: Редактирование спецпредложения.
- **Функциональность**: Изменение условий и контента акции.

### 78. Спецпредложения: Список тегов
- **URL**: `/specials/tags`
- **Файл документации**: [specials-tags-list.component.md](./pages/specials-tags-list.component.md)
- **Описание**: Управление тегами для спецпредложений.
- **Функциональность**: Создание и редактирование тегов.

### 79. Аптеки: Редактирование бренда
- **URL**: `/stores/brands/:id/edit`
- **Файл документации**: [stores-brands-brand-edit.component.md](./pages/stores-brands-brand-edit.component.md)
- **Описание**: Редактирование информации о бренде аптечной сети.
- **Функциональность**: Обновление данных бренда.

### 80. Аптеки: Свойства бренда
- **URL**: `/stores/brands/:id/props`
- **Файл документации**: [stores-brands-brand-props.component.md](./pages/stores-brands-brand-props.component.md)
- **Описание**: Управление дополнительными свойствами бренда.
- **Функциональность**: Настройка атрибутов.

### 81. Аптеки: Предупреждения бренда
- **URL**: `/stores/brands/:id/warnings`
- **Файл документации**: [stores-brands-brand-warnings.component.md](./pages/stores-brands-brand-warnings.component.md)
- **Описание**: Настройка предупреждений для бренда.
- **Функциональность**: Управление уведомлениями.

### 82. Аптеки: Бренды
- **URL**: `/stores/brands`
- **Файл документации**: [stores-brands.component.md](./pages/stores-brands.component.md)
- **Описание**: Список всех брендов аптечных сетей.
- **Функциональность**: Поиск и навигация.

### 83. Аптеки: Контроль
- **URL**: `/stores/control`
- **Файл документации**: [stores-control.component.md](./pages/stores-control.component.md)
- **Описание**: Инструменты для контроля работы аптек.
- **Функциональность**: Мониторинг и управление.

### 84. Аптеки: Кастомное расписание
- **URL**: `/stores/custom-schedule`
- **Файл документации**: [stores-custom-schedule.component.md](./pages/stores-custom-schedule.component.md)
- **Описание**: Установка индивидуального графика работы для аптек.
- **Функциональность**: Настройка расписания.

### 85. Аптеки: Привязка дистрибьютора
- **URL**: `/stores/distributor-linking`
- **Файл документации**: [stores-distributor-linking.component.md](./pages/stores-distributor-linking.component.md)
- **Описание**: Привязка аптек к дистрибьюторам.
- **Функциональность**: Управление связями.

### 86. Аптеки: Редактирование
- **URL**: `/stores/edit/:id`
- **Файл документации**: [stores-edit.component.md](./pages/stores-edit.component.md)
- **Описание**: Редактирование карточки аптеки.
- **Функциональность**: Обновление информации об аптеке.

### 87. Аптеки: Список
- **URL**: `/stores/list`
- **Файл документации**: [stores-list.component.md](./pages/stores-list.component.md)
- **Описание**: Список всех аптек в системе.
- **Функциональность**: Поиск, фильтрация и управление.

### 88. Аптеки: Настройка мерчанта
- **URL**: `/stores/merchants/:id/configure`
- **Файл документации**: [stores-merchants-merchant-configure.component.md](./pages/stores-merchants-merchant-configure.component.md)
- **Описание**: Конфигурация платежного мерчанта для аптеки.
- **Функциональность**: Настройка параметров эквайринга.

### 89. Аптеки: Создание мерчанта
- **URL**: `/stores/merchants/create`
- **Файл документации**: [stores-merchants-merchant-create.component.md](./pages/stores-merchants-merchant-create.component.md)
- **Описание**: Создание нового мерчанта.
- **Функциональность**: Регистрация мерчанта.

### 90. Аптеки: Мерчанты
- **URL**: `/stores/merchants`
- **Файл документации**: [stores-merchants.component.md](./pages/stores-merchants.component.md)
- **Описание**: Список всех мерчантов.
- **Функциональность**: Управление мерчантами.

### 91. Аптеки: Сети
- **URL**: `/stores/networks`
- **Файл документации**: [stores-networks.component.md](./pages/stores-networks.component.md)
- **Описание**: Список аптечных сетей.
- **Функциональность**: Управление сетями.

### 92. Аптеки: Проблемные сети
- **URL**: `/stores/problematic-networks`
- **Файл документации**: [stores-problematic-networks.component.md](./pages/stores-problematic-networks.component.md)
- **Описание**: Список сетей с проблемами (например, с низкой доступностью).
- **Функциональность**: Мониторинг и анализ.

### 93. Аптеки: Вход в аптеку
- **URL**: `/stores/store-entrance`
- **Файл документации**: [stores-store-entrance.component.md](./pages/stores-store-entrance.component.md)
- **Описание**: Управление информацией о входах в аптеку (для курьеров).
- **Функциональность**: Добавление и редактирование данных о входах.
