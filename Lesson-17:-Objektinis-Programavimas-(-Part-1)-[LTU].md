## Įvadas 
Į objektus orientuotas programavimas (OOP) - tai programos struktūrizavimo metodas, kai susijusios savybės ir elgsena sujungiamos į atskirus objektus. 
Konceptualiai objektai yra tarsi sistemos komponentai. Įsivaizduokite programą kaip savotišką gamyklos surinkimo liniją. Kiekviename surinkimo linijos etape sistemos komponentas apdoroja tam tikrą medžiagą ir galiausiai žaliavą paverčia galutiniu produktu.
Objekte yra duomenys, pavyzdžiui, žaliavos arba iš anksto apdorotos medžiagos kiekviename surinkimo linijos etape, ir elgsena, pavyzdžiui, veiksmai, kuriuos atlieka kiekvienas surinkimo linijos komponentas.
Į objektus orientuotas programavimas yra [programavimo paradigma](http://en.wikipedia.org/wiki/Programming_paradigm), kuri suteikia galimybę struktūruoti programas taip, kad savybės ir elgsena būtų sujungtos į atskirus objektus.

Pavyzdžiui, objektas gali reikšti žmogų su tokiomis savybėmis kaip vardas, amžius ir adresas bei elgsena, pavyzdžiui, vaikščiojimas, kalbėjimas, kvėpavimas ir bėgimas. Arba objektas gali reikšti elektroninį laišką su tokiomis savybėmis, kaip gavėjų sąrašas, tema ir turinys, ir tokiomis elgsenomis, kaip priedų pridėjimas ir išsiuntimas.

Kitaip tariant, į objektus orientuotas programavimas - tai metodas, skirtas konkretiems, realaus pasaulio daiktams, pavyzdžiui, automobiliams, modeliuoti, taip pat santykiams tarp daiktų, pavyzdžiui, įmonių ir darbuotojų, mokinių ir mokytojų ir pan. OOP modeliuoja realaus pasaulio esybes kaip programinės įrangos objektus, kurie turi tam tikrus su jais susijusius duomenis ir gali atlikti tam tikras funkcijas.

## Kas yra klasė?
Klasė yra objekto **blueprint**.
Klasę galime įsivaizduoti kaip namo eskizą (prototipą). Jame pateikiama visa informacija apie grindis, duris, langus ir t. t. Remdamiesi šiais aprašymais statome namą. Namas yra objektas.
Kadangi iš namo brėžinio galima sukurti daug namų, iš klasės galime sukurti daug objektų. Objektas dar vadinamas klasės egzemplioriumi, o šio objekto sukūrimo procesas vadinamas **instancija**.
Kaip Pythone funkcijų apibrėžtys prasideda raktažodžiu def, taip ir klasių apibrėžtys prasideda raktažodžiu `class`:

```python
klasė House:
    .
```
Taip sukuriama nauja `House` klasė, neturinti jokių atributų ar metodų.
Naujo objekto sukūrimas iš klasės vadinamas objekto sukūrimu. Naują `House` objektą galite instantizuoti įvesdami klasės pavadinimą, po kurio rašomi atidaromieji ir uždaromieji skliaustai:

```python
>>> House()
<__main__.House objektas adresu 0x105248e40>

```
Dabar turite naują `House` objektą 0x106702d30. Ši juokingai atrodanti raidžių ir skaičių eilutė yra atminties adresas, nurodantis, kur jūsų kompiuterio atmintyje saugomas House objektas. Atkreipkite dėmesį, kad adresas, kurį matysite ekrane, bus kitoks.

Dabar sukurkite antrą `House` objektą:

```python
>>> House()
<__main__.House objektas adresu 0x0034ccd70>
```
Naujasis `House` egzempliorius yra kitame atminties adrese. Taip yra todėl, kad tai visiškai naujas egzempliorius ir yra visiškai unikalus nuo pirmojo instancuoto House objekto.
Galime lengvai palyginti abu objektų egzempliorius:

```python
>>> a = House()
>>> b = House()
>>> a == b
False

```

#### Klasės konstruktorius (````.__init__()````)

Dabar `House` klasė nėra labai įdomi, todėl šiek tiek ją patobulinkime apibrėždami keletą savybių, kurias turėtų turėti visi `House` objektai. Galime rinktis iš daugybės savybių, įskaitant kainą, amžių, spalvą ir miegamųjų skaičių. Kad viskas būtų paprasta, naudosime tik kainą ir amžių.
Savybės, kurias turi turėti visi House objektai, apibrėžiamos metodu, vadinamu ```.__init__()````. Kiekvieną kartą kuriant naują Namo objektą, ```.__init__()```` nustato pradinę objekto būseną, priskirdamas objekto savybių reikšmes. Tai reiškia, kad ** ````.__init__()``` inicializuoja kiekvieną naują klasės egzempliorių**.

Galite nurodyti ```.__init__()```` bet kokį parametrų skaičių, tačiau pirmasis parametras visada bus kintamasis, vadinamas self. Sukūrus naują klasės egzempliorių, jis automatiškai perduodamas ```.__init__()```` parametrui self, kad objektui būtų galima nustatyti naujus atributus.

Atnaujinkime namo klasę su ```.__init__()```` metodu, kuris sukuria .cost ir .age atributus:

```python
klasė House:
    def __init__(self, cost: int, age: float):
        self.cost: int = cost
        self.age: float = age

```
Atkreipkite dėmesį, kad ````.__init__()```` metodo parašas įterptas keturiais tarpais. Metodo esmė išskirta aštuoniais tarpais. **Ši įtrauka yra labai svarbi**. Jis parodo Python, kad ```.__init__()```` metodas priklauso House klasei.

Metodo ```.__init__()```` kūne yra du teiginiai, kuriuose naudojamas kintamasis self:

self.cost = name sukuriamas atributas `cost` ir jam priskiriama parametro `cost` reikšmė.

self.age = age sukuria atributą `age` ir priskiria jam parametro `age` reikšmę.


#### Klasės ir instancijos atributai

Atributai, sukurti ```.__init__()````, vadinami** atributais**. Instancijos atributo **vertė yra būdinga konkrečiam klasės egzemplioriui**. Visi "House" objektai turi kainą ir amžių, tačiau kainos ir amžiaus atributų reikšmės skiriasi priklausomai nuo **House" egzemplioriaus**.

Kita vertus, **klasės atributai** - tai atributai, kurie turi tą pačią reikšmę visiems klasės egzemplioriams. Klasės atributą galite apibrėžti kintamojo vardui priskirdami reikšmę už ``.__init__()``` ribų.

Pavyzdžiui:

```python
class House:
    # Klasės atributas
    location: str = "Somewhere near Trump Tower"

    def __init__(self, cost: int, age: float):
        self.cost: int = cost
        self.age: float = age

```

## **Self** raktažodis
Self naudojamas klasės egzemplioriui atvaizduoti.
Naudodami šį raktažodį galite pasiekti klasės atributus ir metodus pythone. **Jis susieja atributus su pateiktais argumentais**.

👨🏫 ❗ **GERAI ŽINOTI** ❗ 
** `Self` yra ne kas kita kaip konvencija: vardas `self` neturi visiškai jokios ypatingos reikšmės "Python". Tačiau atkreipkite dėmesį, kad nesilaikant šios konvencijos jūsų kodas gali būti mažiau suprantamas kitiems "Python" programuotojams**.

## Instancijos metodai
**Instanciniai metodai** - tai funkcijos, kurios apibrėžtos klasės viduje ir gali būti iškviestos tik iš tos klasės egzemplioriaus. Kaip ir ```.__init__()````, pirmasis egzemplioriaus metodo parametras visada yra `self`:

```python
class House:
    # Klasės atributas
    location: str = "Kažkur netoli Trumpo bokšto"

    def __init__(self, cost: int, age: float):
        self.cost: int = cost
        self.age: float = age
    
    # Instancijos metodas
    def get_cost(self) -> int:
        Namo kaina yra:{self.cost}".

    # Kitas egzemplioriaus metodas
    def get_age(self) -> float:
        return f "Namo amžius yra:{self.age}"

```
Ši namo klasė turi **dvi instancijas**:

* get_cost() - grąžina `int`, rodantį namo `kainą`.
* get_age() - grąžina `float`, rodantį namo amžių.

Inicijuojame klasę ir iškviečiame keletą metodų:

```python
>>> house = Dog(100000, 12.5)

>>> house.get_cost()
"Namo kaina yra: 100000'

>>> house.get_age()
"Namo amžius: 12,5 metų


```
👨🏫 ❗ **PRO PATARIMAS** ❗ 
**Kaip ir įprastose funkcijose, savokų parametrams ir momentiniams metodo argumentams galite priskirti numatytuosius argumentus**

```python
class House:
    # Klasės atributas
    location: str = "Kažkur netoli Trump Tower"

    def __init__(self, cost: int = 50000, age: float= 10.5):
        self.cost: int = cost
        self.age: float = age
    
    # Instancijos metodas
    def get_cost(self) -> int:
        return f "Namo kaina yra:{self.cost}"

    # Kitas egzemplioriaus metodas
    def get_age(self) -> float:
        return f "Namo amžius yra:{self.age}"

    # Dar vienas egzemplioriaus metodas
    def get_house_colour(self, colour: string = 'White') -> string:
        Namo spalva yra:{self.age}".


```

```python
>>> house = Dog(100000, 12.5)

>>> house.get_cost()
"Namo kaina yra: 100000'

>>> house.get_age()
"Namo amžius: 12,5 metų

>>> house.get_house_colour('Blue')
"Namo spalva: mėlyna

>>> another_house = Dog()

>>> another_house.get_cost()
"Namo kaina yra: 50000'

>>> another_house.get_age()
"Namo amžius: 10,5 metų

>>> house.get_house_colour()
"Namo spalva yra: balta
```
## Pratimai: 
🧠 : Pakartokite [Sąlyginiai teiginiai](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-6:-Conditional-Statements), [Kilpos](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-8:-Loops), [Funkcijos](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-10:-Functions), kad užbaigtumėte šias užduotis.

* Sukurkite `Skaičiuotuvo` klasę su pagrindinėmis funkcijomis: sudėti, dalyti, dauginti, atimti ir t. t.. Inicijuokite klasę ir parodykite keletą skaičiavimų.
* Darbuotojo klasėje sukurkite egzempliorių atributus fullname (vardas, pavardė) ir email (el. paštas). Turint asmens vardą ir pavardę:
   - Vardą ir pavardę suformuokite paprasčiausiai sujungdami vardą ir pavardę, atskiriamus tarpeliu.
   - Elektroninį paštą suformuokite sujungdami vardą ir pavardę, tarp jų įterpdami simbolį . ir pabaigoje įrašydami @company.com. Įsitikinkite, kad visas 
     el. laiškas būtų rašomas mažosiomis raidėmis.

* Sukurkite knygos klasę Book, kuri turi du atributus:
    - Pavadinimas
    - autorius

  ir du metodus:

    - Metodas, pavadintas .get_title(), kuris grąžina: "Pavadinimas: " + egzemplioriaus pavadinimas.
    - Metodas .get_autor(), kuris grąžina: "Autorius: " + egzempliorius autorius.

  ir instancuokite šią klasę sukurdami 3 naujas knygas:

    - Pride and Prejudice - Jane Austen (PP)
    - Hamletas - Viljamas Šekspyras (H)
    - Karas ir taika - Levas Tolstojus (WP)

  Naujų egzempliorių pavadinimai turėtų būti atitinkamai PP, H ir WP. Pavyzdžiui, jei, naudodamas šią knygų klasę, instancuočiau šią knygą:

    - Haris Poteris - J. K. Rowling (HP)

  Gaučiau šiuos atributus ir metodus:
  ```python
  HP.title ➞ "Harry Potter"
  HP.author ➞ "J.K. Rowling"
  HP.get_title() ➞ "Pavadinimas: Haris Poteris"
  HP.get_author() ➞ "Autorius: Rowling"
  ```

* Apie šalį galima sakyti, kad ji yra didelė, jei ji yra:

   - Didelė gyventojų skaičiumi.
   - Didelė pagal plotą.

  Šalies klasę papildykite taip, kad joje būtų atributas is_big. Nustatykite jį į True, jei tenkinamas kuris nors iš šių kriterijų:

   - Gyventojų skaičius yra didesnis nei 20 mln.
   - Plotas didesnis nei 3 mln. km².

  Taip pat sukurkite metodą, kuris palygintų šalies gyventojų tankį su kitos šalies objektu. Grąžinkite tokio formato eilutę:
  
  ```python
  {country} has a {smaller / larger} population density than {other_country}
  ```
  Pavyzdys:
  
  ```python
  australia = Country("Australija", 23545500, 7692024)
  andora = Country("Andora", 76098, 468)

  australia.is_big ➞ True
  andorra.is_big ➞ False
  andorra.compare_pd(australia) ➞ "Andoros gyventojų tankis didesnis nei Australijos"
  ```

## 🌐 Papildomas skaitymas (arba žiūrėjimas 📺 ):


* [OOP kursas - "Youtube"] (https://www.youtube.com/watch?v=Ej_02ICOIgs)
* [Corey Schafer: Python OOP Tutorial (keli vaizdo įrašai)](https://www.youtube.com/watch?v=ZDa-Z5JzLYM)
* [Datacamp](https://www.datacamp.com/tutorial/python-oop-tutorial)
***


