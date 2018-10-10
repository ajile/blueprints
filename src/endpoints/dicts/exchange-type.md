# Group Словари

## Exchange Type [/dicts/exchange-types]

### Получение «Способов обмена документами» [GET]

+ Response 200 (application/json)

    + Attributes

        + exchange_types (array[ExchangeType], fixed)

#### Data Structures

##### ExchangeType (object)

+ slug: diadoc (string, required) - Уникальное имя способа обмена документами на латинице. Является идентификатором записи (вместо `id`).
+ translations (array[ExchangeTypeName], required) - Массив переводов.


##### ExchangeTypeName (object)

+ locale: en (enum, required) - Код языка, в формате [ISO 639-1:2002](https://ru.wikipedia.org/wiki/ISO_639-1).
    + Members
        + ru
        + en
+ translation: Diadoc (string, required) - Название записи на языке, соотв. значению в поле `locale`.
