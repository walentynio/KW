## Treść
1. [Testy - przykladowe 25 paragonów](#Testy-przykladowe25paragonów)
2. [Sprzedaż RFD nr 1](#RFDnr1)
3. [Sprzedaż RFD nr 2](#RFDnr2)
   
## Testy - przykladowe 25 paragonów

```
{"commandType":1,"commandInput":{"sales_system_name":"salesSystemNameTest","sales_system_version":"salesSystemVersionTest"}}
```

1//zaprogramować wszystkie stawki PTU(jezeli stawki PTU są ustawione to zmian nie będzie)

```
{ "commandInput": { "A": { "type": 0, "value": 23 }, "B": { "type": 0, "value": 8 }, "C": { "type": 0, "value": 5 }, "D": { "type": 0, "value": 0 }, "E": { "type": 1, "value": 0 }, "F": { "type": 2, "value": 0 }, "G": { "type": 2, "value": 0 } }, "commandType": 3 }
```

2//paragon z towarami we wszystkich stawkach PTU,

```
{"commandType":30,"commandInput":{"1":{"commandType":16},"2":{"commandInput":{"item":{"advanceRemain":0,"canceled":false,"count":1,"name":"AB1","price":77,"ptu":"A","unit":""},"type":1},"commandType":22,"print":true,"returnModel":false,"returnPDF":false},"3":{"commandInput":{"item":{"advanceRemain":0,"canceled":false,"count":1,"name":"AB1","price":777,"ptu":"A","unit":""},"type":1},"commandType":22,"print":true,"returnModel":false,"returnPDF":false},"4":{"commandInput":{"item":{"advanceRemain":0,"canceled":false,"count":1,"name":"AB13","price":772,"ptu":"A","unit":""},"type":1},"commandType":22,"print":true,"returnModel":false,"returnPDF":false},"5":{"commandInput":{"currency_converter":2.54,"currency":"EUR","is_from_registration_currency_conversion":false,"is_informative_conversion":true,"name":"paymentName","payment_type":1,"value":222222.22,"payment_without_terminal":true},"commandType":24},"6":{"commandType":26}}}
```
3//zaprogramować cztery standardowe stawki PTU,

```
{ "commandType": 32, "commandInput": { "settings": [ { "name": "ptu1", "value": "A", "rate": 23.00 }, { "name": "ptu2", "value": "B", "rate": 8.00 }, { "name": "ptu3", "value": "C", "rate": 5.00 }, { "name": "ptu4", "value": "D", "rate": 0.00 } ] } }
```

4//paragon z towarami w standardowych stawkach PTU,

```
{ "commandType": 16 }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "ProduktA", "price": 50, "ptu": "A", "unit": "szt" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "ProduktB", "price": 60, "ptu": "B", "unit": "szt" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "ProduktC", "price": 70, "ptu": "C", "unit": "szt" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "ProduktD", "price": 80, "ptu": "D", "unit": "szt" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 24, "commandInput": { "name": "paymentName", "payment_type": 1, "value": 260, "payment_without_terminal": true } }
```
```
{ "commandType": 26, "commandInput": { "canceled": false }, "print": true, "returnPDF": false, "returnQR": true }
```
alternatywa 
```
{ "commandType": 30, "commandInput": { "1": { "commandType": 16 }, "2": { "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "ProduktA", "price": 50, "ptu": "A", "unit": "szt" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "ProduktB", "price": 60, "ptu": "B", "unit": "szt" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }, "4": { "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "ProduktC", "price": 70, "ptu": "C", "unit": "szt" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }, "5": { "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "ProduktD", "price": 80, "ptu": "D", "unit": "szt" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }, "6": { "commandType": 24, "commandInput": { "name": "paymentName", "payment_type": 1, "value": 260, "payment_without_terminal": true } }, "7": { "commandType": 26, "commandInput": { "canceled": false }, "print": true, "returnPDF": false, "returnQR": true } } }
```

//paragon dwupozycyjny ze storno pierwszej pozycji, (u mnie liczy nie poprawnie)

```
{ "commandType": 16 }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt1", "price": 50, "ptu": "A", "unit": "szt" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt1", "price": 50, "ptu": "A", "unit": "szt" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": true, "count": 1, "name": "Produkt1", "price": 50, "ptu": "A", "unit": "szt" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 24, "commandInput": { "name": "paymentName", "payment_type": 1, "value": 50, "payment_without_terminal": true } }
```
```
{ "commandType": 26, "commandInput": { "canceled": false }, "print": true, "returnPDF": false, "returnQR": true }
```
alternatywa
```
{ "commandType": 30, "commandInput": { "1": {"commandType": 16}, "2": { "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt1", "price": 50, "ptu": "A", "unit": "szt" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt2", "price": 150, "ptu": "B", "unit": "szt" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }, "4": { "commandType": 24, "commandInput": { "name": "paymentName", "payment_type": 1, "value": 200, "payment_without_terminal": true } }, "5": { "commandType": 26, "commandInput": {"canceled": false}, "print": true, "returnPDF": false, "returnQR": true } } }
```


6//paragon jednopozycyjny z narzutem do pozycji i z resztą,

```
{ "commandType": 30, "commandInput": { "1": {"commandType": 16}, "2": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt1", "price": 100, "ptu": "A", "unit": "", "discount": { "name": "Narzut", "type": 1, "unit": 0, "value": 10 } }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandInput": { "currency_converter": 2.54, "currency": "EUR", "is_from_registration_currency_conversion": false, "is_informative_conversion": true, "name": "paymentName", "payment_type": 1, "value": 110, "payment_without_terminal": true }, "commandType": 24 }, "4": {"commandType": 26} } }
```

7//paragon jednopozycyjny z opustem do pozycji i z resztą,

```
{ "commandType": 30, "commandInput": { "1": {"commandType": 16}, "2": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt1", "price": 100, "ptu": "A", "unit": "", "discount": { "name": "Opust", "type": 0, "unit": 0, "value": 10 } }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandInput": { "currency_converter": 2.54, "currency": "EUR", "is_from_registration_currency_conversion": false, "is_informative_conversion": true, "name": "paymentName", "payment_type": 1, "value": 90, "payment_without_terminal": true }, "commandType": 24 }, "4": {"commandType": 26} } }
```
8//paragon dwupozycyjny z narzutem do podsumy, 

```
{ "commandType": 30, "commandInput": { "1": {"commandType": 16}, "2": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt1", "price": 50, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt2", "price": 70, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "4": { "commandInput": { "name": "Narzut", "discount_type": 1, "discount_unit": 0, "value": 10 }, "commandType": 25 }, "5": { "commandInput": { "currency_converter": 2.54, "currency": "EUR", "is_from_registration_currency_conversion": false, "is_informative_conversion": true, "name": "paymentName", "payment_type": 1, "value": 132, "payment_without_terminal": true }, "commandType": 24 }, "6": {"commandType": 26} } }
```

9//paragon dwupozycyjny z opustem od podsumy, 

```
{ "commandType": 30, "commandInput": { "1": {"commandType": 16}, "2": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt1", "price": 50, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt2", "price": 70, "ptu": "A", "unit": "" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "4": { "commandInput": { "name": "Opust", "discount_type": 0, "discount_unit": 0, "value": 10 }, "commandType": 25 }, "5": { "commandInput": { "currency_converter": 2.54, "currency": "EUR", "is_from_registration_currency_conversion": false, "is_informative_conversion": true, "name": "paymentName", "payment_type": 1, "value": 108, "payment_without_terminal": true }, "commandType": 24 }, "6": {"commandType": 26} } }
```
//paragon z kombinacją narzutów i opustów, do pozycji i do podsumy,

```
{ "commandType": 16 }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt1", "price": 50, "ptu": "A", "unit": "", "discount": { "name": "Narzut do pozycji", "type": 1, "unit": 1, "value": 5 } }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt2", "price": 70, "ptu": "A", "unit": "", "discount": { "name": "Opust do pozycji", "type": 0, "unit": 1, "value": 7 } }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 24, "commandInput": { "name": "paymentName", "payment_type": 1, "value": 108, "payment_without_terminal": true } }
```
```
{ "commandType": 26, "commandInput": { "canceled": false }, "print": true, "returnPDF": false, "returnQR": true }
```

11//paragon dwupozycyjny z narzutem do drugiej pozycji i storno tej pozycji (wprowadzać komenda po komendzie)

```
  {"commandType": 16}
```

``` 
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt1", "price": 50, "ptu": "A", "unit": "" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
``` 
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt2", "price": 70, "ptu": "A", "unit": "", "discount": { "name": "Narzut do pozycji", "type": 1, "unit": 0, "value": 10 } }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
 ```

``` 
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": true, "count": 1, "name": "Produkt2", "price": 70, "ptu": "A", "unit": "", "discount": { "name": "Narzut do pozycji", "type": 1, "unit": 0, "value": 10 } }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 24, "commandInput": { "name": "paymentName", "payment_type": 1, "value": 50, "payment_without_terminal": true } }
```
```
{ "commandType": 26, "commandInput": { "canceled": false }, "print": true, "returnPDF": false, "returnQR": true }
```


12//paragon dwupozycyjny z opustem do drugiej pozycji i storno tej pozycji (wprowadzać komenda po komendzie)

```
{ "commandType": 16 }
```

```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt1", "price": 50, "ptu": "A", "unit": "" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```

```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt2", "price": 70, "ptu": "A", "unit": "", "discount": { "name": "Opust do pozycji", "type": 0, "unit": 1, "value": 7 } }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": true, "count": 1, "name": "Produkt2", "price": 70, "ptu": "A", "unit": "", "discount": { "name": "Opust do pozycji", "type": 0, "unit": 1, "value": 7 } }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 24, "commandInput": { "name": "paymentName", "payment_type": 1, "value": 50, "payment_without_terminal": true } }
```
```
{ "commandType": 26, "commandInput": { "canceled": false }, "print": true, "returnPDF": false, "returnQR": true }
```
```
{ "commandType": 26, "commandInput": { "canceled": false }, "print": true, "returnPDF": false, "returnQR": true }
```
13//dwupozycyjny z narzutem do podsumy i storno pierwszej pozycj (wprowadzać komenda po komendzie)

```
{ "commandType": 16 }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt1", "price": 50, "ptu": "A", "unit": "" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt2", "price": 70, "ptu": "A", "unit": "" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 25, "commandInput": { "name": "Narzut do podsumy", "discount_type": 1, "discount_unit": 1, "value": 10 } }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": true, "count": 1, "name": "Produkt1", "price": 50, "ptu": "A", "unit": "" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 24, "commandInput": { "name": "paymentName", "payment_type": 1, "value": 80, "payment_without_terminal": true } }
```
```
{ "commandType": 26, "commandInput": { "canceled": false }, "print": true, "returnPDF": false, "returnQR": true }
```


14//paragon dwupozycyjny z opustem do podsumy i storno pierwszej pozycji (wprowadzać komenda po komendzie)

```
{ "commandType": 16 }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt1", "price": 50, "ptu": "A", "unit": "" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt2", "price": 70, "ptu": "A", "unit": "" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 25, "commandInput": { "name": "Opust do podsumy", "discount_type": 0, "discount_unit": 1, "value": 10 } }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": true, "count": 1, "name": "Produkt1", "price": 50, "ptu": "A", "unit": "" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 24, "commandInput": { "name": "paymentName", "payment_type": 1, "value": 60, "payment_without_terminal": true } }
```
```
{ "commandType": 26, "commandInput": { "canceled": false }, "print": true, "returnPDF": false, "returnQR": true }
```



15//paragon z wydaniem opakowań zwrotnych,

```
{ "commandType": 30, "commandInput": { "1": {"commandType": 16}, "2": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 2, "name": "Opakowanie zwrotne", "price": 10, "ptu": "A", "unit": "szt" }, "type": 1 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandInput": { "currency_converter": 2.54, "currency": "EUR", "is_from_registration_currency_conversion": false, "is_informative_conversion": true, "name": "paymentName", "payment_type": 1, "value": 20, "payment_without_terminal": true }, "commandType": 24 }, "4": { "commandInput": { "canceled": false }, "commandType": 26, "print": true, "returnPDF": false, "returnQR": true } } }
```
//paragon ze zwrotem opakowań zwrotnych,

```
{ "commandType": 30, "commandInput": { "1": {"commandType": 16}, "2": { "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": -2, "name": "Opakowanie zwrotne", "price": 10, "ptu": "A", "unit": "szt" }, "type": 2 }, "commandType": 22, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandInput": { "currency_converter": 2.54, "currency": "EUR", "is_from_registration_currency_conversion": false, "is_informative_conversion": true, "name": "paymentName", "payment_type": 1, "value": -20, "payment_without_terminal": true }, "commandType": 24 }, "4": { "commandInput": {"canceled": false}, "commandType": 26, "print": true, "returnPDF": false, "returnQR": true } } }
```
16//paragon „zerowy” (towar i storno towaru, wydanie i zwrot opakowań
zwrotnych),


```
  {"commandType": 16}
```

```
  {
    "commandType": 22,
    "commandInput": {
      "item": {
        "advanceRemain": 0,
        "canceled": false,
        "count": 1,
        "name": "Produkt1",
        "price": 100,
        "ptu": "A",
        "unit": "szt"
      },
      "type": 1
    },
    "print": true,
    "returnModel": false,
    "returnPDF": false
  }
```

```
{
    "commandType": 22,
    "commandInput": {
      "item": {
        "advanceRemain": 0,
        "canceled": true,
        "count": 1,
        "name": "Produkt1",
        "price": 100,
        "ptu": "A",
        "unit": "szt"
      },
      "type": 1
    },
    "print": true,
    "returnModel": false,
    "returnPDF": false
  }
```

```
{
    "commandType": 22,
    "commandInput": {
      "item": {
        "advanceRemain": 0,
        "canceled": false,
        "count": 2,
        "name": "Opakowanie zwrotne",
        "price": 10,
        "ptu": "A",
        "unit": "szt"
      },
      "type": 1
    },
    "print": true,
    "returnModel": false,
    "returnPDF": false
  }
```
```
{
    "commandType": 22,
    "commandInput": {
      "item": {
        "advanceRemain": 0,
        "canceled": true,
        "count": 2,
        "name": "Opakowanie zwrotne",
        "price": 10,
        "ptu": "A",
        "unit": "szt"
      },
      "type": 1
    },
    "print": true,
    "returnModel": false,
    "returnPDF": false
  }
```

```
{
    "commandType": 24,
    "commandInput": {
      "currency_converter": 2.54,
      "currency": "EUR",
      "is_from_registration_currency_conversion": false,
      "is_informative_conversion": true,
      "name": "paymentName",
      "payment_type": 1,
      "value": 0,
      "payment_without_terminal": true
    }
  }
```
```
  {
    "commandType": 26,
    "commandInput": {"canceled": false},
    "print": true,
    "returnPDF": false,
    "returnQR": true
  }
```

17//raport dobowy (nie do analizy, chodzi o wyzerowanie totalizerów dobowych),

```
{ "commandType": 11, "commandInput": { "print": true, "returnPDF": false, "sales_system_name": "Nazwa programu POS", "sales_system_version": "Wersja programu POS" } }
```

18//paragon z maksymalną dopuszczalną wartością jednej pozycji sprzedaży, 

```
{ "commandType": 30, "commandInput": { "1": {"commandType": 16}, "2": { "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "ProduktMaxValue", "price": 999999.99, "ptu": "A", "unit": "szt" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandType": 24, "commandInput": { "name": "paymentName", "payment_type": 1, "value": 999999.99, "payment_without_terminal": true } }, "4": { "commandType": 26, "commandInput": { "canceled": false }, "print": true, "returnPDF": false, "returnQR": true } } }
```

19//raport dobowy

```
{ "commandType": 11, "commandInput": { "print": true, "returnPDF": false, "sales_system_name": "Nazwa programu POS", "sales_system_version": "Wersja programu POS" } }
```

20//pojedynczy paragon z maksymalną dopuszczalną sumą sprzedaży dla jednej stawki PTU,

```
{ "commandType": 30, "commandInput": { "1": {"commandType": 16}, "2": { "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "ProduktMaxSum", "price": 999999.99, "ptu": "A", "unit": "szt" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandType": 24, "commandInput": { "name": "paymentName", "payment_type": 1, "value": 999999.99, "payment_without_terminal": true } }, "4": { "commandType": 26, "commandInput": { "canceled": false }, "print": true, "returnPDF": false, "returnQR": true } } }
```
21//raport dobowy

```
{ "commandType": 11, "commandInput": { "print": true, "returnPDF": false, "sales_system_name": "Nazwa programu POS", "sales_system_version": "Wersja programu POS" } }
```

22//paragon (lub kilka paragonów) z maksymalną dopuszczalną sumą sprzedaży dobowej dla jednej stawki PTU (wykonać, jeżeli suma sprzedaży dobowej jest wyższa od sumy sprzedaży dla jednego paragonu),

```
{ "commandType": 30, "commandInput": { "1": {"commandType": 16}, "2": { "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "ProduktMaxValue", "price": 999999.99, "ptu": "A", "unit": "szt" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandType": 24, "commandInput": { "name": "paymentName", "payment_type": 1, "value": 999999.99, "payment_without_terminal": true } }, "4": { "commandType": 26, "commandInput": { "canceled": false }, "print": true, "returnPDF": false, "returnQR": true } } }
```

23//raport dobowy 
```
{ "commandType": 11, "commandInput": { "print": true, "returnPDF": false, "sales_system_name": "Nazwa programu POS", "sales_system_version": "Wersja programu POS" } }
```

24//zestaw paragonów anulowanych odpowiadający paragonom i raportom dobowym powyżej – wytworzonych poprzez anulowanie paragonu zamiast jego zakończenia (pierwszy paragon anulowany należy wydrukować w dwóch wersjach: same towary bez podsumowania oraz towary z podsumowaniem),

```
{ "commandType": 30, "commandInput": { "1": { "commandType": 16 }, "2": { "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "ProduktMaxSum", "price": 999999.99, "ptu": "A", "unit": "szt" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandType": 24, "commandInput": { "name": "paymentName", "payment_type": 1, "value": 999999.99, "payment_without_terminal": true } }, "4": { "commandType": 26, "commandInput": { "canceled": false }, "print": true, "returnPDF": false, "returnQR": true }, "5": { "commandType": 16 }, "6": { "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "ProduktMaxSum", "price": 999999.99, "ptu": "A", "unit": "szt" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }, "7": { "commandType": 24, "commandInput": { "name": "paymentName", "payment_type": 1, "value": 999999.99, "payment_without_terminal": true } }, "8": { "commandType": 26, "commandInput": { "canceled": false }, "print": true, "returnPDF": false, "returnQR": true }, "9": { "commandType": 16 }, "10": { "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "ProduktMaxSum", "price": 999999.99, "ptu": "A", "unit": "szt" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }, "11": { "commandType": 24, "commandInput": { "name": "paymentName", "payment_type": 1, "value": 999999.99, "payment_without_terminal": true } }, "12": { "commandType": 26, "commandInput": { "canceled": false }, "print": true, "returnPDF": false, "returnQR": true } } }
```
25//paragon jednopozycyjny całkowicie wystornowany i następnie anulowany,

```
{ "commandType": 30, "commandInput": { "1": { "commandType": 16 }, "2": { "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt1", "price": 100, "ptu": "A", "unit": "szt" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }, "3": { "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": true, "count": 1, "name": "Produkt1", "price": 100, "ptu": "A", "unit": "szt" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }, "4": { "commandType": 26, "commandInput": { "canceled": true }, "print": true, "returnPDF": false, "returnQR": true } } }
```


////////////////////////////////////////////////////////////////////////////////////////ZADANIA DODATKOWE///////////////////////////////////////////////////////////////////////


```
{ "commandType": 30, "commandInput": { "1": { "commandType": 16 }, "2": { "commandType": 22, "commandInput": { "item": { "name": "TOWAR_1_1", "count": 2, "price": 0.01, "ptu": "A" }, "type": 1 }, "print": true }, "3": { "commandType": 22, "commandInput": { "item": { "name": "TOWAR_1_2", "count": 3, "price": 0.01, "ptu": "B" }, "type": 1 }, "print": true }, "4": { "commandType": 22, "commandInput": { "item": { "name": "TOWAR_1_3", "count": 4, "price": 0.01, "ptu": "C" }, "type": 1 }, "print": true }, "5": { "commandType": 22, "commandInput": { "item": { "name": "TOWAR_1_4", "count": 5, "price": 0.01, "ptu": "D" }, "type": 1 }, "print": true }, "6": { "commandType": 22, "commandInput": { "item": { "name": "TOWAR_1_5", "count": 1, "price": 0.01, "ptu": "E" }, "type": 1 }, "print": true }, "7": { "commandType": 22, "commandInput": { "item": { "name": "TOWAR_1_6", "count": 1, "price": 0.01, "ptu": "F" }, "type": 1 }, "print": true }, "8": { "commandType": 22, "commandInput": { "item": { "name": "TOWAR_1_7", "count": 10, "price": 0.01, "ptu": "G" }, "type": 1 }, "print": true }, "9": { "commandType": 22, "commandInput": { "item": { "name": "STORNO TOWAR_1_1", "count": -2, "price": 0.01, "ptu": "A" }, "type": 2 }, "print": true }, "10": { "commandType": 22, "commandInput": { "item": { "name": "STORNO TOWAR_1_2", "count": -3, "price": 0.01, "ptu": "B" }, "type": 2 }, "print": true }, "11": { "commandType": 22, "commandInput": { "item": { "name": "STORNO TOWAR_1_3", "count": -4, "price": 0.01, "ptu": "C" }, "type": 2 }, "print": true }, "12": { "commandType": 22, "commandInput": { "item": { "name": "STORNO TOWAR_1_4", "count": -5, "price": 0.01, "ptu": "D" }, "type": 2 }, "print": true }, "13": { "commandType": 22, "commandInput": { "item": { "name": "STORNO TOWAR_1_5", "count": -1, "price": 0.01, "ptu": "E" }, "type": 2 }, "print": true }, "14": { "commandType": 22, "commandInput": { "item": { "name": "STORNO TOWAR_1_6", "count": -1, "price": 0.01, "ptu": "F" }, "type": 2 }, "print": true }, "15": { "commandType": 22, "commandInput": { "item": { "name": "STORNO TOWAR_1_7", "count": -10, "price": 0.01, "ptu": "G" }, "type": 2 }, "print": true }, "16": { "commandType": 24, "commandInput": { "currency_converter": 2.54, "currency": "EUR", "is_from_registration_currency_conversion": false, "is_informative_conversion": true, "name": "paymentName", "payment_type": 1, "value": 0, "payment_without_terminal": true } }, "17": { "commandType": 26, "commandInput": { "canceled": false }, "print": true, "returnPDF": false, "returnQR": true } } }
```


/////////////////////////////////////////////////////proba dodatkowego zadania 2//////////////////////////////////////////////////////
```
{ "commandType": 16 }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 2, "name": "TOWAR_1_1", "price": 0.01, "ptu": "A", "unit": "" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 3, "name": "TOWAR_1_2", "price": 0.01, "ptu": "B", "unit": "" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 4, "name": "TOWAR_1_3", "price": 0.01, "ptu": "C", "unit": "" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 5, "name": "TOWAR_1_4", "price": 0.01, "ptu": "D", "unit": "" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "TOWAR_1_5", "price": 0.01, "ptu": "E", "unit": "" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "TOWAR_1_6", "price": 0.01, "ptu": "F", "unit": "" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 10, "name": "TOWAR_1_7", "price": 0.01, "ptu": "G", "unit": "" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": true, "count": 1, "name": "TOWAR_1_1", "price": 0.01, "ptu": "A", "unit": "" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
///dajemy opokowanie zwrotne 
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 2, "name": "SŁOIK", "price": 1.25, "ptu": "A", "unit": "szt" }, "type": 2 }, "print": true, "returnModel": false, "returnPDF": false }
```

```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": true, "count": 1, "name": "Opakowanie zwrotne", "price": 1.34, "ptu": "A", "unit": "szt" }, "type": 2 }, "print": true, "returnModel": false, "returnPDF": false }
```

///final
```
{ "commandType": 24, "commandInput": { "name": "paymentName", "payment_type": 1, "value": 1.16, "payment_without_terminal": true } }
```

```
{ "commandType": 26, "commandInput": {"canceled": false}, "print": true, "returnPDF": false, "returnQR": true }
```



/////////////////////////////////////////////////AKTYWACJA STAWEK PTU///////////////////////////////////////////////////
```
{ "commandType": 32, "commandInput": { "settings": [ { "name": "ptu1", "value": "A", "rate": 23.00 }, { "name": "ptu2", "value": "B", "rate": 8.00 }, { "name": "ptu3", "value": "C", "rate": 5.00 }, { "name": "ptu4", "value": "D", "rate": 0.00 }, { "name": "ptu5", "value": "E", "rate": 12.00 }, { "name": "ptu6", "value": "F", "rate": 18.00 }, { "name": "ptu7", "value": "G", "rate": 22.00 } ] } }
```
/////////////////////////////////////////////////////////////////
```
{ "commandType": 4, "commandInput": { "sales_system_name": "salesSystemNameTest", "sales_system_version": "salesSystemVersionTest" } }
```

///////////////////////////////////////////
```
{ "commandInput": { "A": { "type": 0, "value": 23 }, "B": { "type": 0, "value": 8 }, "C": { "type": 0, "value": 5 }, "D": { "type": 0, "value": 2 }, "E": { "type": 0, "value": 3 }, "F": { "type": 0, "value": 4 }, "G": { "type": 0, "value": 6 } }, "commandType": 3 }
```
## RFDnr1
 Paragon fiskalny nr1
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'TOWAR_1_1', 'price': 0.01, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'TOWAR_1_2', 'price': 0.01, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'TOWAR_1_3', 'price': 0.01, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'TOWAR_1_4', 'price': 0.01, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'TOWAR_1_5', 'price': 0.01, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'TOWAR_1_6', 'price': 0.01, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'TOWAR_1_7', 'price': 0.01, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```

//Paragon fiskalny nr4
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_1_TOWAR_1_A', 'price': 0.13, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_1_TOWAR_1_B', 'price': 0.14, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_1_TOWAR_1_C', 'price': 0.15, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_1_TOWAR_1_D', 'price': 0.16, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_1_TOWAR_1_E', 'price': 0.17, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_1_TOWAR_1_F', 'price': 0.18, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_1_TOWAR_1_G', 'price': 0.19, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
//Paragon fiskalny nr5
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_1_TOWAR_1_A', 'price': 0.13, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_1_TOWAR_1_B', 'price': 0.14, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_1_TOWAR_1_C', 'price': 0.15, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_1_TOWAR_1_D', 'price': 0.16, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_1_TOWAR_1_E', 'price': 0.17, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_1_TOWAR_1_F', 'price': 0.18, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_1_TOWAR_1_G', 'price': 0.19, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
## RFDnr2
Paragon fiskalny nr1 
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A', 'price': 0.01, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B', 'price': 0.01, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C', 'price': 0.01, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D', 'price': 0.01, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E', 'price': 0.01, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F', 'price': 0.01, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G', 'price': 0.01, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A1', 'price': 0.01, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B1', 'price': 0.01, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C1', 'price': 0.01, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D1', 'price': 0.01, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E1', 'price': 0.01, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F1', 'price': 0.01, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G1', 'price': 0.01, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B2', 'price': 0.01, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C2', 'price': 0.01, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D2', 'price': 0.01, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E2', 'price': 0.01, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E2', 'price': 0.01, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G2', 'price': 0.01, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
Paragon fiskalny nr2 
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A', 'price': 999.99, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B', 'price': 999.99, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C', 'price': 999.99, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D', 'price': 999.99, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E', 'price': 999.99, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F', 'price': 999.99, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G', 'price': 999.99, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A1', 'price': 999.99, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B1', 'price': 999.99, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C1', 'price': 999.99, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D1', 'price': 999.99, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E1', 'price': 999.99, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F1', 'price': 999.99, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G1', 'price': 999.99, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A2', 'price': 999.99, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B2', 'price': 999.99, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C2', 'price': 999.99, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D2', 'price': 999.99, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E2', 'price': 999.99, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G2', 'price': 999.99, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
Paragon fiskalny nr3 
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A', 'price': 0.26, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B', 'price': 0.09, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C', 'price': 0.06, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D', 'price': 0.03, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E', 'price': 0.03, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F', 'price': 0.03, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G', 'price': 0.03, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A1', 'price': 0.03, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B1', 'price': 0.03, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C1', 'price': 0.03, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D1', 'price': 0.03, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E1', 'price': 0.03, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F1', 'price': 0.03, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G1', 'price': 0.03, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A2', 'price': 0.03, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B2', 'price': 0.03, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C2', 'price': 0.03, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D2', 'price': 0.03, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E2', 'price': 0.03, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G2', 'price': 0.03, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
Paragon fiskalny nr4
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A', 'price': 832.72, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B', 'price': 272.95, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C', 'price': 219.41, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D', 'price': 529.82, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E', 'price': 88.56, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F', 'price': 965.35, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G', 'price': 406.96, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A1', 'price': 811.56, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B1', 'price': 111.44, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C1', 'price': 188.13, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D1', 'price': 258.44, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E1', 'price': 368.05, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F1', 'price': 405.74, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G1', 'price': 293.3, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A2', 'price': 257.5, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B2', 'price': 340.39, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C2', 'price': 554.01, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D2', 'price': 336.04, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E2', 'price': 212.33, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G2', 'price': 822.8, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
Paragon fiskalny nr5
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A', 'price': 210.37, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B', 'price': 750.68, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C', 'price': 130.42, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D', 'price': 584.52, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E', 'price': 713.02, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F', 'price': 909.19, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G', 'price': 276.12, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A1', 'price': 437.66, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B1', 'price': 900.32, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C1', 'price': 870.82, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D1', 'price': 694.6, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E1', 'price': 294.66, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F1', 'price': 311.84, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G1', 'price': 807.88, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A2', 'price': 714.48, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B2', 'price': 425.53, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C2', 'price': 190.21, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D2', 'price': 213.09, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E2', 'price': 617.49, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G2', 'price': 678.43, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
Paragon fiskalny nr6
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A', 'price': 105.46, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B', 'price': 673.64, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C', 'price': 345.309, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D', 'price': 875.96, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E', 'price': 431.14, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F', 'price': 441.11, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G', 'price': 849.09, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A1', 'price': 410.63, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B1', 'price': 950.62, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C1', 'price': 729.4, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D1', 'price': 339.09, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E1', 'price': 761.27, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F1', 'price': 517.69, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G1', 'price': 54.65, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A2', 'price': 772.87, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B2', 'price': 358.1, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C2', 'price': 318.59, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D2', 'price': 886.09, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E2', 'price': 686.11, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G2', 'price': 834.38, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
Paragon fiskalny nr7
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A', 'price': 128.25, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B', 'price': 89.9, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C', 'price': 922.94, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D', 'price': 190.63, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E', 'price': 275.29, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F', 'price': 64.48, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G', 'price': 187.78, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A1', 'price': 710.55, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B1', 'price': 441.43, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C1', 'price': 257.79, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D1', 'price': 110.39, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E1', 'price': 605.67, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F1', 'price': 329.62, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G1', 'price': 314.81, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A2', 'price': 308.4, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B2', 'price': 747.56, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C2', 'price': 597.25, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D2', 'price': 458.9, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E2', 'price': 602.8, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G2', 'price': 835.95, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
Paragon fiskalny nr8
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A', 'price': 536.79, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B', 'price': 322.72, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C', 'price': 406.42, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D', 'price': 747.41, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E', 'price': 802.58, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F', 'price': 700.51, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G', 'price': 372.81, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A1', 'price': 798.76, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B1', 'price': 799.68, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C1', 'price': 827.89, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D1', 'price': 290.58, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E1', 'price': 508.16, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F1', 'price': 770.06, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G1', 'price': 510.04, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A2', 'price': 718.48, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B2', 'price': 719.82, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C2', 'price': 714.92, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D2', 'price': 756.57, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E2', 'price': 44.67, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G2', 'price': 731.13, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
Paragon fiskalny nr9
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A', 'price': 544.01, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B', 'price': 297.26, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C', 'price': 826.21, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```    
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D', 'price': 782.13, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```    
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E', 'price': 417.6, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```     
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F', 'price': 156.44, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```    
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G', 'price': 770.82, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```    
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A1', 'price': 592.98, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```   
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B1', 'price': 382.36, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```   
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C1', 'price': 791.14, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```   
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D1', 'price': 559.02, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```   
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E1', 'price': 857.4, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```    
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F1', 'price': 431.6, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```    
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G1', 'price': 451.0, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```    
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A2', 'price': 222.33, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```   
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B2', 'price': 173.54, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```   
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C2', 'price': 760.48, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```   
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D2', 'price': 646.43, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```   
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E2', 'price': 246.23, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
```   
```
{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G2', 'price': 217.66, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}
``` 
Paragon fiskalny nr10
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A', 'price': 81.9, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B', 'price': 480.47, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C', 'price': 721.89, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D', 'price': 807.77, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E', 'price': 277.17, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F', 'price': 326.14, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G', 'price': 446.99, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A1', 'price': 243.15, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B1', 'price': 326.13, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C1', 'price': 450.94, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D1', 'price': 295.58, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E1', 'price': 541.87, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F1', 'price': 162.94, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G1', 'price': 74.11, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A2', 'price': 553.36, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B2', 'price': 87.26, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C2', 'price': 549.72, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D2', 'price': 867.9, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E2', 'price': 583.92, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G2', 'price': 965.71, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}``` 
Paragon fiskalny nr11
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A', 'price': 678.9, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B', 'price': 340.6, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C', 'price': 339.8, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```     
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D', 'price': 956.75, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E', 'price': 433.45, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F', 'price': 50.27, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```     
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G', 'price': 878.37, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A1', 'price': 114.34, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B1', 'price': 152.66, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C1', 'price': 803.32, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D1', 'price': 309.62, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E1', 'price': 73.37, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F1', 'price': 243.31, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G1', 'price': 572.95, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A2', 'price': 204.31, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B2', 'price': 283.58, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C2', 'price': 565.22, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D2', 'price': 836.36, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E2', 'price': 836.36, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G2', 'price': 522.8, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}``` 
Paragon fiskalny nr12
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A', 'price': 357.02, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B', 'price': 482.42, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C', 'price': 412.96, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D', 'price': 61.53, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```     
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E', 'price': 121.55, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F', 'price': 757.07, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G', 'price': 374.43, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A1', 'price': 632.97, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B1', 'price': 99.46, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C1', 'price': 203.58, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D1', 'price': 401.03, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E1', 'price': 698.36, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F1', 'price': 951.23, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G1', 'price': 580.38, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A2', 'price': 629.98, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B2', 'price': 306.63, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C2', 'price': 415.87, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D2', 'price': 348.41, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E2', 'price': 526.61, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G2', 'price': 456.68, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
Paragon fiskalny nr13
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A', 'price': 704.39, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B', 'price': 864.52, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}``` 
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C', 'price': 179.09, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}``` 
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D', 'price': 379.6, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```  
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E', 'price': 347.83, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}``` 
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F', 'price': 325.2, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```  
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G', 'price': 860.58, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A1', 'price': 902.56, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B1', 'price': 692.89, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C1', 'price': 364.69, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D1', 'price': 409.59, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E1', 'price': 406.93, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F1', 'price': 684.24, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G1', 'price': 807.68, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A2', 'price': 60.98, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B2', 'price': 318.97, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C2', 'price': 971.95, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D2', 'price': 805.03, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E2', 'price': 2.72, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```     
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G2', 'price': 643.06, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
Paragon fiskalny nr14
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A', 'price': 530.21, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B', 'price': 754.9, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}``` 
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C', 'price': 543.17, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D', 'price': 119.55, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E', 'price': 185.4, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}``` 
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F', 'price': 804.26, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G', 'price': 931.55, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A1', 'price': 245.17, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B1', 'price': 183.1, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C1', 'price': 344.18, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D1', 'price': 658.76, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E1', 'price': 984.63, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F1', 'price': 35.44, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G1', 'price': 797.0, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A2', 'price': 838.55, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B2', 'price': 174.4, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C2', 'price': 582.82, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D2', 'price': 484.36, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E2', 'price': 162.84, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G2', 'price': 853.95, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}``` 
Paragon fiskalny nr15
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A', 'price': 757.72, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B', 'price': 331.02, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}``` 
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C', 'price': 540.91, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}``` 
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D', 'price': 173.77, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}``` 
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E', 'price': 432.76, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}``` 
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F', 'price': 905.13, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}``` 
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G', 'price': 330.3, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```  
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A1', 'price': 74.95, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}``` 
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B1', 'price': 425.48, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C1', 'price': 425.48, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D1', 'price': 950.32, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E1', 'price': 531.96, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F1', 'price': 483.48, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G1', 'price': 693.34, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A2', 'price': 424.93, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B2', 'price': 72.73, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C2', 'price': 32.04, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D2', 'price': 88.17, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E2', 'price': 981.13, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G2', 'price': 53.11, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}``` 
Paragon fiskalny nr16
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A', 'price': 461.87, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B', 'price': 80.69, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}``` 
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C', 'price': 509.06, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D', 'price': 714.81, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E', 'price': 542.02, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F', 'price': 416.65, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G', 'price': 259.06, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A1', 'price': 759.97, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B1', 'price': 425.0, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C1', 'price': 50.05, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D1', 'price': 516.08, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E1', 'price': 89.16, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F1', 'price': 602.1, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G1', 'price': 192.31, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A2', 'price': 495.02, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B2', 'price': 452.82, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C2', 'price': 138.02, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D2', 'price': 257.98, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```   
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E2', 'price': 240.7, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```    
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G2', 'price': 54.62, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}``` 
Paragon fiskalny nr17
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_RFD_2_TOWAR_1_A', 'price': 207.63, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_RFD_2_TOWAR_1_B', 'price': 410.03, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_RFD_2_TOWAR_1_C', 'price': 619.18, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_RFD_2_TOWAR_1_D', 'price': 561.0, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_RFD_2_TOWAR_1_E', 'price': 972.95, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_RFD_2_TOWAR_1_F', 'price': 954.14, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_RFD_2_TOWAR_1_G', 'price': 178.69, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_RFD_2_TOWAR_1_A1', 'price': 378.6, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_RFD_2_TOWAR_1_B1', 'price': 752.5, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_RFD_2_TOWAR_1_C1', 'price': 206.49, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_RFD_2_TOWAR_1_D1', 'price': 582.75, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_RFD_2_TOWAR_1_E1', 'price': 283.56, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_RFD_2_TOWAR_1_F1', 'price': 945.27, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_RFD_2_TOWAR_1_G1', 'price': 69.85, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_RFD_2_TOWAR_1_A2', 'price': 769.56, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_RFD_2_TOWAR_1_B2', 'price': 30.27, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_RFD_2_TOWAR_1_C2', 'price': 153.23, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_RFD_2_TOWAR_1_D2', 'price': 275.21, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_RFD_2_TOWAR_1_E2', 'price': 129.64, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_RFD_2_TOWAR_1_G2', 'price': 451.24, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
Paragon fiskalny nr18
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A', 'price': 95.43, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B', 'price': 114.63, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C', 'price': 680.81, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D', 'price': 468.0, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E', 'price': 378.99, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F', 'price': 696.28, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G', 'price': 2.51, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A1', 'price': 526.57, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B1', 'price': 821.95, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C1', 'price': 933.04, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D1', 'price': 456.47, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E1', 'price': 152.6, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F1', 'price': 14.59, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G1', 'price': 950.4, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A2', 'price': 484.29, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B2', 'price': 135.64, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C2', 'price': 375.4, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D2', 'price': 326.93, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E2', 'price': 606.93, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G2', 'price': 968.34, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
Paragon fiskalny nr19
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A', 'price': 169.88, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B', 'price': 620.2, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C', 'price': 370.51, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D', 'price': 752.3, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E', 'price': 281.5, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F', 'price': 163.46, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G', 'price': 840.88, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A1', 'price': 581.17, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B1', 'price': 109.0, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C1', 'price': 839.57, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D1', 'price': 283.01, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E1', 'price': 548.42, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F1', 'price': 964.69, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G1', 'price': 219.47, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A2', 'price': 673.94, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B2', 'price': 760.0, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C2', 'price': 615.38, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D2', 'price': 363.46, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E2', 'price': 693.86, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G2', 'price': 650.01, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
Paragon fiskalny nr20
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A', 'price': 97.93, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B', 'price': 149.25, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C', 'price': 292.8, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D', 'price': 903.09, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E', 'price': 138.73, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F', 'price': 164.46, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G', 'price': 702.96, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A1', 'price': 78.71, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B1', 'price': 151.67, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C1', 'price': 805.26, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D1', 'price': 890.11, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E1', 'price': 781.0, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_F1', 'price': 953.58, 'ptu': 'F', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G1', 'price': 236.92, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_A2', 'price': 647.79, 'ptu': 'A', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_B2', 'price': 963.59, 'ptu': 'B', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_C2', 'price': 439.57, 'ptu': 'C', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_D2', 'price': 816.34, 'ptu': 'D', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_E2', 'price': 97.56, 'ptu': 'E', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```
```{'commandType': 22, 'commandInput': {'item': {'advanceRemain': 0, 'canceled': False, 'count': 1, 'name': 'RFD_2_TOWAR_1_G2', 'price': 533.24, 'ptu': 'G', 'unit': ''}, 'type': 1}, 'print': True, 'returnModel': False, 'returnPDF': False}```

