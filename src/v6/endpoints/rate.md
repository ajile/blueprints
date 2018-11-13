## Тариф [/rates/all?locale={?lang}]

+ Parameters
    + lang: en (string, optional) - Код языка в формате [ISO 639-1:2002](https://ru.wikipedia.org/wiki/ISO_639-1).


### Получение списка [GET]

+ Response 200 (application/json)
    + Attributes
        + *CITY_NAME*
            + currency_code: GBP (string, required)
            + minutes_before_cancellation_fee: 5 (number)
            + vendors (array[Vendor], required)
            + bounds (array, required)
            + transfers (array, required)


### Data Structures

##### Vendor (object)

+ tag: e_class (string, required)
+ title: VIP (string, required)
+ images: london/web/s_class.jpg (array, required)
+ earn_per_hour: 18.97 (number, required)
+ description: Mercedes-Benz S-class (string, required)
+ options (VendorOptions, required)
    + passenger: 3 (string)
    + baggage: 3 (string)
+ cancellation (object, required)
    + min_price: 7.00 (number, required)
    + value_per_minute: 0.65 (number, required)
+ weekday (object, required)
    + pickup_charge: 7.0 (number)
    + min_price: 16.0 (number)
    + value_per_minute: 0.65 (number)
    + value_per_distance_unit: 2.4 (number)
    + distance_unit: "mile" (number)
    + cancellation_fee: 7.0 (number)
    + outside_city_cancellation_fee: 7.0 (number)
    + outside_city_transfer_min_price: 60.0 (number)
    + outside_city_distance_unit_price: 2.4 (number)
    + pickup_distance_unit_price: 2.4 (number)
+ extras (array[object], required)
    + Attributes
        + type: outside_city (string)
        + distance_unit: mile (string)
        + value_per_distance_unit: 2.4 (number)
+ transfers (array[object], required)
    + Attributes
        + price: 130.0 (number)
        + free_waiting_time: 30 (number)
        + to: Gatwick&nbsp;—&nbsp;Central London (string)

##### VendorOptions (object)

+ passenger: 3 (string)
+ baggage: 3 (string)
