---
layout: default
title: Wstęp do programowania w ruby
nav_order: 3
---
![](../images/intros/intro.jpg){: width="250" .float-left .mr-3 }
Wstęp do programowania w ruby
{: .fs-8 .ls-10 .code-example .fw-700}
Ruby to język programowania, który pozwala nam przekazywać instrukcje komputerowi. W przypadku Rubiego, te instrukcje są czytane i natychmiast wykonane, krok po kroku. Potrzebujemy  do tego jednak _interpretera_ Rubiego, coś w rodzaju tłumacza, który rozumie nasze instrukcje i wykonuje je. Jest to oprogramowanie, które musimy najpierw zainstalować na naszym komputerze. Gdy mamy gotowy program w Rubym, mówimy interpreterowi, aby go przeczytał i zrealizował nasze instrukcje. Na przykład, jeśli zapiszemy program w pliku, [w terminalu]({% link /pages/environment/terminal.html %}) używamy polecenia ```ruby nazwa_pliku.rb``` aby interpreter przeczytał i wykonał nasz kod. W tym przypadku komenda `ruby` jest właśnie interpreterem.
Ruby w tym przypadku jest prostszy od języków takich jak Java, gdzie istnieje dodatkowy krok zwany kompilacją. Tam musimy najpierw uzyskać pośrednią formę programu zwaną „bajtkodem”, którą dopiero możemy uruchomić. Jak widzisz, w Ruby możemy bezpośrednio wykonywać kod zapisany w pliku. Jeśli otworzysz taki plik edytorem tekstu, zobaczysz ciąg w miarę zrozumiałego tekstu, przypominającego trochę polecenia w języku angielskim.
```ruby
# Definicja metody, która dodaje dwie liczby
def dodaj(a, b)
  suma = a + b
  return suma
end

# Wywołanie metody z przekazaniem dwóch liczb i zapisanie wyniku w zmiennej
wynik = dodaj(3, 5)

# Wyświetlenie wyniku na ekranie
puts "Wynik dodawania: #{wynik}"
```
Twoje pierwsze programy będą zapewne operować na wyświetlaniu tekstu i składały się z jednego pliku. To jednak dopiero początek, prawdziwe aplikacje to połączenie dziesiątek (jeśli nie setek) takich plików, często korzystających z wsparcia gotowych paczek (bibliotek) lub plików z zewnątrz. Dzięki temu można stworzyć naprawdę pokaźne programy posiadające również interfejs graficzny.

## Składnia języka
Pamiętaj, że w tekście kodu każdy znak czy słowo ma znaczenie, istotna jest także wielkość liter. Część komend będzie wbudowana w język i będzie przypominała angielskie słowa, część stworzysz samodzielnie nadając im własne nazwy. Ruby jest językiem dość elastycznym i pozwala na pewną swobodę, na przykład w przypadku `def dodaj(a, b)` nawiasy można pominąć, używając formy `def dodaj a, b`. Wcięcia w kodzie nie mają znaczenia, ale staraj się ich używać dla zachowania czytelności. Język angielski będzie pomocny w zrozumieniu składni, przyda się również do czytania dokumentacji, szukania rozwiązań problemów, a wreszcie w codziennej pracy do komunikacji.