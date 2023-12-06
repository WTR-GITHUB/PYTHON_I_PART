## `Įvadas`

`Išimtys` - tai įvykiai, kurie sukeliami, kai programa vykdymo metu susiduria su klaida. Įvykus klaidai, galime tvarkyti šias išimtis, kad programa nesugriūtų.

### `Kodėl mums reikalingas išimčių tvarkymas?`

* **Klaidų tvarkymas**: Vykdymo metu įvykus klaidai, programa gali būti besąlygiškai nutraukta. Naudodamiesi išimčių tvarkymu galime tvarkyti nesėkmių scenarijų ir išvengti programos nutraukimo.
* **Kodo atskyrimas**: Klaidų tvarkymas gali padėti mums atskirti kodą, reikalingą klaidoms tvarkyti, nuo pagrindinės logikos. Su klaidomis susijusį kodą galima patalpinti į `except` bloką, kuris jį atskiria nuo įprasto kodo, kuriame yra programos logika.
* **Klaidų tipų grupavimas ir klaidų diferencijavimas**: Tai gali padėti atskirti skirtingo tipo klaidas, su kuriomis susiduriama vykdymo metu. Galime turėti kelis `except` blokus, kurių kiekvienas tvarko tam tikros rūšies klaidas. Toliau straipsnyje matysime, kaip įgyvendinami keli `except` blokai, skirti skirtingoms klaidų rūšims tvarkyti.

