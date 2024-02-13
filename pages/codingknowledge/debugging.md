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

{: .justify-content: space-between }
![](../../images/content/meme.jpg){: width="300" }

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

## StackOverflow i platformy dla programistów
Istnieje kilka platform dla programistów, które mogą być pomocne w rozwiązywaniu problemów. Jednym z najbardziej znanych miejsc jest Stack Overflow. Po wpisaniu błędu w Google, wielce możliwe jest, że to właśnie tę stronę zobaczysz jako pierwszą. SO to ogromna społeczność, gdzie ludzie pytają o problemy związane z programowaniem, a inni udzielają odpowiedzi. Możesz zadać własne pytanie; wtedy ważne jest, aby zrobić to jak najbardziej precyzyjnie i dostarczyć istotne informacje, aby uzyskać pomocne odpowiedzi. Bardziej prawdopodobne jest jednak, że ktoś zadał podobne pytanie wcześniej. Spróbuj najpierw odszukać takie pytania (czasem to kwestia kilku prób ubrania problemu w różne słowa). Kiedy już je znajdziesz, nie ograniczaj się tylko do zaakceptowanych odpowiedzi. Czasem nowsze odpowiedzi lub te z mniejszą ilością głosów mogą być równie wartościowe lub nawet bardziej aktualne. Staraj się także zerknąć w komentarze oraz zrozumieć prezentowany kod, aby nie kopiować go ślepo 🙂
Istnieją również inne miejsca, gdzie w wymianach zdań między programistami można znaleźć przydatne wskazówki. Są to np. Issues na GitHubie, Reddit (np. r/programming, r/learnprogramming) czy tradycyjne fora dyskusyjne. Zawsze warto szukać, zanim się poddasz. Jest mało prawdopodobne, że jesteśmy jedynymi osobami na świecie, których dotknął jakiś konkretny problem 😄

## ChatGPT
Nie można nie wspomnieć o najnowszym wsparciu dla programistów, czyli sztucznej inteligencji. [ChatGPT](https://chat.openai.com/) to darmowa strona, gdzie w formie rozmowy mamy możliwość zadawania pytań. Można poprosić o wytłumaczenie w prostych słowach trudnych dla nas zagadnień, wyjaśnienie wklejonego fragmentu kodu czy uzyskać wskazówki, jak napisać dany kod. Natomiast z tym narzędziem trzeba działać ostrożnie; bardzo łatwo skopiować gotowy kod, nie rozumiejąc go zupełnie. Poza tym, do pewnych rozwiązań warto dochodzić samodzielnie. Sam ChatGPT również nie jest doskonały, bo chociaż rzadko, to potrafi z pełnym przekonaniem prezentować odpowiedzi, które nie są w ogóle poprawne 😉

{: .new-title }
> Ciekawostka
>
> Słowo „bug” (błąd) w informatyce zyskało popularność dzięki Grace Hopper. Podczas prac nad komputerem Mark II na Uniwersytecie Harvarda, zespół admirał napotkał pewne problemy z funkcjonowaniem urządzenia. Okazało się, że winowajcą był nie żaden programista, lecz ćma, która zaplątała się w przekaźnik, utrudniając jego pracę. Admirał Hopper nadała temu wydarzeniu nazwę „debugowanie”, co oznaczało usunięcie robaka – w tym przypadku dosłownie. To nietypowa sytuacja zainicjowała późniejsze użycie terminu „debugowanie” w kontekście usuwania błędów w programowaniu.
