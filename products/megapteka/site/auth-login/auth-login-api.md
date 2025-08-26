## Страница сайта /auth/login

### AuthListService
- **Метод:** get
  - **HTTP:** GET
  - **URL:** ma/site/v2/auth/list
  - **Описание:** Получение списка доступных способов авторизации

### AuthOauthInitService
- **Метод:** post
  - **HTTP:** POST
  - **URL:** ma/site/v1/auth/oauth/init 
  - **Описание:** Инициализация OAuth авторизации (возвращает encrypted_state и link_url; в коде строка URL содержит завершающий пробел)

