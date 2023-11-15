## Duomenų struktūros, Specialūs metodai

Šioje paskaitoje apžvelgsime kai kurias papildomas `python` integruotų duomenų struktūrų funkcijas. Taip pat apžvelgsime **`math`** biblioteką

### `list comprehensions`

Tai labai naudingas būdas padaryti `ciklus` kompaktiškesnius / skaitomesnius / suprantamesnius. 

Pavyzdys:

Tarkime, norime, kad programa mums atspausdintų pirmųjų 10 skaitmenų kvadratus:

```python
squares = []
for number in range(10):
    squares.append(number * number)
print(squares)
```

Tai puikiai veikia, tačiau yra šiek tiek gražesnis būdas tai užrašyti:

```python
squares = [number * number for number in range(10)]
print(squares)
```

Čia matome:

1. `squares` sukuriamas kaip `list`.
2. `list` viduje rašome, kad per ciklą peržiūrime visus skaičius, esančius `range(10)`
3. Kiekvienas objektas `list'e` bus tas skaičius, padaugintas iš jo paties: `number * number `


O jeigu norėtume turėti visus kvadratus, išskyrus 25?:

```python
squares = [number * number for number in range(10) if number != 5]
print(squares)
```

Paprasta, bet efektyvu! 

Dabar pabandykite patys parašyti `list` `comprehension'ą`, kuris grąžintų tik lyginių skaičių tobulus kvadratus:

Atsakymas
```python
squares = [number * number for number in range(10) if number % 2 == 0]
print(squares)
```

Taip pat galima daryti ir su `string` tipo reikšmėmis:

```python
names = ["Albert", "Alma", "Joseph", "Zoro"]
print([name for name in names if name.startswith("A")])
```

Naudodami **and** ir **or** išlygas, galite apjungti ir daugiau loginių grandinių:

```python
names = ["Albert", "Alma", "Joseph", "Zoro"]
print([name for name in names if name.startswith("A") or "e" in name])
```

Kaip matote, čia galite sujungti tiek logikos, kiek tik norite. Tačiau geriausia, kad `list` comprehension'ai būtų kuo trumpesni, nes jei logikos čia bus per daug, gali būti sunku tai suprasti.

#### **Pastaba** ❗ `list`, `set`, `tuple` comprehensions veikia lygiai taip pat, išskyrus tai, kad skiriasi išoriniai skliaustai, visa kita lieka tas pats.


### `dictionary comprehension`

`dict` taip pat turi šią įmantrią vienos eilutės comprehension sintaksę:

Tarkime, turime tą pačią užduotį su kvadratais, bet norime turėti tokią struktūrą  _number: percect_square_: **`{1: 1, 2: 4, 3: 9}`**.


Pavyzdys:

```python
squares = {i: i * i for i in range(10)}
print(squares)
```

### `Enumerate`

Įsivaizduokime, kad turime python ciklą per tam tikrus sąrašo elementus:

```python
values = ["a", "b", "c"]

for value in values:
    print(value)
```

Tai paprastas ciklas. Dabar įsivaizduokite, kad taip pat norite gauti atitinkamą elemento indeksą. Kaip tai padarytumėte?

Galėtumėte padaryti kažką panašaus į tai:

```python
values = ["a", "b", "c"]
index = 0

for value in values:
    print(index, value)
    index += 1
```

Taigi, čia turime sveikąjį skaičių, kuris didėja su kiekviena iteracija, ir tai taip pat veikia. Tačiau, kad mūsų kodas būtų paprastesnis, galime naudoti python built in funkciją **`enumerate()`**


```python
values = ["a", "b", "c"]
for count, value in enumerate(values):
    print(count, value)
```

Jei norėtume pakeisti pradinį skaičių:

```python
values = ["a", "b", "c"]
for count, value in enumerate(values, start=1):
    print(count, value)
```

Jei šiek tiek pasistengsime, galėsime sujungti du dalykus, kuriuos šiandien išmokome:
```python
def even_items(numbers: list) -> list]:
    return [v for i, v in enumerate(numbers, start=1) if not i % 2]

seq = list(range(1, 11))

print(even_items(seq))
```

Pamėginkite suprasti kas čia vyksta. Patarimas: judėti nuo smulkiausiu detalių kaip pvz suprasti ką daro `enumerate`, sujungti detalę po detalės kol bus viskas aišku,

**SVARBU** `enumerate()` grąžina iteratorių, todėl, jei norite pažiūrėti, kas yra viduje, galite jį pravesti pro ciklą ir printinti kiekvieną elementą  arba konvertuoti į `list`.


### `math` biblioteka

Daugumai dalykų susijusių su matematika galite naudoti python `math` biblioteką:

```python
importuoti math
```

Pavyzdžiui, jei norite apskaičiuoti apskritimo plotą:

```python
import math
area = 5 * 5 * math.pi
```

`math.pi` čia yra kontanta, kurią galime naudoti tiesiai iš dėžutės.

Daugiau pavyzdžių:

#### `factorial`

Pavyzdžiui, jei norėtume apskaičiuoti faktorialą: `7! = 7 * 6 * 5 * 4 * 3 * 2 * 1`

Galėtume patys pasirašyti funkciją, bet iš tikrųjų ji jau yra mums prieinama:

```python
import math
math.factorial(7)
```

Be to, šita biblioteka yra gana gerai optimizuotas.


#### `ceil()` ir `floor()`

Jei turite `float` reikšmę, ši funkcija gali pažodžiui gauti jos `ceil()` arba `floor()`. Pavyzdžiai:


```python
import math


print(math.ceil(6.1))

print(math.floor(-11.1))
```

Ar viskas aišku?


#### `power function`


Tarkime, norite, kad skaičius būtų padidintas n'tuoju laipsniu: 5^5 = 5 * 5 * 5 * 5 * 5 * 5 * 5 = 3125:

```python
import math

print(math.pow(5, 5))
```


#### `square root`


````python
importuoti math
print (math.sqrt(9))
```

Math bibliotekoje, kaip minėta anksčiau, yra daug daugiau funkcionalumo. Čia apžvelgėme tik mažą visos bibliotekos dalį. Bet esmė ta, kad jei turite ką nors bendro su matematika, logaritmais, kampų skaičiavimu, trigonometrija ir pan. - naudokite šia biblioteką.



## Pratimai 🧠 :

1. Raskite visus skaičius nuo 1 iki 1000, kurie dalijasi iš 6.
2. Raskite visus skaičius iš 1-1000, kuriuose yra 9.
3. Sukurkite `string` iš daugybės žodžių: Apskaičiuokite, kiek žodžių turi raidę `e`.
4. Naudodami tą patį `string`, kaip ir ankstesniame pratime: apskaičiuokite raidžių, kurios turi daugiau nei 5 simbolius, skaičių.
5. Parašykite programą, kuri patikrintų, ar duotas skaičius yra tobulasis kvadratas.

## 🌐 Papildomas skaitymas:

* [Real Pyhton comprehensions](https://realpython.com/list-comprehension-python/)

* [Real Python math](https://realpython.com/python-math-module/)
***