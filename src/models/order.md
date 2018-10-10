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
+ events (array[Order Event Model], required)
+ paid (boolean, required)
+ price (number)
+ currency: RUB (string)
+ price_details (array[Order Price Detail Model], required)
+ pickup_at (number)
+ pickup (number, required)
+ dropoff (number)
+ real_dropoff (number)
+ created_at (number, required) - Дата создания заказа в БД
+ updated_at (number, required) - Дата изменения заказа в БД
