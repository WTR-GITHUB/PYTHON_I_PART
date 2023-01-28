## Tęsinys
Viena iš galingų, tačiau mažiau populiarių "Python" funkcijų yra *args ir **kwargs argumentai, lambda funkcija.

## *args, **kwargs
Taigi, kas yra `*args` ir `**kwargs` argumentai? Aukščiausiu lygiu jie leidžia funkcijoms _priimti neprivalomus argumentus_ ir suteikia mums lankstumo kviesti funkciją su bet kokiu argumentų skaičiumi. Todėl juos naudodami galime rašyti lankstesnes klases ir modulius.

Paprastas pavyzdys: 🔽 

```python
def check_arguments(mandatory: Any, *args, **kwargs) -> None:
    print (mandatory)
    if args:
        print (args)
    if kvargs:
        print (kvargs)
```

Pirmiau pateikta funkcija `check_arguments` reikalauja bent vieno argumento, vadinamo "privalomas", tačiau ji gali priimti ir papildomus pozicinius bei raktinius argumentus.
Jei iškviesime funkciją su papildomais argumentais, `args` surinks papildomus _pozicinius argumentus_ kaip **tinklą**, nes parametro vardas turi * priešdėlį.

Taip pat `kwargs` surinks papildomus raktinių žodžių argumentus **kaip žodyną**, nes parametro vardas turi ** priešdėlį. Ir `args`, ir `kwargs` bus tušti, jei funkcijai neperduodami jokie papildomi argumentai.
Kad suprastume `args` ir `kwargs` elgesį, iškvieskime savo `check_arguments` metodą su skirtingais argumentais:

```python
>>> check_arguments():
TypeError:
"check_arguments() trūksta 1 privalomo pozicinio argumento: 'mandatory'".
>>> check_arguments('welcome')
welcome

>>> check_arguments('welcome', 1, 2, 3)
welcome
(1, 2, 3)

>>> toy_fun('welcome', 1, 2, 3, name='Sarah', age=26)
welcome
(1, 2, 3)
{"vardas": "Sarah", "amžius": 26}
```
👨🏫 ❗ **GERAI ŽINOTI** ❗ 
** ``args` ir `kwargs` yra paprasta pavadinimų suteikimo konvencija. Aukščiau pateiktas pavyzdys puikiai veiktų, jei pavadintume juos `*parms` ir `**argv` arba bet kaip kitaip. Tikroji sintaksė yra tik žvaigždutė (*) arba dviguba žvaigždutė (**)**.

👨🏫 ❗ **DĖMESIO!** ❗ 
** Naudodami `*args` arba `**kwargs` su kitais parametrais arba naudodami juos kartu, turėtume nepamiršti, kad argumentai turi būti išdėstyti nurodyta tvarka ⬇️ .**

1. **Formalūs argumentai**
2. ***args**
3. **reikšminiai argumentai**
4. ****kwargs**

```python
def my_func(a:int, b:int, *args, c: int = 5, d: int = 9, **kwargs) -> None:
    print (a, b)
    print (type(args), args)
    print (c, d)
    print (type(kvargs), kvargs)

>>> my_func(1, 2, 3, 4, 5, e=6, f = 7)
1, 2
<klasė 'tuple'> (3, 4, 5)
5, 9
<class 'dict'> {'e': 6, 'f': 7}
```
## Lambda funkcija
**Lambda funkcijos** yra _anoniminės_ funkcijos Pythone. Lambda funkcijos yra panašios į įprastas funkcijas. Skirtumas tarp įprastų funkcijų ir lambda funkcijų yra tas, kad jas galima **apibrėžti be pavadinimo**, tačiau įprastos funkcijos apibrėžiamos raktiniu žodžiu `def`.
**_lambda_** raktažodis naudojamas anoniminei arba lambda funkcijai apibrėžti.
Jei galėtume palyginti lambda funkciją su įprasta funkcija:

* `lambda` funkcija gali priimti bet kokį argumentų skaičių, bet gali turėti tik vieną išraišką, o įprasta funkcija turi tikslų argumentų skaičių, kurį deklaruojame apibrėžimo metu.
* `Lambda` funkcijos yra vienos eilutės funkcijos. jos kūnas turi išraišką toje pačioje eilutėje, kurioje ji apibrėžiama. Įprastose funkcijose yra kūno blokai, kuriuose apibrėžtos tam tikros vykdomos frazės.
* Kadangi `lambda` yra vienos eilutės funkcija, ji gali būti iškviečiama iš karto, o įprastinė funkcija turi pati save iškviesti ir jai iškviesti reikia laiko.

Paprasta daugybos funkcija: 

```python
def multiply(x: int,y: int) -> int:
    return * y

