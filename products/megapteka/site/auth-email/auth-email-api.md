## Страница сайта /auth/email

### AuthLoginService
- **Метод:** put
  - **HTTP:** PUT
  - **URL:** ma/site/v1/auth/login
  - **Описание:** Авторизация по email и паролю (получение auth_token)

### ApiAuthCheckService
- **Метод:** post
  - **HTTP:** POST
  - **URL:** ma/site/v1/auth/check
  - **Описание:** Проверка валидности токена после входа

### ClientsService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v2/clients
  - **Описание:** Получение профиля пользователя после успешной авторизации

