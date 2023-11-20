## Įvadas 

**Kas yra funkcija**?
Funkcijos yra patogus būdas suskirstyti kodą į naudingus blokus, leidžiantis sutvarkyti kodą, padaryti jį skaitomesnį, pakartotinai naudoti ir sutaupyti šiek tiek laiko. Be to, funkcijos yra pagrindinis būdas apibrėžti **sąsajas**, kad programuotojai galėtų dalytis savo kodu.
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

Arba atspausdina atsitiktinį `int` skaičių nuo `0` iki `10`:

```python
def get_random_number():
    print(random.randint(0, 10))
```
Kaip ir integruotosios funkcijos, vartotojo apibrėžtos funkcijos **kviečiamos naudojant funkcijos pavadinimą, po kurio pateikiami skliaustai** : 

```python
get_random_number() 
print_smth()
# ir taip toliau....

```

### Pavadinimų suteikimas (`naming`)

Pasirinkti kintamųjų, funkcijų ir (arba) klasių pavadinimus ir pan. gali būti sudėtinga. Rašydami kodą turėtumėte gerai apgalvoti pavadinimų pasirinkimą, nes taip jūsų kodas bus lengviau skaitomas. Geriausias būdas pavadinti `objektus` Python programoje - naudoti aprašomuosius pavadinimus, kad būtų aišku, ką objektas simbolizuoja.

Pagrindinės taisyklės tokios: 

* Metodų pavadinimuose naudokite tik mažąsias raides.

```python
def compute():
  pass
```

* Metodo pavadinime žodžius reikia atskirti pabraukimu.

```python
def apskaičiuoti_smth():
  pass
```

* Neviešo metodo pavadinimas turi prasidėti vienu pabraukimu.

```python
def _get_smth():
  perduoti
```

* Privataus metodo vardo pradžioje naudokite du iš eilės einančius pabraukimus.

```python
def __get_secret():
  pass
```

