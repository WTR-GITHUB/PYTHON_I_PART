## `Įvadas` 
Kad suprastume, kas iš tikrųjų yra `virtualioji aplinka` ir kaip ji gali palengvinti mūsų gyvenimą, apžvelkime keletą dalykų, su kuriais galite susidurti kurdami paprastą "Python" projektą.

Python projektas gali būti priklausomas nuo kelių _trečiųjų šalių bibliotekų_, kad pasiektumėte savo verslo tikslą. Visus šiuos papildomus paketus (bibliotekas) / priklausomybes galite valdyti naudodami python paketų tvarkyklę, vadinamą `pip`.

Norėdami patikrinti savo `pip` versiją, galite atlikti šiuos veiksmus:

```python
python3 -m pip --version
```
Paketą/ biblioteką galite įdiegti naudodami `pip` komandą install:

```python
python -m pip install <package-name>
```
`pip` standartiškai visada įdiegia **naujiausią bet kokio paketo** versiją (kol nepateikiama konkreti to paketo versija) ir taip pat **įdiegia visas priklausomybes**, kurios reiklingos tam paketui/bibliotekai.

### `Kuom naudinga?`
Tarkime, jūs kuriate projektą `Project A`, kuris veikia su Python 3.5 [versija](https://www.python.org/doc/versions/) , ir taip pat pradedate dirbti su kitu Python projektu `Project B`, kuris reikalauja Python 3.9.

Tiek `Project A`, tiek `Project B` tikslams pasiekti gali prireikti bibliotekos `lib A`, tačiau `Project A`, kuris veikia su python 3.5, gali būti suderinamas su kita `lib A` versija, o `Project B` (python 3.9) gali būti suderinamas su kita versija (pvz: [Flask](https://pypi.org/project/Flask/#history)).

Net jei keli jūsų projektai naudoja tą pačią "Python" versiją, gali iškilti atvejis, kai atnaujinama priklausomybės versija (pvz: [Tas pats Flask](https://flask.palletsprojects.com/en/2.2.x/installation/) ) bet kuriam iš jūsų naujų projektų gali pažeisti esamo projekto funkcionalumą.

Kadangi pagal numatytuosius nustatymus kiekvienas jūsų sistemos projektas rašys ir naudos trečiųjų šalių paketus iš to paties katalogo, tai kelia sunkumų, nes **gali pažeisti bet kurio iš jūsų projektų funkcionalumą**.

### `Virtualios aplinkos` 
Oficialioje [Python](https://docs.python.org/) dokumentacijoje rašoma:

Virtuali aplinka - tai tokia "Python" aplinka, kurioje įdiegtas "Python" interpretatorius, bibliotekos ir scenarijai yra izoliuoti nuo kitose virtualiose aplinkose įdiegtų programų ir (pagal numatytuosius nustatymus) bet kokių bibliotekų, įdiegtų "sisteminiame" "Python", t. y. tokiame, kuris įdiegtas kaip operacinės sistemos dalis.

Pirmiau pateiktas apibrėžimas yra pakankamai paprastas, kad suprastumėte, jog `virtualioji aplinka` tiesiog siūlo jums izoliuotą vietą projekto priklausomybėms tvarkyti taip, kad jos **netrukdytų bibliotekoms, įdiegtoms bet kurioje kitoje virtualiojoje aplinkoje arba įdiegtoms jūsų sistemoje**.

Kiekvienam projektui, su kuriuo dirbate, galite tiesiog sukurti virtualią aplinką.
Aptarsime dvi labai populiarias virtualiųjų aplinkų tvarkykles: [venv](https://docs.python.org/3/library/venv.html) ir [Pipenv](https://pipenv.pypa.io/en/latest/).

### `venv`
Įprastas būdas kurti virtualias aplinkas buvo naudojant python biblioteką, žinomą kaip [virtualenv](https://virtualenv.pypa.io/en/latest/), tačiau nuo python versijos `3.3` dalis `virtualenv` iš tikrųjų buvo integruota į python su modulio pavadinimu `venv`. Dabar virtualią aplinką galite sukurti naudodami šią komandą:

```python
python3 -m venv <name_of_your_choice>
```
Kas čia vyksta?

* Na, python3 yra jūsų įdiegta python programa. Jei jūsų įdiegta python versija vadinasi python, python3.7 arba python3.9 ar dar kaip nors kitaip, tuomet naudokite ją;
* `-m venv` yra argumentas, nurodantis python paleisti virtualios aplinkos modulį `venv`;
* Paskutinis argumentas `<name_of_your_choice>` yra jūsų virtualios aplinkos aplanko pavadinimas. Kai kurie žmonės mėgsta naudoti kitą pavadinimą (pvz., env arba .env), tačiau tai priklauso tik nuo jūsų.

👨🏫 ❗ **PRO PATARIMAS** ❗ 
** Jei naudojate `git`, norėdami įsitikinti, kad virtualioje aplinkoje nevaldote versijų, į naują `.gitignore` failo eilutę įrašykite `venv/`. Jei pamiršite šį veiksmą, _galite užkimšti_ savo git saugyklą šimtais papildomų versijų kontroliuojamų failų**

Sukūrus virtualią aplinką, daugiau to daryti nebereikės.

### `Darbo eiga`
Norėdami naudoti virtualią aplinką, turite ją "aktyvuoti" naudodami šią komandą:

(**"MacOS" ir "Linux "**)

```python
source <name_of_your_choice>/bin/activate
```

arba (**Windows**)

```python
<name_of_your_choice>\Scripts\activate
```

Pirmiau pateiktos komandos pakeitė komandas `python` ir `pip` (python paketų tvarkyklė), kad jos būtų nukreiptos į tuos, kurie yra `venv` aplanke. Turėtų pasirodyti naudingas indikatorius, rodantis, kad naudojate virtualią aplinką, pvz:

```python
(<name_of_your_choice>) $
```

Tai reiškia, kad kai su `pip` įdiegsite paketą, pvz:

```python
pip install numpy
```

Dabar jį įdiegsite į virtualią aplinką, esančią aplanke `<name_of_your_choice>`. Jei norite, turėtumėte turėti galimybę peržiūrėti įdiegtų paketų rinkmenas, esančias `<name_of_your_choice>/lib/python3.9/site-packages` . Jei ši versija skiriasi, turėsite pakeisti `python3.9` (arba bet kurią kitą jūsų naudojamą versiją) savo versija.

Pavyzdys:
 
![](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/venv.gif)

Tęsdami šį pavyzdį, jei dabar paleisite "Python" interaktyviuoju režimu, galėsite pasiekti šiuos paketus naudodami šias komandas:

```python
python
import numpy as np
print(np.sqrt(5))
```
Jei viskas vyko teisingai, turėjote pamatyti kažką panašaus į toliau pateiktą pavyzdį:

![](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/venv2.gif)

Taip pat turėtumėte turėti prieigą prie visų bibliotekų, kuriuos įdiegėte naudodami python, kad galėtumėte paleisti savo python failus. Pavyzdžiui, jei norėtumėte naudoti virtualioje aplinkoje esantį python, kad paleistumėte failą, pavadintą `main.py`, tai galėtumėte padaryti naudodami šią komandą:

```python
python main.py
```

Baigę dirbti su virtualia aplinka, galite uždaryti terminalą arba deaktyvuoti aplinką naudodami komanda:
```python
deactivate
```
Taip pat dabar galėsite aktyvuoti kitą virtualią aplinką kitam savo projektui, jei to prireiktų.

### `Aplinkos atkūrimas`
Galite atkurti virtualią "Python" aplinką (pvz., kitame kompiuteryje), dažniausiai norėsite išsaugoti informaciją apie įdiegtas bibliotekas/paketus faile. Tai leis bet kuriam asmeniui, turinčiam jūsų failą, įdiegti tas pačias paketų versijąs, kurią naudojote kurdami projektą. Tačiau greičiausiai vis tiek norėsite nurodyti, kokią "Python" versiją naudojate. Dažniausiai šiam tikslui yra naudojamas failas -  `requirements.txt`.

Jei aktyvavote "Python" virtualiąją aplinką, galite automatiškai sugeneruoti requirements.txt failą, naudodami šiuos veiksmus:

```python
pip freeze > requirements.txt
```
Taigi, jei jūs ar kas nors kitas norėtų sukurti virtualią aplinką ir naudoti tuos pačius paketus, kaip ir jūs, jie gali vadovautis pirmiau pateiktomis komandomis, kad sukurtų ir aktyvuotų virtualią aplinką, o tada įdiegtų savo reikalavimus. Įdiegti reikalavimus galima naudojant `pip install` metodą `-r`, kaip nurodyta toliau:

```python
pip install -r requirements.txt
```

## `Pipenv`
`pipenv` naudojimas turi keletą privalumų, palyginti su `pip` ir `venv` naudojimu. Tai yra pagrindiniai iš jų:
* Jums nebereikia atskirai naudoti `pip` ir `venv`. Vietoj to turite vieną įrankį, kuris atlieka viską - ir dar daugiau!
* `pipenv` atskiria jūsų aukščiausio lygio bibliotekų priklausomybes nuo paskutinio išbandyto derinio (pvz., _pip freeze_ išvesties). Dėl to priklausomybių valdymas jums, kaip kūrėjui, tampa patogesnis.
* `pipenv` skatina naudoti naujausias priklausomybių versijas, kad būtų sumažinta saugumo rizika. Jis netgi gali nuskaityti jūsų priklausomybes dėl žinomų pažeidžiamumų.
* `pipenv` suteikia galimybę susipažinti su jūsų priklausomybių grafiku naudojant `pipenv graph`.
* `pipenv` [sukešuoja](https://www.educative.io/answers/what-is-hashing) visas priklausomybes. Jis aptiks paketus, kurie buvo pažeisti po to, kai iš pradžių įtraukėte juos kaip priklausomybę.
* `pipenv` gali dirbti ir su `requirements.txt` failais. Jei toks failas yra, jis automatiškai jį aptiks ir konvertuos į `Pipfile`.


### `Darbo eiga` 
`Pipenv` yra trečiosios šalies paketas, todėl pirmiausia jį reikia _įdiegti_:

```python
pip install pipenv
```
Tada galite pereiti į savo produkto katalogą (arba sukurti naują katalogą, jei pradedate naują projektą, kaip čia darau aš) ir jame _įdiegti_ `ipipenv`:

```python
mkdir ~/dev/projects/my-new-project && cd ~/dev/projects/my-new-project
pipenv install
```
Taip bus sukurti du nauji failai: `Pipfile` ir `Pipfile.lock`.

Norėdami _įjungti_ virtualią aplinką:

```python
$ pipenv shell
```
Norėdami _įdiegti paketus_ su `pipenv`:


```python
pipenv install <package name>
```

_Paketų_ įtraukimas į aplinką:

```python
pipenv lock -r
```
Norėdami _parodyti, kokie paketai yra įdiegti (ir jų priklausomybės)_, galite paleisti:

```python
pipenv graph
```

Paketų pašalinimas:_

```python
pipenv uninstall <package name>
```

## Pratimai: 

1) Sukurkite virtualią aplinką naudodami python `venv` ir įdiekite bent vieną paketą iš `Pip` saugyklų.
2) Sukurkite virtualią aplinką naudodami python `pipenv` ir įdiekite bent vieną paketą iš `Pip` saugyklų.
3) Naudokite bet kurią iš virtualios aplinkos parinkčių, įdiekite `random-word` paketą ir sukurkite "Python" scenarijų, kuris išspausdintų 5 
   atsitiktinius žodžius (vardai turi būti iš didžiųjų raidžių ir surūšiuoti).

## 🌐 Papildomas skaitymas (arba žiūrėjimas 📺 ):


* [Pipenv official](https://pipenv.pypa.io/en/latest/)
* [Corey Schafer: Pipenv](https://www.youtube.com/watch?v=zDYL22QNiWk&t)
* [Python venv](https://www.datacamp.com/tutorial/python-oop-tutorial)
***


