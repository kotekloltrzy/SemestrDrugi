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
