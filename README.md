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
{ "commandType": 30, "commandInput": { "1": {"commandType": 16}, "2": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt1", "price": 100, "ptu": "A", "unit": "", "discount": { "name": "Narzut", "type": 1, "unit": 0, "value": 10 } }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandInput": { "currency_converter": 2.54, "currency": "EUR", "is_from_registration_currency_conversion": false, "is_informative_conversion": true, "name": "paymentName", "payment_type": 1, "value": 110, "payment_without_terminal": true }, "commandType": 24 }, "4": {"commandType": 26} } }
```

//paragon jednopozycyjny z opustem do pozycji i z resztą,

```
{ "commandType": 30, "commandInput": { "1": {"commandType": 16}, "2": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt1", "price": 100, "ptu": "A", "unit": "", "discount": { "name": "Opust", "type": 0, "unit": 0, "value": 10 } }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandInput": { "currency_converter": 2.54, "currency": "EUR", "is_from_registration_currency_conversion": false, "is_informative_conversion": true, "name": "paymentName", "payment_type": 1, "value": 90, "payment_without_terminal": true }, "commandType": 24 }, "4": {"commandType": 26} } }
```
//paragon dwupozycyjny z narzutem do podsumy, 

```
{ "commandType": 30, "commandInput": { "1": {"commandType": 16}, "2": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt1", "price": 50, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt2", "price": 70, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "4": { "commandInput": { "name": "Narzut", "discount_type": 1, "discount_unit": 0, "value": 10 }, "commandType": 25 }, "5": { "commandInput": { "currency_converter": 2.54, "currency": "EUR", "is_from_registration_currency_conversion": false, "is_informative_conversion": true, "name": "paymentName", "payment_type": 1, "value": 132, "payment_without_terminal": true }, "commandType": 24 }, "6": {"commandType": 26} } }
```

//paragon dwupozycyjny z opustem od podsumy, 

```
{ "commandType": 30, "commandInput": { "1": {"commandType": 16}, "2": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt1", "price": 50, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt2", "price": 70, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "4": { "commandInput": { "name": "Opust", "discount_type": 0, "discount_unit": 0, "value": 10 }, "commandType": 25 }, "5": { "commandInput": { "currency_converter": 2.54, "currency": "EUR", "is_from_registration_currency_conversion": false, "is_informative_conversion": true, "name": "paymentName", "payment_type": 1, "value": 108, "payment_without_terminal": true }, "commandType": 24 }, "6": {"commandType": 26} } }
```
//paragon z kombinacją narzutów i opustów, do pozycji i do podsumy,

```
{ "commandType": 30, "commandInput": { "1": {"commandType": 16}, "2": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt1", "price": 50, "ptu": "A", "unit": "", "discount": { "name": "Opust do pozycji", "type": 0, "unit": 0, "value": 10 } }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt2", "price": 70, "ptu": "A", "unit": "", "discount": { "name": "Narzut do pozycji", "type": 1, "unit": 0, "value": 10 } }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "4": { "commandInput": { "name": "Opust do podsumy", "discount_type": 0, "discount_unit": 0, "value": 5 }, "commandType": 25 }, "5": { "commandInput": { "name": "Narzut do podsumy", "discount_type": 1, "discount_unit": 0, "value": 3 }, "commandType": 25 }, "6": { "commandInput": { "currency_converter": 2.54, "currency": "EUR", "is_from_registration_currency_conversion": false, "is_informative_conversion": true, "name": "paymentName", "payment_type": 1, "value": 126.18, "payment_without_terminal": true }, "commandType": 24 }, "7": {"commandType": 26} } }
```

//paragon dwupozycyjny z narzutem do drugiej pozycji i storno tej pozycji,

```
{ "commandType": 30, "commandInput": { "1": {"commandType": 16}, "2": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt1", "price": 50, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt2", "price": 70, "ptu": "A", "unit": "", "discount": { "name": "Narzut do pozycji", "type": 1, "unit": 0, "value": 10 } }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "4": { "commandInput": { "item": { "advanceRemain": 0, "canceled": true, "count": 1, "name": "Produkt2", "price": 70, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "5": { "commandInput": { "currency_converter": 2.54, "currency": "EUR", "is_from_registration_currency_conversion": false, "is_informative_conversion": true, "name": "paymentName", "payment_type": 1, "value": 50, "payment_without_terminal": true }, "commandType": 24 }, "6": {"commandType": 26} } }
```

///paragon dwupozycyjny z narzutem do drugiej pozycji i storno tej pozycji(Attemp 2)

```
{ "commandType": 30, "commandInput": { "1": {"commandType": 16}, "2": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt1", "price": 50, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt2", "price": 70, "ptu": "A", "unit": "", "discount": { "name": "Narzut do pozycji", "type": 1, "unit": 0, "value": 10 } }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "4": { "commandInput": { "item": { "advanceRemain": 0, "canceled": true, "count": 1, "name": "Produkt2", "price": 70, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "5": { "commandInput": { "currency_converter": 2.54, "currency": "EUR", "is_from_registration_currency_conversion": false, "is_informative_conversion": true, "name": "paymentName", "payment_type": 1, "value": 50, "payment_without_terminal": true }, "commandType": 24 }, "6": { "commandInput": { "canceled": false }, "commandType": 26, "print": true, "returnPDF": false, "returnQR": true } } }
```
//paragon dwupozycyjny z opustem do drugiej pozycji i storno tej pozycji, ten sammy problem

```
{ "commandType": 30, "commandInput": { "1": {"commandType": 16}, "2": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt1", "price": 50, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt2", "price": 70, "ptu": "A", "unit": "", "discount": { "name": "Opust do pozycji", "type": 0, "unit": 0, "value": 10 } }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "4": { "commandInput": { "item": { "advanceRemain": 0, "canceled": true, "count": 1, "name": "Produkt2", "price": 70, "ptu": "A", "unit": "", "discount": { "name": "Opust do pozycji", "type": 0, "unit": 0, "value": 10 } }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "5": { "commandInput": { "currency_converter": 2.54, "currency": "EUR", "is_from_registration_currency_conversion": false, "is_informative_conversion": true, "name": "paymentName", "payment_type": 1, "value": 50, "payment_without_terminal": true }, "commandType": 24 }, "6": { "commandInput": { "canceled": false }, "commandType": 26, "print": true, "returnPDF": false, "returnQR": true } } }
```
//paragon dwupozycyjny z opustem do podsumy i storno pierwszej pozycji,

```
{ "commandType": 30, "commandInput": { "1": {"commandType": 16}, "2": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt1", "price": 50, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt2", "price": 70, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "4": { "commandInput": { "item": { "advanceRemain": 0, "canceled": true, "count": 1, "name": "Produkt1", "price": 50, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "5": { "commandInput": { "name": "Opust do podsumy", "discount_type": 0, "discount_unit": 0, "value": 10 }, "commandType": 25 }, "6": { "commandInput": { "currency_converter": 2.54, "currency": "EUR", "is_from_registration_currency_conversion": false, "is_informative_conversion": true, "name": "paymentName", "payment_type": 1, "value": 63, "payment_without_terminal": true }, "commandType": 24 }, "7": { "commandInput": { "canceled": false }, "commandType": 26, "print": true, "returnPDF": false, "returnQR": true } } }
```
