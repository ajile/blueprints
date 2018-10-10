## Order [/orders/{id}]

+ Parameters

    + id: 5b83bd33c06e3100060000c8 (string) - ID заказа который требуется получить.

### Получение записи [GET]

+ Response 200 (application/json)

    + Attributes

        + data
            + id: 5b83bd33c06e3100060000c8 (string, required) - Уникальный монговский идентификатор заказа
            + type: orders (string, required)
            + attributes (Order Model)
            + relationships (object)

                :[](partials/belogs-to.md NAME:"city" TYPE:"cities" ID:"5b83bd33c06e3100060000c8")

                :[](partials/belogs-to.md NAME:"user" TYPE:"users" ID:"5b83bd33c06e3100060000c8")

                :[](partials/belogs-to.md NAME:"payment_method" TYPE:"payment_methods" ID:"5b83bd33c06e3100060000c8")

                :[](partials/belogs-to.md NAME:"service" TYPE:"services" ID:"5b83bd33c06e3100060000c8")

                :[](partials/belogs-to.md NAME:"car" TYPE:"cars" ID:"5b83bd33c06e3100060000c8")

                :[](partials/has-many.md NAME:"payment_methods" TYPE:"payment_methods")


+ Response 400 (application/json)

    + Attributes

        + errors
            + code: 100 (number, required) - Внутренний код ошибки.
            + status: 400 (string)
            + source (object, required)
                + pointer: /data (string)
            + title: pay failed (string)

+ Response 400 (application/json)

    + Attributes

        + errors
            + code: 200 (number, required) - Внутренний код ошибки.
            + status: 400 (string)
            + source (object, required)
                + pointer: /data (string)
            + title: pay failed (string)

+ Response 500 (application/json)

        Something went wrong
