FORMAT: 1A
HOST: https://api.wheely.com/

# Dashboard

Спецификация API нового дэшборда.



## Order [/orders/{id}]

+ Parameters

    + id: 5b83bd33c06e3100060000c8 (string) - ID заказа который требуется получить.

### Получение одного заказа [GET]

+ Response 200 (application/json)

    + Attributes

        + data
            + id: 5b83bd33c06e3100060000c8 (string, required) - Уникальный монговский идентификатор заказа
            + type: orders (string, required)
            + attributes (Order Model)
            + relationships


+ Response 400 (application/json)

    + Attributes

        + errors
            + code: 777 (number, required) - Внутренний код ошибки.
            + status: 400 (string)
            + source (object, required)
                + pointer: /data (string)
            + title: pay failed (string) - Короткий, человеко-читаемый текст ошибки (может быть локализован).






# Data Structures


## Order Model (object)

+ number: 2752935 (number, required) - Уникальный человекопонятный идентификатор заказа
+ status (enum, required)
    + Default: done
    + Members
        + new
        + accepted
        + scheduled
        + looking_for_drivers
        + car_not_found
        + on_the_way
        + arrived
        + serving
        + done
        + failed
        + cancelled
        + no_show
+ events (array, required)
+ price_details (array, required)
+ price
+ currency
+ paid (boolean, required)
+ created_at (number, required) - Дата создания заказа в БД
+ updated_at (number, required) - Дата изменения заказа в БД
+ pickup_at (number)
+ pickup (number, required)
+ dropoff (number)
+ real_dropoff (number)
