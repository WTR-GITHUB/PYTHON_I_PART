## Python `ciklai`

Python kalboje turim du primityvius ciklus:

* `while` ciklas
* `for` ciklas


### `while` ciklas

Naudodami `while` ciklą, galime vykdyti logiką tol, kol sąlyga yra teisinga:

```python
i = 0
while i < 10:
  print(i)
  i += 1
```
**Pastaba: nepamirškite padidinti `i`, kitaip ciklas tęsis amžinai**.

#### Nesibaigiantys ciklai (`infinite loop`)

Šis ciklas neleis naudotojui kaip argumentą perduoti tuščios vietos, visada lauks, kol bus kas nors įvesta:

```python
while True:
    user_input = input("Enter your name: ")
    if len(user_input) != 0:
        break
print(f"You entered {user_input }")
```

### `for` ciklas

`for` ciklas naudojamas iteruojant seką (`list`, `tuple`, 'dict' ir t.t).


Python kalboje šis ciklas kiek skiriasi nuo kitų kalbų, pagal tai kaip aprašomos sąlygos, tačiau esminė logika išlieka ta pati - iteruoti per tam tikrą rinkinį objektų. 


Naudodami `for` ciklą galime atlikti keletą veiksmų, kiekvienam `list`, `tuple`, 'set' ir t.t elementui.

#### `for` su `list`

```python
names = ["Albert", "Tom", "Leonardo"]
for name in names:
    print(f"Greetings, {name}")
```
#### `for` su `strings`

```python
name = "Code Academy"
for character in name :
    print(character)
```

#### `for` su `dict`:

```python
my_dict = {"name": "Albert", "role": "scientist"}

for key, value in my_dict.items():
    print(key, value)
```

#### `for` su  `sets`, `tuples`:

```python
names = ("Albert", "Tom", "Leonardo")
for name in names:
    print(f"Greetings, {name}")
```


```python
names = {"Albert", "Tom", "Leonardo"}
for name in names:
    print(f"Greetings, {name}")
```

### `range()` funkcija

Funkcija `range()` grąžina skaičių seką, kuri pagal numatytuosius parametrus prasideda nuo 0, didėja per 1 (arba pagal numatytą parametrą) ir sustoja prieš nurodytą skaičių.


#### Sintaksė
`range(start, stop, step)`

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


### `break`

Naudodami `break` komandą, galime sustabdyti ciklą, net jei tarkim, `while` sąlyga yra teisinga:

Šiame pavyzdyje turime apibrėžti indeksuojantį kintamąjį `i`, kurio pradinė reikšmė `0`.

```python
i = 1
while i < 6:
  print(i)
  if i == 3:
    break
  i += 1
```

### `continue`

Naudodami `continue` galime sustabdyti dabartinę iteraciją ir pradėti kitą:


```python
i = 0
while i < 6:
  i += 1
  if i == 3:
    continue
  print(i)
```

## 🧠 Pratimai

1. Sukurkite kintamuosius, kuriuose reprezentuotų vartotojo vardą ir slaptažodį. Pradėkite begalinį ciklą, leidžiantį įvesti vartotojo vardą ir slaptažodį. Jei duomenys teisingi, sustabdykite begalinį ciklą ir išspausdinkite pasisveikinimo pranešimą.
2. Leiskite naudotojui įvesti 10 sveikųjų skaičių, tada spausdinkite šių įvestų skaičių sumą ir vidurkį.
3. Sugeneruokite `dict` iš 10 skaitmenų (`keys`): 1,2,3...10. Kiekvienam `key` turėtų būti priskirta atsitiktinio sveikojo skaičiaus vertė nuo 1 iki 100.
4. Sukurkite PIN kodo nulaužimo programą. Tarkime, PIN kodą sudaro 4 atsitiktiniai skaitmenys. Reikšmę galite saugoti kintamajame. Tada sukurkite ciklą, einantį per visas galimas kombinacijas, kol rasite tą, kurią įvedėte.
5. Sukurkite programą, kuri leistų naudotojui įvesti skaičių seriją ir apskaičiuotų visų skaičių vidurkį. Programa taip pat turėtų išspausdinti visų skaičių `list'a` ir vidurkį.

## 🌐 Papildomas skaitymas:

* [Ciklai] (https://www.dataquest.io/blog/tutorial-advanced-for-loops-python-pandas/)
