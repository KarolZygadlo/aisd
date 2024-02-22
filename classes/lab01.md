## Wprowadzenie do pracowni algorytmów i struktur danych

### Agenda
Przewidywany plan zajęć kształtuje się następująco:
* przedstawienie zasad zaliczenia przedmiotu,
* przedstawienie planu tematów i zajęć na cały semestr,
* przedstawienie sugerowanej literatury przedmiotu,

### Zasady zaliczenia przedmiotu
Zajęcia i obecność:
* w trakcie semestru zostanie zrealizowanych 15 zajęć laboratoryjnych,
* obecność na nich jest obowiązkowa,
* prowadzący akceptuje dwie nieusprawiedliwione nieobecności,
* prowadzący nagradza lub karze studentów za ich aktywność na zajęciach "plusami".

Listy zadań:
* każde laboratorium zawiera listę zadań do wykonania,
* każde zadanie musi zostać wykonane indywidualnie oraz przesłane na wskazane repozytorium,
* wybrane listy zadań będą oceniane, każda lista może być poprawiona dokładnie jeden raz

### Przegląd tematów w semestrze
1. Wprowadzenie do pracowni algorytmów i struktur danych
1. Budowanie algorytmów z wykładu z użyciem schematów blokowych
1. Implementacja wybranych algorytmów podanych na wykładzie w języku programowania
1. Implementacja oraz porównanie złożoności czasowej algorytmów sortowania
1. Budowa algorytmów oraz programów rekurencyjnych
1. Implementacja dynamicznych struktur danych
1. Wykonanie zadań z zakresu geometrii obliczeniowej oraz teorii grafów
1. Podsumowanie semestru

### Literatura
* Piotr Wróblewski, *Algorytmy: struktury danych i techniki programowania*, Wydawnictwo Helion 2022
* Sedgewick Robert *Algorytmy w C++*, Wydawnictwo Helion, 2012

### System kontroli wersji
Należy utworzyć konto użytkownika na platformie [Github](http://github.com/) pod adresem studenckim. Jeżeli student już posiada konto, w ustawieniach profilu można dodać drugi adres. Prowadzący doda studentów do [organizacji uczelnianej](https://github.com/collegiumwitelona), przez którą będzie się odbywała realizacja zajęć i oddawanie list.

Należy sprawdzić czy Git jest zainstalowany w systemie: najlepiej uruchomić wybraną konsolę i wpisać:
```bash
git --version
```

Jeżeli nie jest zainstalowany, należy go zainstalować.Link do .[oprogramowania](https://git-scm.com/downloads)

#### Inicjalizacja repozytorium:
Znając adres repozytorium (np. https://github.com/collegiumwitelona/2024u-aisd-twojanazwauzytkownika) oraz bedąc w  katalogu w którym chcemy utworzyć folder z repozytorium tego kursu, należy wykonać następujące polecenia:

```
git clone ... - w miejsce trzech kropek należy wstawić link do repozytorium np. (np. https://github.com/collegiumwitelona/2024u-aisd-twojanazwauzytkownika)
```

#### Wprowadzanie zmian do repozytorium
Prawdopodobnie przy pierwszych zmianach będzie trzeba dodać poświadczenia uwierzytelniające:
```
git config user.name "Imię Nazwisko"
git config user.email "imie.nazwisko@student.collegiumwitelona.pl"
```

Warto podać swoje prawdziwe dane, aby Github później przyjął żądanie. Po jakiejkolwiek zmianie, dodaniu lub usunięciu pliku, należy zapisać swoje zmiany:
```bash
git add .
git status
git commit -am "zmiany"
git push origin master
```

Kolejne polecenia oznaczają:
```
dodaje wszystkich niedodanych plików z katalogu "." do repozytorium
pokazuje stan repozytorium
tworzy commit o nazwie "zmiany"
przesyła commity na serwer
```

W momencie gdy zostaniemy poproszeni o login oraz hasło, poprzez hasło Github rozumie token, który należy sobie wygenerować.
Aby wygenerować taki token należy będąc zalogowanym przejść na adres:
https://github.com/settings/tokens

Następnie należy wybrać `Generate new token (classic)`, wypełnić niezbędne pola i wygenerowany token zapisać w bezpiecznym miejscu i korzystać z niego podczas komunikacji z Githubem.

Z poziomu narzędzi takich jak produkty JetBrains, SourceTree, GitHub Desktop czy GitKraken te same polecenia można wykonać przez graficzny interfejs użytkownika. 

### Zadanie do wykonania
W repozytorium proszę dodać:
* plik `readme.md` z podanym numerem indeksu, adresem mejlowym oraz imieniem i nazwiskiem studenta;
* katalog o nazwie `lab01` z plikiem `lab01.md`; plik powinien zawierać listę komend potrzebnych do zainicjowania repozytorium, pobrania zmian z serwera oraz wgrania nowych zmian.
