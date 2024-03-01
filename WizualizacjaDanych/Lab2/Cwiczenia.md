# Zadanie 1
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
    wynik = ""
    index = 0
    for litera in string:
        if index % 2 == 0:
            wynik += litera
        index += 1
    return wynik

print(parzyste_indeksy(tekst))
```
### zwraca n (podano, domyslne 1) ostatnich znaki w podanym stringu;
```python
def ostatnie_znaki(string):
    n = int(input(f'Podaj n: '))
    print(string[-n])

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
def ktory_dluzszy(str1, str2):
    dlugosc1 = len(str1)
    dlugosc2 = len(str2)
    if dlugosc1 > dlugosc2:
        print("Pierwszy string jest dłużsy od drugiego")
    else:
        print("Drugi string jest dłuższy od pierwszego")

ktory_dluzszy(tekst, tekst2)
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
## Napisz program (program23.py), który na wejściu dostaje napis postaci "W Roku Pańskim 1345, władca Henryk 12, na rzecz swoich 143209 poddanych uchwalił dekret o 20 procentowej zniżce podatków." Twoim zadaniem jest wyłuskać wszystkie liczby (niech będą tylko całkowite) i wyswietlić ich sumę.
```python

```
