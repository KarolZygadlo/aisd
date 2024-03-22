## Porównanie prostych oraz szybkich metod sortowania

### Krótkie wprowadzenie do algorytmów sortowania

Algorytmy sortowania są jednymi z fundamentalnych koncepcji w informatyce, stanowiąc podstawę wielu bardziej złożonych procedur obliczeniowych. Sortowanie to proces uporządkowywania elementów w liście lub tablicy zgodnie z określonym kryterium, najczęściej wartością numeryczną lub alfabetyczną. Celem sortowania jest zorganizowanie danych w sposób, który ułatwia ich późniejsze wyszukiwanie, analizę lub wizualizację.

Sortowanie jest wszechobecne w informatyce, od prostych aplikacji takich jak organizowanie list kontaktów na smartfonie, po bardziej złożone zastosowania jak algorytmy wyszukiwania, optymalizacja baz danych i przetwarzanie danych naukowych. Ponadto, procesy sortowania są często wykorzystywane do testowania i oceny wydajności algorytmów oraz systemów komputerowych.

### Znaczenie sortowania w informatyce

Znaczenie sortowania w informatyce jest ogromne, ponieważ uporządkowane dane znacznie przyspieszają operacje wyszukiwania i dostępu. Na przykład, posortowana tablica pozwala na stosowanie efektywnego wyszukiwania binarnego, które ma logarytmiczną złożoność czasową, w przeciwieństwie do liniowego wyszukiwania w nieposortowanych danych. W kontekście baz danych, sortowanie jest kluczowe dla efektywnego wykonywania zapytań, które wymagają porządkowania wyników według określonego kryterium.

### Sortowanie proste

#### Wprowadzenie do trzech podstawowych algorytmów: exchangesort, selectionsort, insertionsort

##### Exchangesort (Sortowanie bąbelkowe)

Jest to jeden z najprostszych algorytmów sortowania. Jego idea opiera się na porównywaniu i zamienianiu miejscami sąsiednich elementów, jeśli nie są one w odpowiedniej kolejności. Proces ten jest powtarzany, aż do momentu, kiedy cała tablica zostanie posortowana. Sortowanie bąbelkowe jest łatwe do zrozumienia i implementacji, jednak nie jest zalecane dla dużych zbiorów danych ze względu na swoją niską efektywność.

###### Przykładowa implementacja w Pythonie

```python
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        swapped = False
        for j in range(0, n-i-1):
            if arr[j] > arr[j+1]:
                # Zamiana elementów
                arr[j], arr[j+1] = arr[j+1], arr[j]
                swapped = True
        # Jeśli nie wykonano żadnej zamiany, lista jest już posortowana
        if not swapped:
            break
    return arr
```

###### Analiza złożoności czasowej

- **Najgorszy i średni przypadek:** O(n^2), gdzie n jest liczbą elementów do posortowania. W tych przypadkach, dla każdego z n elementów, algorytm musi przeprowadzić porównania z każdym z pozostałych elementów.
- **Najlepszy przypadek:** O(n). Występuje to, gdy elementy są już posortowane, a algorytm po pierwszym przejściu przez listę nie wykonuje żadnej zamiany, co oznacza, że dalsze iteracje nie są już potrzebne.

##### Selectionsort (Sortowanie przez wybieranie)

W tym algorytmie, w każdej iteracji wyszukiwany jest najmniejszy (lub największy, w zależności od kierunku sortowania) element i umieszczany na odpowiednim miejscu w tablicy. Algorytm dzieli listę na dwie części: posortowaną i nieposortowaną, przenosząc za każdym razem jeden element do części posortowanej. Podobnie jak sortowanie bąbelkowe, sortowanie przez wybieranie nie jest zalecane dla dużych zbiorów danych.

###### Przykładowa implementacja w Pythonie

```python
def selection_sort(arr):
    n = len(arr)
    for i in range(n):
        # Znajdowanie indeksu najmniejszego elementu
        min_index = i
        for j in range(i+1, n):
            if arr[j] < arr[min_index]:
                min_index = j
        # Zamiana elementu z min_index z pierwszym elementem nieposortowanej części
        arr[i], arr[min_index] = arr[min_index], arr[i]
    return arr
```

