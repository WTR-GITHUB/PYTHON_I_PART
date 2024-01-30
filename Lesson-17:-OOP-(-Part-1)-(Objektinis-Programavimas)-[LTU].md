## Įvadas 
Objektinis programavimas (OOP) - tai programos struktūrizavimo metodas, kai susijusios savybės ir elgsena sujungiamos į atskirus objektus. 
Konceptualiai objektai yra tarsi sistemos komponentai. Įsivaizduokite programą kaip savotišką gamyklos surinkimo liniją. Kiekviename surinkimo linijos etape sistemos komponentas apdoroja tam tikrą medžiagą ir galiausiai žaliavą paverčia galutiniu produktu.
Objekte yra duomenys, pavyzdžiui, žaliavos arba iš anksto apdorotos medžiagos kiekviename surinkimo linijos etape, ir elgsena, pavyzdžiui, veiksmai, kuriuos atlieka kiekvienas surinkimo linijos komponentas.
Objektinis programavimas yra [programavimo paradigma](http://en.wikipedia.org/wiki/Programming_paradigm), kuri suteikia galimybę struktūruoti programas taip, kad savybės ir elgsena būtų sujungtos į atskirus objektus.

Pavyzdžiui, objektas gali reikšti `žmogų` su tokiomis savybėmis kaip `vardas`, `amžius` ir `adresas` bei `elgsena`, pavyzdžiui, `vaikščiojimas`, `kalbėjimas`, `kvėpavimas` ir `bėgimas`. Arba objektas gali reikšti elektroninį laišką su tokiomis savybėmis, kaip gavėjų sąrašas, tema ir turinys, ir tokiomis elgsenomis, kaip priedų pridėjimas ir išsiuntimas.

Kitaip tariant, į objektinis programavimas - tai metodas, skirtas konkretiems, realaus pasaulio daiktams, pavyzdžiui, automobiliams, modeliuoti, taip pat santykiams tarp daiktų, pavyzdžiui, įmonių ir darbuotojų, mokinių ir mokytojų ir pan. OOP modeliuoja realaus pasaulio esybes kaip programinės įrangos objektus, kurie turi tam tikrus su jais susijusius duomenis ir gali atlikti tam tikras funkcijas.

### `Kas yra klasė?`
Klasė yra objekto **pirminis planas (blueprint)**.
Klasę galime įsivaizduoti kaip namo eskizą (**prototipą**). Jame pateikiama visa informacija apie grindis, duris, langus ir t. t. Remdamiesi šiais aprašymais statome namą. **Namas yra objektas**.
Kadangi iš namo brėžinio galima sukurti daug namų, iš klasės galime sukurti daug objektų. **Objektas dar vadinamas klasės egzemplioriumi, o šio objekto sukūrimo procesas vadinamas **instancija**.**
Kaip Pythone funkcijų apibrėžtys prasideda raktažodžiu `def`, taip ir klasių apibrėžtys prasideda raktažodžiu `class`:

```python
class House:
    pass
```
Taip sukuriama nauja `House` klasė, neturinti jokių atributų ar metodų.
Naujo objekto sukūrimas iš klasės vadinamas **objekto sukūrimu**. Naują `House` objektą galite instantizuoti įvesdami klasės pavadinimą, po kurio rašomi atidaromieji ir uždaromieji skliaustai:

```python
>>> House()
<__main__.House object at 0x105248e40>


```
Dabar turite naują `House` objektą `0x106702d30`. Ši juokingai atrodanti raidžių ir skaičių eilutė yra **atminties adresas, nurodantis, kur jūsų kompiuterio atmintyje saugomas House objektas**. Atkreipkite dėmesį, kad adresas, kurį matysite ekrane, bus kitoks.

Dabar sukurkite antrą `House` objektą:

```python
>>> House()
<__main__.House object at 0x0034ccd70>
```
Naujasis `House` egzempliorius yra kitame atminties adrese. Taip yra todėl, kad tai visiškai naujas egzempliorius ir yra visiškai unikalus nuo pirmojo instancuoto `House` objekto.
Galime lengvai palyginti abu objektų egzempliorius:

```python
>>> a = House()
>>> b = House()
>>> a == b
False

```

### `Klasės konstruktorius (.__init__())`

Dabar `House` klasė nėra labai įdomi, todėl šiek tiek ją patobulinkime apibrėždami keletą savybių, kurias turėtų turėti visi `House` objektai. Galime rinktis iš daugybės savybių, įskaitant kainą, amžių, spalvą ir miegamųjų skaičių. Kad viskas būtų paprasta, naudosime tik `kainą` ir `amžių`.
Savybės, kurias turi turėti visi `House` objektai, apibrėžiamos metodu, vadinamu `.__init__()`. Kiekvieną kartą kuriant naują `House` objektą, `.__init__()` nustato pradinę objekto būseną, priskirdamas objekto savybių reikšmes. Tai reiškia, kad ** `.__init__()` inicializuoja kiekvieną naują klasės egzempliorių **.

Galite nurodyti `.__init__()` bet kokį parametrų skaičių, tačiau pirmasis parametras visada bus kintamasis, vadinamas `self`. Sukūrus naują klasės egzempliorių, jis automatiškai perduodamas `.__init__()` parametrui `self`, kad objektui būtų galima **nustatyti naujus atributus**.

Atnaujinkime `House` klasę su  `.__init__()` metodu, kuris sukuria `.cost` ir `.age` atributus:

```python
class House:
    def __init__(self, cost: int, age: float):
        self.cost: int = cost
        self.age: float = age


```
Atkreipkite dėmesį, kad `.__init__()` metodo aprašas indentuotas keturiais tarpais. Metodo esmė indentuota aštuoniais tarpais. **Šis indentavimas yra labai svarbus**. Jis parodo Python, kad `.__init__()` metodas priklauso `House` klasei.

Metodo ```.__init__()```` kūne yra du teiginiai, kuriuose naudojamas kintamasis `self`:

`self.cost` = `cost` sukuriamas atributas `cost` ir jam priskiriama parametro `cost` reikšmė.

`self.age` = `age` sukuria atributą `age` ir priskiria jam parametro `age` reikšmę.


### `Klasės ir instancijos atributai`

Atributai, sukurti `.__init__()`, vadinami** atributais**. Instancijos atributo **vertė yra būdinga konkrečiam klasės egzemplioriui**. Visi `House` objektai turi `kainą` ir `amžių`, tačiau `kainos` ir `amžiaus` atributų **reikšmės** skiriasi priklausomai nuo **House egzemplioriaus**.

Kita vertus, **klasės atributai** - tai atributai, kurie turi tą pačią reikšmę visiems klasės egzemplioriams. Klasės atributą galite apibrėžti kintamojo vardui priskirdami reikšmę už `.__init__()` ribų.

Pavyzdžiui:

```python
class House:
    # Class attribute
    location: str = "Somewhere near Trump Tower"

    def __init__(self, cost: int, age: float):
        self.cost: int = cost
        self.age: float = age


```

## **Self** raktažodis
`Self` naudojamas klasės egzemplioriui atvaizduoti.
Naudodami šį raktažodį galite pasiekti klasės atributus ir metodus pythone. **Jis susieja atributus su pateiktais argumentais**.

👨🏫 ❗ **GERAI ŽINOTI** ❗ 
** `Self` yra ne kas kita kaip konvencija: vardas `self` neturi visiškai jokios ypatingos reikšmės "Python" kalboje. Tačiau atkreipkite dėmesį, kad nesilaikant šios konvencijos jūsų kodas gali būti mažiau suprantamas kitiems "Python" programuotojams**.

### `Instancijos metodai`
**Instanciniai metodai** - tai funkcijos, kurios apibrėžtos klasės viduje ir gali būti iškviestos tik iš tos klasės egzemplioriaus. Kaip ir `.__init__()`, pirmasis egzemplioriaus metodo parametras visada yra `self`:

```python
class House:
    # Class attribute
    location: str = "Somewhere near Trump Tower"

    def __init__(self, cost: int, age: float):
        self.cost: int = cost
        self.age: float = age
    
    # Instance method
    def get_cost(self) -> str:
        return f"The house cost is:{self.cost}"

    # Another instance method
    def get_age(self) -> str:
        return f"The house age is:{self.age}"
```

Ši `House` klasė turi **dvi instancijas**:

* get_cost() - grąžina `str`, rodantį namo `kainą`.
* get_age() - grąžina `str`, rodantį namo `amžių`.

Inicijuojame klasę ir iškviečiame keletą metodų:

```python
>>> house = House(100000, 12.5)

>>> house.get_cost()
'The house cost is: 100000'

>>> house.get_age()
'The house age is: 12.5'
```

👨🏫 ❗ **PRO PATARIMAS** ❗ 
**Kaip ir įprastose funkcijose, galite priskirti numatytuosius argumentus**

```python
class House:
    # Class attribute
    location: str = "Somewhere near Trump Tower"

    def __init__(self, cost: int = 50000, age: float= 10.5):
        self.cost: int = cost
        self.age: float = age
    
    # Instance method
    def get_cost(self) -> str:
        return f"The house cost is:{self.cost}"

    # Another instance method
    def get_age(self) -> str:
        return f"The house age is:{self.age}"

    # Yet another instance method
    def get_house_colour(self, colour: string = 'White') -> string:
        return f"The house colour is:{self.age}"
```

```python
>>> house = House(100000, 12.5)

>>> house.get_cost()
'The house cost is: 100000'

>>> house.get_age()
'The house age is: 12.5'

>>> house.get_house_colour('Blue')
'The house colour is: Blue'

>>> another_house = Dog()

>>> another_house.get_cost()
'The house cost is: 50000'

>>> another_house.get_age()
'The house age is: 10.5'

>>> house.get_house_colour()
'The house colour is: White'
```
## Pratimai: 
🧠 : Pakartokite [Sąlyginiai teiginiai](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-6:-Conditional-Statements), [Ciklai](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-8:-Loops), [Funkcijos](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-10:-Functions), kad užbaigtumėte šias užduotis.

1) Sukurkite `Calculator` klasę su pagrindinėmis funkcijomis: sudėti, dalyti, dauginti, atimti ir t. t.. Inicijuokite klasę ir parodykite keletą 
   skaičiavimų.
2) Darbuotojo klasėje sukurkite egzempliorių atributus `fullname` (vardas, pavardė) ir `email` (el. paštas). Turint asmens vardą ir pavardę:
   - Vardą ir pavardę suformuokite paprasčiausiai sujungdami vardą ir pavardę, atskiriamus tarpeliu.
   - Elektroninį paštą suformuokite sujungdami vardą ir pavardę, tarp jų įterpdami simbolį . Pabaigoje įrašydami `@company.com`. Įsitikinkite, kad visas 
     el. laiškas būtų** rašomas mažosiomis raidėmis**.

3) Sukurkite knygos klasę `Book`, kuri turi du atributus:
    - `name`
    - `author`

   ir du metodus:

    - Metodas, pavadintas `.get_title()`, kuris grąžina: "Pavadinimas: " + egzemplioriaus pavadinimas.
    - Metodas `.get_autor()`, kuris grąžina: "Autorius: " + egzempliorius autorius.

  ir instancuokite šią klasę sukurdami 3 naujas knygas:

    - Pride and Prejudice - Jane Austen (PP)
    - Hamletas - Viljamas Šekspyras (H)
    - Karas ir taika - Levas Tolstojus (WP)

   Naujų egzempliorių pavadinimai turėtų būti atitinkamai `pride_and_prejudice`, `hamlet` ir `war_and_peace`. Pavyzdžiui, jei, naudodamas šią knygų 
   klasę, instancuočiau šią knygą:

    - Haris Poteris - J. K. Rowling (harry_potter)

  Gaučiau šiuos atributus ir metodus:
  ```python
  harry_potter.title ➞ "Harry Potter"
  harry_potter.author ➞ "J.K. Rowling"
  harry_potter.get_title() ➞ "Pavadinimas: Haris Poteris"
  harry_potter.get_author() ➞ "Autorius: Rowling"
  ```

4) Apie šalį galima sakyti, kad ji yra didelė, jei ji yra:

   - Didelė gyventojų skaičiumi.
   - Didelė pagal plotą.

  Šalies klasę papildykite taip, kad joje būtų atributas `is_big`. Nustatykite jį į `True`, jei tenkinamas kuris nors iš šių kriterijų:

   - Gyventojų skaičius yra didesnis nei 20 mln.
   - Plotas didesnis nei 3 mln. km².

  Taip pat sukurkite metodą, kuris palygintų šalies gyventojų tankį su kitos šalies objektu. Grąžinkite tokio formato eilutę:
  
  ```python
  {country} has a {smaller / larger} population density than {other_country}
  ```
  Pavyzdys:
  
  ```python
  australia = Country("Australia", 23545500, 7692024)
  andorra = Country("Andorra", 76098, 468)

  australia.is_big ➞ True
  andorra.is_big ➞ False
  andorra.compare_pd(australia) ➞ "Andorra has a larger population density than Australia"
  ```

## 🌐 Papildomas skaitymas (arba žiūrėjimas 📺 ):


* [OOP kursas - "Youtube"] (https://www.youtube.com/watch?v=Ej_02ICOIgs)
* [Corey Schafer: Python OOP Tutorial (keli vaizdo įrašai)](https://www.youtube.com/watch?v=ZDa-Z5JzLYM)
* [Datacamp](https://www.datacamp.com/tutorial/python-oop-tutorial)
***


