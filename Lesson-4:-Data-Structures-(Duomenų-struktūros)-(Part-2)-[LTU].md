## Žodynas (`dictionary`)
❗ Kurso metu bus naudojamas `EN` atitikmuo: `dictionary` arba `dict`.

Tai labai pravarti duomenų struktūra, kuri bus dažnai naudojama kodo struktūrizavimo procese. `Dictionary` yra sudaromas iš rakto (`key`) ir vertės (`value`) porų (`pairs`): `{key: value}`.

`Dictionaries` yra: 

1. mutable ✔️ (gali būti keičiami)
1. dynamic ✔️ (gali didėti ir mažėti)
1. nested ✔️ (gali apimti kitus žodynus arba kitas sudėtingesnes struktūras)

`Dictionary` - tai duomenų rinkinys, kuris yra rūšiuotas (`ordered`),gali būti keičiamas (`changeable`), bet neleidžia dubliuotis rakto (`keys`) reikšmėm. `Dictionary` reikšmės pasiekiamos pagal jų `keys`.

`Dictionary` sukūrimas:

```python
my_dictionary = {}
my_dictionary["name"] = "Tom"
print(my_dictionary["name"]])
```

```python
my_dictionary = {"name": "Tom"}
print(my_dictionary["name"]])
```

### Prieiga prie `dictionary values`

```python
my_dictionary = {"name": "Tom", "pavardė": "Tom", "Tom", "Edison"}
print(f"vardas: {my_dictionary['name']}")
print(f"surname: {my_dictionary['surname']}")
```

Jei reikšmė neegzistuoja, gausime `KeyError`, nes toks `key` neegzistuoja:

```python
my_dictionary = {"name": "Tom", "surname": "Edison"}
print(f"favourite car: {my_dictionary['car']}")
# KeyError: 'car'
```

`Dictionary keys` gali būti bet koks nekintamas (`immutable`) duomenų tipas/struktūra (taigi, negalėsite panaudoti `list` or `dict`) , bet tai negalioja `values`.

### Keičiam `values`

```python
my_dictionary = {"name": "Tom", "surname": "Edison"}
my_dictionary["name"] = "Charles"
print(f"name: {my_dictionary["name"]}")
```

### `key value` pašalinimas

```python
my_dictionary = {"name": "Tom", "surname": "Edison"}
del my_dictionary ["name"]
print(my_dictionary)
```


### Sudėtingesnės (`nested`) struktūros

Matėme, kad `list` gali _talpinti_ kitus `list` savyje kaip `list` elementus. Taip ir `dictionary` gali talpinti kitą `dict` kaip `value`, todėl galime sudaryti tokias sudėtingas hierarchijas:

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

Tarkime, jei norėtume spausdinti visas kalbas (`value` =`languages`) vieną po kitos, galėtume padaryti taip:
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


### `.items()`

Jei norime iteruoti per `dictionary`, naudosime integruotą `.items()` metodą:

```python
d = {'a': 10, 'b': 20, 'c': 30}
print(list(d.items()))
```

### `.keys()`

Šitas metodas grąžina visus `dict` `keys`:

```python
d = {'a': 10, 'b': 20, 'c': 30}
list(d.keys())
```

###  `.values()`
Šitas metodas grąžina visus `dict` `values`:

```python
d = {'a': 10, 'b': 20, 'c': 30}
list(d.values())
```

###  `.pop`
Šitas metodas išmeta `key value` porą, bet gražina tos poros `value`:

```python
d = {'a': 10, 'b': 20, 'c': 30}
result = d.pop('a')
print(result)
print(d)
```

### `.update(obj)`

Tarkim `obj` yra `dict` ir mes turėdami kitą `dict` (pavyzdžiui: `my_dict`) juos abu galime sujungti: `my_dict.update(obj)`.
Jei `key`, kuris ateina iš `obj` neegzistuoja mano `my_dict`, tai jis yra pridedamas iš jo (kaip `key value` pora), o jei egzistuoja - tada `my_dict` `value` pakeičiamas su `value` kurį gavome: 

```python
dict_one = {'a': 10, 'b': 20, 'c': 30}
dict_two = {'b': 200, 'd': 400}
dict_one .update(dict_two )
print(dict_one )
```

```python
dict_one = {'a': 10, 'b': 20, 'c': 30}
dict_one .update([('b', 200), ('d', 400)])
print(dict_one )
```

```python
dict_one = {'a': 10, 'b': 20, 'c': 30}
dict_one .update(b=200, d=400)
print(dict_one )
```

### Iteravimas per `dict`

Pavyzdys:

```python
d = {'a': 10, 'b': 20, 'c': 30}
for key, value in d.items():
    print(key, value)
```

### Dviejų `list` konvertavimas į `dict`

Atkreipkite dėmesį, kad abu `list` turi būti vienodo ilgumo:

```python
test_keys = ["Albert", "Tom", "Stephen"]
test_values = [1, 4, 5]
my_dictionary= dict(zip(test_keys, test_values))
print(my_dictionary)
```

## Aibės (`Set`)

`Set` dažnai naudojami keliems elementams saugoti viename kintamajame.
`Set` - tai kolekcija, kuri yra nerūšiuota, nekeičiama ir neindeksuojama.

**Pastaba: `sets` elementai yra nekeičiami, tačiau galite juos pašalinti arba pridėti naujus elementus**.
 
```python
my_set = {1, 2, 3}
```


Dar viena svarbi savybė - rinkiniuose negalime laikyti dublikatų:

```python
my_set = {1, 2, 3, 1}
print(my_set)
# {1, 2, 3}
```

Tą galim panaudoti, tarkim unikalių reikšmių gavimui iš python `list`:

```python
numbers_list = [1, 2, 3, 4, 5, 5, 5, 5, 6]
numbers_set = set(numbers_list)
print(numbers_set)
# {1, 2, 3, 4, 5, 6}
```

## 🧠Užduotys

1. Parašykite python programą, kuri paprašytų vartotojo įvesti vardą, pavardę, amžių. Įrašykite šias reikšmes į `dict` duomenų struktūrą ir ją 
   išspausdinkite.
2. Pabandykite sukurti `dict` struktūrą, kurioje turite panaudoti visas jums žinomas duomenų struktūras ir tipus.
3. Sukurkite programą, kuri iš sakinių, kuriuos jus įvedėt, sukurtų `dict`, kuriame `keys` reikštų `raides`, o `values`
   šių raidžių dažnumą tuose sakiniuose. Programa turi reikalauti, kad vartotojas įvestų ne mažiau kaip 3 sakinius. 

## 🌐 Papildomas skaitymas:
* [Python duomenų struktūras](https://corporatefinanceinstitute.com/resources/data