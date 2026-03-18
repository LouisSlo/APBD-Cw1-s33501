# Projekt APBD - Ćwiczenia 1 (Git)
**Student:** LouisSlo (s33501)  
**Uczelnia:** Polsko-Japońska Akademia Technik Komputerowych

## Odpowiedzi na pytania do zadania

### 1. Kiedy Git wykona fast-forward, a kiedy powstaje merge commit?
* **Fast-forward:** Występuje w sytuacji, gdy gałąź, którą chcemy dołączyć (np. `feature`), zawiera wszystkie commity gałęzi bazowej (`main`) i żadne nowe commity nie pojawiły się na `main` od momentu rozgałęzienia. Git po prostu przesuwa wskaźnik `main` na ostatni commit gałęzi `feature`.
* **Merge commit:** Powstaje, gdy historia obu gałęzi "rozjechała się" – czyli zarówno na `main`, jak i na gałęzi `feature` pojawiły się nowe, niezależne zmiany. Git musi wtedy stworzyć nowy, dodatkowy commit łączący te dwa nurty historii.



### 2. Czym w praktyce różni się merge od rebase?
* **Merge:** Zachowuje prawdziwą chronologię i strukturę prac. Widzimy dokładnie, kiedy gałąź została stworzona i kiedy połączona. Minusem jest "brudna" historia (dużo linii i commitów typu "Merge branch...").
* **Rebase:** Przepisuje historię tak, jakby praca na gałęzi odbywała się na samym szczycie aktualnego `main`. Dzięki temu historia jest idealnie liniowa i czytelna, ale tracimy informację o tym, kiedy faktycznie dany fragment kodu był tworzony względem innych gałęzi.



### 3. W jaki sposób został rozwiązany konflikt w Twoim repozytorium?
Konflikt został wywołany poprzez jednoczesną modyfikację tej samej linii w pliku `Program.cs` na gałęziach `main` oraz `feature-conflict`.
* **Kroki rozwiązania:**
    1. Git zatrzymał proces merge'a i oznaczył plik jako skonfliktowany.
    2. Otworzyłem plik w IDE (Rider), który wyświetlił obie wersje zmian rozdzielone znacznikami `<<<<<<<`, `=======` i `>>>>>>>`.
    3. Świadomie wybrałem finalną treść linii (łącząc obie wersje lub wybierając jedną z nich) i usunąłem znaczniki konfliktu.
    4. Dodałem plik do obszaru staging (`git add`) i sfinalizowałem proces commitem kończącym merge.