###### Analiza złożoności czasowej

- **W każdym przypadku:** O(n^2), gdzie n jest liczbą elementów do posortowania. Niezależnie od początkowego uporządkowania danych, algorytm zawsze musi porównać każdy element z każdym, aby znaleźć najmniejszy element.

##### Insertionsort (Sortowanie przez wstawianie)

W tym algorytmie, elementy są sukcesywnie wybierane z nieposortowanej części listy i wstawiane na odpowiednie miejsce w części już posortowanej. Jest to proces podobny do sposobu, w jaki niektóre osoby sortują karty w ręku podczas gry. Sortowanie przez wstawianie jest bardziej efektywne niż poprzednie dwa algorytmy, szczególnie dla małych lub częściowo posortowanych zbiorów danych.

###### Przykładowa implementacja w Pythonie

```python
def insertion_sort(arr):
    for i in range(1, len(arr)):
        key = arr[i]
        j = i - 1
        # Przesuwanie elementów większych od key o jedną pozycję w prawo
        while j >= 0 and key < arr[j]:
            arr[j + 1] = arr[j]
            j -= 1
        # Wstawianie klucza na odpowiednie miejsce
        arr[j + 1] = key
    return arr
```

###### Analiza złożoności czasowej

- **Najgorszy i średni przypadek:** O(n^2), gdzie n jest liczbą elementów do posortowania. W tych przypadkach, algorytm musi porównać każdy element z większością elementów w już posortowanej części listy.
- **Najlepszy przypadek:** O(n), występuje, gdy lista jest już posortowana, i algorytm musi tylko raz przejrzeć listę, aby to stwierdzić.

### Sortowanie szybkie

#### Wprowadzenie do zaawansowanych algorytmów sortowania

Zaawansowane algorytmy sortowania stanowią kluczowy element informatyki, umożliwiając efektywne przetwarzanie i organizowanie dużych zbiorów danych. Podczas gdy podstawowe metody sortowania, takie jak sortowanie bąbelkowe czy przez wstawianie, są proste do zrozumienia i implementacji, ich wydajność znacząco spada w przypadku większych zbiorów danych. Zaawansowane algorytmy, takie jak heapsort, quicksort i mergesort, zostały opracowane, aby sprostać tym wyzwaniom, oferując znacznie lepszą wydajność, szczególnie w kontekście dużych lub złożonych zbiorów danych.

#### Krótkie omówienie znaczenia efektywnego sortowania w informatyce

Efektywne sortowanie danych ma fundamentalne znaczenie w wielu dziedzinach informatyki, od optymalizacji algorytmów wyszukiwania po analizę danych i zarządzanie bazami danych. Szybkie i skuteczne sortowanie pozwala na lepszą organizację danych, co z kolei ułatwia ich analizę, wyszukiwanie oraz wydajne przetwarzanie. W kontekście algorytmów, sortowanie wpływa na wydajność kluczowych operacji, takich jak wyszukiwanie, scalanie zbiorów danych i wielu innych operacji, które są niezbędne w codziennej praktyce informatycznej.

#### Przedstawienie trzech algorytmów: heapsort, quicksort, mergesort

##### Heapsort 

Heapsort to efektywny algorytm sortowania, który wykorzystuje strukturę danych zwaną kopcem (heap) do organizacji elementów. Kopiec to specjalny rodzaj pełnego drzewa binarnego, gdzie wartości węzłów spełniają regułę kopca: każdy węzeł jest większy (lub mniejszy) od swoich dzieci. W przypadku heapsortu najczęściej wykorzystuje się kopiec typu max-heap, gdzie wartość każdego węzła jest większa niż wartości jego dzieci.

Jest algorytmem sortowania, który wykorzystuje strukturę kopca binarnego do organizowania danych. Jest to efektywna metoda sortowania, która oferuje stałą złożoność czasową O(n log n) we wszystkich przypadkach, czyniąc ją wyjątkowo stabilną i przewidywalną pod względem wydajności.

