Galingasis "if

# Python sąlygos ir If teiginiai

Vykdydami kodą paprastai norime priimti tam tikrus sprendimus pagal gaunamus duomenis, o if teiginiai leidžia tai padaryti.

Kaip tai atrodo:
```python
if <test_išraiška>:
    teiginys(-iai)
```


Srauto diagrama:

![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/if_else.webp)


Sąlygoms tikrinti python palaiko įprastas matematines išraiškas:

* Lygus: a == b
* nelygu: a != b
* Mažiau nei: a < b
* Mažiau nei arba lygu: a <= b
* Didesnis nei: a > b
* Didesnis arba lygus: a >= b

Pavyzdys:
```python
number1 = 500
number2 = 600
if number1 < number2:
    print("number1 is greater than number2 !")
```
**Svarbu, kad teiginiai po if sąlygos ir dvitaškio (":") būtų įterpti. Python remiasi įtraukomis (baltaisiais tarpais string pradžioje), kad apibrėžtų kodo apimtį. Kitose programavimo kalbose šiam tikslui dažnai naudojami lenktieji skliaustai**.

## Elif
Ką daryti, jei norime išplėsti programą ir išspausdinti ką nors kita, jei teiginys nėra teisingas?

Pavyzdys:

```python
number1 = 500
number2 = 600
if number1 < number2:
    print("number1 is greater than number2 !")
elif number1 == number2:
    print("numbers are equal !")
```

**Pastaba. Gali būti tiek elif teiginių, kiek norime**

```python
number1 = 500
number2 = 600
if number1 < number2:
    print("number1 is greater than number2 !")
elif number1 == number2:
    print("numbers are equal !")
elif...
```

## Else

Raktiniu žodžiu else sugaunama viskas, ko nesugauna ankstesnės sąlygos.

```python
number1 = 500
skaičius2 = 600
if number1 < number2:
    print("number1 yra didesnis už number2 !")
elif number1 == number2:
    print("skaičiai yra lygūs !")
else:
    print("skaičius2 yra didesnis už skaičių1 !")
```

## trumpoji if ... else versija

```python
a = 200
b = 450
print("A") if a > b else print("B")
```

3 sąlygų pavyzdys:

```python
a = 200
b = 200
print("A") if a > b else print("=") if a == b else print("B")
```

## and
Turime daugiau loginių operatorių, kurie leidžia sujungti teiginius į sudėtingesnę logiką

Raktažodis **ir** yra loginis operatorius ir naudojamas sąlyginių teiginių sujungimui:
Iš esmės abi sąlygos turi būti teisingos, kad teiginys grąžintų True:

```python
a = 200
b = 400
c = 500
if c > a and c > b:
    print("C is the greatest of them all!")
```

## or

Raktažodis arba yra loginis operatorius, naudojamas sąlyginiams teiginiams sujungti:
Iš esmės bent viena iš sąlygų turi būti teisinga, kad teiginys grįžtų True:

```python
a = 200
b = 400
c = 500
if b > a or b > c:
    print("B is at least greater than one of the values !")
```

## Įterptinis if

kaip matėme, kad sąrašai gali turėti kitus sąrašus savo viduje, taip ir žodynai turi įterptines struktūras. Išimčių nėra ir if teiginiams.

```python
x = 15

if x > 10:
  print("Above ten,")
  if x > 20:
    print("and also above 20!")
  else:
    print("but not above 20.")
```

## pass

Jei dėl kokių nors priežasčių norime turėti tuščią if teiginį, galime tiesiog atlikti `pass` ir nieko neįvyks.
```python
a = 50
b = 80

if b > a:
  pass
```


## Jei su string reikšmėmis

Su string taip pat galime atlikti logines operacijas.

```python
name = "Tom"

if name == "Tom"
    print("Malonu tave matyti, Tomai")
else:
    print("Sveiki atvykę, vartotojas")
```

Be to, šias žinias galime sujungti ir su sąrašais!

```python
user = "Johnny"
privileged_users = ["Tom", "Albert", "Stephen"]
if user in privileged_users:
    print(f"Welcome home {user}")
else:
    print("INTRUDER ALLERT. Silently calling police...")
```


Arba net žodynai:
```python
my_dict = {"name": "Steven", "born": "1955-02-24", "interests": "Apples"}
if my_dict["name"] == "Steven":
    print("This guy does not like Windows")
else:
    print("No clue who this is")
```

Arba net:

```python
my_dict = {"name": "Steven", "born": "1955-02-24", "interests": "Apples"}
if my_dict["name"] == "Steven":
    print("This guy does not like Windows")
else:
    print("No clue who this is")
```
## 🤔 trumpesnė if versija ❗❗❗ 

Pythone mėgstame daryti dalykus, kurie yra lengviau skaitomi, trumpesni, lengvesni. Kad būtų daugiau ZEN. Pavyzdžiui, jei norime patikrinti, ar naudotojas apskritai įvedė vardą . Užuot tai darę:
```python
...
if name != "":
  print("Name was not entered")
...
```
arba
```python
...
if len(name) == 0:
  print("Name was not entered")
...
```
Do this:
```python
if not name:
  print("Name was not entered")
```

Tas pats taikoma ir kitoms duomenų struktūroms

```python
my_list = []
if not my_list:
  print("oh no, list is empty")
```

## 🧠 Pratimai:

1. Leiskite naudotojui įvesti vardą, pavardę ir amžių. Spausdinkite, ar naudotojui leidžiama įeiti į internetinį kazino, ar ne. 21 metai yra amžiaus riba.
1. Sukurkite duomenų bazę (privilegijuotų naudotojų sąrašas) išspausdinkite konkretų pranešimą su asmeniniu pasveikinimu, jei naudotojas yra privilegijuotas, ir tik "Sveiki atvykęs kitu atveju".
1. Leiskite naudotojui įvesti du skaičius, išspausdinkite, kuris iš jų yra didesnis už kitą, o