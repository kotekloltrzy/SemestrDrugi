# Ćwiczenie 1
## a)
```python
liczby_naturalne = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14]
```
## b)
```python
import math
liczby_naturalne = [0, 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14]
lista_nazwisk = ["Kowalski", "Janowski", "Broda", "Polak", "Kowal"]

piata_potega = [x**5 for x in liczby_naturalne]
print(piata_potega)


def silnia(liczba):
    wynik = 1
    for mnozenie in range(1, liczba+1):
        wynik *= mnozenie
    return wynik


silnia = [silnia(x) for x in range(0, 21)]
print(silnia)

lista_e = [math.e**x for x in range(0, 20)]
print(lista_e)

dlugosc_list = [len(x) for x in lista_nazwisk]
print(dlugosc_list)
```
## c)
```python
import math
list1=[1,2,3,4,5,6,7,8,9,10]
list2=[10,20,30,40,50,60,70,80,90,100]
lista_nazwisk = ["Kowalski", "Janowski", "Broda", "Polak", "Kowal"]
miesiace = ["Styczeń", "Luty", "Marzec", "Kwiecień", "Maj", "Czerwiec",
            "Lipiec", "Sierpień", "Wrzesień", "Październik", "Listopad", "Grudzień"]
lista_float = [12.2, 13.3, 14.4, 21.37, 6.66, 4.2, 6.9, 12.2, 12.2000000001]


print(list1+list2)

suma_wektorow = [list1[x]+list2[x] for x in range(len(list1))]
print(suma_wektorow)

miesiace.sort()
print(miesiace)

def nazwisko_litera(lista, litera):
    wynik = []
    litera = litera.upper()
    for nazwisko in lista:
        if nazwisko[0] > litera:
            wynik.append(nazwisko)
    return wynik

print(nazwisko_litera(lista_nazwisk, "j"))

nazwiska_wieksze_niz_6 = [x for x in lista_nazwisk if len(x)>6]
print(nazwiska_wieksze_niz_6)

def czy_posortowane(lista):
    if lista == sorted(lista):
        return True
    else:
        return False

print(czy_posortowane(lista_nazwisk))
print(czy_posortowane(list1))

def potega_3(lista):
    wynik = [x**3 for x in lista]
    return wynik

print(potega_3(list1))
print(potega_3(list2))

def func(list, n1, n2):
    for liczba in list:
        if liczba == n1:
            index = list.index(liczba)
            list.pop(index)
            list.insert(index, n2)
    return list

print(func(lista_float, 12.2, 59.3))

def func_altered(list, n1, n2):
    for liczba in list:
        if math.isclose(liczba, n1):
            index = list.index(liczba)
            list.pop(index)
            list.insert(index, n2)
    return list

print(func_altered(lista_float, 12.2, 59.3))
```

# Ćwiecznie 2
```python
państwa = {"Polska", "Niemcy", "Norwegia", "Dania", "Wiedeń"}
państwa.add("Polska")
print(państwa)
print("Polska" in państwa)
państwa.remove("Niemcy")
państwa2 = {"Niemcy", "Anglia", "Francja", "Polska"}
państwa3 = {"Wyspy Owcze", "Cypr", "Szkocja", "Polska"}
czesc_wspolna = państwa.intersection(państwa2)
print(czesc_wspolna)
suma_zbiorow = państwa2.union(państwa3)
print(suma_zbiorow)
roznica_zbiorow = państwa.difference(państwa2)
print(roznica_zbiorow)
państwa.issubset(państwa2)
```
# Ćwiczenie 3
```python
krotka = ("jabłko", 12, "kotek", 7, "mleko", 3, 21.37)
krotka[2] = "piesek" ### nie da sie
```
