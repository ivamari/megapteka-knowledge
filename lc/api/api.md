---
title: ЛК аптеки
language_tabs:
  - shell: Shell
  - http: HTTP
  - javascript: JavaScript
  - ruby: Ruby
  - python: Python
  - php: PHP
  - java: Java
  - go: Go
toc_footers: []
includes: []
search: true
code_clipboard: true
highlight_theme: darkula
headingLevel: 2
generator: "@tarslib/widdershins v4.0.30"

---

# ЛК аптеки

# Авторизация

## POST Авторизация

POST /merch-lk/v1/auth/login/

> Body Parameters

```json
{
  "login": "string",
  "password": "string"
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|body|body|object| no |none|
|» login|body|string| yes |Логин пользователя|
|» password|body|string| yes |Пароль|

> Response Examples

> 200 Response

```json
{
  "auth_token": "string"
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» auth_token|string|false|none||Авторизационный токен|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## POST Логаут

POST /merch-lk/v1/auth/logout

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|

> Response Examples

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Проверка авторизации

GET /merch-lk/v1/auth/check

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|

> Response Examples

> 200 Response

```json
{
  "login": "string",
  "permissions": [
    "string"
  ]
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» login|string|true|none||Логин пользователя|
|» permissions|[string]|true|none||Список кодов прав доступа для пользователя|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## POST Телеметрия

POST /merch-lk/v1/auth/telemetry

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|

> Response Examples

> 200 Response

```json
{
  "permission": "string"
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» permission|string|true|none||Код права доступа активного раздела|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

# Аналитика/Дашборд

## GET Аптеки с долгой сборкой

GET /merch-lk/v2/analytics/dashboard/stores/build-time

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|

> Response Examples

> 200 Response

```json
[
  {
    "address": "string",
    "value": "string"
  }
]
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» address|string|true|none||Адрес аптеки|
|» value|string|true|none||Время сборки, текстом для вывода|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Динамика заказов

GET /merch-lk/v2/analytics/dashboard/dynamic/orders

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|

> Response Examples

> 200 Response

```json
[
  {
    "label": "string",
    "value": 0
  }
]
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» label|string|true|none||Период, строкой для вывода|
|» value|integer|true|none||Доля заказов сети от общего количества заказов МА, в %|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Заказы

GET /merch-lk/v2/analytics/dashboard/orders

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|

> Response Examples

> 200 Response

```json
{
  "active": {
    "quantity": 0,
    "amount": 0,
    "average": 0
  },
  "cancel": {
    "quantity": 0,
    "amount": 0,
    "average": 0
  },
  "done": {
    "quantity": 0,
    "amount": 0,
    "average": 0,
    "global_average": 0
  },
  "hung": {
    "quantity": 0,
    "amount": 0,
    "average": 0,
    "urls": [
      {
        "name": "string",
        "url": "string"
      }
    ]
  },
  "meta": {
    "hung_time": "string"
  }
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» active|object|true|none||Активные заказы|
|»» quantity|integer|true|none||Количество|
|»» amount|number|true|none||Сумма|
|»» average|number|true|none||Средний чек|
|» cancel|object|true|none||Отмененные заказы|
|»» quantity|integer|true|none||Количество|
|»» amount|number|true|none||Сумма|
|»» average|number|true|none||Средний чек|
|» done|object|true|none||Выданные заказы|
|»» quantity|integer|true|none||Количество|
|»» amount|number|true|none||Сумма|
|»» average|number|true|none||Средний чек|
|»» global_average|number|true|none||Средний чек среди всех аптек|
|» hung|object|true|none||Зависшие заказы|
|»» quantity|integer|true|none||Количество|
|»» amount|number|true|none||Сумма|
|»» average|number|true|none||Средний чек|
|»» urls|[object]|true|none||none|
|»»» name|string|true|none||Название сети|
|»»» url|string|true|none||URL для отслеживания зависших заказов|
|» meta|object|true|none||none|
|»» hung_time|string|true|none||Время за которое заказ считается зависшим|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Количество аптек

GET /merch-lk/v2/analytics/dashboard/stores/quantity

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|

> Response Examples

> 200 Response

```json
{
  "total": 0,
  "active": 0,
  "inactive": 0,
  "quarantine": 0
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» total|integer|true|none||Общее количество аптек|
|» active|integer|true|none||Количество активных аптек|
|» inactive|integer|true|none||Количество неактивных аптек|
|» quarantine|integer|true|none||Количество аптек в карантине|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Отмены в аптеках

GET /merch-lk/v2/analytics/dashboard/stores/cancel

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|

> Response Examples

> 200 Response

```json
{
  "stores": {
    "cancel_ma_auto": [
      {
        "address": "string",
        "value": 0
      }
    ],
    "cancel_store_before_build": [
      {
        "address": "string",
        "value": 0
      }
    ],
    "cancel_store_before_reservation_end": [
      {
        "address": "string",
        "value": 0
      }
    ]
  }
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» stores|object|true|none||none|
|»» cancel_ma_auto|[object]|true|none||Худшие аптеки по числу отмен, автоматическая отмена МА|
|»»» address|string|true|none||Адрес аптеки|
|»»» value|integer|true|none||Количество заказов|
|»» cancel_store_before_build|[object]|true|none||Худшие аптеки по числу отмен, отмена аптекой до сборки|
|»»» address|string|true|none||Адрес аптеки|
|»»» value|integer|true|none||Количество заказов|
|»» cancel_store_before_reservation_end|[object]|true|none||Худшие аптеки по числу отмен, отмена аптекой до срока брони|
|»»» address|string|true|none||Адрес аптеки|
|»»» value|integer|true|none||Количество заказов|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Рейтинг аптек

GET /merch-lk/v2/analytics/dashboard/stores/rating

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|

> Response Examples

> 200 Response

```json
{
  "stores": {
    "ma_worst": [
      {
        "address": "string",
        "value": 0
      }
    ],
    "ma_best": [
      {
        "address": "string",
        "value": 0
      }
    ],
    "user_worst": [
      {
        "address": "string",
        "value": 0
      }
    ],
    "user_best": [
      {
        "address": "string",
        "value": 0
      }
    ]
  }
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» stores|object|true|none||none|
|»» ma_worst|[object]|true|none||Худшие аптеки по рейтингу Мегаптеки|
|»»» address|string|true|none||Адрес аптеки|
|»»» value|number|true|none||рейтинг аптеки|
|»» ma_best|[object]|true|none||Лучшие аптеки по рейтингу Мегаптеки|
|»»» address|string|true|none||адрес аптеки|
|»»» value|number|true|none||рейтинг аптеки|
|»» user_worst|[object]|true|none||Худшие аптеки по рейтингу клиентов|
|»»» address|string|true|none||адрес аптеки|
|»»» value|number|true|none||рейтинг аптеки|
|»» user_best|[object]|true|none||Лучшие аптеки по рейтингу клиентов|
|»»» address|string|true|none||адрес аптеки|
|»»» value|number|true|none||рейтинг аптеки|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Дашборд

GET /merch-lk/v1/analytics/dashboard

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|

> Response Examples

> 200 Response

```json
{
  "stores": {
    "active": 0,
    "quarantine": 0,
    "ma_worst": [
      {
        "address": "string",
        "value": 0
      }
    ],
    "ma_best": [
      {
        "address": "string",
        "value": 0
      }
    ],
    "user_worst": [
      {
        "address": "string",
        "value": 0
      }
    ],
    "user_best": [
      {
        "address": "string",
        "value": 0
      }
    ],
    "cancel_ma_auto": [
      {
        "address": "string",
        "value": 0
      }
    ],
    "cancel_store_before_build": [
      {
        "address": "string",
        "value": 0
      }
    ],
    "cancel_store_before_reservation_end": [
      {
        "address": "string",
        "value": 0
      }
    ],
    "build_worst": [
      {
        "address": "string",
        "value": "string"
      }
    ]
  },
  "orders": {
    "active": [
      {
        "quantity": 0,
        "amount": 0,
        "average": 0
      }
    ],
    "cancel": [
      {
        "quantity": 0,
        "amount": 0,
        "average": 0
      }
    ],
    "done": [
      {
        "quantity": 0,
        "amount": 0,
        "average": 0,
        "global_average": 0
      }
    ],
    "hung": [
      {
        "quantity": 0,
        "amount": 0,
        "average": 0,
        "url": "string"
      }
    ]
  }
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» stores|object|true|none||none|
|»» active|integer|true|none||Количество активных аптек|
|»» quarantine|integer|true|none||Количество аптек в карантине|
|»» ma_worst|[object]|true|none||Худшие аптеки по рейтингу Мегаптеки|
|»»» address|string|true|none||Адрес аптеки|
|»»» value|number|true|none||Рейтинг аптеки|
|»» ma_best|[object]|true|none||Лучшие аптеки по рейтингу Мегаптеки|
|»»» address|string|true|none||Адрес аптеки|
|»»» value|number|true|none||Рейтинг аптеки|
|»» user_worst|[object]|true|none||Худшие аптеки по рейтингу клиентов|
|»»» address|string|true|none||Адрес аптеки|
|»»» value|number|true|none||Рейтинг аптеки|
|»» user_best|[object]|true|none||Лучшие аптеки по рейтингу клиентов|
|»»» address|string|true|none||Адрес аптеки|
|»»» value|number|true|none||Рейтинг аптеки|
|»» cancel_ma_auto|[object]|true|none||Худшие аптеки по числу отмен, автоматическая отмена МА|
|»»» address|string|true|none||Адрес аптеки|
|»»» value|integer|true|none||Количество заказов|
|»» cancel_store_before_build|[object]|true|none||Худшие аптеки по числу отмен, отмена аптекой до сборки|
|»»» address|string|true|none||Адрес аптеки|
|»»» value|integer|true|none||Количество заказов|
|»» cancel_store_before_reservation_end|[object]|true|none||Худшие аптеки по числу отмен, отмена аптекой до срока брони|
|»»» address|string|true|none||Адрес аптеки|
|»»» value|integer|true|none||Количество заказов|
|»» build_worst|[object]|true|none||Худшие аптеки по времени сборки|
|»»» address|string|true|none||Адрес аптеки|
|»»» value|string|true|none||Время сборки, текстом для вывода|
|» orders|object|true|none||none|
|»» active|[object]|true|none||Время сборки, текстом для вывода|
|»»» quantity|integer|true|none||Количество|
|»»» amount|number|true|none||Сумма|
|»»» average|number|true|none||Средний чек|
|»» cancel|[object]|true|none||Отмененные заказы|
|»»» quantity|integer|true|none||Количество|
|»»» amount|number|true|none||Сумма|
|»»» average|number|true|none||Средний чек|
|»» done|[object]|true|none||Выданные заказы|
|»»» quantity|integer|true|none||Количество|
|»»» amount|number|true|none||Сумма|
|»»» average|number|true|none||Средний чек|
|»»» global_average|number|true|none||Средний чек среди всех аптек|
|»» hung|[object]|true|none||Зависшие заказы|
|»»» quantity|integer|true|none||Количество|
|»»» amount|number|true|none||Сумма|
|»»» average|number|true|none||Средний чек|
|»»» url|string|true|none||URL для отслеживания зависших заказов|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

# Аналитика/Ассортимент

## GET Ассортимент

GET /merch-lk/v1/analytics/assortment

> Body Parameters

```json
{
  "region_ids": [
    0
  ]
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» region_ids|body|[integer]| yes |Идентификаторы регионов, есть ограничение по количеству|

> Response Examples

> 200 Response

```json
{
  "list": [
    {
      "region_id": 0,
      "region_name": "string",
      "data": [
        {
          "item_id": 0,
          "item_name": "string",
          "brand_name": "string",
          "url": "string",
          "stock": "string",
          "price": 0,
          "price_min": 0,
          "rank": 0,
          "rank_max": 0
        }
      ]
    }
  ]
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» list|[object]|true|none||none|
|»» region_id|integer|true|none||Идентификатор региона|
|»» region_name|string|true|none||Название региона|
|»» data|[object]|true|none||none|
|»»» item_id|integer|true|none||Идентификатор товара|
|»»» item_name|string|true|none||Название товара|
|»»» brand_name|string¦null|true|none||Название бренда|
|»»» url|string|true|none||URL на сайте megapteka.ru|
|»»» stock|string|true|none||Наличие в аптеках, в каком проценте аптек сети есть товар|
|»»» price|number|true|none||Минимальная цена мерчанта|
|»»» price_min|number|true|none||Минимальная цена|
|»»» rank|integer|true|none||Место по минимальной цене|
|»»» rank_max|integer|true|none||Максимальное (последнее) место по минимальной цене|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Загрузка отчета

GET /merch-lk/v1/analytics/assortment/download

> Body Parameters

```json
{
  "region_ids": [
    0
  ]
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» region_ids|body|[integer]| yes |Идентификаторы регионов, есть ограничение по количеству|

> Response Examples

> 200 Response

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» list|[object]|true|none||none|
|»» region_id|integer|true|none||Идентификатор региона|
|»» region_name|string|true|none||Название региона|
|»» data|[object]|true|none||none|
|»»» item_id|integer|true|none||Идентификатор товара|
|»»» item_name|string|true|none||Название товара|
|»»» brand_name|string¦null|true|none||Название бренда|
|»»» url|string|true|none||URL на сайте megapteka.ru|
|»»» stock|string|true|none||Наличие в аптеках, в каком проценте аптек сети есть товар|
|»»» price|number|true|none||Минимальная цена мерчанта|
|»»» price_min|number|true|none||Минимальная цена|
|»»» rank|integer|true|none||Место по минимальной цене|
|»»» rank_max|integer|true|none||Максимальное (последнее) место по минимальной цене|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

# Аналитика/Доля

## GET Доля

GET /merch-lk/v1/analytics/part

> Body Parameters

```json
{
  "sort_by": "string",
  "sort_direction": "string"
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» sort_by|body|string| no |Код поля для сортировки (quantity | amount)|
|» sort_direction|body|string| no |Направление сортировки (asc | desc)|

> Response Examples

> 200 Response

```json
{
  "list": [
    {
      "region_id": 0,
      "region_name": "string",
      "quantity_percent": 0,
      "quantity_rank": 0,
      "quantity_max_rank": 0,
      "amount_percent": 0,
      "amount_rank": 0,
      "amount_max_rank": 0
    }
  ]
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» list|[object]|true|none||none|
|»» region_id|integer|true|none||Идентификатор региона|
|»» region_name|string|true|none||Название региона|
|»» quantity_percent|integer|true|none||Процент по количеству|
|»» quantity_rank|integer|true|none||Место по количеству|
|»» quantity_max_rank|integer|true|none||Максимальное (последнее) место по количеству в регионе|
|»» amount_percent|integer|true|none||Процент по сумме|
|»» amount_rank|integer|true|none||Место по сумме|
|»» amount_max_rank|integer|true|none||Максимальное (последнее) место по сумме в регионе|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

# Аптеки

## GET Детальная

GET /merch-lk/v1/stores/detail

> Body Parameters

```json
{
  "uuid": "string"
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» uuid|body|string| yes |Код аптеки|

> Response Examples

> 200 Response

```json
{
  "id": 0,
  "uuid": "string",
  "address": "string",
  "city_name": "string",
  "ma_rating": 0,
  "build_time": "string",
  "is_deleted": true,
  "activity_message": "string",
  "quarantine_until": 0,
  "disconnected_until": 0,
  "schedule": "string",
  "temporary_schedule": [
    {
      "date": 0,
      "is_day_off": true,
      "open_time": 0,
      "close_time": 0
    }
  ]
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|[stores_detail](#schemastores_detail)|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» id|integer|true|none||Идентификатор аптеки|
|» uuid|string|true|none||UUID аптеки|
|» address|string|true|none||Адрес аптеки|
|» city_name|string¦null|true|none||Название города аптеки|
|» ma_rating|integer¦null|true|none||Рейтинг Мегаптеки (0-100)|
|» build_time|string¦null|true|none||Время сборки, текстом для вывода|
|» is_deleted|boolean|true|none||Отметка об удалении|
|» activity_message|string|true|none||Сообщение об активности|
|» quarantine_until|integer¦null|true|none||Дата окончания карантина|
|» disconnected_until|integer¦null|true|none||Отключена до|
|» schedule|string¦null|true|none||График работы|
|» temporary_schedule|[object]|true|none||Временный график работы|
|»» date|integer|true|none||Дата|
|»» is_day_off|boolean|true|none||Флаг выходного дня|
|»» open_time|integer¦null|true|none||Время открытия, null для выходного|
|»» close_time|integer¦null|true|none||Время закрытия, null для выходного|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Загрузка отчета

GET /merch-lk/v1/stores/download

> Body Parameters

```json
{
  "sort_by": "string",
  "sort_direction": "string",
  "id": 0,
  "uuid": "string",
  "address": "string",
  "ma_city_id": "string",
  "query": "string",
  "is_deleted": true,
  "delete_reason": "string"
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» sort_by|body|string| no |Код поля для сортировки (address | rating | build-time)|
|» sort_direction|body|string| no |Направление сортировки (asc | desc)|
|» id|body|integer| no |Идентификатор аптеки|
|» uuid|body|string| no |Код аптеки|
|» address|body|string| no |Адрес аптеки|
|» ma_city_id|body|string| no |Идентификатор города|
|» query|body|string| no |Поисковой запрос, ищет по адресу или коду аптеки|
|» is_deleted|body|boolean| no |Отметка об удалении|
|» delete_reason|body|string| no |Код причины удаления|

> Response Examples

> 200 Response

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|string|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## POST Заявка на смену графика

POST /merch-lk/v1/stores/schedule/edit

> Body Parameters

```json
{
  "store_id": 0,
  "message": "string"
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» store_id|body|integer| yes |Идентификатор аптеки|
|» message|body|string| yes |Сообщение|

> Response Examples

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## POST Изменение “как найти вход”

POST /merch-lk/v1/stores/entrance-info/edit

> Body Parameters

```json
{
  "store_id": 0,
  "message": "string"
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» store_id|body|integer| yes |Идентификатор аптеки|
|» message|body|string¦null| yes |Сообщение|

> Response Examples

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Количество аптек с высокой оценкой

GET /merch-lk/v1/stores/high-rated

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|

> Response Examples

> 200 Response

```json
{
  "quantity": 0
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» quantity|integer|true|none||Количество аптек|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## POST Отправка фото

POST /merch-lk/v1/stores/control/create

> Body Parameters

```json
{
  "store_id": 0,
  "photos": [
    "string"
  ]
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» store_id|body|integer| no |Идентификатор аптеки|
|» photos|body|[string]| no |Массив фотографий аптеки|

> Response Examples

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Список фото

GET /merch-lk/v1/stores/photos

> Body Parameters

```json
{
  "store_id": 0
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |none|
|body|body|object| no |none|
|» store_id|body|integer| yes |Идентификатор аптеки|

> Response Examples

> 200 Response

```json
{
  "list": [
    {
      "image_id": 0,
      "image_url": "string",
      "preview_image_url": "string"
    }
  ]
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» list|[object]|true|none||none|
|»» image_id|integer|true|none||Идентификатор изображения|
|»» image_url|string|true|none||URL изображения|
|»» preview_image_url|string|true|none||URL превью изображения|

## POST Удаление фото

POST /merch-lk/v1/stores/photos/delete

> Body Parameters

```json
{
  "id": 0
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |none|
|body|body|object| no |none|
|» id|body|integer| yes |Идентификатор изображения|

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|

## GET Причины отключения аптек

GET /merch-lk/v1/stores/disconnect-reasons

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|

> Response Examples

> 200 Response

```json
{
  "list": [
    {
      "code": "string",
      "name": "string"
    }
  ]
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» list|[object]|true|none||none|
|»» code|string|true|none||Код|
|»» name|string|true|none||Название|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Список

GET /merch-lk/v1/stores

> Body Parameters

```json
{
  "sort_by": "string",
  "sort_direction": "string",
  "id": 0,
  "uuid": "string",
  "address": "string",
  "query": "string",
  "ma_city_id": 0,
  "is_deleted": true,
  "delete_reason": "string"
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» sort_by|body|string| no |Код поля для сортировки (address | rating | build-time)|
|» sort_direction|body|string| no |Направление сортировки (asc | desc)|
|» id|body|integer| no |Идентификатор аптеки|
|» uuid|body|string| no |Код аптеки|
|» address|body|string| no |Адрес аптеки|
|» query|body|string| no |Поисковой запрос, ищет по адресу или коду аптеки|
|» ma_city_id|body|integer| no |Идентификатор города|
|» is_deleted|body|boolean| no |Отметка об удалении|
|» delete_reason|body|string| no |Код причины удаления|

> Response Examples

> 200 Response

```json
{
  "list": [
    {
      "id": 0,
      "uuid": "string",
      "address": "string",
      "full_address": "string",
      "city_name": "string",
      "ma_rating": 0,
      "user_rating": 0,
      "build_time": "string",
      "is_deleted": true,
      "activity_message": "string",
      "quarantine_until": 0,
      "disconnected_until": 0,
      "schedule": "string",
      "temporary_schedule": [
        {
          "date": 0,
          "is_day_off": true,
          "open_time": 0,
          "close_time": 0
        }
      ],
      "photos_quantity": 0,
      "entrance_info": "string",
      "can_be_enabled": true,
      "is_active_pricebot": true
    }
  ],
  "total": 0
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» list|[object]|true|none||none|
|»» id|integer|true|none||Идентификатор аптеки|
|»» uuid|string|true|none||UUID аптеки|
|»» address|string|true|none||Адрес аптеки|
|»» full_address|string|true|none||Адрес аптеки с городом|
|»» city_name|string¦null|true|none||Название города аптеки|
|»» ma_rating|integer¦null|true|none||Рейтинг Мегаптеки (0-100)|
|»» user_rating|number¦null|true|none||Пользовательский рейтинг на основе оценок заказов (0.0-5.0)|
|»» build_time|string¦null|true|none||Время сборки, текстом для вывода|
|»» is_deleted|boolean|true|none||Отметка об удалении|
|»» activity_message|string|true|none||Сообщение об активности|
|»» quarantine_until|integer¦null|true|none||Дата окончания карантина|
|»» disconnected_until|integer¦null|true|none||Отключена до|
|»» schedule|string¦null|true|none||График работы|
|»» temporary_schedule|[object]|true|none||Временный график работы|
|»»» date|integer|true|none||Дата|
|»»» is_day_off|boolean|true|none||Флаг выходного дня|
|»»» open_time|integer¦null|true|none||Время открытия, null для выходного|
|»»» close_time|integer¦null|true|none||Время закрытия, null для выходного|
|»» photos_quantity|integer|true|none||Количество фотографий (аптечный контроль)|
|»» entrance_info|string¦null|true|none||Описание как найти вход|
|»» can_be_enabled|boolean|true|none||Флаг возможности включения аптеки|
|»» is_active_pricebot|boolean¦null|false|none||Флаг возможности включения аптеки|
|» total|integer|true|none||Общее количество элементов в ответе|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## POST Скрытие аптеки из ЛК

POST /merch-lk/v1/stores/hide

> Body Parameters

```json
{
  "store_id": 0
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» store_id|body|integer| yes |Идентификатор аптеки|

> Response Examples

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## POST Управление активностью аптеки

POST /merch-lk/v1/stores/enabled/edit

> Body Parameters

```json
{
  "store_id": 0,
  "is_enabled": true,
  "disconnect_days": 0
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» store_id|body|integer| yes |Идентификатор аптеки|
|» is_enabled|body|boolean| yes |Флаг активности аптеки (true = включить / false = выключить)|
|» disconnect_days|body|integer| no |Количество дней, на которое аптека будет отключена|

> Response Examples

> 200 Response

```json
{
  "disconnected_until": 0
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» disconnected_until|integer¦null|true|none||Отключена до|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

# Города

## GET Список / поиск

GET /merch-lk/v1/cities

> Body Parameters

```json
{
  "query": "string",
  "id": 0,
  "region_id": 0,
  "page": 0,
  "count": 0
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» query|body|string| no |Поисковый запрос|
|» id|body|integer| no |Идентификатор города|
|» region_id|body|integer| no |Идентификатор региона|
|» page|body|integer| no |Номер страницы (по умолчанию 1)|
|» count|body|integer| no |Количество элементов в ответе|

> Response Examples

> 200 Response

```json
{
  "list": [
    {
      "id": 0,
      "name": "string"
    }
  ]
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» list|[object]|true|none||none|
|»» id|integer|true|none||Идентификатор города|
|»» name|string|true|none||Название города, сразу с регионом|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

# Заказы

## GET Детальный заказ

GET /merch-lk/v1/orders/detail

> Body Parameters

```json
{
  "id": 0
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» id|body|integer| yes |Идентификатор заказа|

> Response Examples

> 200 Response

```json
{
  "id": 0,
  "external_id": "string",
  "creation_date": 0,
  "amount": 0,
  "customer_name": "string",
  "customer_phone": "string",
  "cancel_comment": "string",
  "store_uuid": "string",
  "store_address": "string",
  "status_name": "string",
  "status_color": "string",
  "is_hung": true,
  "is_excluded_for_reports": true,
  "items": [
    {
      "id": 0,
      "uuid": "string",
      "etalon_name": "string",
      "etalon_brand_name": "string",
      "name": "string",
      "brand_name": "string",
      "price": 0,
      "quantity": 0,
      "amount": 0,
      "orig_price": 0,
      "orig_quantity": 0
    }
  ],
  "log": [
    {
      "date": 0,
      "source_name": "string",
      "status_name": "string"
    }
  ]
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» id|integer|true|none||Идентификатор заказа|
|» external_id|string¦null|true|none||Номер заказа для клиента|
|» creation_date|integer|true|none||Дата создания заказа|
|» amount|number|true|none||Сумма заказа|
|» customer_name|string|true|none||Имя покупателя|
|» customer_phone|string|true|none||Телефон покупателя|
|» cancel_comment|string¦null|true|none||Комментарий отмены|
|» store_uuid|string|true|none||UUID аптеки|
|» store_address|string|true|none||Адрес аптеки|
|» status_name|string|true|none||Название статуса заказа|
|» status_color|string|true|none||Цвет статуса заказа|
|» is_hung|boolean|true|none||Флаг зависшего заказа|
|» is_excluded_for_reports|boolean|true|none||Флаг зависшего заказа|
|» items|[object]|true|none||Состав заказа|
|»» id|integer|true|none||Идентификатор позиции|
|»» uuid|string|true|none||код товара|
|»» etalon_name|string|true|none||Название товара из эталонного каталога|
|»» etalon_brand_name|string¦null|true|none||Название бренда товара из эталонного каталога|
|»» name|string|true|none||Название товара от мерчанта|
|»» brand_name|string¦null|true|none||Название бренда товара от мерчанта|
|»» price|number|true|none||Цена товара|
|»» quantity|integer|true|none||Количество товара|
|»» amount|number|true|none||Сумма товара|
|»» orig_price|number¦null|true|none||Старая цена товара|
|»» orig_quantity|integer¦null|true|none||Старое количество товара|
|» log|[object]|true|none||История заказа|
|»» date|integer|true|none||Дата изменения|
|»» source_name|string|true|none||Название источника изменений|
|»» status_name|string|true|none||Название статуса заказа|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Загрузка отчета

GET /merch-lk/v1/orders/download

> Body Parameters

```json
{
  "id": 0,
  "external_id": "string",
  "store_id": 0,
  "ma_city_id": 0,
  "month": 0,
  "is_over": true,
  "cancel_reason": "string"
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» id|body|integer| no |Отметка завершенности заказа|
|» external_id|body|string| no |Номер заказа для клиента|
|» store_id|body|integer| no |Идентификатор аптеки|
|» ma_city_id|body|integer| no |Идентификатор города|
|» month|body|integer| no |Дата начала месяца, по умолчанию будет использоваться текущий месяц|
|» is_over|body|boolean| no |Отметка завершенности заказа|
|» cancel_reason|body|string| no |Код причины отмены|

> Response Examples

> 200 Response

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» list|[object]|false|none||none|
|»» id|integer|true|none||Идентификатор заказа|
|»» external_id|string¦null|true|none||Номер заказа для клиента|
|»» creation_date|integer|true|none||Дата создания заказа|
|»» status_name|string|true|none||Название статуса заказа|
|»» status_color|string|true|none||Цвет статуса заказа|
|»» amount|number|true|none||Сумма заказа|
|»» cancel_comment|string¦null|true|none||Комментарий отмены|
|»» city_name|string|true|none||Название города|
|»» store_uuid|string|true|none||UUID аптеки|
|»» store_address|string|true|none||Фдрес аптеки|
|»» rate|integer¦null|true|none||Оценка|
|»» rate_text|string¦null|true|none||Текст отзыва|
|»» is_hung|boolean|true|none||Флаг зависшего заказа|
|»» is_excluded_for_reports|boolean|true|none||Флаг зависшего заказа|
|» total|integer|true|none||Общее количество элементов в ответе|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Месяцы для фильтра заказов

GET /merch-lk/v1/orders/months

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|

> Response Examples

> 200 Response

```json
{
  "months": [
    0
  ]
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» months|[integer]|true|none||Массив месяцев для фильтра|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Метаданные списка

GET /merch-lk/v2/orders/meta

> Body Parameters

```json
{
  "month": 0,
  "store_id": 0,
  "ma_city_id": 0
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» month|body|integer| no |Дата начала месяца, по умолчанию будет использоваться текущий месяц|
|» store_id|body|integer| no |Идентификатор аптеки|
|» ma_city_id|body|integer| no |Идентификатор города|

> Response Examples

> 200 Response

```json
{
  "location_name": "string",
  "current_period": {
    "from": 0,
    "to": 0
  },
  "orders": {
    "total": {
      "quantity": 0,
      "part": 0
    },
    "done": {
      "quantity": 0,
      "part": 0
    },
    "cancel": {
      "quantity": 0,
      "part": 0
    },
    "amount": 0,
    "amount_done": 0,
    "average": 0,
    "avg_build": "string"
  }
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» location_name|string¦null|true|none||Название локации (аптеки или города)|
|» current_period|object|true|none||none|
|»» from|integer|true|none||Дата начала выбранного периода|
|»» to|integer|true|none||Дата конца выбранного периода|
|» orders|object|true|none||none|
|»» total|object|true|none||none|
|»»» quantity|integer|true|none||Количество созданных|
|»»» part|integer|true|none||Процент созданных|
|»» done|object|true|none||none|
|»»» quantity|integer|true|none||Количество выданных|
|»»» part|integer|true|none||Процент выданных|
|»» cancel|object|true|none||none|
|»»» quantity|integer|true|none||Количество отмененных|
|»»» part|integer|true|none||Процент отмененных|
|»» amount|number|true|none||Сумма|
|»» amount_done|number|true|none||Cумма выданных заказов|
|»» average|number|true|none||Средний чек|
|»» avg_build|string|true|none||Среднее время сборки|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Причины отмены

GET /merch-lk/v1/orders/cancel-reasons

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|

> Response Examples

> 200 Response

```json
{
  "list": [
    {
      "code": "string",
      "name": "string"
    }
  ]
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» list|[object]|true|none||none|
|»» code|string|true|none||Код|
|»» name|string|true|none||Название|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Статусы

GET /merch-lk/v1/orders/statuses

> Body Parameters

```json
{
  "is_over": true
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» is_over|body|boolean| no |Отметка завершенности заказа|

> Response Examples

> 200 Response

```json
{
  "list": [
    {
      "id": 0,
      "name": "string",
      "is_completed": true
    }
  ]
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» list|[object]|false|none||none|
|»» id|integer|true|none||Идентификатор|
|»» name|string|true|none||Название|
|»» is_completed|boolean|true|none||Флаг успешного завершения заказа|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Список

GET /merch-lk/v1/orders

> Body Parameters

```json
{
  "id": 0,
  "external_id": "string",
  "store_id": 0,
  "ma_city_id": 0,
  "month": 0,
  "is_over": true,
  "cancel_reason": "string",
  "page": 0,
  "count": 0
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» id|body|integer| no |Отметка завершенности заказа|
|» external_id|body|string| no |Номер заказа для клиента|
|» store_id|body|integer| no |Идентификатор аптеки|
|» ma_city_id|body|integer| no |Идентификатор города|
|» month|body|integer| no |Дата начала месяца, по умолчанию будет использоваться текущий месяц|
|» is_over|body|boolean| no |Отметка завершенности заказа|
|» cancel_reason|body|string| no |Код причины отмены|
|» page|body|integer| no |Номер страницы (по умолчанию 1)|
|» count|body|integer| no |Количество элементов в ответе|

> Response Examples

> 200 Response

```json
{
  "list": [
    {
      "id": 0,
      "external_id": "string",
      "creation_date": 0,
      "status_name": "string",
      "status_color": "string",
      "amount": 0,
      "cancel_comment": "string",
      "city_name": "string",
      "store_uuid": "string",
      "store_address": "string",
      "rate": 0,
      "rate_text": "string",
      "is_hung": true,
      "is_excluded_for_reports": true
    }
  ],
  "total": 0
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» list|[object]|false|none||none|
|»» id|integer|true|none||Идентификатор заказа|
|»» external_id|string¦null|true|none||Номер заказа для клиента|
|»» creation_date|integer|true|none||Дата создания заказа|
|»» status_name|string|true|none||Название статуса заказа|
|»» status_color|string|true|none||Цвет статуса заказа|
|»» amount|number|true|none||Сумма заказа|
|»» cancel_comment|string¦null|true|none||Комментарий отмены|
|»» city_name|string|true|none||Название города|
|»» store_uuid|string|true|none||UUID аптеки|
|»» store_address|string|true|none||Фдрес аптеки|
|»» rate|integer¦null|true|none||Оценка|
|»» rate_text|string¦null|true|none||Текст отзыва|
|»» is_hung|boolean|true|none||Флаг зависшего заказа|
|»» is_excluded_for_reports|boolean|true|none||Флаг зависшего заказа|
|» total|integer|true|none||Общее количество элементов в ответе|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## POST Создание заказа для теста

POST /merch-lk/v1/orders/test/create

> Body Parameters

```json
{
  "store_id": 0
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» store_id|body|integer| yes |Идентификатор аптеки|

> Response Examples

> 200 Response

```json
{
  "id": 0,
  "external_id": "string"
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» id|integer|true|none||Идентификатор заказа|
|» external_id|string¦null|true|none||Номер заказа для клиента|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

# Обратная связь

## GET Список

GET /merch-lk/v1/feedback

> Body Parameters

```json
{
  "page": 0,
  "count": 0
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» page|body|integer| no |Номер страницы (по умолчанию 1)|
|» count|body|integer| no |Количество элементов в ответе|

> Response Examples

> 200 Response

```json
{
  "list": [
    {
      "id": 0,
      "message": "string",
      "creation_date": 0,
      "operator_login": "string",
      "network_name": "string"
    }
  ],
  "total": 0
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» list|[object]|true|none||none|
|»» id|integer|true|none||Идентификатор|
|»» message|string|true|none||Сообщение|
|»» creation_date|integer|true|none||Дата создания|
|»» operator_login|string|true|none||Логин оператора|
|»» network_name|string|true|none||Названия сетей|
|» total|integer|true|none||Общее число элементов в ответе|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## POST Создание

POST /merch-lk/v1/feedback/create

> Body Parameters

```json
{
  "message": "string"
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» message|body|string| yes |Сообщение|

> Response Examples

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

# Отзывы

## POST Запрос наклеек

POST /merch-lk/v1/reviews/request-stickers

> Body Parameters

```json
{
  "name": "string",
  "network": "string",
  "phone": "string"
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» name|body|string| yes |Имя|
|» network|body|string| yes |Название сети|
|» phone|body|string| yes |Телефон|

> Response Examples

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Загрузка отчета

GET /merch-lk/v1/reviews/download

> Body Parameters

```json
{
  "rate": 0,
  "store_id": 0,
  "month": 0,
  "is_completed": true,
  "cancel_reason": "string"
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» rate|body|integer| no |Оценка|
|» store_id|body|integer| no |Идентификатор аптеки|
|» month|body|integer| no |Дата начала месяца, по умолчанию будет использоваться текущий месяц|
|» is_completed|body|boolean| no |Флаг успешного завершения заказа|
|» cancel_reason|body|string| no |Код причины отмены|

> Response Examples

> 200 Response

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» list|[object]|true|none||none|
|»» creation_date|integer|true|none||Дата создания отзыва|
|»» text|string|true|none||Текст отзыва|
|»» rate|integer|true|none||Оценка|
|»» order_id|string|true|none||ID заказа|
|»» order_external_id|string¦null|true|none||Номер заказа для клиента|
|»» order_status_name|string|true|none||Название статуса заказа|
|»» order_status_color|string|true|none||Цвет статуса заказа|
|»» store_uuid|string|true|none||UUID аптеки|
|»» store_address|string|true|none||Адрес аптеки|
|» total|integer|true|none||Общее количество элементов в ответе|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Метаданные списка

GET /merch-lk/v1/reviews/meta

> Body Parameters

```json
{
  "month": 0,
  "store_id": 0
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» month|body|integer| no |Дата начала месяца, по умолчанию будет использоваться текущий месяц|
|» store_id|body|integer| no |Идентификатор аптеки|

> Response Examples

> 200 Response

```json
{
  "location_name": "string",
  "current_period": {
    "from": 0,
    "to": 0
  },
  "reviews": {
    "total": 0,
    "comments": 0,
    "average": 0
  }
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» location_name|string¦null|true|none||Название локации (аптеки или города)|
|» current_period|object|true|none||none|
|»» from|integer|true|none||Дата начала выбранного периода|
|»» to|integer|true|none||Дата конца выбранного периода|
|» reviews|object|true|none||none|
|»» total|integer|true|none||Общее количество оценок|
|»» comments|integer|true|none||Количество оценок с комментарием (отзывы)|
|»» average|number¦null|true|none||Средняя оценка|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Список

GET /merch-lk/v1/reviews

> Body Parameters

```json
{
  "rate": 0,
  "store_id": 0,
  "month": 0,
  "is_completed": true,
  "cancel_reason": "string",
  "page": 0,
  "count": 0
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» rate|body|integer| no |Оценка|
|» store_id|body|integer| no |Идентификатор аптеки|
|» month|body|integer| no |Дата начала месяца, по умолчанию будет использоваться текущий месяц|
|» is_completed|body|boolean| no |Флаг успешного завершения заказа|
|» cancel_reason|body|string| no |Код причины отмены|
|» page|body|integer| no |Номер страницы (по умолчанию 1)|
|» count|body|integer| no |Количество элементов в ответе|

> Response Examples

> 200 Response

```json
{
  "list": [
    {
      "creation_date": 0,
      "text": "string",
      "rate": 0,
      "order_id": "string",
      "order_external_id": "string",
      "order_status_name": "string",
      "order_status_color": "string",
      "store_uuid": "string",
      "store_address": "string"
    }
  ],
  "total": 0
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» list|[object]|true|none||none|
|»» creation_date|integer|true|none||Дата создания отзыва|
|»» text|string|true|none||Текст отзыва|
|»» rate|integer|true|none||Оценка|
|»» order_id|string|true|none||ID заказа|
|»» order_external_id|string¦null|true|none||Номер заказа для клиента|
|»» order_status_name|string|true|none||Название статуса заказа|
|»» order_status_color|string|true|none||Цвет статуса заказа|
|»» store_uuid|string|true|none||UUID аптеки|
|»» store_address|string|true|none||Адрес аптеки|
|» total|integer|true|none||Общее количество элементов в ответе|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

# Отмены

## GET Загрузка отчета

GET /merch-lk/v1/cancels/download

> Body Parameters

```json
{
  "store_uuid": "string",
  "store_id": 0,
  "ma_city_id": 0,
  "month": 0
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» store_uuid|body|string| no |Код аптеки|
|» store_id|body|integer| no |Идентификатор аптеки|
|» ma_city_id|body|integer| no |Идентификатор города|
|» month|body|integer| no |Дата начала месяца, по умолчанию будет использоваться текущий месяц|

> Response Examples

> 200 Response

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Метаданные списка

GET /merch-lk/v1/cancels/meta

> Body Parameters

```json
{
  "month": 0,
  "store_uuid": "string",
  "store_id": 0,
  "ma_city_id": 0
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» month|body|integer| no |Дата начала месяца, по умолчанию будет использоваться текущий месяц|
|» store_uuid|body|string| no |Код аптеки|
|» store_id|body|integer| no |Идентификатор аптеки|
|» ma_city_id|body|integer| no |Идентификатор города|

> Response Examples

> 200 Response

```json
{
  "location_name": "string",
  "current_period": {
    "from": 0,
    "to": 0
  },
  "orders": {
    "general": {
      "total": 0,
      "done": 0
    },
    "reasons": [
      {
        "label": "string",
        "quantity": 0,
        "part": 0
      }
    ]
  }
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» location_name|string¦null|true|none||Название локации (аптеки или города)|
|» current_period|object|true|none||none|
|»» from|integer|true|none||Дата начала выбранного периода|
|»» to|integer|true|none||Дата конца выбранного периода|
|» orders|object|true|none||none|
|»» general|object|true|none||none|
|»»» total|integer|true|none||Количество созданных|
|»»» done|integer|true|none||Количество выданных|
|»» reasons|[object]|true|none||none|
|»»» label|string|true|none||Причина отмены|
|»»» quantity|integer|true|none||Количество отмен|
|»»» part|integer|true|none||Доля в процентах|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Список

GET /merch-lk/v1/cancels

> Body Parameters

```json
{
  "sort_by": "string",
  "sort_direction": "string",
  "store_uuid": "string",
  "store_id": 0,
  "ma_city_id": 0,
  "month": 0,
  "page": 0,
  "count": 0
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» sort_by|body|string| no |Код поля для сортировки:|
|» sort_direction|body|string| no |Направление сортировки (asc | desc)|
|» store_uuid|body|string| no |Код аптеки|
|» store_id|body|integer| no |Идентификатор аптеки|
|» ma_city_id|body|integer| no |Идентификатор города|
|» month|body|integer| no |Дата начала месяца, по умолчанию будет использоваться текущий месяц|
|» page|body|integer| no |Номер страницы (по умолчанию 1)|
|» count|body|integer| no |Количество элементов в ответе|

#### Description

**» sort_by**: Код поля для сортировки:
total
ma-auto
client
store-before-build
store-before-reservation-end
store-reservation-end

> Response Examples

> 200 Response

```json
{
  "list": [
    {
      "store_uuid": "string",
      "store_address": "string",
      "total": 0,
      "ma_auto": 0,
      "ma_auto_part": 0,
      "client": 0,
      "client_part": 0,
      "store_before_build": 0,
      "store_before_build_part": 0,
      "store_before_reservation_end": 0,
      "store_before_reservation_end_part": 0,
      "store_reservation_end": 0,
      "store_reservation_end_part": 0
    }
  ],
  "total": 0
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» list|[object]|true|none||none|
|»» store_uuid|string|true|none||Код аптеки|
|»» store_address|string|true|none||Адрес аптеки|
|»» total|integer|true|none||Количество созданных заказов|
|»» ma_auto|integer|true|none||Количество отмененных, автоматическая отмена МА|
|»» ma_auto_part|integer|true|none||Доля отмененных, автоматическая отмена МА|
|»» client|integer|true|none||Количество отмененных, отмена клиентом|
|»» client_part|integer|true|none||Доля отмененных, отмена клиентом|
|»» store_before_build|integer|true|none||Количество отмененных, отмена аптекой до сборки|
|»» store_before_build_part|integer|true|none||Доля отмененных, отмена аптекой до сборки|
|»» store_before_reservation_end|integer|true|none||Количество отмененных, отмена аптекой до конца срока брони|
|»» store_before_reservation_end_part|integer|true|none||Доля отмененных, отмена аптекой до конца срока брони|
|»» store_reservation_end|integer|true|none||Количество отмененных, отмена аптекой по сроку брони|
|»» store_reservation_end_part|integer|true|none||Доля отмененных, отмена аптекой по сроку брони|
|» total|integer|true|none||Общее количество элементов в ответе|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

# Регионы

## GET Список / поиск

GET /merch-lk/v1/regions

> Body Parameters

```json
{
  "query": "string",
  "id": 0,
  "ids": [
    0
  ],
  "page": 0,
  "count": 0
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» query|body|string| no |Поисковый запрос|
|» id|body|integer| no |Идентификатор региона|
|» ids|body|[integer]| no |Список идентификаторов регионов|
|» page|body|integer| no |Номер страницы (по умолчанию 1)|
|» count|body|integer| no |Количество элементов в ответе|

> Response Examples

> 200 Response

```json
{
  "list": [
    {
      "id": 0,
      "name": "string"
    }
  ]
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» list|[object]|true|none||none|
|»» id|integer|true|none||Идентификатор региона|
|»» name|string|true|none||Название региона|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

# СТМ

## GET Детальная

GET /merch-lk/v1/drugs/detail

> Body Parameters

```json
{
  "id": 0
}
```

### Params

|Name|Location|Type|Required|Description|
|---|---|---|---|---|
|Auth-Token|header|string| yes |Токен авторизации|
|body|body|object| no |none|
|» id|body|integer| yes |Идентификатор товара|

> Response Examples

> 200 Response

```json
{
  "id": 0,
  "name": "string",
  "url": "string",
  "images": [
    {
      "id": "string",
      "url": "string"
    }
  ],
  "props": [
    {
      "code": "string",
      "name": "string",
      "value": "string",
      "type": "string"
    }
  ],
  "blocks": [
    {
      "id": 0,
      "title": "string",
      "content": "string"
    }
  ],
  "vendor_images": {
    "id": 0,
    "url": "string"
  },
  "vendor_blocks": {
    "id": 0,
    "title": "string",
    "content": "string"
  },
  "stickers": {
    "color": "string",
    "icon": "string",
    "name": "string"
  }
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» id|integer|true|none||Идентификатор товара|
|» name|string|true|none||Название товара|
|» url|string|true|none||URL детальной страницы товара на сайте|
|» images|[object]|true|none||Массив изображений товара|
|»» id|string|true|none||Идентификатор изображения|
|»» url|string|true|none||URL изображения|
|» props|[object]|true|none||Массив свойств товара, для не ЛС пустой массив|
|»» code|string|true|none||Символьный код свойства|
|»» name|string|true|none||Название свойства|
|»» value|string¦null|true|none||Значение свойства|
|»» type|string|true|none||Тип свойства: text | html|
|» blocks|[object]¦null|true|none||Массив блоков описания, null если нельзя добавлять блоки|
|»» id|integer|true|none||Идентификатор блока|
|»» title|string¦null|true|none||Заголовок блока|
|»» content|string|true|none||Контент блока|
|» vendor_images|object|true|none||none|
|»» id|integer|true|none||Идентификатор изображения|
|»» url|string|true|none||URL изображения|
|» vendor_blocks|object|true|none||none|
|»» id|integer|true|none||Идентификатор блока|
|»» title|string¦null|true|none||Заголовок блока|
|»» content|string|true|none||Контент блока|
|» stickers|object|true|none||Стикеры|
|»» color|string|true|none||Цвет фона в hex|
|»» icon|string|true|none||URL иконки|
|»» name|string|true|none||Название стикера|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## POST Редактирование

POST /merch-lk/v1/drugs/detail/update

> Body Parameters

```json
{
  "id": 0,
  "image": {
    "new": {},
    "deleted": "string"
  },
  "prop": {
    "code": "string",
    "value": "string"
  },
  "block": {
    "id": 0,
    "title": "string",
    "content": "string",
    "deleted": 0
  },
  "vendor_image": {
    "new": "string",
    "deleted": 0
  },
  "vendor_block": {
    "id": 0,
    "title": "string",
    "content": "string",
    "deleted": 0
  }
}
```

### Params

|Name|Location|Type|Required|Title|Description|
|---|---|---|---|---|---|
|Auth-Token|header|string| yes ||Токен авторизации|
|body|body|object| no ||none|
|» id|body|integer| yes ||Идентификатор товара|
|» image|body|object| no ||none|
|»» new|body|object| no | file|Новое изображение|
|»» deleted|body|string| no ||Идентификатор изображения, которое нужно удалить|
|» prop|body|object| no ||Свойство, которое нужно обновить, принимается только для ЛС|
|»» code|body|string| no ||Символьный код свойства|
|»» value|body|string| no ||Значение свойства|
|» block|body|object| no ||none|
|»» id|body|integer¦null| no ||Идентификатор блока, если null, значит новый блок|
|»» title|body|string¦null| no ||Заголовок блока|
|»» content|body|string| no ||Контент блока|
|»» deleted|body|integer| no ||Идентификатор блока, который нужно удалить|
|» vendor_image|body|object| no ||none|
|»» new|body|string| no | file|Новое изображение|
|»» deleted|body|integer| no ||Идентификатор изображения, которое нужно удалить|
|» vendor_block|body|object| no ||none|
|»» id|body|integer¦null| no ||Идентификатор блока, если null, значит новый блок|
|»» title|body|string¦null| no ||Заголовок блока|
|»» content|body|string| no ||Контент блока|
|»» deleted|body|integer| no ||Идентификатор блока, который нужно удалить|

> Response Examples

> 200 Response

```json
{
  "stickers": {}
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» stickers|object|true|none||none|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Список

GET /merch-lk/v1/drugs

> Body Parameters

```json
{
  "query": "string",
  "page": 0,
  "count": 0
}
```

### Params

|Name|Location|Type|Required|Title|Description|
|---|---|---|---|---|---|
|Auth-Token|header|string| yes ||Токен авторизации|
|body|body|object| no ||none|
|» query|body|string| no ||Строка для поиска|
|» page|body|integer| no ||Номер страницы (по умолчанию 1)|
|» count|body|integer| no ||Количество элементов в ответе|

> Response Examples

> 200 Response

```json
{
  "list": [
    {
      "id": 0,
      "name": "string",
      "image_url": "string",
      "stickers": [
        {
          "color": "string",
          "icon": "string",
          "name": "string"
        }
      ]
    }
  ],
  "total": 0
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» list|[object]|true|none||none|
|»» id|integer|true|none||Идентификатор товара|
|»» name|string|true|none||Название товара|
|»» image_url|string¦null|true|none||URL основной картинки товара|
|»» stickers|[object]|true|none||Стикеры|
|»»» color|string|true|none||Цвет фона в hex|
|»»» icon|string|true|none||URL иконки|
|»»» name|string|true|none||Название стикер|
|» total|integer|true|none||Общее количество элементов в ответе|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

# Суперадмин

## POST Выбор сети

POST /merch-lk/v1/superadmin/networks/set

> Body Parameters

```json
{
  "id": 0
}
```

### Params

|Name|Location|Type|Required|Title|Description|
|---|---|---|---|---|---|
|Auth-Token|header|string| yes ||Токен авторизации|
|body|body|object| no ||none|
|» id|body|integer| yes ||Идентификатор|

> Response Examples

> 200 Response

```json
{
  "name": "string"
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» name|string|true|none||Название|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Список

GET /merch-lk/v1/superadmin/networks

> Body Parameters

```json
{
  "name": "string"
}
```

### Params

|Name|Location|Type|Required|Title|Description|
|---|---|---|---|---|---|
|Auth-Token|header|string| yes ||Токен авторизации|
|body|body|object| no ||none|
|» name|body|string| no ||Название|

> Response Examples

> 200 Response

```json
{
  "list": [
    {
      "id": 0,
      "name": "string"
    }
  ]
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» list|[object]|true|none||none|
|»» id|integer|true|none||Идентификатор|
|»» name|string|true|none||Название|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

# Товары

## GET Сводка остатков по аптекам

GET /merch-lk/v1/items/stores

> Body Parameters

```json
{
  "sort_by": "string",
  "sort_direction": "string",
  "store_uuid": "string",
  "address": "string",
  "ma_city_id": 0,
  "page": 0,
  "count": 0
}
```

### Params

|Name|Location|Type|Required|Title|Description|
|---|---|---|---|---|---|
|Auth-Token|header|string| yes ||Токен авторизации|
|body|body|object| no ||none|
|» sort_by|body|string| no ||Код поля для сортировки:|
|» sort_direction|body|string| no ||Направление сортировки (asc | desc)|
|» store_uuid|body|string| no ||Код аптеки|
|» address|body|string| no ||Адрес аптеки|
|» ma_city_id|body|integer| no ||Идентификатор города|
|» page|body|integer| no ||Номер страницы (по умолчанию 1)|
|» count|body|integer| no ||Количество элементов в ответе|

#### Description

**» sort_by**: Код поля для сортировки:
                      active
                      unconnected
                      disabled

> Response Examples

> 200 Response

```json
{
  "list": [
    {
      "store_id": 0,
      "store_uuid": "string",
      "store_address": "string",
      "city_name": "string",
      "active_count": 0,
      "unconnected_count": 0,
      "disabled_count": 0
    }
  ],
  "total": 0
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» list|[object]|true|none||none|
|»» store_id|integer|true|none||Идентификатор аптеки|
|»» store_uuid|string|true|none||Код аптеки|
|»» store_address|string|true|none||Адрес аптеки|
|»» city_name|string|true|none||Город|
|»» active_count|integer|true|none||Количество активных товаров|
|»» unconnected_count|integer|true|none||Количество несвязанных товаров|
|»» disabled_count|integer|true|none||Количество отключенных товаров|
|» total|integer|true|none||Общее количество элементов в ответе|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

# Товары/Несвязанные товары

## GET Загрузка отчета

GET /merch-lk/v1/items/unconnected/download

> Body Parameters

```json
{
  "uuid": "string",
  "name": "string",
  "store_id": "string",
  "store_uuid": "string"
}
```

### Params

|Name|Location|Type|Required|Title|Description|
|---|---|---|---|---|---|
|Auth-Token|header|string| yes ||Токен авторизации|
|body|body|object| no ||none|
|» uuid|body|string| no ||Код товара|
|» name|body|string| no ||Название товара|
|» store_id|body|string| no ||Идентификатор аптеки|
|» store_uuid|body|string| no ||UUID аптеки|

> Response Examples

> 200 Response

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Заявка на добавление ШК в эталон

GET /merch-lk/v1/items/unconnected/add-barcode

> Body Parameters

```json
{
  "barcode": "string",
  "item_uuid": "string",
  "item_name": "string",
  "brand_name": "string"
}
```

### Params

|Name|Location|Type|Required|Title|Description|
|---|---|---|---|---|---|
|Auth-Token|header|string| yes ||Токен авторизации|
|body|body|object| no ||none|
|» barcode|body|string| yes ||ШК от мерчанта|
|» item_uuid|body|string| yes ||Код товара|
|» item_name|body|string| yes ||Название товара|
|» brand_name|body|string| no ||Название бренда от мерчанта|

> Response Examples

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Список

GET /merch-lk/v1/items/unconnected

> Body Parameters

```json
{
  "uuid": "string",
  "name": "string",
  "store_id": 0,
  "store_uuid": "string",
  "page": 0,
  "count": 0
}
```

### Params

|Name|Location|Type|Required|Title|Description|
|---|---|---|---|---|---|
|Auth-Token|header|string| yes ||Токен авторизации|
|body|body|object| no ||none|
|» uuid|body|string| no ||Код товара|
|» name|body|string| no ||Название товара|
|» store_id|body|integer| no ||Идентификатор аптеки|
|» store_uuid|body|string| no ||UUID аптеки|
|» page|body|integer| no ||Номер страницы (по умолчанию 1)|
|» count|body|integer| no ||Количество элементов в ответе|

> Response Examples

> 200 Response

```json
{
  "list": [
    {
      "item_uuid": "string",
      "item_name": "string",
      "brand_name": "string",
      "barcodes": [
        {
          "barcode": "string",
          "is_valid": true
        }
      ],
      "protek": [
        "string"
      ],
      "katren": [
        "string"
      ],
      "egk": [
        "string"
      ],
      "eas": [
        "string"
      ],
      "series": "string"
    }
  ],
  "total": 0
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» list|[object]|true|none||none|
|»» item_uuid|string|true|none||none|
|»» item_name|string|true|none||none|
|»» brand_name|string¦null|true|none||none|
|»» barcodes|[object]|true|none||none|
|»»» barcode|string|true|none||none|
|»»» is_valid|boolean|true|none||none|
|»» protek|[string]¦null|true|none||none|
|»» katren|[string]¦null|true|none||none|
|»» egk|[string]¦null|true|none||none|
|»» eas|[string]¦null|true|none||none|
|»» series|string¦null|false|none||none|
|» total|integer|true|none||none|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

# Товары/Цены и остатки

## GET Варианты активности

GET /merch-lk/v1/items/prices/activity-options

### Params

|Name|Location|Type|Required|Title|Description|
|---|---|---|---|---|---|
|Auth-Token|header|string| yes ||Токен авторизации|

> Response Examples

> 200 Response

```json
{
  "list": [
    {
      "code": "string",
      "name": "string"
    }
  ]
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» list|[object]|true|none||none|
|»» code|string|true|none||Код|
|»» name|string|true|none||Название|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Варианты причин отключения

GET /merch-lk/v1/items/prices/qurantine-options

### Params

|Name|Location|Type|Required|Title|Description|
|---|---|---|---|---|---|
|Auth-Token|header|string| yes ||Токен авторизации|

> Response Examples

> 200 Response

```json
{
  "list": [
    {
      "code": "string",
      "name": "string"
    }
  ]
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» list|[object]|true|none||none|
|»» code|string|true|none||Код|
|»» name|string|true|none||Название|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Список

GET /merch-lk/v2/items/prices

> Body Parameters

```json
{
  "item_uuid": "string",
  "item_name": "string",
  "store_id": 0,
  "store_uuid": 0,
  "price_activity": "string",
  "meta": {
    "skip_calc_total": true
  },
  "page": 0,
  "count": 0
}
```

### Params

|Name|Location|Type|Required|Title|Description|
|---|---|---|---|---|---|
|Auth-Token|header|string| yes ||Токен авторизации|
|body|body|object| no ||none|
|» item_uuid|body|string| no ||Код товара|
|» item_name|body|string| no ||Название товара|
|» store_id|body|integer| no ||Идентификатор аптеки|
|» store_uuid|body|integer| no ||Код аптеки|
|» price_activity|body|string| no ||Код активности|
|» meta|body|object| no ||none|
|»» skip_calc_total|body|boolean| no ||Флаг пропуска расчёта total|
|» page|body|integer| no ||Номер страницы (по умолчанию 1)|
|» count|body|integer| no ||Количество элементов в ответе|

> Response Examples

> 200 Response

```json
{
  "list": [
    {
      "merchant_item_uuid": "string",
      "merchant_item_name": "string",
      "merchant_brand_name": "string",
      "merchant_series": "string",
      "merchant_barcodes": [
        "string"
      ],
      "merchant_protek": [
        "string"
      ],
      "merchant_katren": [
        "string"
      ],
      "merchant_egk": [
        "string"
      ],
      "merchant_eas": [
        "string"
      ],
      "price": 0,
      "available_count": 0,
      "is_active": true,
      "activity_message": "string",
      "disable_reason": {
        "description": "string",
        "quarantine_until_date": 0,
        "order_id": 0,
        "order_external_id": "string",
        "region_avg_price": 0
      },
      "item_id": 0,
      "item_name": "string",
      "brand_name": "string",
      "store_id": 0,
      "store_uuid": "string",
      "store_addres": "string",
      "city_name": "string"
    }
  ],
  "total": 0,
  "meta": {
    "hide_pagination": true,
    "skip_calc_total": true
  }
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» list|[object]|true|none||none|
|»» merchant_item_uuid|string|true|none||Код товара от мерчанта|
|»» merchant_item_name|string|true|none||Название товара от мерчанта|
|»» merchant_brand_name|string¦null|true|none||Название бренда от мерчанта|
|»» merchant_series|string¦null|true|none||Код партии от мерчанта|
|»» merchant_barcodes|[string]¦null|true|none||ШК от мерчанта|
|»» merchant_protek|[string]¦null|true|none||Коды протек от мерчанта|
|»» merchant_katren|[string]¦null|true|none||Коды катрен от мерчанта|
|»» merchant_egk|[string]¦null|true|none||Коды ЕГК от мерчанта|
|»» merchant_eas|[string]¦null|true|none||Коды ЕАС от мерчанта|
|»» price|number|true|none||Цена|
|»» available_count|integer¦null|true|none||Доступное количество товара (остаток)|
|»» is_active|boolean|true|none||Сообщение об активности|
|»» activity_message|string¦null|true|none||Сообщение об активности|
|»» disable_reason|object¦null|true|none||Причина отключения|
|»»» description|string|true|none||Описание причины отключения|
|»»» quarantine_until_date|integer¦null|true|none||Дата окончания карантина|
|»»» order_id|integer¦null|true|none||Идентификатор заказа|
|»»» order_external_id|string¦null|true|none||Номер заказа для клиента|
|»»» region_avg_price|number¦null|true|none||Средняя цена по региону|
|»» item_id|integer¦null|true|none||Идентификатор эталонного товара|
|»» item_name|string¦null|true|none||Название эталонного товара|
|»» brand_name|string¦null|true|none||Бренд эталонного товара|
|»» store_id|integer|true|none||Идентификатор аптеки|
|»» store_uuid|string|true|none||Код аптеки|
|»» store_addres|string|true|none||Адрес аптеки|
|»» city_name|string|true|none||Город|
|» total|integer¦null|true|none||Общее число элементов в ответе|
|» meta|object|true|none||none|
|»» hide_pagination|boolean|true|none||Флаг скрытия постранички, т.е. в ответе сразу все строки|
|»» skip_calc_total|boolean|true|none||Флаг пропуска расчета total|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Загрузка отчета

GET /merch-lk/v2/items/prices/download

> Body Parameters

```json
{
  "item_uuid": "string",
  "item_name": "string",
  "store_id": 0,
  "store_uuid": 0,
  "price_activity": "string"
}
```

### Params

|Name|Location|Type|Required|Title|Description|
|---|---|---|---|---|---|
|Auth-Token|header|string| yes ||Токен авторизации|
|body|body|object| no ||none|
|» item_uuid|body|string| no ||Код товара|
|» item_name|body|string| no ||Название товара|
|» store_id|body|integer| no ||Идентификатор аптеки|
|» store_uuid|body|integer| no ||Код аптеки|
|» price_activity|body|string| no ||Код активности|

> Response Examples

> 200 Response

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» list|[object]|true|none||none|
|»» merchant_item_uuid|string|true|none||Код товара от мерчанта|
|»» merchant_item_name|string|true|none||Название товара от мерчанта|
|»» merchant_brand_name|string¦null|true|none||Название бренда от мерчанта|
|»» merchant_series|string¦null|true|none||Код партии от мерчанта|
|»» merchant_barcodes|[string]¦null|true|none||ШК от мерчанта|
|»» merchant_protek|[string]¦null|true|none||Коды протек от мерчанта|
|»» merchant_katren|[string]¦null|true|none||Коды катрен от мерчанта|
|»» merchant_egk|[string]¦null|true|none||Коды ЕГК от мерчанта|
|»» merchant_eas|[string]¦null|true|none||Коды ЕАС от мерчанта|
|»» price|number|true|none||Цена|
|»» available_count|integer¦null|true|none||Доступное количество товара (остаток)|
|»» is_active|boolean|true|none||Сообщение об активности|
|»» activity_message|string¦null|true|none||Сообщение об активности|
|»» disable_reason|object¦null|true|none||Причина отключения|
|»»» description|string|true|none||Описание причины отключения|
|»»» quarantine_until_date|integer¦null|true|none||Дата окончания карантина|
|»»» order_id|integer¦null|true|none||Идентификатор заказа|
|»»» order_external_id|string¦null|true|none||Номер заказа для клиента|
|»»» region_avg_price|number¦null|true|none||Средняя цена по региону|
|»» item_id|integer¦null|true|none||Идентификатор эталонного товара|
|»» item_name|string¦null|true|none||Название эталонного товара|
|»» brand_name|string¦null|true|none||Бренд эталонного товара|
|»» store_id|integer|true|none||Идентификатор аптеки|
|»» store_uuid|string|true|none||Код аптеки|
|»» store_addres|string|true|none||Адрес аптеки|
|»» city_name|string|true|none||Город|
|» total|integer¦null|true|none||Общее число элементов в ответе|
|» meta|object|true|none||none|
|»» hide_pagination|boolean|true|none||Флаг скрытия постранички, т.е. в ответе сразу все строки|
|»» skip_calc_total|boolean|true|none||Флаг пропуска расчета total|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

# Ценовой робот/Аптеки

## GET Список

GET /merch-lk/v1/pricebot/stores

> Body Parameters

```json
{
  "page": 0,
  "count": 0
}
```

### Params

|Name|Location|Type|Required|Title|Description|
|---|---|---|---|---|---|
|Auth-Token|header|string| yes ||Токен авторизации|
|body|body|object| no ||none|
|» page|body|integer| no ||Номер страницы (по умолчанию 1)|
|» count|body|integer| no ||Количество элементов в ответе|

> Response Examples

> 200 Response

```json
{
  "list": [
    {
      "id": 0,
      "uuid": "string",
      "address": "string",
      "city_name": "string",
      "is_deleted": true,
      "activity_message": "string",
      "quarantine_until": 0,
      "disconnected_until": 0,
      "is_active_pricebot": true
    }
  ],
  "total": 0
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» list|[object]|true|none||none|
|»» id|integer|true|none||Идентификатор аптеки|
|»» uuid|string|true|none||UUID аптеки|
|»» address|string|true|none||Адрес аптеки|
|»» city_name|string|true|none||Название города аптеки|
|»» is_deleted|boolean|true|none||Отметка об удалении|
|»» activity_message|string|true|none||Сообщение об активности|
|»» quarantine_until|integer¦null|true|none||Дата окончания карантина|
|»» disconnected_until|integer¦null|true|none||Отключена до|
|»» is_active_pricebot|boolean¦null|true|none||Флаг возможности включения аптеки|
|» total|integer|true|none||Общее количество элементов в ответе|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

# Ценовой робот/Заказы

## GET Загрузка отчета

GET /merch-lk/v1/pricebot/orders/download

> Body Parameters

```json
{
  "store_id": 0,
  "month": 0,
  "status_id": 0,
  "item_uuid": "string",
  "item_name": "string",
  "is_stale": true
}
```

### Params

|Name|Location|Type|Required|Title|Description|
|---|---|---|---|---|---|
|Auth-Token|header|string| yes ||Токен авторизации|
|body|body|object| no ||none|
|» store_id|body|integer| no ||Идентификатор аптеки|
|» month|body|integer| no ||Дата начала месяца, по умолчанию будет использоваться текущий месяц|
|» status_id|body|integer| no ||Статус заказа|
|» item_uuid|body|string| no ||Код товара|
|» item_name|body|string| no ||Название товара от мерчанта|
|» is_stale|body|boolean| no ||Только заказы с неликвидными товарами|

> Response Examples

> 200 Response

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Метаданные списка продаж

GET /merch-lk/v2/pricebot/orders/meta/sales

> Body Parameters

```json
{
  "month": 0,
  "store_id": 0,
  "status_id": 0
}
```

### Params

|Name|Location|Type|Required|Title|Description|
|---|---|---|---|---|---|
|Auth-Token|header|string| yes ||Токен авторизации|
|body|body|object| no ||none|
|» month|body|integer| no ||Дата начала месяца, по умолчанию будет использоваться текущий месяц|
|» store_id|body|integer| no ||Идентификатор аптеки|
|» status_id|body|integer| no ||Статус заказа|

> Response Examples

> 200 Response

```json
{
  "meta": {
    "title": "string"
  },
  "data": {
    "left_col": [
      {
        "label": "string",
        "value": "string"
      }
    ],
    "right_col": [
      {
        "label": "string",
        "value": "string"
      }
    ]
  }
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» meta|object|true|none||none|
|»» title|string¦null|true|none||Заголовок|
|» data|object|true|none||none|
|»» left_col|[object]|true|none||none|
|»»» label|string|true|none||Название|
|»»» value|string|true|none||Значение|
|»» right_col|[object]|true|none||none|
|»»» label|string|true|none||Название|
|»»» value|string|true|none||Значение|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Метаданные списка контрактных

GET /merch-lk/v2/pricebot/orders/meta/contract

> Body Parameters

```json
{
  "month": 0,
  "store_id": 0,
  "status_id": 0
}
```

### Params

|Name|Location|Type|Required|Title|Description|
|---|---|---|---|---|---|
|Auth-Token|header|string| yes ||Токен авторизации|
|body|body|object| no ||none|
|» month|body|integer| no ||Дата начала месяца, по умолчанию будет использоваться текущий месяц|
|» store_id|body|integer| no ||Идентификатор аптеки|
|» status_id|body|integer| no ||Статус заказа|

> Response Examples

> 200 Response

```json
{
  "meta": {
    "title": "string"
  },
  "data": {
    "left_col": [
      {
        "label": "string",
        "value": "string"
      }
    ],
    "right_col": [
      {
        "label": "string",
        "value": "string"
      }
    ]
  }
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» meta|object|true|none||none|
|»» title|string¦null|true|none||Заголовок|
|» data|object|true|none||none|
|»» left_col|[object]|true|none||none|
|»»» label|string|true|none||Название|
|»»» value|string|true|none||Значение|
|»» right_col|[object]|true|none||none|
|»»» label|string|true|none||Название|
|»»» value|string|true|none||Значение|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## GET Список

GET /merch-lk/v1/pricebot/orders

> Body Parameters

```json
{
  "store_id": 0,
  "month": 0,
  "status_id": 0,
  "item_uuid": "string",
  "item_name": "string",
  "is_stale": true,
  "page": 0,
  "count": 0
}
```

### Params

|Name|Location|Type|Required|Title|Description|
|---|---|---|---|---|---|
|Auth-Token|header|string| yes ||Токен авторизации|
|body|body|object| no ||none|
|» store_id|body|integer| no ||Идентификатор аптеки|
|» month|body|integer| no ||Дата начала месяца, по умолчанию будет использоваться текущий месяц|
|» status_id|body|integer| no ||Статус заказа|
|» item_uuid|body|string| no ||Код товара|
|» item_name|body|string| no ||Название товара от мерчанта|
|» is_stale|body|boolean| no ||Только заказы с неликвидными товарами|
|» page|body|integer| no ||Номер страницы (по умолчанию 1)|
|» count|body|integer| no ||Количество элементов в ответе|

> Response Examples

> 200 Response

```json
{
  "list": [
    {
      "order_id": 0,
      "order_external_id": "string",
      "creation_date": 0,
      "store_uuid": "string",
      "store_address": "string",
      "item_name": "string",
      "brand_name": "string",
      "orig_price": 0,
      "price_init": 0,
      "price": 0,
      "margin": 0,
      "margin_percent": 0,
      "date_init": 0,
      "status_name": "string",
      "status_color": "string"
    }
  ],
  "total": 0
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» list|[object]|true|none||none|
|»» order_id|integer|true|none||Идентификатор заказа|
|»» order_external_id|string¦null|true|none||Номер заказа для клиента|
|»» creation_date|integer|true|none||Дата создания заказа|
|»» store_uuid|string|true|none||Код аптеки|
|»» store_address|string|true|none||Адрес аптеки|
|»» item_name|string|true|none||Название товара от мерчанта|
|»» brand_name|string¦null|true|none||Название бренда от мерчанта|
|»» orig_price|number¦null|true|none||Розничная цена|
|»» price_init|number¦null|true|none||Закупочная цена|
|»» price|number|true|none||Цена продажи|
|»» margin|number¦null|true|none||Наценка|
|»» margin_percent|number¦null|true|none||Процент наценки|
|»» date_init|integer¦null|true|none||Дата поставки|
|»» status_name|string|true|none||Название статуса заказа|
|»» status_color|string|true|none||Цвет статуса заказа|
|» total|integer|true|none||Общее количество элементов в ответе|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

# Ценовой робот/Настройки

## GET Список

GET /merch-lk/v1/pricebot/settings

### Params

|Name|Location|Type|Required|Title|Description|
|---|---|---|---|---|---|
|Auth-Token|header|string| yes ||Токен авторизации|

> Response Examples

> 200 Response

```json
{
  "old_items": true,
  "contract_items": true
}
```

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|Inline|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **200**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» old_items|boolean|true|none||Нелеквиды|
|» contract_items|boolean|true|none||Контрактные товары|

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

## POST Изменение

POST /merch-lk/v1/pricebot/settings/update

> Body Parameters

```json
{
  "old_items": true,
  "contract_items": true
}
```

### Params

|Name|Location|Type|Required|Title|Description|
|---|---|---|---|---|---|
|Auth-Token|header|string| yes ||Токен авторизации|
|body|body|object| no ||none|
|» old_items|body|boolean| yes ||Нелеквиды|
|» contract_items|body|boolean| yes ||Контрактные товары|

> Response Examples

> 500 Response

```json
{
  "message": "Какое-то сообщение об ошибке",
  "action": null
}
```

### Responses

|HTTP Status Code |Meaning|Description|Data schema|
|---|---|---|---|
|200|[OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)|none|None|
|500|[Internal Server Error](https://tools.ietf.org/html/rfc7231#section-6.6.1)|none|Inline|

### Responses Data Schema

HTTP Status Code **500**

|Name|Type|Required|Restrictions|Title|description|
|---|---|---|---|---|---|
|» message|string|false|none||Сообщение для пользователя|
|» action|string¦null|false|none||Действие, которое нужно совершить при возникновении ошибки|

# Data Schema

<h2 id="tocS_stores_detail">stores_detail</h2>

<a id="schemastores_detail"></a>
<a id="schema_stores_detail"></a>
<a id="tocSstores_detail"></a>
<a id="tocsstores_detail"></a>

```json
{
  "id": 0,
  "uuid": "string",
  "address": "string",
  "city_name": "string",
  "ma_rating": 0,
  "build_time": "string",
  "is_deleted": true,
  "activity_message": "string",
  "quarantine_until": 0,
  "disconnected_until": 0,
  "schedule": "string",
  "temporary_schedule": [
    {
      "date": 0,
      "is_day_off": true,
      "open_time": 0,
      "close_time": 0
    }
  ]
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|id|integer|true|none||Идентификатор аптеки|
|uuid|string|true|none||UUID аптеки|
|address|string|true|none||Адрес аптеки|
|city_name|string¦null|true|none||Название города аптеки|
|ma_rating|integer¦null|true|none||Рейтинг Мегаптеки (0-100)|
|build_time|string¦null|true|none||Время сборки, текстом для вывода|
|is_deleted|boolean|true|none||Отметка об удалении|
|activity_message|string|true|none||Сообщение об активности|
|quarantine_until|integer¦null|true|none||Дата окончания карантина|
|disconnected_until|integer¦null|true|none||Отключена до|
|schedule|string¦null|true|none||График работы|
|temporary_schedule|[object]|true|none||Временный график работы|
|» date|integer|true|none||Дата|
|» is_day_off|boolean|true|none||Флаг выходного дня|
|» open_time|integer¦null|true|none||Время открытия, null для выходного|
|» close_time|integer¦null|true|none||Время закрытия, null для выходного|

<h2 id="tocS_Постраничка">Постраничка</h2>

<a id="schemaпостраничка"></a>
<a id="schema_Постраничка"></a>
<a id="tocSпостраничка"></a>
<a id="tocsпостраничка"></a>

```json
{
  "page": 0,
  "count": 0
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|page|integer|false|none||Номер страницы (по умолчанию 1)|
|count|integer|false|none||Количество элементов в ответе|

<h2 id="tocS_Метаданные списка">Метаданные списка</h2>

<a id="schemaметаданные списка"></a>
<a id="schema_Метаданные списка"></a>
<a id="tocSметаданные списка"></a>
<a id="tocsметаданные списка"></a>

```json
{
  "meta": {
    "title": "string"
  },
  "data": {
    "left_col": [
      {
        "label": "string",
        "value": "string"
      }
    ],
    "right_col": [
      {
        "label": "string",
        "value": "string"
      }
    ]
  }
}

```

### Attribute

|Name|Type|Required|Restrictions|Title|Description|
|---|---|---|---|---|---|
|meta|object|true|none||none|
|» title|string¦null|true|none||Заголовок|
|data|object|true|none||none|
|» left_col|[object]|true|none||none|
|»» label|string|true|none||Название|
|»» value|string|true|none||Значение|
|» right_col|[object]|true|none||none|
|»» label|string|true|none||Название|
|»» value|string|true|none||Значение|

