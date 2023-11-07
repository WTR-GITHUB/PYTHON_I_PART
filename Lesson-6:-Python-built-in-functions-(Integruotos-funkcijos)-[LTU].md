## 🐍 Integruotos funkcijos

### `print()`

Kaip matėme ankščiau, jau porą kartų naudojome `print` ir su ja susipažinome. Svarbu paminėti, kad ši funkcija iš tikrųjų ji gana universali:

`print(object(s), sep=separator, end=end, file=file, flush=flush)`

| argumentas| reikšmė |
| ------------- | ------------- |
| object(s) | Bet koks objektas. |
| sep='separatorius' | Neprivaloma. Nurodykite, kaip atskirti objektus, jei jų yra daugiau nei vienas. Numatytoji reikšmė yra ' '  |
| end='end' | Neprivaloma. Nurodykite, ką spausdinti pabaigoje. Numatytoji reikšmė yra "\n" (string'o padavimas) |
| file | Neprivaloma. Objektas su rašymo metodu. Numatytoji reikšmė yra sys.stdout |
| flush | Neprivaloma. Loginis reikšmė, nurodanti, ar išvestis išplaunama (True), ar buferizuojama (False). Numatytoji reikšmė yra False |

Keletas pavyzdžių:

```python
# Simple print
print("hello world")

# Gets the same result but slightly different:
print("hello", "world")

# Gets the same result but is even more different:
print(*["hello", "world"])

# let's play with separator:
print("hello world", sep=",")

# some more
print("hello", "world", sep=" amazing ")
```

### `type()`

Kita naudinga funkcija yra `type`. Ji padeda suprasti, su kokiu objektu susiduriame:


Pavyzdžiai:
```python
greet = "Hello World"
print(type(a))

number = 2022
print(type(number))

my_list = [1, 2, 3]
print(type(my_list))

print(type(my_list[0]))
```

Vėliau tai labai pravers dirbant su sudėtingesnėmis programomis.

### `len()`

Šią funkciją jau matėme anksčiau dirbant su `list` duomenų struktūra. Kaip pamenate, ji grąžina `list` arba `tuple` ilgį.
Nepaisant to, ji vis dar veikia ir su `string` tipo duomenimis. 

Pavyzdžiai:
```python
word = "word"
length = len(word)

print(f "Word {word} length is : {length}")
```

Primename, kaip tai veikia su `list`:

```python
my_list = [1, 2, 3]

print(f "list {my_list} length is: {len(my_list)}")
```

### `round()`

Funkcija leidžia suapvalinti skaičių iki tam tikro dešimtainio laipsnio:

`round(number, ndigits=None)`

| argumentas| reikšmė |
| ------------- | ------------- |
| number| skaičius, kurį reikia apvalinti |
| ndigits | dešimtųjų skaitmenų, pagal numatytuosius nustatymus - `None`, o tai reiškia, kad bus apvalinama iki **sveikojo skaičiaus vertės** |


Pavyzdžiai:

```python
print(round(1.999))

print(round(1.5555, 2))
```

### `sorted()`

Ką daryti, jei norėtume surūšiuoti `list` arba `tuple` reikšmes:

`sorted(iterable, key=None, reverse=False)`
| argumentas| reikšmė |
| ------------- | ------------- |
| iterable | seka (string, tuple, list) arba kolekcija (aibė, žodynas, užšaldyta aibė), arba bet koks kitas iteratorius.  |
| reverse| (pasirinktinai) - Jei True, surūšiuotas list yra atvirkštinis (arba surūšiuotas mažėjančia tvarka). Jei nenurodyta, numatytasis nustatymas yra False.  |
| key | (Neprivaloma) - Funkcija, kuri naudojama kaip raktas rūšiavimui palyginti. Numatytoji reikšmė yra None.  |


Pavyzdžiai:
```python
my_list = [45, 20, 14, 55]
sorted_list = sorted(my_list)

print(sorted_list)

sorted_reverse_list = sorted(my_list, reverse=True)

print(sorted_reverse_list)
```

Kaip elgtis su `string` reikšmėmis?

```python
my_list = ["Albert", "Nicola", "Thomas"]
sorted_list = sorted(my_list)

print(sorted_list)

sorted_reverse_list = sorted(my_list, reverse=True)

print(sorted_reverse_list)
```


Kitas integruotas funkcijas galite pamatyti čia: [nuoroda](https://docs.python.org/3/library/functions.html)

## 🧠 Pratimai:

1. Sukurkite Python `list` su įvairiausiais  tipo objektais. Išspausdinkite visus **tipus**. 
1. Atspausdinkite visus šiuos objektus ir jų tipus , atskirtus "|" simboliu.
1. Sukurkit `list` su `float` tipo duomenimis, turinčius 3 skaitmenis po kablelio. Sukurkite kitą `list` su visomis reikšmėmis, suapvalintomis iki 2 ženklų po kablelio. Atspausdinkit abiejus `list`.
1. Sukurkite `list` su mokinių vardais ir juos surūšiuokite, rezultatą išspausdinkite į terminalą.
1. Parašykite programą, kuri leistų vartotojui įrašyti bet kokį kintamąjį skaičių ir jį suapvalinti iki tam tikro skaičiaus po kablelio.


## 🌐 Papildomas skaitymas:
[Integruotos funkcijos] (https://www.programiz.com/python-programming/methods/built-in)
