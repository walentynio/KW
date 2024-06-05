# KW

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
//paragon dwupozycyjny ze storno pierwszej pozycji, (u mnie liczy nie poprawnie)

```
{ "commandType": 16 }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt1", "price": 50, "ptu": "A", "unit": "szt" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": false, "count": 1, "name": "Produkt2", "price": 100, "ptu": "A", "unit": "szt" }, "type": 1 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 22, "commandInput": { "item": { "advanceRemain": 0, "canceled": true, "count": 1, "name": "Produkt1", "price": 50, "ptu": "A", "unit": "szt" }, "type": 2 }, "print": true, "returnModel": false, "returnPDF": false }
```
```
{ "commandType": 24, "commandInput": { "name": "paymentName", "payment_type": 1, "value": 100, "payment_without_terminal": true } }
```
```
{ "commandType": 26, "commandInput": { "canceled": false }, "print": true, "returnPDF": false, "returnQR": true }
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
