---
layout: default
title: Pozdrawiacz
parent: Zadania
nav_order: 2
---
![](../../images/intros/greeter.jpg){: width="250" .float-left .mr-3 }
Zadanie – Pozdrawiacz (Greeter) w Ruby
{: .fs-8 .ls-10 .code-example .fw-700}

Zadanie polega na stworzeniu Pozdrawiacza w ruby.

Plik nazywał się będzie `greeter.rb` i będzie uruchamiany w ten sposób:
```shell
ruby greeter.rb
```
W środku pliku stwórz klasę nową klasę Greetera, a następnie obiekt typu Greeter. W ruby wszystko zawsze jest jakimś obiektem i te obiekty odpalają swoje funkcje. W fekcie powstanie coś w tym stylu:
```ruby
class Greeter
# tu będzie kod tej klasy
end

greeter = Greeter.new # tworzymy obiekt i przypisujemy do zmiennej
puts greeter.say # odpalamy metodę say (musisz ją sama stworzyć) i wyświetlamy jej rezultat na ekranie
```

Metoda  `say`  powinna zwracać taki tekst:  
**„Dzień dobry! Dzisiaj jest piątek, 15 minut po godzinie 9”**
Jak już ta pierwsza wersja będzie ogarnięta, można dodać parę usprawnień:  
-  w pierwszej części dnia będzie mówić „Dzień dobry” a wieczorem „Dobry wieczór”
-  poprawić tekst, żeby brzmiał bardziej po polsku dla wszystkich liczebników, czyli „1  **minuta**  po” ale już „2  **minuty**  po”

{: .note-title }
> Wskazówka
>
> Konieczne będzie użycie klasy `Time`, o której można poczytać [tutaj](https://www.tutorialspoint.com/ruby/ruby_date_time.htm).