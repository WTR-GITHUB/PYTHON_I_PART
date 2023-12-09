## Registravimo biblioteka

Registravimas (nuo šiol - `logging`) yra labai naudingas įrankis programuotojo arsenale. Jis gali padėti jums geriau suprasti programos vykdymą ir atrasti scenarijus, apie kuriuos galbūt net nebūtumėte pagalvoję kuriant.

Naudingus duomenis ištinkamose vietose registruodami ne tik galite lengva ir greitai išspręsti klaidas, bet ir naudoti duomenis analizuoti programos našumą planuoti jos mastui ar ieškoti naudojimo modelių marketingo planams.

Python kalbos registravimo (logging) [modulis](https://docs.python.org/3/library/logging.html) yra paruoštas naudoti ir galingas modulis, kuris yra pritaikytas tiek pradedantiesiems, tiek įmonėms. Jį naudoja dauguma trečiųjų šalių Python bibliotekų, todėl galite integruoti savo registracijos pranešimus su jais iš pradžių, kad gautumėte vientisą žurnalą savo programai.

### `Importuokite biblioteką`
`import logging`

### `logging vs print`

`logging` ir `print` abu gali būti naudojami kodo derinimui, tačiau vis dar yra priežasčių rinktis `logging` nei `print()`.

`Logging` failas yra failas, kuriame yra registro pranešimas, kartu su kita informacija, pvz., eilutes numeris, modulio pavadinimas, data, laikas ir kt. Kita vertus, `print` sakinys turi tik registro pranešimą.

`logging` failas saugo programos įrašus net ir po to, kai jis uždarytas, bet `print` sakinys praras visus įrašus ir registro pranešimus, kai vykdymas sustos.

Vienintelis kartas, kai turėtumėte apsvarstyti `print()` sakinio naudojimą, yra tada, kai jums reikia rodyti pagalbos pranešimą komandinėje eilutėje.

### `Loginimas`

Yra penki būdai, kaip rodyti `logging` pranešimą Python su nustatant registravimo lygius:  **DEBUG**, **INFO**, **WARNING**, **ERROR**, and **CRITICAL**.

```python
import logging

logging.debug('This is a debug message')
logging.info('This is an info message')
logging.warning('This is a warning message')
logging.error('This is an error message')
logging.critical('This is a critical message')

-------------------OUTPUT---------------------
WARNING:root:This is a `warning` message
ERROR:root:This is an `error` message
CRITICAL:root:This is a `critical` message
```
Pirmiau pateiktoje kodo išvestyje reikia atkreipti dėmesį į du dalykus:


- **root** yra numatytasis visų `logging` registratorius.
- Spausdinami tik trys `logging` pranešimai. To priežastis - **`logging` pranešimų rimtumo lygis**, o spausdinami tik didesni arba lygūs rimtumo lygiui `WARNING` pranešimai.


### `Penki logging registravimo lygiai`
 - **DEBUG**: Jis naudojamas problemai diagnozuoti. Jame pateikiama išsami informacija apie problemą. Sunkumo lygis yra 10.
 - **INFO**: Jame pateikiamas sėkmingo programos vykdymo patvirtinimo pranešimas. Sunkumo lygis yra 20.
 - **WARNING**: Šis pranešimas skirtas, kai susidaro netikėta situacija. Sunkumo lygis yra 30.
 - **ERROR**: Jis pateikiamas dėl rimtesnės problemos nei įspėjimas. Jis gali būti dėl tam tikros integruotos klaidos kaip sintaksės ar loginė klaida. 
   Sunkumo lygis yra 40.
 - **CRITICAL**: Tai įvyksta, kai programos vykdymas sustoja ir ji nebegali veikti pati. Sunkumo lygis yra 50.

### `basicConfig`

Galime spausdinti `DEBUG` ir `INFO` pranešimus, **pakeitę pagrindinę `logger` konfigūraciją** su `basicConfig(**kwargs)` pagalba.
Yra keletas dažniausiai naudojamų parametrų:

 - **level**: Norint pakeisti pagrindinį loggerį į nurodytą rimtumo lygį.
 - **filename**: Failo, kuriame bus saugomi logs, pavadinimas.
 - **filemode**: Jei nurodomas failo vardas, tai nurodo failo atidarymo režimą. Numatytoji reikšmė yra `append(a)`
 - **format**: Tai yra logging pranešimo formatas.
 - **datefmt** : Nurodomas datos ir laiko formatas.

Pavyzdys:
```python
import logging
logging.basicConfig(level=logging.DEBUG, format='%(asctime)s - %(name)s - %(levelname)s - %(message)s', datefmt='%d/%m/%Y %H:%M:%S')
logging.debug('This is Debug Message')
logging.info('This is an info message')
-------------------------CONSOLE OUTPUT------------------
12/05/2021 20:46:41 - root - DEBUG - This is Debug Message
12/05/2021 20:46:41 - root - INFO - This is an info message
```
### `Įrašymas į failą`
Panašiai, norėdami registruoti rezultatą** į failą**, galite pridėti failo pavadinimą ir failo režimą prie `basicConfig`:

```python
import logging
logging.basicConfig(level=logging.DEBUG,filename='data.log', filemode='a', format='%(asctime)s - %(name)s - %(levelname)s - %(message)s', datefmt='%d/%m/%Y %H:%M:%S')
name = input("Enter Your Name:\n")
logging.info(f"{name} has logged in successfully !!")

-----------------data.log file output-------------
12/05/2021 21:01:37 - root - INFO - Tom has logged in successfully !!
12/05/2021 21:02:47 - root - INFO - Karl has logged in successfully !!
12/05/2021 21:03:27 - root - INFO - Rahul has logged in successfully !!
```
#### `Logging Exception`
`logging modulis` taip pat gali atsekti ir parodyti _visiškas išimtines klaidas_, kurios atsiranda vykdant programą. Naudojant `exc_info` su nustatytu argumentu `True`:

```python
import logging
a = 10
b = 0
try:
  c = a / b
except Exception as e:
  logging.error("Exception Occurred", exc_info=True)  ## At default it is True
  
 ----------------------------------CONSOLE OUTPUT------------------------
ERROR:root:Exception Occurred        ## If exc_info=False then only this message will print
Traceback (most recent call last):
  File "C:\Users\minde\Desktop\ds\python\advance_concepts\logging_code.py", line 5, in <module>
    c = a / b
ZeroDivisionError: division by zero
```

## Pratimai: 

1) Sukurkite paprastą programą, kuri registruotų (logs) visus įvesties duomenis iš terminalo. Konfigūracijose turi būti rodomi visi papildomi duomenys (laikas, data, lygis ir t. t.).
2) Parašykite funkciją, kuri perkeltų visus vieno tipo elementus į `list` galą:

  ```python
  move_to_end([1, 3, 2, 4, 4, 1], 1) ➞ [3, 2, 4, 4, 1, 1]
  # Move all the 1s to the end of the array.
  ```
  Registruokite įvestis ir rezultatus į failą.