Labai geras pavadinimų suteikimo taisyklių ir pavyzdžių šaltinis yra čia: [Python Function Naming](https://melevir.medium.com/python-functions-naming-tips-376f12549f9) ❗ **Turite perskaityti!** ❗

## `return` teiginys 
`return` teiginiai naudojami funkcijai užbaigti ir grąžinti išraišką, kurią galima naudoti vėliau. Tačiau jos nėra privalomos ir gali būti nenaudojamos, jei jų nereikia.
Sintaksė:
```
return [expression]
```
### Keletas pavyzdžių:

```python
def find_sum(num1, num2):
    '''Returns the sum of num1 and num2.'''
    sum_nums = num1 + num2  # Finds the sum of num1 and num2
    return sum_nums  # Returns the sum of the numbers
```

```python
def even_odd(num):

    '''
    Returns "even" if num is even, and "odd" if num is odd.    
    Parameters:
        num (int): Any integer    Returns:
        type (string): "even" if num is even; "odd" if num is odd
    '''

    if num % 2 == 0:  # Checks if num/2 has a remainder of 0
        return "even"  # If it has a remainder of 0, return "even"
    else:
        return "odd"  # If it doesn't, return "odd"
```


👨🏫 ❗ **ATTENTION** ❗ 
**Jei [išraiška] paliekama tuščia, išeinant iš funkcijos bus grąžinamas [``None``](https://realpython.com/null-in-python/) tipo objektas**

```python
def check_if_exist(a=None):
  if a:
    return a
  return
    
```

## Funkcijų parametrai (argumentai):
Parametrai, arba argumentai, yra reikšmės, kurias galite perduoti funkcijai ir nuo kurių priklauso, kaip bus vykdoma funkcija. Yra įvairių būdų, kaip galime perduoti parametrus.

### Poziciniai parametrai:
Dažniausiai parametrai perduodami iškviečiant funkciją ir perduodant parametrus toje pačioje pozicijoje, kaip ir funkcijos apibrėžime. Paimkime dalijimo funkcijos pavyzdį:

```python
def integer_division(num_one, num_two):
    return num_one // num_two

integer_division(10, 2)

----OUTPUT----
>>>> 5
```

## ℹ️ Trumpas įvadas į tipo anotacijas
`tipo anotacijomis`, Python kalboje yra visiškai neprivalomos. Vis dėlto jų naudojimas jūsų kode yra labai naudingas.
Pythone vartojamas tipo terminas reiškia objekto **tipą**. Objektai daugiausia yra daiktai, kuriuose yra duomenų, o funkcijos veikia tuos duomenis. Pavyzdžiui; Python objektas "integer" gali saugoti sveikojo skaičiaus reikšmes ir su juo galima atlikti tam tikras užduotis, pavyzdžiui, atlikti aritmetinius skaičiavimus.

Objektai turi griežtus tipus. Negalite saugoti eilutės reikšmės sveikojo skaičiaus objekto tipe, nes tai neleidžiama šiame konkrečiame tipe. Tačiau vardai, kuriuos naudojame savo kode, gali nurodyti į bet kurį objekto tipą. Turite skirti šiek tiek laiko kodo peržiūrai, kad suprastumėte, kaip galima naudoti konkretų vardą, jei objektų tipai nėra aiškiai anotuoti. Tai bus akivaizdesnė problema, jei turite sudėtingą kodo bazę.

Šiam sunkumui spręsti "Python 3.5" įdiegtos tipų užuominos.
Paprastas funkcijos, kuri sudeda du skaičius, pavyzdys (be `tipų užuominų`):

```python
def add_two_int_numbers(a,b):
  return a + b
```

Ir su `tipo anotacijomis`: 

```python
def add_two_int_numbers(a: int, b: int) -> int:
  return a + b
```

#### Kodėl reikia naudoti tipo anotacijas? 
* Statiškai tipinės kalbos reikalauja, kad apibrėžtumėte objektų tipus, ir jos gali pagauti klaidas prieš paleidimo laiką. Python yra dinamiškai tipizuota kalba ir neverčia jūsų to daryti. Šis lankstumas turi savo kainą. Padidėjus jūsų kodo bazei, gali būti sudėtinga spręsti paleidimo metu atsirandančias TypeErrors klaidas, jei neapibrėšite tipų su tipų užuominomis.
* Turite apsvarstyti galimybę naudoti tipų užuominas, kad padėtumėte kitiems ir sau. Tipų užuominos padidina kodo skaitomumą, kai kodas yra savaime suprantamas.
* Tipų užuominos taip pat padeda kurti ir palaikyti švaresnę kodo architektūrą, nes į tipus reikia atsižvelgti juos anotuojant savo kode.

#### Keletas pavyzdžių, kuriuos lengva sekti:

**Kintamųjų anotacijos**:
Norint anotuoti kintamųjų tipus, pradedama nuo kintamojo pavadinimo ir tęsiama : galiausiai nurodomas kintamojo duomenų tipas.

```python
type_annotation_int: int = 43
type_annotation_float: float = 2,54
type_annotation_string: str = 'efe'
type_annotation_bool: bool = True
```
Taip pat galite anotuoti sudėtingesnius integruotus duomenų tipus, pavyzdžiui, diksus, sąrašus ir tuples. Prieš tai reikia importuoti (apie tai sužinosime kitoje paskaitoje) tipavimo modulį.

```python
from typing import List, Tuple
Dicttype_annotation_tuple: Tuple[str] = ('1','2','3')
type_annotation_list: List[str] = ['a', 'b', 'c']
type_annotation_dict: Dict[str, int] = {'a': 1, 'b': 2}
```
**Duomenų tipų derinimas**:
Jei jūsų kintamasis arba grąžinamas tipas gali būti kelių skirtingų tipų, galite naudoti Union tipo anotaciją.

Iki "Python 3.10" įdiegimas atrodo taip:

```python
from typing import List, Dict
uniontype_annotation_list: List[Union[float,int]] = [1.23, 3.32, 1, 3]
type_annotation_dict: Dict[str, Union[float,int]] = {'a': 1, 'b': 2}
```
Anotacija List[Union[float[float,int]]] reiškia, kad kintamasis type_annotation_list turėtų būti sąrašas, kurio kiekvienas elementas yra arba slankiojo kablelio, arba sveikasis skaičius.

Python 3.10 versijoje Union galima pakeisti naujuoju union operatoriumi | ir jums nereikia nieko importuoti iš rašymo modulio:
```python
type_annotation_list: Sąrašas[float | int]= [1.23, 3.32, 1, 3]
```
**Neprivalomas operatorius**:
Pasirenkamasis[???] - tai sutrumpintas Union[???, None] variantas, kuris iš esmės nurodo, kad reikalingas arba konkretaus tipo objektas, arba None.
```python
type_annotation_list: List[Optional[int]] = [1, 3]
```
Šis įgyvendinimas pasikeitė su 3.10 versija: dabar Optional galima užrašyti kaip List [int | None]

**Funkcijų anotacijos**:
Ankstesniame pavyzdyje matėme, kaip pridėti tipo užuominas prie grąžinimo tipo, argumentų . Dabar sudėtingesnis pavyzdys:
```python
from typing import Tuple, Optional

def the_func(x: Union[int, float], y: Tuple[str, str], z: Optional[float] = None) -> str:
   return 'Jūs iškvietėte the_func su ' + str(x) + str(y) + str(z)
```
Šis pavyzdys rodo, kad the_func() priima tris argumentus, x, y ir z, kad x gali būti sveikasis skaičius arba kintamasis, y turi būti tuple, kuriame saugomos eilutės, o z gali būti none arba kintamasis. Grąžinimo tipas yra str, kurį nurodote naudodami -> po baigiamųjų skliaustų, bet prieš dvitaškį.
ℹ️ 

## Užduotys

❗ Visose užduotyse turi būti nurodyti tipai ❗ 
* Patys sukurkite bent 5 skirtingas funkcijas ir jas išbandykite.
* Sukurkite funkciją, kuri prie kiekvieno sąrašo nario prideda eilutės galūnę.
* Sukurkite mini python programą, kuri kaip įvestį paimtų du skaičius ir grąžintų jų sumą, atimtį, dalybą, daugybą.
* Sukurkite funkciją, kuri grąžintų tik unikalius simbolius turinčias eilutes.


## 🌐 Papildomas skaitymas:

* [Type Annotations in Python 3.8](https://medium.com/analytics-vidhya/type-annotations-in-python-3-8-3b401384403d)

* [Real Phyton](https://realpython.com/defining-your-own-python-function/)

* [Real Python Youtube](https://www.youtube.com/watch?v=Q93bwyZoXk0)
***
ℹ️ 