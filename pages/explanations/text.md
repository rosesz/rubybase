---
layout: default
title: Wypisywanie tekstu
parent: Wyjaśnienia
nav_order: 2
---
![](../../images/intros/oop.jpg){: width="250" .float-left .mr-3 }
Wypisywanie tekstu
{: .fs-8 .ls-10 .code-example .fw-700}

### Zmienne tekstowe
Tekst zawsze musi być opakowany albo w `"` albo w `'` (jest jeszcze trzecia opcja że tekst będzie tzw. symbolem, ale to taki specyficzny rodzaj tylko dla krótkich słów więc na razie go pomińmy – ale stosuje się wtedy dwukropek).

Gołe słowa w kodzie nie opakowane w pazurki Ruby traktuje jako część kodu, tzn. będzie myślał że to jest albo zmienna albo metoda. Omyłkowe użycie zwróci - `undefined variable or method`. 


### Wypisywanie zmiennych
Jest kilka sposobów wypisywania zmiennych na ekran, np.
```
puts "początek tekstu" + zmienna + " koniec tekstu"
```

Albo stosując tzw. string interpolation
```
puts "początek tekstu #{zmienna} koniec tekstu"
```

{: .warning-title }
> Uwaga
>
> Drugi sposób (interpolacja) zadziała tylko z podwójnym cudzysłowem `"` ale nie z `'`.

Natomiast kiedy jedna ze zmiennych jest liczbą:

```
a = 15
"Pierwsza część " + a + "druga część"
```
nie zadziała, bo 15 jest liczbą. za to poniższe by zadziałało:  
```
a = "15"
"Pierwsza część " + a + "druga część"
```
rozwiązaniem problemu jets dodanie  `to_s`  czyli rzutowania na stringa:  

```
a = "15"
"Pierwsza część " + a.to_s + "druga część"
```

### Porównanie `print` vs `puts`

Różnica jest taka, że `puts` wpisuje tekst na ekran i od razu potem przechodzi do nowej linii.
```
> print 1,2,3
```
```
123
> puts 1,2,3

1

2

3
```
Czyli w zasadzie jeśli wypisuje się tylko jedną rzecz (a nie trzy tak jak w powyższym przykładzie) to nie ma to większego znaczenia.