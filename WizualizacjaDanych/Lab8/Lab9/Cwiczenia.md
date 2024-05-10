```python
import matplotlib.pyplot as plt
import pandas as pd

df = pd.read_csv('penguins.csv', sep=",", header="infer")

srednia_waga_sex = df.groupby(['sex'])['body_mass_g'].mean()

print('\n', "Średnia waga płci\n", srednia_waga_sex)

srednia_waga_spec = df.groupby(['species'])['body_mass_g'].mean()

print('\n', 'Średnia waga gatunku\n', srednia_waga_spec)

najwieksza_waga = df[df['body_mass_g'] == df['body_mass_g'].max()]
najmnieszja_waga = df[df['body_mass_g'] == df['body_mass_g'].min()]
print('\n', "Najcięższy pingwin\n", najwieksza_waga)
print('\n', "Najlżejszy pingwin\n", najmnieszja_waga)

ilosc_gatunku = df.groupby(['island', 'species']).size()

print('\n', "Ilość pingwinów sortując gatunkami\n", ilosc_gatunku)

ilosc_Adelie = df[df['species'] == 'Adelie'].groupby(['island']).size()

print('\n', 'Ilość pingwinów Adelie na wyspach\n', ilosc_Adelie)

plot1 = ilosc_gatunku.plot(kind="bar", title="Ilość pingwinów na wyspach")
plt.show()

plot2 = plt.scatter(df['bill_length_mm'], df['bill_depth_mm'])
plt.show()

plot3 = df.plot.scatter('bill_length_mm', 'bill_depth_mm', s=df['body_mass_g']**5/2000**5)
plt.show()
```
