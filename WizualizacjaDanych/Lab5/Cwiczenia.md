# Ćwiczenie 1
```python
class Car:
    def __init__(self, marka, rok):
        self.marka = marka
        self.rok = rok


car1 = Car("Toyota", 2002)
car2 = Car("Opel", 1999)

print(car1.marka, car1.rok, car2.marka, car2.rok)
car1 = car2
print(car1.marka, car1.rok, car2.marka, car2.rok)
```

# Ćwiczenie 2
```python
class Fruit:
    def __init__(self, weight, color="Red"):
        self.color = color
        self.weight = weight

    def isfresh(self, color):
        if color is self.color:
            return True
        return False


Apple = Fruit(1)
Banana = Fruit(5, "Yellow")
Orange = Fruit(1, "Orange")
print("Apple", Apple.color, Apple.weight, ", Banana", Banana.color, Banana.weight,
      ", Orange", Orange.color, Orange.weight)
print(Apple.isfresh("Green"), Banana.isfresh("Yellow"), Orange.isfresh("Orange"))
```

# Ćwiczenie 3
```python
class Account:
    def __init__(self, numer_konta, saldo=0):
        self.saldo = saldo
        self.numer_konta = numer_konta

    def przelew_miedzy_kontami(self, konto_odbiorcy):
        kwota = int(input(f'Podaj kwotę przelewu z konta {self.numer_konta} na konto {konto_odbiorcy.numer_konta}: '))
        if kwota > self.saldo:
            print("Niewystarczające środki na koncie")
            return
        self.saldo -= kwota
        konto_odbiorcy.saldo += kwota
        print(self.numer_konta, ": ", self.saldo)
        print(konto_odbiorcy.numer_konta, ": ", konto_odbiorcy.saldo)

    def przelew_zewnetrzny(self):
        adres = str(input(f'Podaj numer konta na który chcesz zrobić przelew: '))
        kwota = int(input(f'Podaj kwotę przelewu z konta {self.numer_konta} na konto {adres}: '))
        if kwota > self.saldo:
            print("Niewystarczające środki na koncie")
            return
        self.saldo -= kwota
        print(self.numer_konta, ": ", self.saldo)

    def wplata(self):
        kwota = int(input(f'Podaj kwotę wpłaty na konto {self.numer_konta}: '))
        self.saldo += kwota
        print(self.numer_konta, ": ", self.saldo)

    def wyplata(self):
        kwota = int(input(f'Podaj kwotę wypłaty z konta {self.numer_konta}: '))
        if kwota > self.saldo:
            print("Niewystarczające środki na koncie")
            return
        self.saldo -= kwota
        print(self.numer_konta, ": ", self.saldo)


Andrzej = Account(2137, 10000)
Janusz = Account(1234, 1500)
Jan = Account(4444, 4444)
print(Andrzej.numer_konta, ": ", Andrzej.saldo)
print(Janusz.numer_konta, ": ", Janusz.saldo)
print(Jan.numer_konta, ": ", Jan.saldo)
Andrzej.przelew_miedzy_kontami(Janusz)
Jan.wplata()
Janusz.wyplata()
print(Andrzej.numer_konta, ": ", Andrzej.saldo)
print(Janusz.numer_konta, ": ", Janusz.saldo)
print(Jan.numer_konta, ": ", Jan.saldo)
```
# Ćwiczenie 4
```python
class Romanian:
    def __init__(self, liczba):
        self.liczba = liczba

    def zamiana_na_rzymskie(self):
        jednosci = {"1": "I", "2": "II", "3": "III", "4": "IV", "5": "V", "6": "VI", "7": "VII", "8": "VIII", "9": "IX"}
        dziesiatki = {"1": "X", "2": "XX", "3": "XXX", "4": "XL", "5": "L", "6": "LX", "7": "LXX", "8": "LXXX", "9": "XC"}
        setki = {"1": "C", "2": "CC", "3": "CCC", "4": "CD", "5": "D", "6": "DC", "7": "DCC", "8": "DCCC", "9": "CM"}
        tysiace = {"1": "M", "2": "MM", "3": "MMM"}
        rzymska = ""

        for cyfra in str(self.liczba):
            if self.liczba >= 1000:
                if cyfra != "0":
                    rzymska += tysiace[cyfra]
                    self.liczba -= int(cyfra)*1000
                    continue
            if self.liczba >= 100:
                if cyfra != "0":
                    rzymska += setki[cyfra]
                    self.liczba -= int(cyfra) * 100
                    continue
            if self.liczba >= 10:
                if cyfra != "0":
                    rzymska += dziesiatki[cyfra]
                    self.liczba -= int(cyfra) * 10
                    continue
            if cyfra != "0":
                rzymska += jednosci[cyfra]
                self.liczba -= int(cyfra)
                continue
        return rzymska

    def sprawdzanie(self):
        lista = list(self.liczba)
        for n in range(len(lista)):
            if lista[n] == "I":
                if len(lista) >= 2:
                    if lista[n+1] == "X":
                        return 9
                    if lista[n+1] == "I":
                        if len(lista) >= 3:
                            if lista[n+2] == "I":
                                return 3
                        return 2
                    if lista[n+1] == "V":
                        return 4
                return 1
            if lista[n] == "V":
                if len(lista) >= 2:
                    if lista[n+1] == "I":
                        if len(lista) >= 3:
                            if lista[n+2] == "I":
                                if len(lista) >= 4:
                                    if lista[n+3] == "I":
                                        return 8
                                return 7
                        return 6
                return 5
            if lista[n] == "X":
                if len(lista) >= 2:
                    if lista[n+1] == "C":
                        return 90
                    if lista[n+1] == "X":
                        if len(lista) >= 3:
                            if lista[n+2] == "X":
                                return 30
                        return 20
                    if lista[n+1] == "L":
                        return 40
                return 10
            if lista[n] == "L":
                if len(lista) >= 2:
                    if lista[n+1] == "X":
                        if len(lista) >= 3:
                            if lista[n+2] == "X":
                                if len(lista) >= 4:
                                    if lista[n+3] == "X":
                                        return 80
                                return 70
                        return 60
                return 50
            if lista[n] == "C":
                if len(lista) >= 2:
                    if lista[n+1] == "M":
                        return 900
                    if lista[n+1] == "C":
                        if len(lista) >= 3:
                            if lista[n+2] == "C":
                                return 300
                        return 200
                    if lista[n+1] == "D":
                        return 400
                return 100
            if lista[n] == "D":
                if len(lista) >= 2:
                    if lista[n+1] == "C":
                        if len(lista) >= 3:
                            if lista[n+2] == "C":
                                if len(lista) >= 4:
                                    if lista[n+3] == "C":
                                        return 800
                                return 700
                        return 600
                return 500
            if lista[n] == "M":
                if len(lista) >= 2:
                    if lista[n + 1] == "M":
                        if len(lista) >= 3:
                            if lista[n + 2] == "M":
                                return 3000
                        return 2000
                return 1000
    # jednosci = {"I": 1, "II": 2, "III": 3, "IV": 4, "V": 5, "VI": 6, "VII": 7, "VIII": 8, "IX": 9}
    # dziesiatki = {"X": 1, "XX": 2, "XXX": 3, "XL": 4, "L": 5, "LX": 6, "LXX": 7, "LXXX": 8, "XC": 9}
    # setki = {"C": 1, "CC": 2, "CCC": 3, "CD": 4, "D": 5, "DC": 6, "DCC": 7, "DCCC": 8, "CM": 9}
    # tysiace = {"M": 1, "MM": 2, "MMM": 3}


Liczba = Romanian(int(input(f'Podaj liczbę między 3999 a 1: ')))
Rzymska = Romanian(str(input(f'Podaj liczbę rzysmką: ')))

print(Liczba.zamiana_na_rzymskie())
print(Rzymska.sprawdzanie())
```
