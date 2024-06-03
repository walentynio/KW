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
{ "commandInput": { "canceled": false, "e_receipt_type": 4 }, "commandType": 26, "print": true, { "commandType": 30, "commandInput": { "1": { "commandType": 16 }, "2": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "AB1", "price": 77, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "AB1", "price": 777, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "4": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "AB13", "price": 772, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "5": { "commandInput": { "currency_converter": 2.54, "currency": "EUR", "is_from_registration_currency_conversion": false, "is_informative_conversion": true, "name": "paymentName", "payment_type": 1, "value": 222222.22, "payment_without_terminal": true }, "commandType": 24 }, "6": { "commandType": 26 } } } "returnPDF": false, "returnQR": true }
```
