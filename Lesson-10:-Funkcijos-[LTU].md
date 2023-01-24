## Įvadas 
Kas yra funkcija?
Funkcijos yra patogus būdas suskirstyti kodą į naudingus blokus, leidžiantis sutvarkyti kodą, padaryti jį skaitomesnį, pakartotinai naudoti ir sutaupyti šiek tiek laiko. Be to, funkcijos yra pagrindinis būdas apibrėžti sąsajas, kad programuotojai galėtų dalytis savo kodu.
Pythone funkciją apibrėžiate raktiniu žodžiu _**def**_, tada rašote funkcijos identifikatorių (pavadinimą), po kurio seka skliaustai ir dvitaškis.
Kitas dalykas, kurį turite padaryti, tai įsitikinti, kad įterpėte skirtuką arba 4 tarpus, o tada nurodykite, ką norite, kad funkcija jums atliktų.

```python
def function_name():
    # What to make the function do
```

Paprastas pavyzdys - funkcija, kuri spausdina 'Hello world':

```python
def print_smth():
    print('Hello world!')
```

Arba atspausdina atsitiktinį `int` skaičių nuo 0 iki 10:

```python
def get_random_number():
    print(random.randit(0, 10))
```
Kaip ir integruotosios funkcijos, vartotojo apibrėžtos funkcijos **kviečiamos naudojant funkcijos pavadinimą, po kurio pateikiami skliaustai** : 

```python
get_random_number() 
print_smth()
# ir taip toliau....

```

## Pavadinimų suteikimas

Pasirinkti kintamųjų, funkcijų ir (arba) klasių pavadinimus ir pan. gali būti sudėtinga. Rašydami kodą turėtumėte gerai apgalvoti pavadinimų pasirinkimą, nes taip jūsų kodas bus lengviau skaitomas. Geriausias būdas pavadinti objektus Python programoje - naudoti aprašomuosius pavadinimus, kad būtų aišku, ką objektas simbolizuoja.

Pagrindinės taisyklės tokios: 

* Metodų pavadinimuose naudokite tik mažąsias raides.

```python
def compute():
  pass
```

* Metodo pavadinime žodžius reikia atskirti pabraukimu.

```python
def apskaičiuoti_smth():
  pass
```

* Neviešo metodo pavadinimas turi prasidėti vienu pabraukimu.

```python
def _get_smth():
  perduoti
```

* Jei metodo vardą reikia iškraipyti, metodo vardo pradžioje naudokite du iš eilės einančius pabraukimus.

```python
def __get_secret():
  pass
```

Labai geras pavadinimų suteikimo taisyklių ir pavyzdžių šaltinis yra čia: [Python Function Naming](https://melevir.medium.com/python-functions-naming-tips-376f12549f9) ❗ **Turite perskaityti!** ❗

## Grąžinimo teiginys 
Grąžinimo teiginiai naudojami funkcijai užbaigti ir grąžinti išraišką, kurią galima naudoti vėliau. Tačiau jos nėra privalomos ir gali būti nenaudojamos, jei jų nereikia.
Sintaksė:
```
return [išraiška]
```
#### Keletas pavyzdžių:

```python
def find_sum(num1, num2):
    '''Grąžina num1 ir num2 sumą.''''
    sum_nums = num1 + num2 # Suranda num1 ir num2 sumą
    return sum_nums # Grąžina skaičių sumą
```

```python
def even_odd(num):

    '''
    Grąžina "lyginis", jei num yra lyginis, ir "nelyginis", jei num yra nelyginis.    
    Parametrai:
        (int): Grąžinama:
        type (eilutė): "lyginis", jei num yra lyginis; "nelyginis", jei num yra nelyginis
    '''

    if num % 2 == 0: # Patikrina, ar num/2 turi likutį 0
        return "lyginis" # Jei likutis lygus 0, grąžinama "lyginis"
    else:
        # Jei neturi, grąžinama "nelyginis".
```


👨🏫 ❗ **ATTENTION** ❗ 
**Jei [išraiška] paliekama tuščia, išeinant iš funkcijos bus grąžinamas [``None``](https://realpython.com/null-in-python/) tipo objektas**

```python
def check_if_exist(a=None):
  if a:
    return a
  return
    
```

## Funkcijų parametrai:
Parametrai, arba argumentai, yra reikšmės, kurias galite perduoti funkcijai ir nuo kurių priklauso, kaip bus vykdoma funkcija. Yra įvairių būdų, kaip galime perduoti parametrus.

Poziciniai parametrai:
Dažniausiai parametrai perduodami iškviečiant funkciją ir perduodant parametrus toje pačioje pozicijoje, kaip ir funkcijos apibrėžime. Paimkime dalijimo funkcijos pavyzdį:

```python
def integer_division(num_one, num_two):
    // num_vienas // num_dvi

integer_division(10, 2)

----OUTPUT----
>>>> 5
```
