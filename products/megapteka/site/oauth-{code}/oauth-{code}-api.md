## Страница сайта /oauth/{code}

### AuthOauthConfirmService
- **Метод:** post
  - **HTTP:** POST
  - **URL:** ma/site/v1/auth/oauth/confirm 
  - **Описание:** Подтверждение OAuth авторизации (получение auth_token по code/encrypted_state)

### ApiAuthCheckService
- **Метод:** post
  - **HTTP:** POST
  - **URL:** ma/site/v1/auth/check
  - **Описание:** Проверка валидности полученного auth_token после OAuth входа

### ClientsService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v2/clients
  - **Описание:** Получение профиля пользователя после успешной авторизации

### ApiItemsFavoritesIdsService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v1/items/favorites/ids
  - **Описание:** Синхронизация избранного (получение списка id) при входе

### OrdersDialogService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v5/orders/dialog
  - **Описание:** Получение активных заказов для обновления счетчика после авторизации

