# Ćwiczenie 1
```python
import numpy as np

my_array = np.array([x for x in range(10, 39, 2)])
my_array.resize(2)
dodawanie = my_array + 3
zwielokrotnij = my_array**2
my_array2 = np.array([x for x in range(10, 39, 2)])


def dzielenie_6(tabelka):
    for x in range(len(tabelka)):
        if tabelka[x] % 6 == 2:
            tabelka[x] = 0


dzielenie_6(my_array2)


def change(A, x):
    temp = A
    for n in range(len(temp)):
        if temp[n] == 0:
            temp[n] = x
    return temp


print(change(my_array2, 123))
```

# Ćwiczenie 2
```python
import numpy as np
from numpy.linalg import inv

A = np.array([(1, 1, 2), (2, 1, 0), (4, 1, 2)])
B = np.array([(2, 5, 7), (2, 8, 0), (4, 3, 1)])

dodawanie = A + B
mnozenie = A @ B
mnozenie_po_elementowe = A * B
transponowanie = np.transpose(A)
odwrocona_macierz = inv(A)
potega_elementow = A ** 5
potega_macierzy_A = A @ A @ A @ A @ A

C = np.array([1, 2, 4])
D = np.array([(2, 5, 7)])
mnozenie_D_C = D @ C
mnozenie_po_elementowe_C_D = C * D
suma_C_D = C + D

E = np.array([(1, 5), (2, 1)])
F = np.array([(2, 1), (2, 8)])
dzielenie_E_F = E/F
dzielenie_2_E_F = E//F
modulo_E_F = E % F
```

# Ćwiczenie 3
```python
import numpy as np
import pandas as pd

Panstwo = np.array(["China", "Japan", "Germany", "USA", "South Korea", "India", "Brazil", "Mexico", "Spain", "Russia"])
r1999 = np.array([0.56, 8.1, 5.3, 5.63, 2.36, 0.53, 1.1, 0.99, 2.28, 0.94])
r2014 = np.array([19.91, 8.27, 5.6, 4.25, 4.12, 3.15, 2.31, 1.91, 1.89, 1.69])

tabelka = {"Państwo": Panstwo, "1999": r1999, "2014": r2014}
gotowa_tabelka = pd.DataFrame(tabelka, index=["1", "2", "3", "4", "5", "6", "7", "8", "9", "10"])
print(gotowa_tabelka)


def procentowy_wzrost(tab1, tab2):
    for n in range(len(tab1)):
        wynik = (tab2[n] - tab1[n]) / tab1[n] * 100
        print(f"{"%.2f" % wynik}%")


procentowy_wzrost(r1999, r2014)


def najm_najw(pans, tab1, tab2):
    najw1999 = tab1[0]
    najw1999p = pans[0]
    najw2014 = tab1[0]
    najw2014p = pans[0]
    najm1999 = tab2[0]
    najm1999p = pans[0]
    najm2014 = tab2[0]
    najm2014p = pans[0]
    for n in range(len(tab1)):
        if tab1[n] > najw1999:
            najw1999 = tab1[n]
            najw1999p = pans[n]
        if tab1[n] < najm1999:
            najm1999 = tab1[n]
            najm1999p = pans[n]
        if tab2[n] > najw2014:
            najw2014 = tab2[n]
            najw2014p = pans[n]
        if tab2[n] < najw2014:
            najm2014 = tab2[n]
            najm2014p = pans[n]
    print(f"Najwiecej samochodów w 1999r: {najw1999p}: {najw1999}\n"
          f"Najmniej samochodów w 1999r: {najm1999p}: {najm1999}\n"
          f"Najwiecej samochodów w 2014r: {najw2014p}: {najw2014}\n"
          f"Najmniej samochodów w 2014r: {najm2014p}: {najm2014}\n")


najm_najw(Panstwo, r1999, r2014)

def mniej_niz_wczesniej(pans, tab1, tab2):
    for n in range(len(tab1)):
        if tab1[n] > tab2[n]:
            print(f"W {pans[n]} wyprodukowało mniej samochodów w 2014r niż w 1999r")


mniej_niz_wczesniej(Panstwo, r1999, r2014)
```

#Cwiczenie 4
```python
import numpy as np
import pandas as pd

Imiona = np.array(["Anna", "Zofia", "Sylwia", "Katarzyna", "Teresa", "Tomasz", "Cezary", "Zenon", "Filip", "Adrian"])
Wiek = np.array([21, 40, 13, 31, 34, 14, 13, 28, 20, 15])
Plec = np.array(["K", "K" ,"K" ,"K" ,"K", "M", "M", "M", "M", "M"])
Wga = np.array([65, ])
```
