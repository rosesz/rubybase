---
layout: default
title: Programowanie obiektowe
parent: Wyjaśnienia
nav_order: 2
---
![](../../images/intros/oop.jpg){: width="250" .float-left .mr-3 }
Programowanie obiektowe
{: .fs-8 .ls-10 .code-example .fw-700}
## Wstęp
Obiekty, obiekty... ten termin ciagle pojawia się przy nauce programowania i może przyprawiać o ból głowy 🙂
Na początek troche teorii:
- [O metodach](https://www.theodinproject.com/lessons/ruby-methods)
- [O klasach](https://www.codecademy.com/courses/learn-ruby/lessons/object-oriented-programming-i/exercises/why-classes)

## Pierwszy przykład
Przykład programowania obiektowego:
```
# Najpierw definiujemy klasę, żeby móc poźniej tworzyć obiekty tej klasy
# Obiekt to jakaś zmienna w ruby, która została stworzona według konkretnego wzorca
# i możemy od tego oobiektu oczekiwać, że będzie miał konkretne właściwości.
# np. jak obiekt jest typu Pies, to oczekuję, że będzie mógł szczekać :)

class Pies
  def szczekaj
    "Hau Hau"
  end

  def warcz
    "Wrrr"
  end
end

azor = Pies.new # tworzymy nowy obiekt i przypisujemy do zmiennej azor
burek = Pies.new # kolejny obiekt

puts azor.szczekaj # wołamy metodę szczekaj, azor ma tę metodę, bo jest obiektem klasy Pies a następnie wypisujemy na ekran
puts azor.warcz

puts burek.szczekaj
puts burek.warcz
```
Powyższy kod można zapisać na dysku do pliku `example.rb` i uruchomić:
```
ruby sciezka/do/pliku/example.rb
```
Lub skorzstać z narzędzie online do uruchamiania kodu, jak np. [TryRuby](https://try.ruby-lang.org/) bądź [Replit](https://replit.com/languages/ruby).

## Metoda `initialize` – konstruktor
Metoda  `initialize`  to taka specjalna metoda, która odpala się tylko raz, kiedy tworzysz obiekt. Często mówi się o tej metodzie, że to jest „konstruktor”. Czyli w momencie, kiedy tworzysz obiekt, w np. `Greeter.new`, tak naprawdę pod spodem wywoływana jest metoda  `initalize`  właśnie, można sobie wyobrazić w głowie, że jest to coś w stylu (uwaga, to niepoprawny kod)  Greeter.initialize. Dodając argumenty do metody `initialize`, czyli np. minutes, to można ich używać tworząc obiekt (wołając metodę `new`), np. `Greeter.new(25)`. Idąc dalej tym tropem można by dodać więcej argumentów, modyfikując metodę `initalize`:  
```
def initalize(minutes, hour)
  @minutes = minutes
  @hour = hour
end
```
I używając tego następnie podać wszystkie argumenty tworząc obiekt `Greeter.new(25, 9)` 

## Zmienne w obiektach
W ruby mamy dwa rodzaje zmiennych, lokalne (takie używane tylko w obrębie jednej metody i nigdzie więcej) oraz pola obiektu. Pola obiektu to właśnie te z @ 🙂 Jak już było wspomniane jeden obiekt może mieć wiele metod. Wracając do przykładu z psami:  
```
class Pies
  def szczekaj
    "Hau Hau"
  end

  def warcz
    "Wrrr"
  end 
end
```
Zmodyfikujmy go trochę, że pies będzie szczekał capslokiem albo nie, w zależności od tego, czy jest mały czy duży 🙂  
```
  def szczekaj(rozmiar)
    if rozmiar == "mały"
      "Hau Hau"
    else
      "HAU HAU"
    end
  end
```
I teraz używamy tego kodu w ten sposób:  
```
azor = Pies.new # tworzymy nowy obiekt typu Pies i przypisujemy do zmiennej azor
azor.szczekaj("mały") # wypisze "Hau Hau"
azor.szczekaj("duży") # wypisze "HAU HAU"
```
Taki kod działa, ale jak się o nim pomyśli to jest trochę bez sensu. Dlaczego azor może być nagle duży albo mały? To jeden pies, jego rozmiar się nie zmieni. Poza tym problem pojawia się z metodą  `warcz`, ona nic nie wie o rozmiarze psa. Trzeba by również i tę metodę zmodyfikować i przesłać rozmiar psa w argumencie, trochę bez sensu. I tu właśnie przydaje się konstruktor.  
```
class Pies
  def initialize(rozmiar)
    @rozmiar = rozmiar
  end

  def szczekaj
    if @rozmiar == "mały"
      "Hau Hau"
    else
      "HAU HAU"
    end
  end

  def warcz
    if @rozmiar == "mały"
      "Wrrr"
    else
      "WRRR"
    end
  end 
end
```
Teraz możemy tego użyć w ten sposób, metoda  `szczekaj`  może już nie mieć żadnych argumentów. Po prostu w obrębie tego samego psa argumenty przekazane w konstruktorze a następnie przypisane do pól obiektu (tych z @) są już znane.
```
azor = Pies.new("mały")
burek = Pies.new("duży)

azor.szczekaj # Hau Hau
azor.warcz # Wrrr

burek.szczekaj # HAU HAU
burek.warcz # WRRR
```
W konstruktorze można podać dowolną ilość parametrów, nie tylko jeden. W przypadku psa warto podać rasę, imię itp. Bo to są cechy, które po tym jak tworzymy nowego psa już się raczej nie zmienią  
Dla odmiany są zmienne, które powinny pozostać zmiennymi lokalnymi. Przykładowo powiedzmy, że tylko w metodzie  `szczekaj`  nie chcemy ręcznie pisać za każdym razem “Hau”, tylko żeby ruby zrobiło to za nas. Liczbę tę przypiszemy sobie na sztywno do zmiennej  `ile_razy`. To jest tylko pomocnicza zmienna w obrębie tej metody, nie potrzebujemy jej gdzie indziej ani nie jest bezpośrednio związana z psem.  
```
  def szczekaj
    ile_razy = 5
    if @rozmiar == "mały"
      "Hau" * ile_razy
    else
      "HAU" * ile_razy
    end
  end
```
Gdybym teraz w metodzie  `warcz`  spróbowała użyć  `ile_razy`  to poleciałby błąd, bo to lokalna zmienna tylko na potrzeby  `szczekaj`. Na końcu znajdzie się kompletny przykład, można go pobrać i uruchomić u siebie.
Jeszcze jedna sprawa na koniec, w konstruktorze jest dużo takiego powtarzania się:  
```
  def initialize(rozmiar, imie, rasa)
    @rozmiar = rozmiar
    @imie = imie
    @rasa = rasa
  end
```
To dlatego, że np.  `rasa`  to tylko lokalna zmienna i inne metody poza  `initialize`  nic o niej nie wiedzą. Dlatego musimy skopiować wartość do zmiennej  `@rasa`  (to dwie różne zmienne, mimo, że wyglądają podobnie), która już będzie widziana przez inne metody w psie.

Zmodifikowany przykład w całości, gotowy do uruchomienia:
```
class Pies
  def initialize(rozmiar, imie, rasa)
    @rozmiar = rozmiar
    @imie = imie
    @rasa = rasa
  end

  def szczekaj
    ile_razy = 5
    if @rozmiar == "mały"
      "Hau " * 5
    else
      "HAU " * 5
    end
  end

  def warcz
    if @rozmiar == "mały"
      "Wrrr"
    else
      "WRRR"
    end
  end

  def przedstaw_sie
    "Jestem #{@imie} i jestem psem rasy #{@rasa}"
  end
end

azor = Pies.new("mały", "Azor", "szpic")
burek = Pies.new("duży", "Burek", "terrier")


puts azor.przedstaw_sie
puts azor.szczekaj
puts azor.warcz

puts burek.przedstaw_sie
puts burek.szczekaj
puts burek.warcz
```
