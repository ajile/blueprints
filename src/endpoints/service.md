## Service [/services/{id}]

+ Parameters

    + id: 5b83bd33c06e3100060000c8 (string) - ID города который требуется получить.

### Получение записи [GET]

+ Response 200 (application/json)

    + Attributes

        + data
            + id: 5b83bd33c06e3100060000c8 (string, required) - Уникальный монговский идентификатор
            + type: services (string, required)
            + attributes (Service Model)
            + relationships


+ Response 400 (application/json)

    + Attributes

        + errors
            + code: 777 (number, required) - Внутренний код ошибки.
            + status: 400 (string)
            + source (object, required)
                + pointer: /data (string)
            + title: pay failed (string) - Короткий, человеко-читаемый текст ошибки (может быть локализован).
