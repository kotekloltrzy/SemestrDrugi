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

A = np.array([(1, 1, 2), (2, 1, 0), (4, 1, 2)])
B = np.array([(2, 5, 7), (2, 8, 0), (4, 3, 1)])

dodawanie = A + B
mnozenie = A @ B
```
