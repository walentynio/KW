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
{ "commandInput": { "canceled": false, "e_receipt_type": 4 }, "commandType": 26, "print": true, "subCommands": { "1": { "commandType": 30, "commandInput": { "cashier_name": "Cashier1", "cash_register": "Register1", "paragon_id": "12345" } }, "2": { "commandType": 16 }, "3": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Item A", "price": 100, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "4": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Item B", "price": 200, "ptu": "B", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "5": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Item C", "price": 300, "ptu": "C", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "6": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Item D", "price": 400, "ptu": "D", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "7": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Item F", "price": 500, "ptu": "F", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "8": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Item G", "price": 600, "ptu": "G", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "9": { "commandInput": { "currency_converter": 2.54, "currency": "EUR", "is_from_registration_currency_conversion": false, "is_informative_conversion": true, "name": "paymentName", "payment_type": 1, "value": 2222.22, "payment_without_terminal": true }, "commandType": 24 }, "10": { "commandType": 26 } }, "returnPDF": false, "returnQR": true }
```
//

```
{ "commandType": 30, "commandInput": { "1": { "commandType": 16 }, "2": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Item 1", "price": 100, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandInput": { "item": { "advanceRemain": 0, "canceled": true, "count": 1, "name": "Item 1", "price": -100, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "4": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Item 2", "price": 200, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "5": { "commandInput": { "currency_converter": 2.54, "currency": "EUR", "is_from_registration_currency_conversion": false, "is_informative_conversion": true, "name": "paymentName", "payment_type": 1, "value": 200, "payment_without_terminal": true }, "commandType": 24 }, "6": { "commandType": 26 } } }
```
