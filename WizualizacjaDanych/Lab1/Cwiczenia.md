### Ćwiczenie 1
```python
def hello_world():
    print("Witaj świecie!")

hello_wordl()
```

### ćwiczenie 6 a
```python
def tabliczka(n):
    m = abs(n)
    if 0 < m < 100:
        for a in range(0, m+1):
            for b in range(0, m+1):
                print(a*b, end='\t')
            print()
    else:
        print("n is too large")
tabliczka(int(input(f'Podaj liczbę całkowitą n: ')))
```

### Ćwiczenie 6 b
```python
import math
def ulamek(a, b):
    p = a//math.gcd(a, b)
    q = b//math.gcd(a, b)
    print(p," ",q)


ulamek(int(input(f'Podaj liczbę całkowitą a: ')),
       int(input(f'Podaj liczbę całkowitą b: ')))
```

### Ćwiczenie 6 c
```python
import math
def silnia(k):
    odp = 1
    for i in range(1, k+1):
        odp *= i
    return odp

def parametr(n):
    e1 = (1 + 1/n)**n
    e2 = 0
    for k in range(0, n+1):
        e2 += (1/silnia(k))
    print(f"e1 = {e1}, e2 = {e2}")
    print(e1 - math.e,'\n',e2 - math.e,"\n", abs(e1 - math.e),"\n", abs(e2 - math.e))

print(parametr(int(input(f'Podaj liczbę całkowitą n: '))))
```

### Ćwiczenie 6 d
```python
def najwiekszy_wspolny_dzielnik_dwoch_liczb(a, b):
    if a >= b:
        for dzielnik in range(a+1, 1, -1):
            if a%dzielnik == 0 and b%dzielnik ==0:
                return dzielnik
    else:
        for dzielnik in range(b+1, 1, -1):
            if a%dzielnik == 0 and b%dzielnik ==0:
                return dzielnik

print(najwiekszy_wspolny_dzielnik_dwoch_liczb(
    int(input(f'Podaj liczbę a: '))
, int(input(f'Podaj liczbę b: '))))
```
