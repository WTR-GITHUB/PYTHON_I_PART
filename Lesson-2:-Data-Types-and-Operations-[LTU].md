## Įvadas

Python `Duomenų tipai` naudojami kintamojo tipui apibrėžti. Jis apibrėžia, kokio **tipo duomenis** ketiname saugoti kintamajame. Duomenys, saugomi atmintyje, gali būti **daugelio tipų**. Pavyzdžiui, asmens amžius saugomas kaip skaitinė reikšmė, o jo adresas - kaip raidiniai skaitmeniniai simboliai.

# Sveikieji skaičiai

Z = {..., -3, -2, -1, 0, 1, 2, 3, ...}

Kaip instancijuoti kintamąjį kaip sveikąjį skaičių Pythone:

```python
a = 5
print(a)

b = 25
print(b)
```

# Operacijos su sveikaisiais skaičiais:
Galimos operacijos:
| Operacija| Rezultatas |
| ------------- | ------------- |
| x + y | x ir y suma |
| x - y | x ir y skirtumas |
| x * y | x ir y sandauga |
| x / y | x ir y dalyba |
| x // y | x ir y dalyba paliekant sveikojo skaičiau dalį|
| x % y | x / y likutis |
| x ** y | x keliamas y laipsniu |

```python
a = 5
b = 25

c = a + b 
print(c)

c = a - b
print(c)

c = a * b
print(c)

c = b / a
print(c)

c = b // a
print(c)


c = a % b
print(c)

c = a ** b
print(c)
```

# Float tipas

Z = {..., -2.5 , ..., -2.0, ... , -1.0, ... , 0, ... , 1.0, ... , 2.0, ... , 2.5, ...}

#### Atkreipkite dėmesį, kad tarp dviejų skaičių yra begalybė float reikšmių.

# Operacijos su float skaičiais
Tie patys veiksmai ir (arba) matematinės išraiškos taikomos ir kintamiesiems skaičiams

Galimos operacijos:
| Operacija| Rezultatas |
| ------------- | ------------- |
| x + y | x ir y suma |
| x - y | x ir y skirtumas |
| x * y | x ir y sandauga |
| x / y | x ir y dalyba |
| x // y | x ir y dalyba paliekant sveikojo skaičiau dalį|
| x % y | x / y likutis |
| x ** y | x keliamas y laipsniu |

```python
a = 5.5
b = 25.3

c = a + b 
print(c)

c = a - b
print(c)

c = a * b
print(c)

c = b / a
print(a)

c = b // a
print(a)


c = a % b
print(c)

c = a ** b
print(c)
```

# string

String- tai tiesiog tekstas, gali būti viena raidė, gali būti pilnas rišlus sakinys:
```python
letter = "a"
name = "Code Academy"
sentence = "I really enjoy learning python !"
```


