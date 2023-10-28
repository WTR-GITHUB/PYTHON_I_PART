

## Python sąlyginiai sakiniai (`if` conditional statement)
❗ Kurso metu bus naudojami EN atitikmuo: `conditional statement`.  

`If` _conditional statement_ dažnai naudojamas jei norim implementuoti tam tikrą loginę seką su turimais kintamaisiai ir reikiamomis aplinkybėmis: 

Kaip tai atrodo:

```python
if <test_expression>:
    statement(s)
```


Loginė `if conditional statement` diagrama:

![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/if_else.webp)


Sąlygoms tikrinti python palaiko įprastas matematines išraiškas:

* Lygus: a == b
* Nelygu: a != b
* Mažiau nei: a < b
* Mažiau nei arba lygu: a <= b
* Daugiau nei: a > b
* Daugiau arba lygus: a >= b

Pavyzdys:

```python
number_one = 500
number_two = 600
if number_one < number_two :
    print("number_one is greater than number_two !")
```
** Svarbu, kad po `conditional statement` būtų pateikta instrukcija, ką daryti toliau, tam tikrai sąlygai pasitvirtinus. Python remiasi _indentacija_ (`indentation`), kad apibrėžtų kodo apimtį ir ribas, t.y. kur prasideda ir užsibaigia `if` bloko logika. **

### `elif`
Jei norime išplėsti programą ir patikrinti papildomą sąlygą, naudojame `elif` : 

Pavyzdys:

```python
number_one = 500
number_two = 600
if number_one < number_two:
    print("number_one is greater than number_two!")
elif number_one == number_two:
    print("Numbers are equal !")
```

**Pastaba. Galit naudoti tiek `elif` teiginių, kiek tik prireiks**

```python
number_one = 500
number_two = 600
if number_one < number_two :
    print("number_one is greater than number_two  !")
elif number_one == number_two :
    print("numbers are equal !")
elif...
```

### `else`

Raktiniu žodžiu `else` _sugaunama_ viskas, ko _nesugaudė_ ankstesnės sąlygos:

```python
number_one = 500
number_two = 600
if number_one < number_two :
    print("number_one is greater than number_two  !")
elif number_one == number_two :
    print("numbers are equal !")
else:
    print("number_two is greater than number_one !")
```

## Sutrumpinta `if ... else` versija:

```python
a = 200
b = 450
print("A") if a > b else print("B")
```

3 _sąlygų_ pavyzdys:

```python
a = 200
b = 200
print("A") if a > b else print("=") if a == b else print("B")
```

### `and`
Turime daugiau loginių operatorių, kurie leidžia praplėsti lognius veiksmus.

Raktažodis `and` yra loginis operatorius, kuris yra naudojamas sąlyginių teiginių sujungimui.
Iš esmės abi sąlygos turi būti teisingos, kad teiginys grąžintų `True`:

```python
a = 200
b = 400
c = 500
if c > a and c > b:
    print("C is the greatest of them all!")
```

### `or`

Raktažodis arba yra loginis operatorius,kuris yra naudojamas sąlyginiams teiginiams sujungti.
Iš esmės bent viena iš sąlygų turi būti teisinga, kad teiginys grįžtų `True`:

```python
a = 200
b = 400
c = 500
if b > a or b > c:
    print("B is at least greater than one of the values !")
```

## Įterptinis `if`

Kaip matėme, kad `list'ai` gali turėti kitus `list'us` savo _viduje_, kaip ir `dictionary` turi įterptines struktūras. Išimčių nėra ir `if` teiginiams:

```python
x = 15

if x > 10:
  print("Above 10")
  if x > 20:
    print("and also above 20!")
  else:
    print("Above 10 but bellow 20!.")
```

### `pass`

Jei dėl kokių nors priežasčių norime turėti tuščią `if` teiginį ir kad python interpretatorius nemestų klaidos, galime tiesiog panaudoti `pass` sąlygą:

```python
a = 50
b = 80

if b > a:
  pass
```


### `if` su `string` reikšmėmis

Su `string` taip pat galime atlikti logines operacijas:

```python
name = "Tom"

if name == "Tom":
    print("Nice to see you Tom")
else:
    print("welcome, user")
```

Be to, tai taikoma ir `list` duomenų struktūroms:

```python
user = "Johnny"
privileged_users = ["Tom", "Albert", "Stephen"]
if user in privileged_users:
    print(f"Welcome home {user}")
else:
    print("INTRUDER ALLERT. Silently calling police...")
```


`dictionaries`:

```python
my_dict = {"name": "Steven", "born": "1955-02-24", "interests": "Apples"}
if my_dict["name"] == "Steven":
    print("This guy does not like Windows")
else:
    print("No clue who this is")
```

```python
my_dict = {"name": "Steven", "born": "1955-02-24", "interests": "Apples"}
if my_dict["name"] == "Steven":
    print("This guy does not like Windows")
else:
    print("No clue who this is")
```
### Trumpesnė `if..` versija 

Python kalboje mėgstame daryti dalykus, kurie yra lengviau skaitomi, trumpesni, lengvesni. Pavyzdžiui, jei norime patikrinti, ar naudotojas apskritai įvedė vardą (`name`) . Užuot tai darę:

```python
...
if name != "":
  print("Name was not entered")
...
```
arba:

```python
...
if len(name) == 0:
  print("Name was not entered")
...
```
Darykim taip:

```python
if not name:
  print("Name was not entered")
```

Tas pats taikoma ir kitoms duomenų struktūroms:

```python
my_list = []
if not my_list:
  print("oh no, list is empty")
```

## 🧠 Pratimai:

1. Leiskite naudotojui įvesti vardą, pavardę ir amžių. Išspausdinkite, ar naudotojas gali patekti į internetinį kazino, ar ne. 21 metai yra amžiaus riba.
2. Sukurkite duomenų bazę (privilegijuotų naudotojų sąrašas), išspausdinkite konkretų pranešimą su asmeniniu pasveikinimu, jei naudotojas yra 
   privilegijuotas,arba tik "Sveiki atvykę" kitu atveju.
3. Leiskite naudotojui įvesti du skaičius. Išspausdinkite, kuris iš jų didesnis už kitą,arba ar jie lygūs.
4. Parašykite nedidelę skaičiuotuvo programą, kuri leistų naudotojui įvesti du skaičius ir simbolį, ir tada atlikti operaciją bei išspausdinti atsakymą.
5. Sukurkite skaičių nuo 1 iki 10 spėjimo žaidimą su atsitiktinių skaičių biblioteka. (GALBŪT IDĖJA VĖLESNIAM LAIKUI)


## 🌐 Papildomas skaitymas:
[RealPython] (https://realpython.com/python-conditional-statements/)