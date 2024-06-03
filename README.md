# KW

```
{"commandType":1,"commandInput":{"sales_system_name":"salesSystemNameTest","sales_system_version":"salesSystemVersionTest"}}
```

//zaprogramować wszystkie stawki PTU(jezeli stawki PTU są ustawione to zmian nie będzie)

```
{ "commandInput": { "A": { "type": 0, "value": 23 }, "B": { "type": 0, "value": 8 }, "C": { "type": 0, "value": 5 }, "D": { "type": 0, "value": 0 }, "E": { "type": 1, "value": 0 }, "F": { "type": 2, "value": 0 }, "G": { "type": 2, "value": 0 } }, "commandType": 3 }
```

//paragon z towarami we wszystkich stawkach PTU,

```
{"commandType":30,"commandInput":{"1":{"commandType":16},"2":{"commandInput":{"item":{"advanceRemain":0,"canceled":false,"count":1,"name":"AB1","price":77,"ptu":"A","unit":""},"type":1},"commandType":22,"print":true,"returnModel":false,"returnPDF":false},"3":{"commandInput":{"item":{"advanceRemain":0,"canceled":false,"count":1,"name":"AB1","price":777,"ptu":"A","unit":""},"type":1},"commandType":22,"print":true,"returnModel":false,"returnPDF":false},"4":{"commandInput":{"item":{"advanceRemain":0,"canceled":false,"count":1,"name":"AB13","price":772,"ptu":"A","unit":""},"type":1},"commandType":22,"print":true,"returnModel":false,"returnPDF":false},"5":{"commandInput":{"currency_converter":2.54,"currency":"EUR","is_from_registration_currency_conversion":false,"is_informative_conversion":true,"name":"paymentName","payment_type":1,"value":222222.22,"payment_without_terminal":true},"commandType":24},"6":{"commandType":26}}}
```
//zaprogramować cztery standardowe stawki PTU,

```
{ "commandType": 30, "commandInput": { "1": { "commandType": 16 }, "2": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "AB1", "price": 77, "ptu": "C", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "AB1", "price": 777, "ptu": "B", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "4": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "AB13", "price": 772, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "5": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 3, "name": "AB22", "price": 22, "ptu": "D", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "6": { "commandInput": { "currency_converter": 2.54, "currency": "EUR", "is_from_registration_currency_conversion": false, "is_informative_conversion": true, "name": "paymentName", "payment_type": 1, "value": 222222.22, "payment_without_terminal": true }, "commandType": 24 }, "7": { "commandType": 26 } } }
```

//paragon z towarami w standardowych stawkach PTU, nie zrobiłem

```
{ "commandInput": { "A": { "type": 0, "value": 23 }, "B": { "type": 0, "value": 8 }, "C": { "type": 0, "value": 5 }, "D": { "type": 0, "value": 0 }, "E": { "type": 0, "value": 0 }, "F": { "type": 0, "value": 0 }, "G": { "type": 0, "value": 0 } }, "commandType": 3 }
```
//paragon dwupozycyjny ze storno pierwszej pozycji,

```
{ "commandType": 30, "commandInput": { "1": { "commandType": 16 }, "2": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Item 1", "price": 100, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandInput": { "item": { "advanceRemain": 0, "canceled": true, "count": 1, "name": "Item 1", "price": -100, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "4": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Item 2", "price": 200, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "5": { "commandInput": { "currency_converter": 2.54, "currency": "EUR", "is_from_registration_currency_conversion": false, "is_informative_conversion": true, "name": "paymentName", "payment_type": 1, "value": 200, "payment_without_terminal": true }, "commandType": 24 }, "6": { "commandType": 26 } } }
```

//paragon jednopozycyjny z narzutem do pozycji i z resztą,

```
{ "commandType": 30, "commandInput": { "1": { "commandType": 16 }, "2": { "commandInput": { "item": { "advanceRemain": 0.0, "canceled": false, "count": 1.0, "name": "Item 1", "price": 100.0, "ptu": "A", "unit": "", "discount": { "name": "NARZUT_10%", "type": 1, "unit": 0, "value": 10.0 } }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandInput": { "currency_converter": 2.54, "currency": "EUR", "is_from_registration_currency_conversion": false, "is_informative_conversion": true, "name": "paymentName", "payment_type": 1, "value": 150.0, "payment_without_terminal": true, "change": 40.0 // Сдача }, "commandType": 24 }, "4": { "commandType": 26 } } }
```

//paragon jednopozycyjny z opustem do pozycji i z resztą,

```
{ "commandType": 30, "commandInput": { "1": { "commandType": 16 }, "2": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Item 1", "price": 100, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandInput": { "discount": { "amount": 20, "type": "percentage" } }, "commandType": 23, "print": true, "returnModel": false, "returnPDF": false }, "4": { "commandInput": { "currency_converter": 2.54, "currency": "EUR", "is_from_registration_currency_conversion": false, "is_informative_conversion": true, "name": "paymentName", "payment_type": 1, "value": 150, "payment_without_terminal": true, "change": 70 }, "commandType": 24 }, "5": { "commandType": 26 } } }
```
