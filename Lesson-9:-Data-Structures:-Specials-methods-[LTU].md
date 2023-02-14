# Duomenų struktūros, Specialūs metodai

Šioje paskaitoje apžvelgsime kai kurias papildomas python integruotų duomenų struktūrų funkcijas. Taip pat apžvelgsime **`math`** biblioteką

## list comprehensions

Tai labai naudingas būdas padaryti ciklus kompaktiškesnius / skaitomesnius / suprantamesnius. 

Pavyzdys:

Tarkime, norite programos, kuri gautų pirmuosius 10 tobulų kvadratų, kaip tai padaryti?

```python
squares = []
for number in range(10):
    squares.append(number * number)
print(squares)
```

Tai puikiai veikia, tačiau yra šiek tiek gražesnis būdas tai užrašyti, kuris yra dar suprantamesnis žmogui:

```python
squares = [number * number for number in range(10)]
print(squares)
```

Argi ne gražu? Viskas, ką ji daro:

1. sukuria squares kaip sąrašą.
1. sąrašo viduje rašoma, kad per ciklą peržiūrime visus skaičius, esančius `range(10)`
1. kiekvienas objektas sąraše bus tas ciklo skaičius, padaugintas iš jo paties: `number * number `


Dar daugiau, o kas, jei norėtume turėti visus tobulus kvadratus, išskyrus 25? Pabandykite tai užrašyti be sąrašo supratimo.

Įgyvendinimas su sąrašo supratimu:

```python
squares = [number * number for number in range(10) if number != 5]
print(squares)
```

**Bum**, paprasta, bet efektyvu ir vis dar labai suprantama žmogui. 

Dabar pabandykite patys parašyti list comprehension'ą, kuris grąžintų tik lyginių skaičių tobulus kvadratus:




Atsakymas
```python
squares = [number * number for number in range(10) if number % 2 == 0]
print(squares)
```

Gerai, kol kas tokius skaičius matėme tik su sveikaisiais skaičiais, bet ar galime dirbti ir su string reikšmėmis? Žinoma!

Tarkime, turite vardų sąrašą ir norite išfiltruoti tik tuos, kurie prasideda tam tikra raide:

```python
names = ["Albert", "Alma", "Joseph", "Zoro"]
print([name for name in names if name.startswith("A")])
```

Naudodami **and** ir **or** išlygas, galite apjungti ir daugiau loginių grandinių:

```python
names = ["Albert", "Alma", "Joseph", "Zoro"]
print([name for name in names if name.startswith("A") or "e" in name])
```

Kaip matote, čia galite sujungti tiek logikos, kiek tik norite. Tačiau geriausia, kad list comprehension'ai būtų kuo trumpesni, nes jei logikos čia bus per daug, po poros dienų ji gali tapti nesuprantama net jums patiems...

#### **Pastaba** ❗ list, set, tuple comprehensions veikia lygiai taip pat, išskyrus tai, kad skiriasi išoriniai skliaustai, visa kita lieka tas pats.


## ## dictionary comprehensions

Žodynai taip pat turi šią įmantrią vienos eilutės comprehension sintaksę:

Tarkime, turime tą pačią tobulų kvadratų problemą, bet norime turėti tokią struktūrą _number: percect_square_: **`{1: 1, 2: 4, 3: 9}`**
Pabandykite patys tai parašyti be dictionary comprehension.


dictionary comprehension pavyzdys:

```python
squares = {i: i * i for i in range(10)}
print(squares)
```

Pabandykite atlikti abu pratimus kuriuos darėm su sąrašais:
1. Programa be tobulo kvadrato 5.
1. tik nelyginių skaičių tobuli kvadratai.

## Enumerate

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

Taigi čia turime sveikąjį skaičių, kuris didėja su kiekviena iteracija, ir tai taip pat veikia. Tačiau, kad mūsų kodas būtų paprastesnis, galime naudoti python build int funkciją **`enumerate()`**


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


Jei šiek tiek pasistengsime, galėsime sujungti du dalykus, kurių šiandien išmokome:
```python
def even_items(numbers: list) -> list]:
    return [v for i, v in enumerate(numbers, start=1) if not i % 2]

seq = list(range(1, 11))

print(even_items(seq))
```

Pamėginkite suprasti kas čia vyksta. Patarimas: judėti nuo smulkiausiu detalių kaip pvz suprasti ką daro enumerate čia, sujungti detalę po detalės kol bus viskas aišku,

**SVARBU** enumerate() grąžina iteratorių, todėl, jei norite pažiūrėti, kas yra viduje, galite jį pravesti pro ciklą ir printinti kiekvieną elementą  arba konvertuoti į sąrašą.


## math biblioteka

Daugumai dalykų susijusių su matematika galite naudoti python `math` biblioteką. Tai yra integruota biblioteka, kad pradėti ją naudoti tiesiog:

```python
importuoti math
```

viskas.

Pavyzdžiui, jei norite apskaičiuoti apskritimo plotą:

```python
import math
area = 5 * 5 * math.pi
```

math.pi čia yra kontanta, kurią galime naudoti tiesiai iš dėžutės.

Yra daugybė kitų funkcijų, galėtume praleisti visą dieną apžvelgdami šią biblioteką, nes ji didžiulė, tačiau panagrinėkime dar kelias funkcijas.

#### faktorialas

Pavyzdžiui, jei norėtume apskaičiuoti faktorialą: `7! = 7 * 6 * 5 * 4 * 3 * 2 * 1`

Galėtume patys parašyti funkciją, bet iš tikrųjų ji jau yra mums prieinama:

```python
import math
math.factorial(7)
```

Be to, jis iš tikrųjų yra gana gerai optimizuotas.


#### ceil() ir floor()

Jei turite float reikšmę, ši funkcija gali pažodžiui gauti jos "grindis" arba "lubas". Pavyzdžiai:


```python
import math


print(math.ceil(6.1))

print(math.floor(-11.1))
```

Ar viskas aišku?


#### kelimo n-uoju laipsniu funkcija


Tarkime, norite, kad skaičius būtų padidintas n galingumu: 5^5 = 5 * 5 * 5 * 5 * 5 * 5 * 5 = 3125

Atlikite tai be math bibliotekos.

su matematika:


```python
import math

print(math.pow(5, 5))
```


#### kvadratinė šaknis


````python
importuoti math
print (math.sqrt(9))
```

Math bibliotekoje, kaip minėta anksčiau, yra daug daugiau dalykų, čia apžvelgėme tik mažą visos bibliotekos dalį. Bet esmė ta, kad jei turite ką nors bendro su matematika, logaritmais, kampų skaičiavimu, trigonometrija ir pan. - naudokite šia biblioteką.


## 🌐 Papildomas skaitymas:

* [Real Pyhton comprehensions](https://realpython.com/list-comprehension-python/)

* [Real Python math](https://realpython.com/python-math-module/)
***


## Pratimai 🧠 :

1. Raskite visus skaičius nuo 1 iki 1000, kurie dalijasi iš 6.
1. Raskite visus skaičius iš 1-1000, kuriuose yra 9.
1. Sukurkite stringą iš daugybės žodžių: Apskaičiuokite, kiek žodžių turi raidę "e".
1. Naudodami tą patį stringą, kaip ir ankstesniame pratime: apskaičiuokite raidžių, kurios turi daugiau nei 5 simbolius, skaičių.
1. Parašykite programą, kuri patikrintų, ar duotas skaičius yra tobulasis kvadratas.
