## List (sąrašai)

Šiame skyriuje apžvelgsime pirmąją Python _duomenų struktūrą_ - `sąrašą` (nuo šiol naudosim EN terminą - 'list' arba sukurtą svetimybę - 'list'e') arba tai, kas kitose programavimo kalbose vadinama `masyvu` (`array`).

`List` gali neturėti reikšmių, jie gali būti tušti arba juose gali būti tiek objektų, kiek leidžia operatyvioji atmintis. Be to, taip jau atsitiko, kad Python programoje `list` galima laikyti _bet kokio tipo reikšmes_, tai gali būti kiti **objektai, funkcijos, eilutės, sveikieji skaičiai, jūsų pačių duomenų tipai ar net kiti list**. Svarbu paminėti ir tai, kad `list` esančios objektų reikšmės galime keisti.

### Žymėjimas

`List` žymėjimas yra laužtiniai skliaustai: [ ] - du skliaustai, tarp kurių yra kableliais atskirtos reikšmės.

### Tuščio `List` sukūrimas `Python` programoje:

```python
my_list = [] # Instantiating empty list
```
### Specialūs `List` metodai

#### .append()
Su metodu `.append()`, galima įterpti elementą į 'list': `append(<object>)`

```python
my_list = []

name = "Tom"
my_list.append(name)
print(my_list)
```

#### .count(obj)
Kadangi `list'e` gali būti dubliuotų reikšmių, ši funkcija leidžia apskaičiuoti elemento dažnį sąraše:

```python
my_list = [1, 1, 2 ,3 ,4 ,5]
print(my_list.count(1)) # 2
```
#### .insert()
Kaip matėme, `append` visada prideda reikšmę į `list'o` galą, o `.insert()` -  leidžia pridėti reikšmę į bet kurį norimą indeksą (`index`):

```python
my_list = [1, 1, 2 ,3 ,4 ,5]
my_list.insert(1, 50)
print(my_list) 
# [1, 50, 1, 2, 3, 4, 5]
```
#### .remove()
Pavadinimas _kalba pats už save_: šiuo metodu tiesiog išmesime tam tikrą reikšmę iš `list'o`:

```python
my_list = [1, 1, 2 ,3 ,4 ,5]
my_list.remove(1)
print(my_list)
```
Funkcija pašalins pirmą rastą objektą. Jei norite iš  `list'o` pašalinti tam tikrą elementą, tai galite padaryti naudodami `slicing` mechanizmą:

```python
my_list = [1, 1, 2 ,3 ,4 ,5]
my_list.remove(my_list[-1]) # removing last item from the list
print(my_list) [1, 1, 2, 3, 4]
```
### "Python" integruotos `List` funkcijos

Kadangi su tokiomis funkcijomis, kaip `print` ir dar keliomis kitomis, jau susidūrėme, su "Python" `list` duomenų struktūra taip pat galima jas panaudoti:

#### len()
Atkreipkite dėmesį, kad dabar neturime simbolio `.`, o tai reiškia, kad yra atskirų funkcijų, kurios nepriklauso konkrečiam duomenų tipui.

Kaip jau aptarėme anksčiau, `list` duomenų struktūra gali būti bet kokio _ilgio_, todėl būtų gerai žinoti, su kokio dydžio `list'u` susiduriame. Čia praverčia `len()`:

```python
my_list = ["name", 123, None, True]
print(len(my_list)) # 4
```

#### max()
Jei tarkim turite `list'a` sudarytą iš `int`, `float` reikšmių , naudodami šią funkciją galite sužinoti **didžiausią reikšmę**:

```python
my_list = [50, 99, 1, -50]
print(max(my_list))
```

#### min
Jei tarkim turite `list'a` sudarytą `int`, `float` reikšmių , naudodami šią funkciją galite sužinoti **mažiausią reikšmę**:

```python
my_list = [50, 99, 1, -50]
print(min(my_list))
```

### `List` elementų iteravimas

Viena iš `list` stiprybių yra ta, kad jei norime atlikti tam tikras operacijas su elementais esančiais duomenų struktūroje, galim iteruoti per jas ir atlikti tam tikrus veiksmus:

🦺 Mes suprantam, kad dar nepraėjome _ciklų_ temos, bet šiuo taveju, tai gali būti puiki vieta įvadui ateinančiom paskaitoms 🦺 

```python
my_list = [1, 2, 3]
for item in my_list:
    print(item)
```
arba galime atlikti keletą operacijų vienu kartu!

```python
my_list = [1, 2, 3]
for item in my_list:
    print(item + 20)
```

### Reikšmės keitimas `List'e`

```python
my_list = [1, 2, 3]
my_list[2] = 5
print(my_list)
```
### Skirstymas dalimis (`slicing`)
Kaip ir `string` atveju, taip ir su `list` galime atlikti `slicing` operacijas. Beto, ** kiekvienas 'list' elementas turi indeksą (`index`), prasidedantį nuo 0** :

```python
my_list = ["first", "second", "third"]
print(my_list[-1])
print(my_list[:1])
print(my_list[::2])
print(my_list[::-1])
print(my_list[0:2])
```

### Operatorius `in`

Jei norite patikrinti, ar tam tikras objektas yra `list'e`, galite daryti taip:

```python
my_list = [1, 2, 3]
print(1 in my_list)
```
## Tuple

Dar viena labai panaši duomenų struktūra yra `Tuple`. Pagrindinis skirtumas yra tas, kad `Tuple` objektų reikšmės yra nekeičiamos. Tai reiškia, kad turime objektą, kuriame yra kelios reikšmės, jos gali būti dubliuojamos, beveik visos savybės yra panašios, išskyrus tai, kad `Tuple` elementų negalima keisti.

### Žymėjimas

Tuple žymėjimas `**( )**` - du skliausteliai, kur vertės atskiriamos kableliais.

### Tuple kūrimas

```python
empty_tuple = ()
tuple_single_item = (1,)
another_tuple = (1, 2, 3)
```
Atkreipkite dėmesį, kad po kiekvieno elemento `tuple` turi būti kablelis, nors gali būti tik vienas elementas. Visa kita yra tas pats, kaip ir `list'e`.

### Operacijos 

Tai yra lygiai tas pats kaip su sąrašais, išskyrus tai, kad `tuple` yra nekintantis. Jei bandysite priskirti naują reikšmę, gausite klaidą:

🛑 
```python
my_tuple = (1, 2, 3)
my_tuple[0] = 500 # TypeError: 'tuple' object does not support item assignment
```

### `Tuple` ir `List` palyginimas

Dabar atrodo, kad `list` yra daug _pranašesni_ už `tuples`, tačiau programavime ne visada viskas yra vienpusiška,ir tai priklauso nuo tam tikrų situacijų.
Paprastai **statinėms reikšmėms, kurios nesikeičia, rekomenduojama naudoti** `tuple`, nes python kalboje jis yra šiek tiek greitesnis nei `list`. O `list` turėtume naudoti visada, kai reikšmės gali keistis, arba kai pats 'list' didės arba mažės.

## 🧠 Užduotys:

**`Visus atsakymus reikia spausdinti terminale`**
1. Parašykite python programą, kuri susumuoja visus `list` elementus (visi `list` elementai yra `int` arba `float` tipo. `List'a` sukurkite patys).
2. Parašykite python programą, kuri padaugina visus `list` elementus (visi `list` elementai yra `int` arba `float` tipo. `List'a` sukurkite patys).
3. Parašykite python programą, kuri iš `list'o` gauna didžiausią vertę (visi `list` elementai yra `int` arba `float` tipo. `List'a` sukurkite patys).
4. Parašykite python programą, kuri sujungia visas `list` esančias `string` duomenų tipo reikšmes (visi elementai yra `string` tipo, `list'a` sukurkite 
   patys)
5. Sukurkite du `list'us`ir juos sudėkite, įsitikinkite, kad viskas veikia taip, kaip norite.
6. Parašykite python programą, kuri paprašytų naudotojo įvesti 3 `int` tipo skaitmenis (1,2,3 etc..) ir rastų didžiausią įvestą reikšmę.
7. Pabandykite atlikti tuos pačius pratimus su `tuples` (jei įmanoma).

## 🌐  Papildomi skaitiniai:

* [w3schools](https://www.w3schools.com/python/python_lists.asp)
* [Daugiau skaitinių](https://www.programiz.com/python-programming/list)