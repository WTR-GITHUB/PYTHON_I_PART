## SĄRAŠAI

Šiame skyriuje apžvelgsime vieną Python duomenų struktūrą - `sąrašą` arba tai, kas kitose programavimo kalbose vadinama `masyvu`.

`Sąrašuose` gali nebūti jokių reikšmių, jie gali būti tušti arba juose gali būti tiek objektų, kiek leidžia operatyvioji atmintis. Be to, taip jau atsitiko, kad Python programoje `sąrašuose` galima laikyti _bet kokio tipo reikšmes_, tai gali būti kiti objektai, funkcijos, eilutės, sveikieji skaičiai, jūsų pačių duomenų tipai ar net kiti sąrašai. Svarbu paminėti ir tai, kad sąraše galime keisti reikšmes, sąrašai yra keičiami Python objektai.


## Žymėjimas

Sąrašo žymėjiomas yra laužtiniai skliaustai: [ ] - du skliaustai, tarp kurių yra kableliais atskirtos reikšmės.

## Tuščio sąrašo sukūrimas programoje "Python:

```python
my_list = [] # Instantiating empty list
```
## Specialūs python sąrašų metodai

### .append()
Yra metodas .append(), kuriuo galima įterpti elementą į sąrašą: append(<objektas>)

```python
my_list = []

name = "Tom"
my_list.append(name)
print(my_list)
```

### .count(obj)
Kadangi sąraše gali būti dubliuotų reikšmių, ši funkcija leidžia apskaičiuoti elemento dažnį sąraše:

```python
my_list = [1, 1, 2 ,3 ,4 ,5]
print(my_list.count(1)) # 2
```
### .insert()
Kaip matėme, `append` visada prideda reikšmę į sąrašo galą, o `.insert()` leidžia pridėti reikšmę į bet kurį norimą indeksą:

```python
my_list = [1, 1, 2 ,3 ,4 ,5]
my_list.insert(1, 50)
print(my_list) # [1, 50, 1, 2, 3, 4, 5]
```
### .remove()
Pavadinimas kalba pats už save: šiuo metodu tiesiog išmesime tam tikrą reikšmę iš sąrašo:

```python
my_list = [1, 1, 2 ,3 ,4 ,5]
my_list.remove(1)
print(my_list)
```
Funkcija pašalins pirmą rastą objektą. Jei norite iš sąrašo pašalinti tam tikrą elementą, tai galite padaryti naudodami `pjaustymo` mechanizmą:

```python
my_list = [1, 1, 2 ,3 ,4 ,5]
my_list.remove(my_list[-1]) # removing last item from the list
print(my_list) [1, 1, 2, 3, 4]
```
## "Python" integruotos sąrašo funkcijos

Kadangi su tokiomis funkcijomis, kaip `print` ir tikriausiai dar keliomis kitomis, jau susidūrėme, "Python" sąrašuose taip pat naudojama nemažai tokių funkcijų, todėl nereikia kiekvieną kartą išradinėti dviračio iš naujo.

### len()
Atkreipkite dėmesį, kad dabar neturime simbolio ".", o tai reiškia, kad yra atskirų funkcijų, kurios nepriklauso konkrečiam duomenų tipui.

Kaip jau aptarėme anksčiau, sąrašai gali būti bet kokio ilgio, todėl būtų gerai žinoti, su kokio dydžio sąrašu susiduriame. čia praverčia `len()`:

```python
my_list = ["name", 123, None, True]
print(len(my_list)) # 4
```

### max()
Jei turite `int`, `float` reikšmių sąrašą, naudodami šią funkciją galite sužinoti didžiausią reikšmę:

```python
my_list = [50, 99, 1, -50]
print(max(my_list))
```

### min
Jei turite `int`, `float` reikšmių sąrašą, naudodami šią funkciją galite sužinoti mažiausią reikšmę:

```python
my_list = [50, 99, 1, -50]
print(min(my_list))
```

## Sąrašo elementų iteravimas

Didžiausia sąrašų stiprybė yra ta, kad galime turėti tam tikrų veiksmų, objektų, kuriuos norime atlikti vieną po kito, sąrašą, galime juos iteruoti ir atlikti tam tikrus veiksmus:

