## Įvadas 
Kaip jau žinome, Python yra objektinio programavimo kalba. Python kalboje **viskas yra objektas**. Kaip ir kitose į _objektus_ orientuotose kalbose, kuriant objektus naudojant `klases`, taikomi **4 pagrindiniai švaraus ir glausto kodo rašymo principai**. Šie principai vadinami **keturiomis objektinio programavimo (OOP)** paradigmomis. Tai yra:  **paveldimumas, polimorfizmas, inkapsuliacija ir abstrakcija**. 

### `Kodėl OOP`?
Galima paminėti keletą aspektų:
* Daug lengviau prižiūrėti ir atnaujinti esamą kodą.
* Suteikia galimybę pakartotinai naudoti kodą.
* Suteikia modulinę struktūrą.
* Lengva derinti.

### `Prieigos modifikatoriai (access modifiers)`
Daugumoje `OOP` kalbų prieigos modifikatoriai naudojami siekiant apriboti **prieigą prie klasės kintamųjų ir funkcijų**. Daugumoje kalbų naudojami trijų tipų prieigos modifikatoriai: `private`, `public` ir `protected`.

Kaip ir bet kurioje kitoje [objektinio programavimo kalboje](https://en.wikipedia.org/wiki/List_of_object-oriented_programming_languages), prieiga prie kintamųjų ar funkcijų gali būti apribota ir "Python" naudojant prieigos modifikatorius. Python naudoja `underscores`, kad nurodytų konkretaus duomenų nario ir klasės nario funkcijos prieigos modifikatorių.

Prieigos modifikatoriai atlieka **svarbų vaidmenį apsaugant duomenis nuo neleistinos prieigos ir nuo manipuliavimo jais**. Įgyvendinant paveldėjimą (žr. šį skyrių ⬇️ ) kyla didžiulė rizika, kad duomenys bus sunaikinti (jais bus manipuliuojama) dėl nepageidaujamų duomenų perkėlimo iš `base` klasės į 'child' klasę. Todėl labai svarbu numatyti tinkamus prieigos modifikatorius skirtingiems duomenų nariams ir nario funkcijoms, atsižvelgiant į reikalavimus.
Pythone yra 3 (klasės) prieigos modifikatorių tipai. Šie prieigos modifikatoriai apibrėžia, kaip galima pasiekti klasės narius. 
Tai:
* `Public` - nariai, deklaruoti kaip `public`, yra pasiekiami iš klasės išorės per klasės objektą.
* `Protected` - nariai, deklaruoti kaip `protected`, yra prieinami už klasės ribų, bet tik iš jos išvestinėje klasėje, kuri yra antrinėje klasėje arba 
   poklasyje.
* `Private` - šie nariai pasiekiami tik iš klasės vidaus. Išorinė prieiga neleidžiama.

_Public_
```python
# defining a class Employee
class Employee:
    # constructor
    def __init__(self, name: str, sal: int):
        self.name = name # Public attribute
        self.sal = sal

---- OUTPUT ----
>>> emp = Employee("Ironman", 999000);
>>> emp.sal
999000
```

👨🏫 ❗ **Dėmesio** ❗ 
**Pagal numatytuosius nustatymus visi klasės kintamieji ir nario funkcijos python programoje yra vieši**.

_Protected_
```python
# defining a class Employee
class Employee:
    # constructor
    def __init__(self, name: str, sal: int):
        self._name = name # Protected attribute
        self._sal = sal # Protected attribute

---- OUTPUT ----
>>> emp = Employee("Captain", 10000);
>>> emp.sal
10000
```

_Private_
```python
# defining a class Employee
class Employee:
    # constructor
    def __init__(self, name: str, sal: int):
        self.__name = name # Private attribute
        self.__sal = sal # Private attribute

---- OUTPUT ----
>>> emp = Employee("Bill", 10000);
>>> emp.__sal;

AttributeError: 'employee' object has no attribute '__sal'
```
ℹ️ 
**Taip pat yra **privatūs ir apsaugoti metodai**. Prieigos modifikatorių veikimo mechanizmas taikomas toks pat kaip ir klasės atributų:**
**Privatus metodas gali būti iškviestas tik konkrečios klasės viduje, o apsaugotas metodas - konkrečios klasės viduje ir jos antrinėse klasėse.**

_Private method_
```python
class Example:
  def __init__(self):
    self.__a = "This is a private variable"  def __can_not_run(self):
    print("Can't be executed outside of this class")

>>> ex = Example()
>>> print(ex.__a)

Traceback (most recent call last):
  File "<input>", line 1, in <module>
AttributeError: 'Example' object has no attribute '__a'>>> ex.__can_not_run()
Traceback (most recent call last):
  File "<input>", line 1, in <module>
AttributeError: 'Example' object has no attribute '__can_not_run'
```
_Protected method_

```python
class User:
    def __init__(self,username) -> None:
        self.username = username
    
    def _check_account_existence(self):
        print(f"Checking if {self.username} has signed up already.")

---- OUTPUT ----
>>> user = User("cowboy")
>>> user._check_account_existence()
Checking if cowboy has signed up already.
```
💁 **Priminimas**: 
* Saugomų metodų apibūdinimui naudojamas priešdėlis yra **vienas pabraukimas**, o privačių metodų priešdėlis yra **du pabraukimai**.
* Saugomus metodus galime tiesiogiai iškviesti už klasės ribų, naudodami jų metodų pavadinimus. Tačiau norint iškviesti privačius metodus, reikia [vardų keitimo](https://www.geeksforgeeks.org/name-mangling-in-python/).

Be šių dviejų akivaizdžių apsaugotų ir privačių metodų skirtumų, pagrindinis skirtumas tarp šių dviejų rūšių metodų_ yra susijęs su jų prieinamumu poklasių viduje. Tai reiškia, kad apsaugoti metodai yra prieinami poklasių viduje, o privatūs metodai nėra prieinami poklasių viduje (nors to priežastis taip pat yra vardų keitimas). 
ℹ️ 

## `Keturios OOP paradigmos`

### `Paveldimumas (Inheritance)`

Paveldėjimas - tai procesas, kurio metu viena klasė paveldi kitos klasės savybes. Ši naujai suformuota klasė vadinama `dukterine (child)` klase, o kita klasė - `tėvine/motinine klase (base)`. Tai užtikrina pakartotinį kodo panaudojimą, nes naudojame esamą klasę naujos klasės savybėms padidinti. Dukterinė klasė gali naudotis visais tėvinės klasės duomenų nariais ir funkcijomis.

Pythone, norėdami paveldėti klasę, apibrėždami klasę naudojame `ChildClass(ParentClass)`: 🔽 

```python
class Employee:                     
    def __init__(self, name: str,age: int, exp: int, salary: int):                          ## Defining The Constructor With Common data
        ## Instance Attributes                                       ## instance attributes that are only accessible by the object of the class
        self.name = name                                              
        self.age = age
        self.exp = exp
        self.salary = salary

    def show(self) -> None:                                                   ## A Simple method that prints the data 
        print(self.name,self.age,self.exp,self.salary)                ## Printing all the variables


class Engineers(Employee):                                            ## Parent class Employee inherit by child Enginners

    def __init__(self, name: str,age: int, exp: int, salary: int, level: int):                     ## Constructor of Enginners class(child)
        super().__init__(name,age,exp,salary)                         ## accessing the parent class constructor and instance attributes with the help of super method
        self.level = level                                            ## Assigning a new attribute level for the Enginner class


    def print_data(self):                                             ## Creating a New Method for the Enginner class that is only accessable by the object of Enginner class
        print(self.level)                                             ## Printing the level of the Enginner



class Designers(Employee):                                           ## Parent class Employee inherit by child Designers

        def __init__(self,name,age,exp,salary,position):               
            super().__init__(name,age,exp,salary)                    
            self.position = position                                 ## Extending the attributes of parent class by adding a new attribute position
        
        def show(self):                                              ## A Simple Method Belong to the Designer Class that is used to print the data
            super().show()                                           ## Accessing parent class method and extending it to print the position also
            print(self.position)                                     ## Printing the position of the Designer


obj_E = Engineers("Alex",35,10,50000,'JR Developer')                ## Creating an object for the Enginners class, Need to paas arguments because It is a inherit class

obj_E.show()                                                        ## accessing parent method show with the help of the child class object
obj_E.print_data()                                                  ## accessing child class method debug, that is only access by the Designers object

obj_D = Designers("Karl",45,20,55000,"UI Designer")                 
obj_D.show()                                                        ## printing all the data 

'''
obj_E.debug()                                                       ## AttributeError: 'Engineers' object has no attribute 'debug'  ,debug is not a member of the Enginners class
Employee('Garry',35,10,50000).show()                                ## Garry 35 10 50000   ,because a class can access class attributes without the need of an object
obj = Employee('Garry',35,10,50000)
obj.debug()                                                         ## AttributeError: 'Employee' object has no attribute 'debug' , A parent can not access a child class
'''
```
Iš pradžių turime pagrindinę klasę `Employee`, kuri turi pagrindinę informaciją: vardą, amžių, patirtį ir atlyginimą. Darbuotojo klasė turi konstruktorių, kuriame yra visi egzemplioriaus atributai. Galiausiai taip pat turime metodą, pavadintą show, kuris turi tik spausdinimo teiginį ir naudojamas informacijai spausdinti.
Inžinierius ir konstruktorius yra `base` klasės Darbuotojas antrinės klasės.
Metodas** `super()` padeda antrinei klasei pasiekti patronuojančios klasės narius. Inžinierių klasė gauna prieigą prie vardo, amžiaus, exp ir atlyginimo informacijos iš tėvinės klasės.

### `Įkapsuliavimas (Encapsulation)`
**Kapsuliavimas** - tai duomenų paslėpimo procesas, suteikiantis duomenims saugumą, paverčiant kintamąjį apsaugotu. Saugomą narį gali pasiekti tik klasės narys. Jei bandysite jį pasiekti už klasės ribų įprastai, sukurdami objektą, bus padaryta klaida. Norėdami pasiekti saugomą narį, turite naudoti `object._protectedmember`.

Pythone, norėdami sukurti apsaugotą narį, naudojame konvenciją, pagal kurią prieš nario pavadinimą rašome vieną pabraukimą, pvz., `_name.`

Inkapsuliavimas apsaugo objektą nuo nepageidaujamos klientų prieigos. Tai sumažina žmogiškųjų klaidų tikimybę ir supaprastina programos priežiūrą. Inkapsuliavimas leidžia pasiekti lygį neatskleidžiant detalių: 🔽 

```python
class Parent:                                      ## Creating a class name Parent
    def __init__(self):                            ## Constructor of parent class

        # protected member
        self._mobilenumber = 5555551234            ## Protected member of the class Parent 

class Child(Parent):                               ## Child class inhering properties from the Parent class
    def __init__(self):                            ## Constructor of the class name 
        Parent.__init__(self)                      ## accessing members of the Parent class, another way is to used super()
        print("Calling Protected Member") 
        print(self._mobilenumber)                  ## accessing protected member using the class member

obj = Child()                                      ## creating the object 
print(obj.mobilenumber)                            ## AttributeError: 'Child' object has no attribute 'mobilenumber'
print(obj._mobilenumber)                           ## Prints mobilenumber, explicitly allowing the access to protected member
```
`_mobilenumber` yra apsaugotas klasės narys, kurį klasės nariai ir objektas gali pasiekti tik gavę aiškų leidimą.


### `Polimorfizmas (Polymorphism)`
Polimorfizmas - tai skirtingų formų turėjimas. Tai reiškia, kad funkcija, turinti tą patį pavadinimą, gali atlikti visai kitą funkciją. Vienas geriausių polimorfizmo pavyzdžių yra funkcija `len()`. Kai ją naudojame `list`, ji grąžina sąrašo elementų skaičių. Kai ją naudojame `dict`, ji grąžina raktų skaičių. Kai ją naudojame su `str`, ji grąžina eilutės simbolių skaičių. Pažiūrėkime polimorfizmo pavyzdį. Paprastas pavyzdys: ⏬
```python
def add(x: int, y: int, z: int = 0) -> int:
    return x+y+z

print(add(5, 6))
print(add(5, 7, 4)) 
----------OUTPUT--------------
11
16
```

Pirmiau pateiktame kode parodyta, kaip viena funkcija gali būti naudojama dviejų ir trijų skaičių sudėčiai vienu metu atlikti.
Dabar pažiūrėkime į polimorfizmą klasės metode:

```python
class Rectangle:
    def __init__(self, l, b):
        self.l = l
        self.b = b

    def area(self):
        return self.l * self.b

class Square:
    def __init__(self, side):
        self.s = side

    def area(self):
        return self.s ** 2

rec = Rectangle(10, 20)
squ = Square(10)
for data in (rec, squ):
    print(data.area())    
    
-----------------------------OUTPUT----------------------------
200
100
```

Pirmiau pateiktame kode `area()` atlieka dvi užduotis skirtinguose programos egzemplioriuose. Iš vienos pusės ji apskaičiuoja stačiakampio plotą, o iš kitos pusės - kvadrato plotą toje pačioje programoje.

### `Abstrakcija (Abstraction)`
**Abstrakcija** naudojama vidiniam funkcijos funkcionalumui nuo naudotojų paslėpti. Taikant `abstrakciją`, kiekvienas objektas atskleidžiamas tik aukšto lygio jo naudojimo mechanizmu. Metodas, kuris turi tik **deklaraciją, o ne apibrėžtį, vadinamas abstrakčiuoju metodu**. Abstraktusis metodas neturi nieko savo viduje. Klasė, kuri turi abstraktų metodą, vadinama abstrakčia klase.

Standartiškai "Python" nepalaiko abstrakčiųjų klasių, tačiau yra modulis `abc`, kuris leidžia "Python" kurti abstrakčiuosius metodus ir klases.
Daugiau apie abstrakciją: 📖 [Real Phyton : Python Interfaces](https://realpython.com/python-interface/)

## Pratimai: 
🧠 : Pakartokite [Sąlyginiai teiginiai](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-6:-Conditional-Statements), [Kilpos](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-8:-Loops), [Funkcijos](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-10:-Functions), kad užbaigtumėte šias užduotis.
1) Sukurkite keletą savo pavyzdžių, kuriuose parodytumėte ir panaudotumėt keletą OOP paradigmų praktikoje.

2) Parašykite klasę `CoffeeShop`, kuri turi tris inicializuotos klasės kintamuosius:

  - `name`: `str` (iš esmės parduotuvės pavadinimas)
  - `meniu` : elementų sąrašas (`list`) (`dict` tipo), kuriame kiekvienas elementas turi elementą (elemento pavadinimą), tipą (ar tai maistas, ar 
     gėrimas) ir kainą.
  - `orders`: tuščias `list`

    ir septyni metodai:

   - `add_order`: į užsakymų sąrašo pabaigą įtraukia prekės pavadinimą, jei jis yra meniu, priešingu atveju grąžina "Šiuo metu šios prekės nėra!".
   - `fulfill_order`: jei užsakymų sąrašas nėra tuščias, grąžinama "{prekė} yra paruošta!". Jei užsakymų sąrašas tuščias, grąžinkite "Visi užsakymai 
     įvykdyti!".
   - `list_orders`: grąžina priimtų užsakymų prekių pavadinimus, priešingu atveju - tuščią sąrašą.
   - `due_amount`: grąžina bendrą mokėtiną sumą už priimtus užsakymus.
   - `cheapest_item`: grąžina pigiausio meniu elemento pavadinimą.
   - `drinks_only`: grąžina tik meniu gėrimų tipo elementų pavadinimus.
   - `food_only`: grąžina tik meniu maisto tipo elementų pavadinimus.

  SVARBU: Užsakymai vykdomi FIFO (first IN, first OUT) tvarka.

  Pavyzdžiai: 

    ```python
    tcs.add_order("hot cocoa") ➞ "This item is currently unavailable!"
    # Tesha's coffee shop does not sell hot cocoa
    tcs.add_order("iced tea") ➞ "This item is currently unavailable!"
    # specifying the variant of "iced tea" will help the process

    tcs.add_order("cinnamon roll") ➞  "Order added!"
    tcs.add_order("iced coffee") ➞ "Order added!"
    tcs.list_orders ➞ ["cinnamon roll", "iced coffee"]
    # all items of the current order

    tcs.due_amount() ➞ 2.17
    tcs.fulfill_order() ➞ "The cinnamon roll is ready!"
    tcs.fulfill_order() ➞ "The iced coffee is ready!"
    tcs.fulfill_order() ➞ "All orders have been fulfilled!"
    # all orders have been presumably served

    tcs.list_orders() ➞ []
    # an empty list is returned if all orders have been exhausted

    tcs.due_amount() ➞ 0.0
    # no new orders taken, expect a zero payable

    tcs.cheapest_item() ➞ "lemonade"
    tcs.drinks_only() ➞ ["orange juice", "lemonade", "cranberry juice", "pineapple juice", "lemon iced tea", "vanilla chai latte", "hot chocolate", 
    "iced coffee"]
    tcs.food_only() ➞ ["tuna sandwich", "ham and cheese sandwich", "bacon and egg", "steak", "hamburger", "cinnamon roll"]
    ```

3) Atnaujinkite ankstesnės užduoties sprendimą, naudodami OOP paradigmas. (Minimaliai: įkapsuliavimas, paveldimumas)
4) Sukurkite Python programą, imituojančią elektronikos parduotuvę. Parduotuvėje parduodami įvairių tipų elektroniniai prietaisai, pvz., nešiojamieji 
   kompiuteriai, išmanieji telefonai ir televizoriai.

   - Sukurkite bazinę klasę `ElectronicDevice` su tokiais atributais kaip `brand`, `price` ir `warranty_period`. Ji turėtų turėti metodus `get_details()` 
     ir  `pirkti()`. Metodas `purchase()` turėtų sumažinti įrenginio atsargas `1`.

    - Sukurkite antrines klases `Laptop`, Smartphone` ir `Television`, kurios paveldi iš klasės `ElectronicDevice`. Kiekviena iš šių klasių turėtų turėti 
      papildomų joms būdingų atributų. Pavyzdžiui, `Laptop` gali turėti `ram` ir `storage`, `Smartphone` gali turėti `screen_size` ir 
      `battery_capacity`, o `Television` gali turėti `screen_size` ir `resolution`.

    - Naudokite prieigos modifikatorius, kad užtikrintumėte, jog kainos ir atsargų atributai negali būti tiesiogiai pasiekiami ar keičiami už klasės 
      ribų.

    - Sukurkite kiekvieno įrenginio klasės instance ir iškvieskite jų metodus, kad išbandytumėte funkcionalumą.

    - Įgyvendinkite `Discount` klasę, kurią galima taikyti elektroniniams prietaisams, kad sumažėtų jų kaina. Ši klasė turėtų turėti metodą 
      `apply_discount()`, kuris priima `ElectronicDevice` objektą ir nuolaidos procentą bei grąžina kainą po nuolaidos.

## 🌐 Papildomas skaitymas (arba žiūrėjimas 📺 ):


* [OOP kursas - Youtube](https://www.youtube.com/watch?v=Ej_02ICOIgs)
* [Corey Schafer: Python OOP Tutorial (keli vaizdo įrašai)](https://www.youtube.com/watch?v=ZDa-Z5JzLYM)
* [Datacamp](https://www.datacamp.com/tutorial/python-oop-tutorial)
***