###### Algorytm Heapsort - główne etapy

Algorytm Heapsort składa się z dwóch głównych etapów, które razem zapewniają efektywne sortowanie danych:

1. Budowanie kopca

- **Proces:** Rozpoczyna się od środkowych elementów listy wejściowej i przechodzi w kierunku jej początku.
- **Cel:** Przywrócenie własności kopca dla każdego węzła. W przypadku max-heapa, każdy rodzic ma wartość większą niż jego dzieci. Dla min-heapa, każdy rodzic ma wartość mniejszą niż jego dzieci.
- **Mechanizm:** Dla każdego węzła sprawdzane jest, czy spełnia on warunki kopca. Jeśli nie, następuje przekształcenie struktury tak, aby własności kopca zostały przywrócone.

2. Sortowanie

- **Proces:** Po zbudowaniu kopca, algorytm iteracyjnie usuwa największy element z kopca (korzeń) i umieszcza go na końcu listy.
- **Mechanizm przywracania kopca:** Po usunięciu elementu, kopiec musi zostać przywrócony. Algorytm *heapify* jest stosowany do korzenia, aby zapewnić, że największy element znajdzie się na górze kopca.
- **Iteracja:** Proces jest powtarzany - usuwanie korzenia, umieszczanie na końcu, przywracanie struktury kopca - aż wszystkie elementy zostaną usunięte z kopca i umieszczone w odpowiedniej kolejności w liście wyjściowej, co skutkuje posortowaną listą.

Te dwa etapy, budowanie kopca i sortowanie, są kluczowe dla zrozumienia i efektywnego zaimplementowania algorytmu Heapsort.

###### Przykładowa implementacja w Pythonie

```python
def heapify(arr, n, i):
    largest = i
    left = 2 * i + 1
    right = 2 * i + 2

    if left < n and arr[largest] < arr[left]:
        largest = left

    if right < n and arr[largest] < arr[right]:
        largest = right

    if largest != i:
        arr[i], arr[largest] = arr[largest], arr[i]
        heapify(arr, n, largest)

def heapsort(arr):
    n = len(arr)

    for i in range(n // 2 - 1, -1, -1):
        heapify(arr, n, i)

    for i in range(n - 1, 0, -1):
        arr[i], arr[0] = arr[0], arr[i]
        heapify(arr, i, 0)

    return arr
```

###### Analiza złożoności czasowej

Złożoność czasowa algorytmu Heapsort wynosi O(n log n) dla najlepszego, średniego i najgorszego przypadku. Jest to wynik kombinacji procesu budowania kopca (O(n)) oraz procesu sortowania (O(n log n)), gdzie n jest liczbą elementów do posortowania.

##### Quicksort

Quicksort to jeden z najbardziej znanych i szeroko stosowanych algorytmów sortowania, działający na zasadzie "dziel i zwyciężaj". Kluczowym elementem algorytmu jest wybór tzw. pivota, czyli elementu odniesienia, względem którego sortowane są pozostałe elementy listy. Lista jest dzielona na dwie podlisty: elementy mniejsze od pivota i elementy większe od pivota. Te podlisty są następnie sortowane rekurencyjnie, co prowadzi do całkowitego posortowania listy.

###### Przykładowa implementacja w Pythonie

```python
def quicksort(arr):
    if len(arr) <= 1:
        return arr
    else:
        pivot = arr[len(arr) // 2]
        less = [x for x in arr if x < pivot]
        equal = [x for x in arr if x == pivot]
        greater = [x for x in arr if x > pivot]
        return quicksort(less) + equal + quicksort(greater)
```

W tej implementacji, pivot jest wybierany jako element środkowy listy. Następnie lista jest dzielona na trzy podlisty: elementy mniejsze od pivota, równe pivotowi i większe od pivota. Podlisty mniejsze i większe są sortowane rekurencyjnie, a cała posortowana lista jest zwracana poprzez konkatenację posortowanych podlist i listy zawierającej pivota.

###### Analiza złożoności czasowej Quicksorta

