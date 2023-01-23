# 🐍 Integruotos funkcijos

## print()

Kaip matėme anksčiau, jau porą kartų naudojome `print` ir su ja susipažinome. Pačios funkcijos nekūrėme, nes ji pateikiama iškart po python įdiegimo. Svarbu paminėti, kad ši funkcija nėra tokia nuobodi, kaip gali pasirodyti iš pirmo žvilgsnio, iš tikrųjų ji gana universali.

print(object(s), sep=separator, end=end, file=file, flush=flush)

| argumentas| reikšmė |
| ------------- | ------------- |
| object(s) | Bet koks objektas ir tiek, kiek norite. Prieš spausdinant bus konvertuotas į string'ą |
| sep='separatorius' | Neprivaloma. Nurodykite, kaip atskirti objektus, jei jų yra daugiau nei vienas. Numatytoji reikšmė yra ' '  |
| end='end' | Neprivaloma. Nurodykite, ką spausdinti pabaigoje. Numatytoji reikšmė yra "\n" (string'o padavimas) |
| file | Neprivaloma. Objektas su rašymo metodu. Numatytoji reikšmė yra sys.stdout |
| flush | Neprivaloma. Loginis reikšmė, nurodanti, ar išvestis išplaunama (True), ar buferizuojama (False). Numatytoji reikšmė yra False |

Keletas pavyzdžių:
```python
# Paprastas spausdinimas
print("hello world")

# Gaunamas tas pats rezultatas, bet šiek tiek kitaip:
print("hello", "world")

# Gaunamas tas pats rezultatas, bet jis dar labiau skiriasi:
print(*["hello", "world"])

# Pažaiskime su skirtuku:
print("hello world", sep=",")

# dar šiek tiek
print("hello", "world", sep=" amazing ")
```

## type()

Kita naudinga funkcija, padedanti suprasti, su kuo susiduriame "Python", yra type. dažnai ji padeda suprasti, su kokiu objektu susiduriame. Iš esmės ji pasako, su kokios rūšies objektu turime reikalą.


Pavyzdžiai:
```python
greet = "Hello World"
print(type(a))

number = 2022
print(type(number))

my_list = [1, 2, 3]
print(type(my_list))

print(type(my_list[0]))
```

Vėliau tai labai pravers dirbant su sudėtingesnėmis programomis.

## len()
Šią funkciją jau matėme anksčiau su list, todėl esame šiek tiek susipažinę ir su in. Kaip pamenate, ji grąžina list arba tuple ilgį.
Nepaisant to, ji vis dar veikia ir su string'u. 

Pavyzdžiai:
```python
word = "kažkas"
length = len(word)

print(f "Žodžio {žodis} ilgis yra: {ilgis}")
```

Primename, kaip tai veikia su list:

```python
my_list = [1, 2, 3]

print(f "list {my_list} ilgis yra: {len(my_list)}")
```

## round()

Funkcija leidžia suapvalinti kintamąjį skaičių iki tam tikro dešimtainio taško. Ji taip pat gana naudinga.

round(skaičius, ndigits=None)
| argumentas| reikšmė |
| ------------- | ------------- |
| skaičius | skaičius, kurį reikia apvalinti |
| ndigits | dešimtųjų skaitmenų, pagal numatytuosius nustatymus - None, o tai reiškia, kad bus apvalinama iki sveikojo skaičiaus vertės |


Pavyzdžiai:

```python
print(round(1.999))

print(round(1.5555, 2))
```

## rūšiuota

Ką daryti, jei norėtume surūšiuoti list arba tuple reikšmes

sorted(iterable, key=None, reverse=False)
| argumentas| reikšmė |
| ------------- | ------------- |
| iterable | seka (string, tuple, list) arba kolekcija (aibė, žodynas, užšaldyta aibė), arba bet koks kitas iteratorius.  |
| reverse| (pasirinktinai) - Jei True, surūšiuotas list yra atvirkštinis (arba surūšiuotas mažėjančia tvarka). Jei nenurodyta, numatytasis nustatymas yra False.  |
| key | (Neprivaloma) - Funkcija, kuri naudojama kaip raktas rūšiavimui palyginti. Numatytoji reikšmė yra None.  |


Pavyzdžiai:
```python
my_list = [45, 20, 14, 55]
sorted_list = sorted(my_list)

print(sorted_list)

sorted_reverse_list = sorted(my_list, reverse=True)

print(sorted_reverse_list)
```

Kaip elgtis su string reikšmėmis?

```python
my_list = ["Albert", "Nicola", "Thomas"]
sorted_list = sorted(my_list)

print(sorted_list)

sorted_reverse_list = sorted(my_list, reverse=True)

print(sorted_reverse_list)
```

Vis dar veikia!


Daugybę kitų integruotų funkcijų galite ištirti [nuoroda](https://docs.python.org/3/library/functions.html) Kai kurios iš jų mums dar per ankstyvos, tačiau, tobulėjant kursui, naudosime vis daugiau ir daugiau jų.

## 🧠 Pratimai:

1. Sukurkite įvairių tipų Python objektų list ir išspausdinkite visus tipus. Tas, kuris surinks daugiausiai unikalių tipų, laimi pagarbos taškų:
1. Atspausdinkite visus elementus, atskirtus "|"
1. Sukurkite kintamųjų skaičių list su 3 ženklais po kablelio, sukurkite kitą list su visomis reikšmėmis, suapvalintomis iki 2 ženklų po kablelio.
1. Sukurkite list su mokinių vardais ir juos surūšiuokite, rezultatą išspausdinkite į terminalą.
1. Parašykite programą, kuri leistų vartotojui įrašyti bet kokį kintamąjį skaičių ir jį suapvalinti.


## 🌐 Papildomas skaitymas:
[visi integruoti dalykai] (https://www.programiz.com/python-programming/methods/built-in)
