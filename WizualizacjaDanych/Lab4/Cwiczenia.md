# Ćwiczenie 1
```python
names = ["michal", "nela", "ola", "przemek"]

wielkie_litery = [x.capitalize() for x in names]
print(wielkie_litery)

literka_l = [x for x in names if "l" in x]
print(literka_l)

zenskie = tuple([x for x in names if x.endswith("a")])
print(zenskie)

dlugosc = sum(len(x) for x in names)
print(dlugosc)
```
# Ćwiczenie 2
```python
cyfry = {"1": "jeden", "2": "dwa", "3": "trzy", "4": "cztery", "5": "pięć", "6": "sześć",
        "7": "siedem", "8": "osiem", "9": "dziewięć", "0": "zero"}


def ciag_cyfr(string):
    for element in string:
        if '0' <= element <= '9':
            print(f'{cyfry[element]} ', end=' ')


ciag_cyfr(str(input(f"Podaj ciąg znaków: ")))
```

# Ćwieczenie 3
```python
def iloczyn(*args):
    wynik = 1
    for element in args:
        wynik *= element
    return wynik


print(iloczyn(12, 45, 23, 36, -10))


def suma_n_poteg(n, *args):
    wynik = 0
    for element in args:
        wynik += element ** n
    return wynik


print(suma_n_poteg(2, 2, 4, 5))


def mean(*args):
    wynik = 0
    for element in args:
        wynik += element
    wynik /= len(args)
    return wynik


print(mean(4, 6))


def gmean(*args):
    wynik = 1
    for element in args:
        wynik *= element
    wynik **= 1/len(args)
    return wynik


print(gmean(2, 8))


def dlugosc_stringow(*args):
    wynik = 0
    for element in args:
        wynik += len(element)

    return wynik


print(dlugosc_stringow("ala ma kota", "kot ma ale", "mleko stoi w lodówce"))

def najmniejsza_najwieksza(*args):
    lista = list(args)
    lista.sort()
    wynik = []
    wynik.append(lista[0])
    wynik.append(lista[-1])
    odpowiedz = tuple(wynik)
    return odpowiedz

print(najmniejsza_najwieksza(12, 34, 65, 19, 1, 99, 15))
```

# Ćwiczenie 4
```python

```
