## Страница сайта /basket

### Описание
Группа маршрутов оформления заказа. Подмаршруты:
- /basket/order — оформление заказа
- /basket/order-multi — мультиоформление
- /basket/preorders — предзаказы (guard countItemGuard)
- /basket/discount — скидочные предложения (guard countItemGuard)
- /basket/on-order — товары под заказ
- /basket/success — страница успешного заказа

### Основные задействованные API (описаны в других файлах)
- ma/site/v4/orders/basket (OrdersBasketService) — состав заказа при повторе
- ma/site/v1/items/sum (ItemsSumService.get) — пересчет корзины
- ma/site/v1/cart/online (CartOnlineService.post) — синхронизация онлайн-корзины
- ma/site/v5/orders / ma/site/v5/orders/detail (OrdersService / OrdersDetailService) — список и детали заказов

### Guards / Поведение
- countItemGuard блокирует доступ к отдельным веткам при пустой корзине.
- После успешного оформления выполняется обновление активных заказов (ActiveOrdersService.updateList()).

### Примечания
Специфических собственных HTTP вызовов маршрутизация /basket не делает — используются сервисы заказа и корзины.

