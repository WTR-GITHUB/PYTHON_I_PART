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
