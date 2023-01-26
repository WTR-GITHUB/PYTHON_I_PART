# Žodynas

labai galinga duomenų struktūra, kuri bus dažnai naudojama. Žodyne saugomos rakto ir vertės poros, naudodami raktą - gausite vertę {key: value}.
Žodynai yra: 

1. keičiami ✔️ (gali būti keičiami)
1. dinaminiai ✔️ (gali didėti ir mažėti)
1. įterptiniai ✔️ (gali apimti kitus žodynus arba kitas sudėtingas struktūras)

Žodynas - tai rinkinys, kuris yra rūšiuotas, keičiamas ir neleidžia dubliuotis rakto reikšmėm.

Pagrindinis skirtumas tarp python sąrašų yra tas, kad žodynų reikšmės pasiekiamos pagal raktus.
Žodyno sukūrimas ir verčių į jį įtraukimas
Pavyzdžiai:

```python
my_dictionary = {}
my_dictionary["name"] = "Tom"
print(my_dictionary["name"]])
```

```python
my_dictionary = {"name": "Tom"}
print(my_dictionary["name"]])
```

## Prieiga prie žodyno reikšmių

```python
my_dictionary = {"name": "Tom", "pavardė": "Tom", "Tom", "Edison"}
print(f"vardas: {my_dictionary['name']}")
print(f"surname: {my_dictionary['surname']}")
```

Jei reikšmė neegzistuoja, gausime KeyError, nes toks raktas neegzistuoja:
```python
my_dictionary = {"name": "Tom", "surname": "Edison"}
print(f"favourite car: {my_dictionary['car']}")
```

Panašiai kaip ir sąrašų atveju, žodynų raktai ir reikšmės gali būti bet kokie objektai. Tačiau paprastai raktai būna string'ai, o reikšmės gali būti bet kas.

## Changing values in dictionary

```python
my_dictionary = {"name": "Tom", "surname": "Edison"}
my_dictionary["name"] = "Charles"
print(f"name: {my_dictionary["name"]})
```

## Rakto pašalinimas iš žodyno

```python
my_dictionary = {"name": "Tom", "surname": "Edison"}
del my_dictionary ["name"]
print(my_dictionary)
```


## Sudėtingesnės struktūros!

Kaip ir su sąrašais, matėme, kad sąrašuose gali būti kitų sąrašų, taip ir su žodynu gali būti kito diciotnario reikšmė, todėl galime sudaryti tokias sudėtingas hierarchijas
```python
user_info = {
	"name": "Albert",
	"pavardė": "Einstein",
	"profesija": {
		"vaidmuo": "profesorius",
		"darbo vieta": "profesorius": "Berlyno universitetas".
	},
        "languages": "kalbos": "vokiečių", "lotynų", "italų", "anglų", "prancūzų"]: ["vokiečių", "lotynų", "italų", "anglų", "prancūzų"]
}
```

Tarkime, jei norėtume spausdinti visas kalbas vieną po kitos, galėtume padaryti taip:
```python
user_info = {
	"name": "Albert",
	"surname": "Einstein",
	"occupation": {
		"role": "Professor",
		"workplace": "University of Berlin"
	},
        "languages": ["German", "Latin", "Italian", "English", "French"]
}

for language in user_info["languages"]:
    print(language)
```
Galimybės čia neribotos, galime eiti vis giliau ir giliau.


## Žodynas į tuplių sąrašą su .items()

Bus daug situacijų, dažniausiai, kai norėsime iteruoti per žodyną, naudosime žodyne integruotą .items() metodą.

```python
d = {'a': 10, 'b': 20, 'c': 30}
print(list(d.items()))
```

## .keys()

grąžina mums visus žodyno raktus:

```python
d = {'a': 10, 'b': 20, 'c': 30}
list(d.keys())
```

## .values()
```python
d = {'a': 10, 'b': 20, 'c': 30}
list(d.values())
```

## .pop

```python
d = {'a': 10, 'b': 20, 'c': 30}
d.pop('a')
print(d)
```

## .update(<obj>)

Jei <obj> yra žodynas, d.update(<obj>) sujungia įrašus iš <obj> į d. Kiekvienam <obj> raktui:
Jei rakto nėra d, rakto ir vertės pora iš <obj> įtraukiama į d.
Jei raktas jau yra d, atitinkama to rakto reikšmė d atnaujinama į reikšmę iš <obj>.

Pavyzdžiai:

```python
d1 = {'a': 10, 'b': 20, 'c': 30}
d2 = {'b': 200, 'd': 400}
d1.update(d2)
print(d1)
```

```python
d1 = {'a': 10, 'b': 20, 'c': 30}
d1.update([[('b', 200), ('d', 400)]])
print(d1)
```

```python
d1 = {'a': 10, 'b': 20, 'c': 30}
d1.update(b=200, d=400)
print(d1)
```

## Iteravimas per žodyną

Pavyzdys:
```python
d = {'a': 10, 'b': 20, 'c': 30}
for key, value in d.items():
    print(key, value)
```

## dviejų sąrašų konvertavimas į žodyną

Atkreipkite dėmesį, kad sąrašai turi būti vienodo dydžio:
```python
test_keys = ["Albert", "Tom", "Stephen"]
test_values = [1, 4, 5]
my_dictionary= dict(zip(test_keys, test_values))
print(my_dictionary)
```

# Set

Set naudojami keliems elementams saugoti viename kintamajame.
Set yra vienas iš 4 Pythono duomenų tipų, naudojamų duomenų rinkiniams saugoti, kiti trys yra [List].
Set - tai kolekcija, kuri yra nerūriuota, nekeičiama* ir neindeksuojama.

**Pastaba: aibės elementai yra nekeičiami, tačiau galite pašalinti elementus ir pridėti naujų elementų**.

Užrašas:
Apibūdinimas: 
```python
my_set = {1, 2, 3}
```


Dar viena svarbi savybė - rinkiniuose negalime turėti dublikatų:

```python
my_set = {1, 2, 3, 1}
print(my_set)
```

unikalių reikšmių gavimas iš python sąrašo:
```python
numbers_list = [1, 2, 3, 4, 5, 5, 5, 5, 6]
numbers_set = set(numbers_list)
print(numbers_set)
```

## 🧠Užduotys

1. Parašykite python programą, kuri paprašytų vartotojo įvesti vardą, pavardę, amžių. Įrašykite šias reikšmes į žodyną ir išspausdinkite žodyną
1. Pabandykite sukurti struktūrą, panašią į čia pateiktą: [iš tuščio žodyno: `my_dict = {}`


## 🌐 Papildomas skaitymas:
* [Daugiau apie Python duomenų struktūras](https://corporatefinanceinstitute.com/resources/data