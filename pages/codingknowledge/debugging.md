---
layout: default
title: Rozwiązywanie problemów
parent: Pisanie kodu i poszukiwanie informacji
nav_order: 3
---
![](../../images/intros/debugging.jpg){: width="250" .float-left .mr-3 }
Rozwiązywanie problemów
{: .fs-8 .ls-10 .code-example .fw-700}
W pracy programisty codziennością jest to, że coś nie działa 🙂 Nie ma się czym przejmować, najważniejsze to umieć sobie radzić z takimi sytuacjami.
![](../../images/content/meme.jpg){: width="400" }


## Debugowanie
Poniżej kilka rad, co można zrobić w różnych sytuacjach, kiedy kod nie funkcjonuje tak, jak chcemy:
- Kod zwraca błąd – idealnie! Trzeba dokładnie wczytać się w wiadomość, a być może od razu znajdziemy w niej sugestię, co i gdzie zrobić, by go naprawić. Jeśli nie jest to jasne od razu, nic straconego. Najlepiej skopiować treść błędu i wkleić go w Google. Przy kopiowaniu można pominąć słowa nie mające znaczenia, jak np. nazwa użytej przez nas zmiennej. Warto też czasem opakować część tekstu w `""``, które w Google wyszukają zdanie w całości, dokładnie tak, jak zostało wpisane. Jest bardzo duża szansa, że w sieci znajdziemy osoby, które już miały podobny problem i udzielą wskazówek, co robić dalej :)
- Gorszą sytuacją jest to, kiedy nie ma żadnego błędu, a kod i tak nie robi tego, co zakładamy. Często to znaczy, że składnia jako tako jest poprawna, tylko została przez nas źle użyta. Warto sprawdzić kod pod kątem literówek, przyjrzeć się miejscom, gdzie używamy operatorów czy instrukcji warunkowych.
- Możemy próbować „podglądnąć”, co się dzieje w kodzie poprzez wypisywanie tekstu na ekran. Wystarczy użyć do tego zwykłej instrukcji puts. Możemy na przykład wypisać zawartość zmiennej na danym etapie, sprawdzić, czy podczas uruchamiania kodu „wchodzimy” do pętli czy do instrukcji warunkowej.
```ruby
if zmienna == 2
  puts "zmienna to 2"
else
  puts "podglądam co jest #{zmienna}"
end
```
Jeśli podglądamy obiekt, przydatna może być metoda [inspect](https://apidock.com/ruby/Object/inspect).
- Dużo wygodniejszym od wypisywania tekstu będzie użycie narzędzie dedykowanego debugowaniu, np. [pry](https://laflamablanc.medium.com/debugging-ruby-code-with-pry-a0bf1f5e97ca)

Poniżej kilka artykułów na temat debugowania:
- [How to Debug Your Code for Beginners](https://www.freecodecamp.org/news/what-is-debugging-how-to-debug-code/)
- [How to Debug & Fix Your Ruby Programs](https://www.rubyguides.com/2015/07/ruby-debugging/)

{: .new-title }
> Ciekawostka
>
> Słowo „bug” (błąd) w informatyce zyskało popularność dzięki Grace Hopper. Podczas prac nad komputerem Mark II na Uniwersytecie Harvarda, zespół admirał napotkał pewne problemy z funkcjonowaniem urządzenia. Okazało się, że winowajcą był nie żaden programista, lecz ćma, która zaplątała się w przekaźnik, utrudniając jego pracę. Admirał Hopper nadała temu wydarzeniu nazwę „debugowanie”, co oznaczało usunięcie robaka – w tym przypadku dosłownie. To nietypowa sytuacja zainicjowała późniejsze użycie terminu „debugowanie” w kontekście usuwania błędów w programowaniu.
