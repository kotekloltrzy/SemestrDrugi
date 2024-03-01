# Zadanie 1
## a) Utwórz plik program21.py
### Czy wiesz, co robią funkcje sufit i podłoga ( math.ceil(), math.floor() )? Porównaj z funkcją round()
```python
import math
liczba = 12.4
print(math.ceil(liczba))
print(math.floor(liczba))
print(round(liczba))
```
### Przeczytaj różnicę pomiędzy math.fmod(x, y) oraz x%y. Napisz funkcje, która zwraca x%y jeżeli x,y są integer oraz math.fmod(x, y) jeżeli chociażby jeden z nich jest float.
```python
def modulo(liczba1, liczba2):
    if isinstance(liczba1, float) or isinstance(liczba2, float):
        print(math.fmod(liczba1, liczba2))
    else:
        print(liczba1 % liczba2)


modulo(liczba, y)
```
### Napisz funkcje, która dla podanych liczb a, n wypisuje na konsoli w jednym wierszu logka dla każdego k od 2 do n, podzielone separatorem |.
```python
def logarytmy(a, n):
    for k in range(2, n+1):
        print(math.log(a, k), end=" | ")
        
        
logarytmy(10, 5)
```
### Napisz funkcje, która dla podanej liczby a zwraca math.exp(a), math.e**a, math.pow(math.e, a)
```python
def potega(a):
    print(math.exp(a))
    print(math.e**a)
    print(math.pow(math.e, a))

potega(10)
```

## b) Ćwiczyć przy pomocy Python Console.
### Znaleźć przykład, dla którego wynik math.pow() różni się od wynika ∗∗.
```python

```
### Znaleźć przykład, dla którego wynik math.remainder() różni sie od wynika %.
```python

```
### Co to jest za funkcje cosh oraz sinh? Sprawdź, czy na ile ich wyniki róznią sie od obliczenia według definicji (można spróbować uzywać math.isclose()).
```python
print(math.cosh(1))
print(math.sinh(1))
```

# Zadanie 2
## a) Stwórz zmienną str i przypisz jej dowolny długi string (mający co najmniej 20 znaków). Pracuj na konsoli
### wyświetl znak o indeksie 12
```python
string = 'kotek lubi pić mleczko'
print(string[12])
```
### wykonaj znane operacje arytmetyczne na stringach i ich wynik wy±wietl na konsoli.
```python
print(string[0:5])
```
### wyswietl dlugosc stringu
```python
print(len(string))
```
### Po¢wicz inny funkcje dla string. Zwróć uwaga na mo»liwo±ci używania indeksów.
```python
print(string[-7:-1])
```
## b) Napisz program (program22.py) z funkcjami, które:
### zwraca string ze znakami o parzystym numerze indeksu w podanym stringu
```python
tekst = "kotek lubi pić mleczko"


def parzyste_indeksy(string):
    print(string[::2])


parzyste_indeksy(tekst)
```
### zwraca n (podano, domyslne 1) ostatnich znaki w podanym stringu;
```python
def ostatnie_znaki(string, n=1):
    print(string[-n:])


ostatnie_znaki(tekst)
```
### pobiera string i zwraca string, powstały z odwrócenia kolejno±ci znaków;
```python
def odwrocony_string(string):
    wynik = ''
    for a in string:
        wynik = a + wynik
    return wynik

print(odwrocony_string(tekst))
```

### sprawdza, czy zdanie jest palindromem
```python
def czy_palindrom(string):
    odwrocony_tekst = odwrocony_string(string)
    if odwrocony_tekst == string:
        print("String jest palindromem")
    else:
        print("String nie jest palindromem")

czy_palindrom(tekst)
```

### pobiera 2 stringa i zwraca, które jest dłuższy (1 czy 2);
```python
def ktory_dluzszy(str1):
    str2 = str(input(f'Podaj tekst: '))
    dlugosc1 = len(str1)
    dlugosc2 = len(str2)
    if dlugosc1 > dlugosc2:
        print("Pierwszy string jest dłużsy od drugiego")
    if dlugosc1 < dlugosc2:
        print("Drugi string jest dłuższy od pierwszego")
    else:
        print("Oba stringi są tej samej długości")

ktory_dluzszy(tekst)
```

### Napisz funkcję, która wstawi podane imie i datę urodzenia do stringu 'My name is ... . My date of birth is... .'
```python
def formatowanie():
    name = str(input(f'Podaj swoje imię: '))
    birthdate = str(input(f'Podaj swoją datę urodzenia: '))
    print(f'My namie is {name}. My date of birth is {birthdate}.')

formatowanie()
```

# Zadanie 3
## Napisz program (program23.py), który na wejściu dostaje napis postaci "W Roku Pańskim 1345, władca Henryk 12, na rzecz swoich 143209 poddanych uchwalił dekret o 20 procentowej zniżce podatków." Twoim zadaniem jest wyłuskać wszystkie liczby (niech będą tylko całkowite) i wyswietlić ich sumę.
```python
napis = "W Roku Pańskim 1345, władca Henryk 12, " \
        "na rzecz swoich 143209 poddanych uchwalił dekret o 20 procentowej zniżce podatków."
print(napis)

def liczby(string):
    cyfry = ''
    wynik = 0
    for litera in string:
        if litera.isnumeric():
            cyfry += litera
    for a in cyfry:
        wynik += int(a)
    print(wynik)


liczby(napis)
```