Svarbu aiškiai atskirti, kas yra klaida "Python" programoje, nes jos yra dvi. Viena klaida vadinama `sintaksės` klaida ([arba analizės klaida](https://rollbar.com/blog/python-syntaxerror/)). Taip nutinka, kai mūsų programa yra analizuojama ir aptinka neteisingą teiginį mūsų kode. Tokio tipo klaidų negalima tvarkyti.

Pavyzdys:
```python
print(Hello World)
```

```
File "test.py", line 1

    print(Hello World)

                ^

SyntaxError: invalid syntax
```

Kitas klaidų tipas, kurį galime pastebėti, yra `išimties (Execption)` klaida. Tokio tipo klaidos atsiranda, kai mūsų kodas yra sintaksiškai teisingas, tačiau programos vykdymo metu įvyko netikėtas įvykis. Jos nėra besąlygiškai kritinės ir gali būti tvarkomos vykdymo metu.

### `Išimčių gaudymas ir tvarkymas`
Išimtims gaudyti naudojame kodo bloką, vadinamą `try-except`. Kodo dalį, kuri, kaip įtariama, yra klaidos šaltinis, įdedame į `try` bloką, tada atsakymą fiksuojame ir projektuojame `except` bloke.

Paprastas kodo pavyzdys būtų toks: 
```python
def my_func() -> Any:
  try:
    # code which might throw/raise exception
  except <exception_to_handle>:
    # code to be executed once the exception is handled.

my_func()

```

Pagrindinė išimčių tvarkymo schema yra čia žemiau ⬇️ 

![ah](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/try_except_else_finally.webp)

Python sudaro kelios integruotos išimtys, kurias galime panaudoti savo programose: ⬇️

![[](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/1%20yKRseWKBjdccXRoFsjIIQw.png)

### --- Pavyzdžiai ---

#### Basic:
Naudokime paprastą funkciją 2 skaičiams padalyti ir pabandykime išspręsti galimą klaidą:
```python
def divide_two_numbers(dividend: int, divisor: int) -> None:
    try:
        quotient = dividend / divisor
        print(f'Result = {quotient}')
    except ZeroDivisionError:
        print('Divisor is zero; Division is impossible')
```
Galimi rezultatai: 
```
>>> divide(50, 2)
Result = 25
>>> divide(50, 0)
Divisor is zero; Division is impossible
```

### `Daugiau nei viena except išlyga`
Gali būti, kad jūsų kodas gali sukelti daugiau nei vieno tipo išimtis. Tai gali būti `ValueError`, `AttributeError`, `KeyError` ir t.t. Tai kai kurios iš jau minėtų integruotų išimčių. Paimkime paprasto teiginio pavyzdį:
```python
>>> int_value = int(a)
```
Šis teiginys gali iššaukti `ValueError` arba `TypeError`, arba iš viso nesukelti jokių išimčių, priklausomai nuo kintamojo `a` tipo ir vertės. Tarkime, `a = 3,2` arba `a = '1200'`, tada jokių išimčių nebus; jei `a = '12k'`, tada iškils `ValueError`, o jei `a = [1, 2]`, tada iškils `TypeError`.

Štai kaip elgsimės abiem atvejais:

```python
from typing import Union


def my_dummy_int_func(a: Union[str, float]) -> None:
    try:
        int_value = int(a)
    except ValueError:
        print('Value of "a" cannot be deduced to integer')
    except TypeError:
        print('Type of "a" is incompatible; should either be a number or a string')
```
#### `Kelios išimtys vienoje išimties sąlygoje`

```
try:
    # exception prone code here	
except (exception_1, exception_2, .... ,exception_n):
    # code to be executed once the exception is handled
```

Ir tas pats pavyzdys, kaip aukščiau:

```python
def my_dummy_int_func(a: Union[string, float]) -> None:
    try:
        int_value = int(a)
    except (ValueError, TypeError):
        print('Error occurred. Either "a" is not an integer or type of "a" is incompatible')
```

#### `Aliasing`
Atkreipkite dėmesį į šią kodo eilutę:

```
except (exception_1, exception_2, ..) as e:
```
Tai reiškia, kad išimčiai (išimtims) suteikiamas vardas. Techniškai tai vadinama _aliasing_.
Naudodami `aliasing`, galime prieiti prie išimties (-čių) su bendru vardu. Tai naudinga, jei norite naudoti tvarkomos išimties atributus. `Aliasing` atliekamas naudojant raktinį žodį `as` (kodas viršuje):

```python
try:
    # try code
except (exception_1, exception_2, ..) as <alias>:
    # exception handling here
    # you can access attributes of exception(s) being handled through it’s alias < alias >;
```
Kur < alias > turėtų būti pakeistas kintamojo vardu.

Pavyzdys: 

```python
try:
    raise NameError('Undefined name')
    # raise ValueError('Invalid name')
except (NameError, ValueError) as err:
    print(f'Got exception with msg {err.args})

Output:
('Invalid name')
```

ℹ️ - "Python" suteikia galimybę rankiniu būdu iškelti išimtį. Tai raktažodis `raise`. Raktažodis `raise` priima tik vieną argumentą, kuris yra arba išimčių klasė (išvestinė iš `Exception` klasės), arba išimties egzempliorius. Toliau pateiktame pavyzdyje argumentas yra` išimties egzempliorius` su eilutės pranešimu. Siunčiant šį eilutės pranešimą (neprivalomas), jis turėtų apibūdinti klaidą.

```python
>>> raise AssertionError('Asserted statement is incorrect')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
    raise AssertionError('Asserted statement is incorrect')
AssertionError: Asserted statement is incorrect
```

👨🏫 ❗ **DĖMESIO** ❗ 
**Jeigu sutapatinate vieną išimtį, aplinkiniai skliaustai neprivalomi. Skliausteliai yra privalomi, jei sutapatinate kelias išimtis, kaip pirmiau pateiktame pavyzdyje.** ⏫ ⏫  


**Supaprastintas alias kodo šablonas yra toks:** 

```python
def dummy_func() -> None:
    try:
        # dummy full of errors code 😒 
    except Exception as e:
        print(f'Heh, I cought another one...{e}')
```

👨🏫 ❗ **PRO PATARIMAS** ❗ 
**Stenkite vengti bendrinės `except` išlygos, kitaip galite nepastebėti ir (arba) netinkamai elgtis su galimomis klaidomis** 🔽 
```python

def my_func() -> Any:
  try:
    # code which might throw/raise exception
  except:
    print('Ups! Something went wrong!')

my_func()
```

#### `else sąlyga` 
Jei yra `else` išlyga, ji visada turi sekti po `except` išlygos. Kodas, įrašytas `else` sąlygoje, vykdomas tik tada, kai kodas, įrašytas `try` sąlygoje, nesukelia jokios išimties. Jei `try` bloke atsiranda išimtis, `else` blokas nebus vykdomas, nors `except` dalis ją apdoroja:

```python
def divide(a: Union[int, float], b: Union[int, float]) -> Optional[float]:
    try:
        output = a / b
    except ZeroDivisionError:
        print('Cannot divide by zero')
    else:
        print(f'Output = {output}'))
```

```python
>>> divide(20, 10)
Output = 2.0>>> divide(20, 0)
Cannot divide by zero
```

#### `finally sąlyga`
`Finally` sąlyga: `try` teiginys turi paskutinę sąlygą `finally`, kuri iš esmės naudojama kaip valymo veiksmams. Kai ji naudojama, ji turėtų sekti po visų kitų kodo blokų. Nuostata `finally` vykdoma bet kuriuo atveju, nepriklausomai nuo to, ar įvyko išimtis, ar ne. Sąlygai `finally` griežtai nereikia, kad būtų sąlygos `else` arba `except`:

```python
def divide(a: Union[int, float], b: Union[int, float]) -> Optional[float]:
    try:
        output = a / b
    except ZeroDivisionError:
	    print('Cannot divide by zero')
    else:
        print(f'Output = {output}'))
    finally:
        print('Executing finally clause')
```

```python
>>> divide(2, 1)
Output = 2.0
Executing finally clause>>> divide(2, 0)
Cannot divide by zero
Executing finally clause>>> divide("2", "1")
Executing finally clause
Traceback (most recent call last):
 File "<stdin>", line 1, in <module>
 File "<stdin>", line 3, in divide
TypeError: unsupported operand type(s) for /: 'str' and 'str'
```
`Finally` visada vykdoma prieš paliekant [try](https://docs.python.org/3/reference/compound_stmts.html#try) teiginį, nepriklausomai nuo to, ar įvyko išimtis, ar ne. Kai `try` sakinyje įvyko išimtis ir ji nebuvo apdorota [except](https://docs.python.org/3/reference/compound_stmts.html#except) sakiniu (arba ji įvyko except ar else sakinyje), ji iš naujo iškeliama (žr. trečiąjį divide funkcijos iškvietimą pirmiau) po to, kai įvykdomas [finally](https://docs.python.org/3/reference/compound_stmts.html#finally) sakinys. Klauzulė `finally` taip pat vykdoma "išeinant", kai bet kuri kita "try" sakinio sąlyga paliekama per [break](https://docs.python.org/3/reference/simple_stmts.html#break), [continue](https://docs.python.org/3/reference/simple_stmts.html#continue) arba [return](https://docs.python.org/3/reference/simple_stmts.html#return) teiginį.

## Pratimai: 

🧠 : Pakartokite [Funkcijos](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-10:-Functions) ir [Funkcijos (2 dalis)](https://github.com/CodeAcademy-Online/python-new-material/wiki/Lesson-11:-Functions-(-Part-2-)), kad užbaigtumėte šias užduotis.

1) Sukurkite bent 5 skirtingas funkcijas ir pabandykite apdoroti bent 5 integruotas "Python" išimtis.
2) Sukurkite funkciją, kuri apimtų visą klaidų tvarkymo ciklą (try/except/else/finally) su realaus pasaulio scenarijaus pavyzdžiu.
3) Sukurkite mini "Python" programą, kuri įvestų du skaičius ir grąžintų jų sumą, atimtį, dalybą, daugybą. Tvarkykite visas galimas klaidas.  
4) Atnaujinkite ankstesnę užduotį su galimomis `raise` išimtimis.


## 🌐 Papildomas skaitymas:

* [Oficiali Python svetainė](https://docs.python.org/3/tutorial/errors.html)

* [Real Phyton](https://realpython.com/python-exceptions/)

* [Dataquest](https://www.dataquest.io/blog/python-exceptions/)
***