3) Sukurkite 3 funkcijas, kurios yra susijusios viena su kita (viena iškviečiama kitoje), ir išbandykite visus `logging` sunkumo lygius pagal savo projektą. 
  
  Funkcijų pavyzdžiai:

  ```python
  def check_engine() -> None:
    pass
   
  def start_car() -> None:
    check_engine()...
  .......
    

4) Sukurkite programą, kuri priima 4 duomenų tipus/struktūras: `strings`, `numbers`, `list`, `dict`. Iteriuokite 10 kartų su įvestimis ir užregistruokite, koks duomenų tipas/struktūra ir kiek kartų buvo įvesta. Apdorokite visas galimas klaidas ir jas užregistruokite.


5) Sukurkite apskaitos programą , kuri paimtų metines pajamas, išlaidas, PVM tarifą (visos reikšmės turi būti kintamos) ir apskaičiuotų pelną, sumokėtus mokesčius 4 skirtingomis valiutomis (USD, EU, JPY, CNY). Visi skaičiavimai ir rezultatai turėtų būti spausdinami ekrane. Visi duomenys ir galimos klaidos turi būti registruojami į failą. 

## 🌐 Papildomas skaitymas (arba žiūrėjimas📺 ):

* [Real Python](https://realpython.com/python-logging/)
* [Corey Schafer: Logging (keli vaizdo įrašai)](https://www.youtube.com/watch?v=-ARI4Cz-awo)
***