print(multiply(2,3))
>>> 6
```
galime perrašyti kaip `lambda` funkciją:

```python
multiplication= lambda x,y : x * y
print(multiplication(2,3))
>>> 6
```
Argumentus funkcijai galime perduoti apsupdami funkciją ir jos argumentą skliaustais:

```python
multiplication= (lambda x,y : x * y)(2,3)
print(multiplication)
>>> 6
```

#### Naudojimas
Pirmenybė teikiama lambda funkcijai:

* Kai norite, kad funkcija būtų naudojama vieną kartą.
* Kai funkcijos apibrėžtyje yra viena išraiška.
* Kai norite parašyti aiškią sintaksę, turėdami kelias kodo eilutes.

Tačiau jis nėra tinkamas:

* Kai funkciją reikia naudoti vėl ir vėl.
* kai funkcijos apibrėžtyje yra daug ar sudėtingų išraiškų.

## Pratimai: 
Duomenų struktūros (1 dalis)](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-3:-Data-Structures-(1 dalis)), [Duomenų struktūros (2 dalis)](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-5:-Data-Structures-(2 dalis)), [Sąlyginiai teiginiai](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-6:-Conditional-Statements), [Ciklai](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-8:-Loops), kad užbaigtumėte šią užduotį.

* Parašykite funkciją, kuri paima du sąrašus ir prie pirmojo sąrašo pirmojo elemento prideda antrojo sąrašo pirmąjį elementą, antrojo sąrašo antrąjį 
  elementą, antrojo sąrašo antrąjį elementą ir antrojo sąrašo antrąjį elementą. 
  pirmąjį sąrašą su antruoju antrojo sąrašo elementu ir t. t., ir t. t. Grąžinkite True, jei visi elementų deriniai sudaro tą patį skaičių. Priešingu 
  atveju grąžinama False.
  Pavyzdys: 

  ```python
  puzzle_pieces([1, 2, 3, 4], [4, 3, 2, 1]) ➞ True
  # 1 + 4 = 5; 2 + 3 = 5; 3 + 2 = 5; 4 + 1 = 5
  # Abiejų sąrašų suma yra [5, 5, 5, 5, 5]
  puzzle_pieces([1, 8, 5, 0, -1, 7], [0, -7, -4, 1, 2, -6]) ➞ True
  puzzle_pieces([1, 2], [-1, -1]) ➞ False
  puzzle_pieces([9, 8, 7], [7, 8, 9, 10]) ➞ False
  ```

* Tarp lyginių ir nelyginių skaičių vyksta didelis karas. Šiame kare jau žuvo daug skaičių, todėl tavo užduotis - jį nutraukti. Jūs turite 
  nustatyti, kurios grupės sumos didesnės: lyginių ar nelyginių. Laimi didesnė grupė.

  Sukurkite funkciją, kuri paimtų sveikųjų skaičių sąrašą, atskirai suskaičiuotų lyginių ir nelyginių skaičių sumas, tada grąžintų lyginių ir nelyginių 
  skaičių sumų skirtumą skaičių.

  Pavyzdys: 
  ```python
  war_of_numbers([2, 8, 7, 5]) ➞ 2
  # 2 + 8 = 10
  # 7 + 5 = 12
  # 12 yra didesnis už 10
  # Taigi grąžiname 12 - 10 = 2
  war_of_numbers([12, 90, 75]) ➞ 27
  war_of_numbers([5, 9, 45, 6, 2, 7, 34, 8, 6, 90, 5, 243]) ➞ 168
  ```

* Jums duotas bigramų masyvas ir žodžių masyvas. Parašykite funkciją, kuri grąžintų True, jei iš šio masyvo galima rasti kiekvieną bigramą 
  bent vieną kartą žodžių masyve.
   
  Pavyzdys:
  ```python
  can_find([["at", "be", "th", "au"], ["beautiful", "the", "hat"]) ➞ True
  can_find([["ay", "be", "ta", "cu"], ["maybe", "beta", "abet", "course"]) ➞ False
  # "cu" nėra nė viename iš žodžių.
  can_find(["th", "fo", "ma", "or"], ["the", "many", "for", "forest"]) ➞ True
  can_find(["oo", "mi", "ki", "la"], ["milk", "chocolate", "cooks", "cooks"]) ➞ False
  ```
* Iš naujo įgyvendinkite kai kuriuos ankstesnius sprendimus naudodami lambda funkciją. 

## 🌐 Papildomas skaitymas:

* [Type Annotations in Python 3.8](https://medium.com/analytics-vidhya/type-annotations-in-python-3-8-3b401384403d)

* [Real Phyton](https://realpython.com/defining-your-own-python-function/)

* [Real Python Youtube](https://www.youtube.com/watch?v=Q93bwyZoXk0)
***


