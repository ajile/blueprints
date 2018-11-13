## User Model (object)

+ id: 544e3efe2cc1b3d1d200075b (string, required) - Уникальный идентификатор пользователя
+ first_name: Иван (string, optional) - Имя пользователя
+ last_name: Иванов (string, optional) - Фамилия пользователя
+ middle_name: Иванович (string, optional) - Отчество пользователя
+ email: foo@bar.baz (string, required) - Адрес эл. почты
+ phone: +79165334030 (Phone, required) - Телефон пользователя
+ payment_methods (array[Card Payment Method, Invoice Payment Method], required) - Массив способов оплаты, доступных пользователю
+ city_name: moscow (string, required)
+ client: web (string, required)
+ dpr: 1 (string, required)
+ partner: true (boolean, optional) - Является ли пользователь партнером
+ updated_at: `2018-11-12T18:06:17Z` (string)
+ invite (Invite Model, required) - Информация о личном промокоде пользователя, который используется в реферальной системе Вили
+ credits (array[Money], required) - Массив бонусных счетов пользователя в разных валютах. Если value какого-либо счета отрицательный, значит у пользователя есть неоплаченный долг в размере ABS(value)
+ bonuses (array)
+ cards (array)
+ city_id: 503393f9d64e13dc67a82fda (string)
+ company (object)
  + id: `5178812d2cc1b35dfa000001` (string)
  + name: `ООО "ВИЛИ РАЗРАБОТКА"` (string)
  + admin: true (boolean)
+ created_at: `2014-10-27T12:47:58Z`
+ roles: `admin`, `controller`, `pr_manager` (array[string])
+ sip (object)
  + _id: "5ad9e275d515db0005000034" (string)
  + oktell_login: "vladimirmilkov150121153913" (string)
  + oktell_password: "qwerty123" (string)
  + password: "qwerty123" (string)
  + username: "vladimirmilkovdev150121154417" (string)
