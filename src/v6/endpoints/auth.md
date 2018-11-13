## Токен [/auth/oauth/token]

### Получение токена [POST]

Эндпоинт принимает креденшелы пользователя, создает и возвращает авторизационный токен, вместе с сопутствующими данными. В случае аутентификации по телефону, эндпоинт возвращает только токен, остальные данные (такие как `пользователь` и `водитель`) могут быть получены отдельно.

+ Request Получение токена по эл. почте (application/json)

  + Body

    + Attributes (Password Payload)

+ Response 200 (application/json)
    + Attributes
        + driver ([Driver Model](../models/driver.md), optional)
        + token ([Token Model](../models/token.md), required)
        + user ([User Model](../models/user.md), required)

+ Request Получение токена по телефону (application/json)

  + Body

    + Attributes (Phone Payload)

+ Response 200 (application/json)
    + Attributes
        + token ([Token Model](../models/token.md), required)
          + activation_needed: true

+ Response 401 (application/json)
    + Attributes
        + errors (object, required)
          + invalid_app: `Bad app` (array[string], required) - человекопонятная локализованная ошибки

+ Response 401 (application/json)
    + Attributes
        + errors (object, required)
          + invalid_user: `Bad user` (array[string], required) - человекопонятная локализованная ошибки


### Активация токена [PUT /auth/oauth/activate]

Эндпоинт активирует авторизационный токен пользователя.

+ Request (application/json)

  Посылаем пин-код и токен, который мы хотим активировать. После успешной активации поле токена `activation_needed` должно стать `true`.

  + Headers
      :[partials/headers/accept-language.md](partials/headers/accept-language.md)

  + Body
    + Attributes
      + token: `7hbe5F3DvlRXSN9Rs8BG` (string, required) - Токен, который нужно активировать
      + pin: 1234 (number, required) - Код верификации, высланный сервером пользователю

+ Response 200 (application/json)
    + Attributes
        + user ([User Model](../models/user.md), required)

+ Response 401 (application/json)

    Неправильный пин

    + Attributes
        + errors (object, required)
          + invalid_pin: `The code is incorrect. Please check it` (array[string], required) - человекопонятная локализованная ошибки

+ Response 401 (application/json)

    Неправильный token

    + Attributes
        + errors (object, required)
          + invalid_token: `The token is incorrect` (array[string], required) - человекопонятная локализованная ошибки


### Продление токена [POST /auth/oauth/refresh]

Эндпоинт продлевает срок жизни переданного JWT. Ручку следует использовать в момент протухания токена.

+ Request (application/json)

  Посылаем токен, который мы хотим продлить.

  + Headers
      :[partials/headers/accept-language.md](partials/headers/accept-language.md)

  + Body
    + Attributes
      + app_id: 55e08577e779891040000001 (string, required) - Идентификатор приложения для которого требуется создать авторизационный токен
      + app_secret: 55e08577e779891040000001 (string, required)
      + refresh_token: `7hbe5F3DvlRXSN9Rs8BG` (string, required) - Специальный токен для продления основого токена

+ Response 200 (application/json)
    + Attributes
        + token ([Token Model](../models/token.md), required) - Обновленный Access Token

+ Response 401 (application/json)
    + Attributes
        + errors (object, required)
          + invalid_refresh_token: `The refresh token is incorrect` (array[string], required) - человекопонятная локализованная ошибки


## Пин-код [/auto_call/{phone}]

+ Parameters
  + phone: 79160000000 (Phone, required) - Номер телефона на которые требуется позвонить и продиктовать пин.

### Запрос звонка с диктовкой [POST]

Запрос звонка автоответчика с диктовкой проверочного кода

+ Headers
    :[partials/headers/accept-language.md](partials/headers/accept-language.md)

+ Response 200 (application/json)
    + Attributes (object)

+ Response 404 (application/json)
    + Attributes
        + errors (object, required)
          + entity_not_found: `Not found` (array[string], required) - Верификационный код для введенного номера не запрашивался


### Data structure

#### Base Payload (object)
+ app_id: 55e08577e779891040000001 (string, required) - Идентификатор приложения для которого требуется создать авторизационный токен


#### Password Payload (Base Payload)
+ email: foo@wheely.com (string, requred) - Эл. почта пользователя
+ password: qwerty123 (string, requred) - Пароль


#### Phone Payload (Base Payload)
+ phone: 79160000000 (Phone, requred) - Номер телефона пользователя
