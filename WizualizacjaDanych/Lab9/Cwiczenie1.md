```python
import numpy as np
import matplotlib.pyplot as plt
import math

x = np.linspace(-10, 10, 100)
y = (1/(1+x**2))
plt.plot(x, y, 'green', linestyle="solid", label="1/1+x^2")
plt.legend(title='Wykres')
plt.show()

x2 = np.linspace(0, 3)
y2 = x2**2
y3 = math.e**x2
y4 = x2**x2
plt.subplot(3, 1, 1)
plt.plot(x2, y2, 'green', linestyle='dashed', label="x^2")
plt.subplot(3, 1, 2)
plt.plot(x2, y3, 'red', linestyle='dotted', label="e^x")
plt.subplot(3, 1, 3)
plt.plot(x2, y4, 'blue', linestyle='solid', label="x^x")
plt.legend(title='Wykres')
plt.show()

x3 = np.linspace(0, 4)
y5 = x3**2
y6 = math.e**x3
y7 = x3**x3
plt.subplot(3, 1, 1)
plt.plot(x3, y5, 'green', linestyle='dashed', label="x^2")
plt.subplot(3, 1, 2)
plt.plot(x3, y6, 'red', linestyle='dotted', label="e^x")
plt.subplot(3, 1, 3)
plt.plot(x3, y7, 'blue', linestyle='solid', label="x^x")
plt.legend(title='Wykres')
plt.show()
```