# String operacijos
Stringai Pythone turi begalę funkcijų kurias galime naudoti, daugiau informacijos [čia](https://www.w3schools.com/python/python_ref_string.asp)

Be to, su string galime išrinkti tam tikrus žodžio simbolius. Štai kaip tai veikia:
![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/string_ops.png)
```python
name = "Code Academy"
print(name[5])

# A

print(name[-2])

# m

print(name[5:12])

# Academy

print(name[5:])

# Academy

print(name[:4])

# Code

print(name[5:12:1])

# Academy

print(name[5::2])

# Aaey

print(name[::-1])

# ymedacA edoC

print(name.split())

# ['Code', 'Academy']

print(name.upper())

# CODE ACADEMY

print(name.replace('c', 'k'))

# Code Akademy

print(name.replace('Code', 'Music'))

```


Taip pat galima gauti paskutinį arba priešpaskutinį string'o simbolį:
```python
print(name[-1])
print(name[-2])
```

Taip pat galite atlikti string'o pjaustymą (slicing):
```python
name = "Code Academy"
print(name[:4])

print(name[5:12])
```

Pabandykite atlikti bet kurį iš aukščiau pateiktoje nuorodoje aprašytų metodų:
```python
name = "Code Academy"
print(name.upper())

print(name.replace('c', 'k'))
```
Arba bet kurį kitą, ką norite.

# String apjungimas
Taip pat galite sujungti įvairius string'us, kad sudarytumėte kitus kintamuosius:

```python
greeting = "Hello, my name is"
name = "Tom"

completed_greeting = f"{greeting} {name}"
print(completed_greeting)
```
Arba:

```python
greeting = "Hello, my name is"
name = "Tom"

completed_greeting = greeting + " " + name
print(completed_greeting)
```

Oho! "+" operatorius veikia ir su string reikšmėmis! Viskas, ką jis daro, yra sujungimas. Tokia gudrybė turi terminą _Operator overloading_ mes išmoksime keletą gudrybių, kaip pritaikyti tam tikrus operatorius mūsų klasėms. Deja, "-" stringo atveju neturi jokios ypatingos prasmės, todėl šis metodas string tipui neleidžiamas.

# Tipų konvertavimas
Dar svarbiau paminėti metodus, leidžiančius paversti duomenis iš vieno tipo į kitą:
Tipai: 

```python
str()
int()
float()
```

Svarbu paminėti, kad ne visi duomenų tipai yra suderinami su tokiomis operacijomis. Pavyzdžiui:
```python
a = "Hello"
b = int(a)
```
Tai paprasčiausiai išmes klaidą, tai būtų kažkokia nesamonė, kaip string'as iš raidžių gali būti paverstas skaitine išraiška?

Pagrindinė taisyklė yra ta, kad visus sveikuosius skaičius, float skaičius galima išversti į string, bet ne visus string galima paversti į int() arba float():

```python
✅ 
a = "55"
b = int(a)
c = float(a)

a = 55
b = str(a)
c = float(a)

🛑 
a = "Sveiki"
b = int(a)

c = float(a)

```

# Vartotojo įvestis

Programa gali paprašyti vartotojo ką nors įvesti ir naudoti tai tolesnėms operacijoms:

```python
name = input("Enter you name: ")
age = input("Enter your age: ")

print(f"Your name is {name}, you are {age} years old"
```


# Taisyklingas kintamųjų vadinimas

Pagal PEP8 https://peps.python.org/pep-0008/ yra tam tikros gairės, kurių reikia laikytis suteikiant kintamųjų pavadinimus. Pythone paprasti kintamieji, kaip šiandien matėme, turėtų būti pavadinti `snake_case` stiliumi. Be to, konstantos visada turėtų būti rašomos didžiosiomis raidėmis, o paslėpti kintamieji arba funkcijos turėtų prasidėti raide "_".

✅ 
```python
_hidden_variable = "secret"
PI = 3,14
vardas = "Albert"
pavardė = "Einstein"
```
⛔ 
įmanoma, bet neatitinka PEP8:
```python
Name = "Albert"
First_Name = "Albert"
FIRST_NAME = "Alb
```


"Python" supras tokią tokį užrašymą, bet jūsų kolegoms bus sunku suprasti kokie kintamieji pas jus naudojami, tad vardan visų - naudokit teisingas `naming` konvencijas.

Kintamieji negali būti vadinami kaip "Python" built-in funkcijos arba specialūs žodžiai, pvz:

"False", "None", "True", "and", "as", "assert", "async", "await", "break", "class", "continue", "def", "del", "elif", "else", "except", "finally", "for", "from", "global", "if", "import", "in", "is", "lambda", "nonlocal", "not", "or", "pass", "raise", "return", "try", "while", "with", "yield



# Pratimai 🧠 
1
* Sukurkite programą, leidžiančią vartotojui įvesti savo vardą ir amžių
* Apskaičiuoti metus, kuriais vartotojas gimė
* Išspausdinti atsakymą į terminalą


2
* Sukurti programą, leidžiančią vartotojui įvesti visą sakinį
* išspausdinti sakinį atbuline tvarka
* spausdinti kas antrą sakinio raidę

3
* Sukurkite programą, kuri tikisi, kad naudotojas įves du skaičius
* padauginkite šiuos skaičius ir išspausdinkite atsakymą
* Sukurkite panašias programas su kitais ženklais.

## 🌐 Papildomas skaitymas:

* [kita medžiaga](https://pythonhumanities.com/lesson-04-python-integers-and-floats/#:~:text=Numeriai%20in%20Python%20egzistuoja%20in,iš%20ir%20eksportuojami%20į%20Excel).
* [operacijos su string reikšmėm](https://www.w3schools.com/python/python_ref_string.asp)