```python
my_list = [1, 2, 3]
for item in my_list:
    print(item)
```
arba galime atlikti keletą operacijų pakeliui!

````python
my_list = [1, 2, 3]
for item in my_list:
    print(item + 20)
```

## Esamos reikšmės keitimas sąraše

````python
my_list = [1, 2, 3]
my_list[2] = 5
print(my_list)
```
## Skirstymas dalimis
Kaip ir eilutės atveju, taip ir sąrašo elementus galime `pjaustyti` griežinėliais. kiekvienas sąrašo elementas turi indeksą, prasidedantį nuo 0. Taigi galime atlikti tokio paties tipo pjaustymą:

````python
my_list = ["first", "second", "third"]
print(my_list[-1])
print(my_list[:1])
print(my_list[::2])
print(my_list[::-1])
print(my_list[0:2])
```

## Operatorius `in` su sąrašais

Jei norite patikrinti, ar tam tikras objektas yra sąraše, galite daryti taip:

````python
my_list = [1, 2, 3]
print(1 in my_list)
```
# Tuple

Dar viena labai panaši python integruota duomenų struktūra yra `Tuple`. Pagrindinis skirtumas yra tas, kad `Tuple` yra nekeičiama. Tai reiškia, kad turime objektą, kuriame yra kelios reikšmės, jos gali būti dubliuojamos, beveik visos savybės yra panašios, išskyrus tai, kad `Tuple` elementų pagal konstrukciją negalima keisti.

## Žymėjimas

Tuple užrašas python'e yra `**( )**` - du skliausteliai, tarp kurių vertės atskiriamos kableliais.

### Tuple kūrimas

````python
empty_tuple = ()
tuple_single_item = (1,)
another_tuple = (1, 2, 3)
```
Atkreipkite dėmesį, kad po kiekvieno elemento `tuple` turi būti kablelis, nors gali būti tik vienas elementas. Visa kita yra tas pats, kaip ir sąraše.

### Operacijos 

Tai yra lygiai tas pats kaip su sąrašais, išskyrus tai, kad `tuple` yra nekintantis. Jei bandysite priskirti naują reikšmę, gausite klaidą:

🛑 
```python
my_tuple = (1, 2, 3)
my_tuple[0] = 500 # TypeError: 'tuple' object does not support item assignment
```

# `Tuple` ir sąrašų santykis

Dabar atrodo, kad `sąrašai` yra daug geresni už `tuples`, tačiau programavime ne visada viskas yra vienpusiška, tai priklauso nuo tam tikrų situacijų.
Paprastai statinėms reikšmėms, kurios nesikeičia, rekomenduojama naudoti `Tuple`, nes pythone jis yra šiek tiek greitesnis nei `sąrašai`. O `sąrašus` turėtume naudoti visada, kai turime reikšmių, kurios keisis, arba kai pats sąrašas didės arba mažės.

## 🧠 Užduotys:

**`visus atsakymus reikia spausdinti terminale`**
1. Parašykite python programą, kuri susumuoja visus sąrašo elementus (visi sąrašo elementai yra sveikieji arba kintamieji skaičiai, sąrašą sukurkite patys).
2. Parašykite python programą, kuri padaugina visus sąrašo elementus (visi sąrašo elementai yra sveikieji skaičiai arba slankiosios vertės, sąrašą sukurkite patys)
3. Parašykite python programą, kuri iš sąrašo gauna didžiausią vertę (visi sąrašo elementai yra sveikieji skaičiai arba plaukiojantieji dydžiai, patys sukurkite sąrašą)
4. Parašykite python programą, kuri sujungia visas sąraše esančias eilutes (visi elementai yra eilutės, sąrašą sukurkite patys)
5. Sukurkite du sąrašus ir juos sudėkite, įsitikinkite, kad viskas veikia taip, kaip norite.
6. Parašykite python programą, kuri paprašytų naudotojo įvesti 3 sveikuosius skaičius ir rastų didžiausią įvestą reikšmę.
7. Pabandykite atlikti tuos pačius pratimus su `tuples`.

## 🌐  Papildomi skaitiniai:

* [w3schools](https://www.w3schools.com/python/python_lists.asp)
* [more material](https://www.programiz.com/python-programming/list)