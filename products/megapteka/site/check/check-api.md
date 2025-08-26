## Страница сайта /check

Маршруты вложены: /check, /check/phone, /check/{order_id}

### OrdersService (список)
- **HTTP:** GET
- **URL:** ma/site/v5/orders
- **Описание:** Список последних заказов (OrderCheckIndexResolver; page=1,count=5)

### OrdersDetailService (деталь)
- **HTTP:** GET
- **URL:** ma/site/v5/orders/detail
- **Описание:** Детали заказа по id (OrderCheckDetailResolver). Автодобавление city_id и device_token.

### OrderCheckIndexResolver
- Если есть auth token или device token — запрашивает список заказов, иначе возвращает null.

### OrderCheckPhoneResolver
- Возвращает сохранённый в состоянии заказ (ORDER_CHECK_STATE) или редирект /check.

### OrderCheckDetailResolver
- Валидирует order_id и наличие токенов (user/device). Ошибка/отсутствие => редирект /check или /lk/orders.


