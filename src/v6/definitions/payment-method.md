## Base Payment Method (object)

Информация о возможном способе оплаты пользователя.

### Properties

+ id: 1d200075c544e3efe2cc1b3d (string, required) - Уникальный идентификатор способа оплаты
+ type (enum, required) - Тип данного способа оплаты
  + card (string) - банковская карта
  + invoice (string) - корпоративный счет

## Card Payment Method (Base Payment Method)

+ type: card (string, required)
+ ownership_type (enum, required) - Тип владения картой
  + personal (string) - персональная карта
  + corporate (string) - корпоративная карта
+ name: `MasterCard ****` (enum, required)
  + `Visa ****` (string) - для карт Visa
  + `MasterCard ****` (string) - для карт MasterCard
  + `AMEX ****` (string) - для карт American Express
  + `Diners ****` (string) - для карт DinersClub
  + `МИР ****` (string) - для карт МИР
+ card_brand: `mastercard` (enum, required) - Бренд карты
  + visa (string)
  + mastercard (string)
  + amex (string)
  + diners_club (string)
  + mir (string)
+ card_level: `platinum` (enum, required)
  + platinum (string)
  + signature (string)
  + infinite (string)


## Invoice Payment Method (Base Payment Method)

+ type: invoice (string, required)
+ monthly_limit (Money, required) - Ежемесячный лимит для пользователя этого корпоративного счета. Если value == 0 — пользователь может совершать заказы без ежемесячного ограничения
+ monthly_total (Money, required) - Суммарная стоимость заказов данного пользователя, оплачиваемых этим корпоративным счетом и совершенных в текущем месяце
+ name: `ООО Санкт-Тестинбург` (string, required) - Название способа оплаты — название компании, владеющей корпоративным счетом в Вили
