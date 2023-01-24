## Įvadas 
Kas yra funkcija?
Funkcijos yra patogus būdas suskirstyti kodą į naudingus blokus, leidžiantis sutvarkyti kodą, padaryti jį skaitomesnį, pakartotinai naudoti ir sutaupyti šiek tiek laiko. Be to, funkcijos yra pagrindinis būdas apibrėžti sąsajas, kad programuotojai galėtų dalytis savo kodu.
Pythone funkciją apibrėžiate raktiniu žodžiu _**def**_, tada rašote funkcijos identifikatorių (pavadinimą), po kurio seka skliaustai ir dvitaškis.
Kitas dalykas, kurį turite padaryti, tai įsitikinti, kad įterpėte skirtuką arba 4 tarpus, o tada nurodykite, ką norite, kad funkcija jums atliktų.

```python
def function_name():
    # What to make the function do
```

Paprastas pavyzdys - funkcija, kuri spausdina 'Hello world':

```python
def print_smth():
    print('Hello world!')
```

Arba atspausdina atsitiktinį `int` skaičių nuo 0 iki 10:

```python
def get_random_number():
    print(random.randit(0, 10))
```
Kaip ir integruotosios funkcijos, vartotojo apibrėžtos funkcijos **kviečiamos naudojant funkcijos pavadinimą, po kurio pateikiami skliaustai** : 

```python
get_random_number() 
print_smth()
# ir taip toliau....

```