- **Najlepszy i średni przypadek:** O(n log n), gdzie `n` jest liczbą elementów do posortowania. Taka złożoność jest osiągana, gdy w każdym kroku podziału lista dzielona jest na dwie mniej więcej równe części, co pozwala na efektywne wykorzystanie strategii dziel i zwyciężaj.

- **Najgorszy przypadek:** O(n^2). Do takiej sytuacji może dojść, gdy wybrany pivot jest każdorazowo najmniejszym lub największym elementem z listy, co prowadzi do niekorzystnego podziału, gdzie jedna z nowych podlist jest pusta, a druga zawiera resztę elementów. W takim przypadku, każdy kolejny krok podziału redukuje rozmiar problemu tylko o jeden, co prowadzi do kwadratowej złożoności czasowej.

Ta analiza podkreśla znaczenie odpowiedniego wyboru pivota w algorytmie Quicksort oraz wpływ tego wyboru na ogólną wydajność sortowania.


##### Mergesort

Mergesort jest algorytmem sortowania, który wykorzystuje metodę "dziel i zwyciężaj". Działa poprzez podział listy na dwie równe części, rekurencyjne sortowanie każdej z nich, a następnie scalanie posortowanych podlist w jedną uporządkowaną listę. Jest to podejście rekurencyjne, które skutecznie redukuje złożoność problemu sortowania na każdym poziomie podziału.

###### Przykładowa implementacja w Pythonie

```python
def merge_sort(arr):
    if len(arr) > 1:
        mid = len(arr) // 2
        L = arr[:mid]
        R = arr[mid:]

        merge_sort(L)
        merge_sort(R)

        i = j = k = 0

        while i < len(L) and j < len(R):
            if L[i] < R[j]:
                arr[k] = L[i]
                i += 1
            else:
                arr[k] = R[j]
                j += 1
            k += 1

        while i < len(L):
            arr[k] = L[i]
            i += 1
            k += 1

        while j < len(R):
            arr[k] = R[j]
            j += 1
            k += 1

    return arr
```

###### Analiza złożoności czasowej 

Mergesort ma złożoność czasową O(n log n) we wszystkich przypadkach, niezależnie od początkowego uporządkowania danych. Ta efektywność wynika z podziału listy na połowy i linearnego scalania, co zapewnia logarytmiczne zmniejszenie liczby porównań na każdym poziomie rekurencji.

### Zadania do wykonania

1. **Zaimplementuj sortowanie bąbelkowe:**
   - Napisz własną funkcję sortowania bąbelkowego w dowolnym języku.
   - Przetestuj ją na różnych zestawach danych, aby zobaczyć, jak działa w praktyce.

2. **Analiza sortowania przez wybieranie:**
   - Zaimplementuj sortowanie przez wybieranie.
   - Porównaj jego wydajność z sortowaniem bąbelkowym na identycznych zestawach danych.

3. **Eksperyment z sortowaniem przez wstawianie:**
   - Stwórz funkcję realizującą sortowanie przez wstawianie.
   - Zbadaj, jak dobrze radzi sobie z częściowo posortowanymi danymi w porównaniu do całkowicie losowych danych.

4. **Porównanie sortowania bąbelkowego i przez wstawianie:**
   - Porównaj czas wykonania sortowania bąbelkowego i przez wstawianie na dużych zbiorach danych.
   - Zastanów się, dlaczego jeden z nich może być szybszy od drugiego w różnych warunkach.

5. **Implementacja i analiza Quicksorta:**
   - Napisz funkcję wykonującą sortowanie szybkie.
   - Zbadaj, jak wybór pivota wpływa na wydajność algorytmu.

6. **Praktyczne zastosowanie Mergesorta:**
   - Zaimplementuj Mergesort i przetestuj jego działanie.
   - Porównaj jego użycie pamięci z Quicksortem i zastanów się, kiedy każde z nich może być bardziej odpowiednie.

7. **Heapsort w akcji:**
   - Stwórz implementację Heapsorta.
   - Zbadaj jego zachowanie na listach o różnym rozmiarze i zróżnicowanym uporządkowaniu danych.