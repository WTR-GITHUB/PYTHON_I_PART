# sveikieji skaičiai

Z = {..., -3, -2, -1, 0, 1, 2, 3, ...}

Kaip instancuoti kintamąjį kaip sveikąjį skaičių Pythone

````python
a = 5
print(a)

b = 25
print(b)
```

# Operacijos su sveikaisiais skaičiais
Galimos operacijos:
| Operacija| Rezultatas |
| ------------- | ------------- |
| x + y | x ir y suma |
| x - y | x ir y skirtumas |
| x * y | x ir y sandauga |
| x / y | x ir y sandauga |
| x // y | x ir y sandauga |
| x % y | x / y likutis |
| x ** y | x iki galybės y |

````python
a = 5
b = 25

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
:check

# Float tipas

Z = {..., -2.5 , ..., -2.0, ... , -1.0, ... , 0, ... , 1.0, ... , 2.0, ... , 2.5, ...}

#### Atkreipkite dėmesį, kad tarp dviejų kintamųjų gali būti begalė skaičių galimybių.

# Operacijos su sveikaisiais skaičiais
Tie patys veiksmai ir (arba) matematinės išraiškos taikomos ir kintamiesiems skaičiams

Galimos operacijos:
| Operacija| Rezultatas |
| ------------- | ------------- |
| x + y | x ir y suma |
| x - y | x ir y skirtumas |
| x * y | x ir y sandauga |
| x / y | x ir y sandauga |
| x // y | x ir y sandauga |
| x % y | x / y likutis |
| x ** y | x iki galybės y |

````python
a = 5
b = 25

c = a + b 
print(c) # atspausdina 20

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

# Stygos

Stygos - tai tiesiog teksto dalis, kuri gali būti viena raidė, žodis while arba visas sakinys:
```python
raidė = "a"
pavadinimas = "Code Academy"
sakinys = "Man labai patinka mokytis python !"
```


# Operacijos su eilutėmis
Į eilutes "Python" įdiegta daug naudingų funkcijų, daugiau informacijos [čia](https://www.w3schools.com/python/python_ref_string.asp)

Be to, su eilutėmis galime išrinkti tam tikrus žodžio simbolius. Pythone tai veikia:
![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/string_ops.png)
````python
name = "Code Academy"
print(name[5])

# A

print(name[-2])

# m

print(name[5:12])

# Akademija

print(name[5:])

# Akademija

print(name[:4])

# Kodas

print(name[5:12:1])

# Akademija

print(name[5::2])

# Aaey

print(name[::-1])

# ymedacA edoC

print(name.split())

# ["Kodas", "Akademija"]

print(name.upper())

# CODE ACADEMY

print(name.replace('c', 'k'))

# Kodas Akademy

print(name.replace('Code', 'Music'))

```

Taip pat galima gauti paskutinį arba priešpaskutinį eilutės simbolį:
````python
print(name[-1])
print(name[-2])
```

Taip pat galite atlikti eilutės pjaustymą:
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
Arba bet kuris kitas, kaip norite.

# Jungiant eilutę
Taip pat galite sujungti įvairias eilutes, kad sudarytumėte kitus kintamuosius:

```python
pasisveikinimas = "Sveiki, mano vardas yra"
vardas = "Tomas"

completed_greeting = f"{greeting} {vardas}"
print(completed_greeteting)
```
Arba:

```python
sveikinimas = "Sveiki, mano vardas yra"
vardas = "Tom"

completed_greeteting = greeting + " " + name
print(completed_greeteting)
```

Wow! "+" operatorius veikia ir su eilutėmis! Viskas, ką jis daro, yra sujungimas. Tokia gudrybė turi terminą _Operatoriaus perkrovimas_ mes išmoksime keletą gudrybių, kaip pritaikyti tam tikrus operatorius mūsų klasėms. Deja, "-" eilutės atveju neturi jokios ypatingos prasmės, todėl šis metodas eilutės tipui neleidžiamas.

# Tipų konvertavimas
Dar svarbiau paminėti metodus, leidžiančius paversti duomenis iš vieno tipo į kitą:
Tipai: ````python
str()
int()
float()
```

Svarbu paminėti, kad ne visi duomenų tipai yra suderinami su tokiomis operacijomis. Pavyzdžiui:
```python
a = "Hello"
b = int(a)
```
Tai paprasčiausiai išmes klaidą, nes net nėra prasmės, kaip alhapnumerinė reikšmė staiga gali tapti sveikuoju skaičiumi

Pagrindinė taisyklė yra ta, kad visus sveikuosius skaičius, kintamuosius skaičius galima išversti į eilutę, bet tik skaitines eilutes galima paversti int() arba float():

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
name = input("Įveskite savo vardą: ")
age = input("Įveskite savo amžių: ")

print(f "Jūsų vardas yra {vardas}, jums yra {vaikas} metų"
```


# Kintamųjų pavadinimų suteikimo taisyklės

Pagal PEP8 https://peps.python.org/pep-0008/ yra tam tikros gairės, kurių reikia laikytis suteikiant kintamųjų pavadinimus. Pythone paprasti kintamieji, kaip šiandien matėme, turėtų būti pavadinti gyvatės_case stiliumi. Be to, konstantos turėtų būti rašomos visomis didžiosiomis raidėmis, o paslėpti kintamieji arba funkcijos turėtų prasidėti raide "_".

✅ 
````python
_hidden_variable = "secret"
PI = 3,14
vardas = "Albert"
pavardė = "Einstein"
```
⛔ 
įmanoma, bet neatitinka PEP8:
```python
Vardas = "Albert"
First_Name = "Albert"
FIRST_NAME = "Alb

"Python" supras tokią sąvoką, bet jūsų kolegos jūsų už tai nekenčia, todėl laikykitės pavadinimų konvencijos, kad visiems būtų lengviau.

Kintamieji negali būti vadinami kaip "Python" sukurtos funkcijos arba specialūs žodžiai, pvz:
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
* [operacijos su eilutėmis](https://www.w3schools.com/python/python_ref_string.asp)



Translated with www.DeepL.com/Translator (free version)