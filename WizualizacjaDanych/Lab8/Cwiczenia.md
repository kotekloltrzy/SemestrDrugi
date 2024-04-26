# Ćwiczenie 1
```python
import numpy as np
import pandas as pd

data = np.genfromtxt('jajka2024.csv', delimiter=";", dtype='|U16', encoding="UTF8")

data0 = data[1:2:, 1::]


def strtofloat(string):
    wynik = 0.00
    i = 0
    for a in string:
        if a.isnumeric():
            wynik += (int(a) * (0.1 ** i))
            i += 1
    return wynik


def srednia(tablica):
    x = 0
    wynik = 0.00
    for n in range(1, 17):
        temp = tablica[n:n+1:, 1::]
        for a in temp:
            for b in a:
                kropki = b.replace(",", ".")
                wynik += strtofloat(kropki)
                x += 1
    return round((round(wynik, 2)/x), 2)


print(f'Średnia cena jajek: {srednia(data)}')


def naj(tablica):
    najdrozsze = tablica[1:2:, 1:2:]
    najtansze = tablica[1:2:, 1:2:]
    for x in range(1, 7):
        for n in range(1, 17):
            temp = tablica[n:n+1:, x:x+1:]
            for a in temp:
                if a > najdrozsze:
                    najdrozsze = a
                if a < najtansze:
                    najtansze = a
    print(f'Najtańsze jaja: {najtansze}\nNajdroższe jaja: {najdrozsze}')


naj(data)
```
