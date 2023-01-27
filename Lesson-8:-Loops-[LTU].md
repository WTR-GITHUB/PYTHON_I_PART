# Python ciklai

Python turi dvi primityvias ciklo komandas:

* while ciklai
* for ciklai


## While ciklas

Naudodami while ciklą galime vykdyti logiką tol, kol sąlyga yra teisinga.

```python
i = 0
while i < 10:
  print(i)
  i += 1
```
**Pastaba: nepamirškite padidinti i, kitaip ciklas tęsis amžinai**.

#### nesibaigiančios ciklai (infinite loop)

Šis ciklas neleis naudotojui kaip argumentą perduoti tuščios vietos, visada lauks, kol bus kas nors įvesta.
```python
while True:
    user_input = input("Įveskite savo vardą: ")
    if len(user_input) != 0:
        break
print(f "Jūs įvedėte {user_input }")
```

## For ciklai

For ciklas naudojamas iteruojant seką (sąrašą, tuple, žodyną, rinkinį arba eilutę).


Pythone šis ciklas kiek skiriasi nuo kitų kalbų, pagal tai kaip aprašomos sąlygos, tačiau esminė logika išlieka ta pati - iteruoti per tam tikrą rinkinį objektų. 


Naudodami for ciklą galime atlikti keletą veiksmų, po vieną kartą kiekvienam sąrašo, tuple, aibės ir t. t. elementui.

#### ciklas per sąrašus
```python
names = ["Albert", "Tom", "Leonardo"]
for name in names:
    print(f "Sveiki, {pavadinimas}")
```
#### ciklas per eilutes

```python
name = "Code Academy"
for character in name :
    print(character)
```

#### prasukime ciklą per žodynus:

```python
my_dict = {"name": "Albert", "role": "Albert": "Albert", "Albert", "Albert", "Albert", "Albert", "Albert".}

for key, value in my_dict.items():
    print(key, value)
```

#### ciklas per setus, tuples:
Tai lygiai tas pats, kaip ir su sąrašais
```python
names = ("Albert", "Tom", "Leonardo")
for name in names:
    print(f "Sveiki atvykę, {pavadinimas}")
```


```python
names = {"Albert", "Tom", "Leonardo"}
for name in names:
    print(f "Sveiki atvykę, {pavadinimas}")
```

## range() funkcija

Funkcija range() grąžina skaičių seką, kuri pagal numatytuosius nustatymus prasideda nuo 0, didėja 1 (pagal numatytuosius nustatymus) ir sustoja prieš nurodytą skaičių.


#### Sintaksė
range(start, stop, step)

| argumentas| reikšmė |
| ------------- | ------------- |
| start | Neprivaloma. Sveikasis skaičius, nurodantis, nuo kurios pozicijos pradėti. Numatytoji reikšmė yra 0 |
| stop | Būtina. Sveikasis skaičius, nurodantis, kurioje pozicijoje reikia sustoti (neįskaičiuota).  |
| žingsnis | Neprivaloma. Sveikasis skaičius, nurodantis žingsnio didinimą. Numatytoji reikšmė yra 1 |


```python
x = range(3, 6)
for n in x:
  print(n)
```

```python
for n in range(10):
  print(n)
```


## break

Naudodami break sakinį galime sustabdyti ciklą, net jei while sąlyga yra teisinga:

Šiame pavyzdyje turime apibrėžti indeksuojantį kintamąjį i, kurį nustatome į 0.

```python
i = 1
while i < 6:
  print(i)
  if i == 3:
    break
  i += 1
```

## tęsti

Naudodami teiginį continue galime sustabdyti dabartinę iteraciją ir tęsti kitą:


```python
i = 0
while i < 6:
  i += 1
  if i == 3:
    continue
  print(i)
```

## 🧠 Pratimai

1. Sukurkite kintamuosius, kuriuose būtų vartotojo vardo ir slaptažodžio stringai. Pradėkite begalinį ciklą, leidžiantį įvesti vartotojo vardą ir slaptažodį. Jei duomenys teisingi, sustabdykite begalinį ciklą ir išspausdinkite pasisveikinimo pranešimą.
1. Leiskite naudotojui įvesti 10 sveikųjų skaičių, tada spausdinkite šių įvestų skaičių sumą ir vidurkį.
1. Sugeneruokite 10 raktų žodyną: 1,2,3...10. Kiekviename iš jų turėtų būti įrašyta atsitiktinio sveikojo skaičiaus vertė nuo 1 iki 100.
1. Sukurkite PIN kodo nulaužimo programą. Tarkime, PIN kodą sudaro 4 atsitiktiniai skaitmenys. Reikšmę galite saugoti kintamajame. Tada sukurkite ciklą, einantį per visas galimas kombinacijas, kol rasite tą, kurią įvedėte.

## 🌐 Papildomas skaitymas:

* [daugiau apie ciklus] (https://www.dataquest.io/blog/tutorial-advanced-for-loops-python-pandas/)
