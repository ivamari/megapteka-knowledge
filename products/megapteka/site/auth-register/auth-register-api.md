## Страница сайта /auth/register

### AuthRegisterService
- **Метод:** put
  - **HTTP:** PUT
  - **URL:** ma/site/v1/auth/register
  - **Описание:** Регистрация пользователя (создание аккаунта, возвращает auth_token)

### ApiAuthCheckService
- **Метод:** post
  - **HTTP:** POST
  - **URL:** ma/site/v1/auth/check
  - **Описание:** Проверка валидности токена сразу после регистрации

### ClientsService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v2/clients
  - **Описание:** Получение профиля пользователя после успешной регистрации

