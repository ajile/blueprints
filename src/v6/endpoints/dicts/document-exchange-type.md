## Способы обмена документами [/dicts/document-exchange-types]

### Получение списка [GET]

Возвращает список доступных способов обмена документами между Wheely и др. компаниями, вместе с локализацией.

+ Response 200 (application/json)
    + Attributes
        + exchange_types (array[`DocumentExchangeType`], fixed)

### Data Structures

##### DocumentExchangeType (object)

+ exchange_type: diadoc (string, required) - Уникальное имя способа обмена документами на латинице. Является идентификатором записи (вместо `id`).
+ translations (array[`DocumentExchangeTypeName`], required) - Массив переводов.


##### DocumentExchangeTypeName (object)

+ locale: en (enum, required) - Код языка, в формате [ISO 639-1:2002](https://ru.wikipedia.org/wiki/ISO_639-1).
    + Members
        + ru
        + en
+ translation: Diadoc (string, required) - Название записи на языке, соотв. значению в поле `locale`.
