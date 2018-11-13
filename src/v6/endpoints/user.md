## Пользователь [/user]

### Создание новой записи [POST]

Ручка отвечает за заведение в системе нового пользователя.

+ Attributes
    + user (User Model)

+ Response 200 (application/json)
    + Attributes
        + user (User Model)

+ Response 402 (application/json)
    + Attributes
        + errors (array[string])


### Получение конкретной записи [GET /user/{id}]

+ Parameters
    + id (string) ... Идентификатор пользователя, данные которого запрашиваются

+ Request (application/json)
    + Headers
        :[partials/headers/authorization.md](partials/headers/authorization.md)
        :[partials/headers/accept-language.md](partials/headers/accept-language.md)
        Content-Type: application/json

+ Response 200 (application/json)

    + Attributes

        + user (User Model)


### Частичное изменение данных [PATCH /user/{id}]

+ Response 200 (application/json)

    + Attributes

        + user (User Model)


### Полное замещение данных [PUT /user/{id}]

+ Response 200 (application/json)

    + Attributes

        + user (User Model)


### Удаление записи [DELETE /user/{id}]

+ Response 200 (application/json)

    + Attributes (object)


### Изменение номера телефона [PATCH /user]

+ Request 200 (application/json)

  + Body

    + Attributes
        + pin: 1234 (string, required) - Код верификации
        + user (object, required)
            + phone: 79000000000 (Phone, required)

+ Response 200 (application/json)

    + Attributes
        + user (User Model, required)
