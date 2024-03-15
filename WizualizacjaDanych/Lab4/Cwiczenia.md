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
        return min(args), max(args)

print(najmniejsza_najwieksza(12, 34, 65, 19, 1, 99, 15))
```

# Ćwiczenie 4
```python
def imie_numer_telefonu(**kwargs):
    for n in kwargs:
        print(n, "ma numer", kwargs[n])


imie_numer_telefonu(Michal="123456789", Kuba="987654321")


def srednie_zarobki(**kwargs):
    wynik = 0
    ilosc_miesiecy = 0
    for n in kwargs:
        wynik += int(kwargs[n])
        ilosc_miesiecy += 1
    wynik /= ilosc_miesiecy
    return wynik


print(srednie_zarobki(Styczen="123456", Luty="654321", Marzec="100000", Kwiecien='150000'))
```

# Ćwiczenie 5
```python
def czy_pesel(string):
    if len(string) != 11:
        print("Podano za mało znaków, porządana liczba ma 11 znaków")
        return False
    if string.isnumeric():
        return True
    print("Podany ciąg znaków jest o złym formacie, należy podać ciąg cyfr.")


def data_urodzenia(string):
    if czy_pesel(string):
        rok = string[0:2]
        miesiac = string[2:4]
        dzien = string[4:6]
        if 80 < int(miesiac) < 93:
            rok = 1800 + int(string[0:2])
            miesiac = int(miesiac) - 80
        if 0 < int(miesiac) < 13:
            rok = 1900 + int(string[0:2])
            miesiac = int(miesiac)
        if 20 < int(miesiac) < 33:
            rok = 2000 + int(string[0:2])
            miesiac = int(miesiac) - 20
        if 40 < int(miesiac) < 53:
            rok = 2100 + int(string[0:2])
            miesiac = int(miesiac) - 40
        if 60 < int(miesiac) < 73:
            rok = 2200 + int(string[0:2])
            miesiac = int(miesiac) - 60
        print(f"Data urodzenia: {rok}/{miesiac}/{dzien}")


def plec_pesel(string):
    plec = string[10]
    if int(plec) % 2 == 0:
        wynik = "Kobieta"
    wynik = "Mężczyzna"
    print(f'Płeć: {wynik}')


def cyfra_kontrolna(string):
    jeden = 0
    index = {1: 1, 2: 3, 3: 7, 4: 9, 5: 1, 6: 3, 7: 7, 8: 9, 9: 1, 10: 3, 11: 1}
    miejsce = 0
    for element in string[0:10]:
        miejsce += 1
        jeden += int(element) * index[miejsce]
    dwa = jeden % 10
    trzy = 10 - dwa
    if dwa != 0:
        if string[10] == trzy:
            print("Podany pesel jest prawidłowy")
            return True
    elif dwa == 0:
        if int(string[10]) == 0:
            print("Podany pesel jest prawidłowy")
            return True
        else:
            print("Podany pesel nie jest prawidłowy")
            return False
    else:
        print("Podany pesel nie jest prawidłowy")
        return False


def pesel(string):
    if czy_pesel(string):
        data_urodzenia(string)
        plec_pesel(string)
        cyfra_kontrolna(string)
    return(czy_pesel(string) and cyfra_kontrolna(string))


a = pesel("03250800510")
print(a)

```
