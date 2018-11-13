## Driver Model (object)

+ id: 544e3efe2cc1b3d1d200075b (string, required) - Уникальный идентификатор пользователя
+ first_name: Иван (string, optional) - Имя пользователя
+ last_name: Иванов (string, optional) - Фамилия пользователя
+ birthday: "2000-12-14" (string)
+ check_fake_gps_apps: false (boolean)
+ city_id: 503393f9d64e13dc67a82fda (string)
+ demand_heatmap_available: false (boolean)
+ email: foo@bar.baz (string, required) - Адрес эл. почты
+ invite (Invite Model, required) - Информация о личном промокоде пользователя, который используется в реферальной системе Вили
+ mandatory_dropoff: true (boolean)
+ phone: +79165334030 (Phone, required) - Телефон пользователя
+ rating: 5
+ score: 0
+ services (array)
+ support_phone: `+442036088304` (string) - номер телефона саппорта
+ vehicles_hidden: false (boolean) - может ли водитель самостоятельно выбирать машину
