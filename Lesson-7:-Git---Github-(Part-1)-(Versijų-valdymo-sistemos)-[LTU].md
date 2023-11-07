## Versijų valdymo sistemos (git, GitLab, GitHub, bitbucket...)

##Ę Kas tai?
Paprasčiau tariant, tai programinė įranga, leidžianti jums versijuoti savo kodą dirbant su kolegomis.

Kurso metu naudosime populiariausią "GitHub" - [www.github.com](http://www.github.com/). Taigi jei dar neturite paskyros - užsiregistruokite.

Atsisiųskite `git bash`: [nuoroda](https://git-scm.com/downloads).

### Ką galime pasiekti naudodami `git`? 🗺️ 

Taigi, ką reiškia versijų valdymas? Naudodami `git` galime išsaugoti kiekvieną atliktą kodo pakeitimą ir bet kuriuo metu grįžti prie bet kurios projekto versijos/ etapo. Be to, taip pat galime lengvai dirbti komandoje, nereikia siųsti vienas kitam kodo dalių elektroniniu paštu ir pan. Visa informacija gražiai saugoma [github] (http://www.github.com/) Be to, šiuolaikinės VSC sistemos, tokios kaip `github` ar `gitlab` jums leidžia sklandžiai diegti, testuoti ir daryti kitus fantastiškus dalykus su kodo baze.

## "git" nustatymas 🧰 

Atsidarykite `git bash`, jei naudojate `windows` arba integruotą terminalą (Mac,Linux):
1. Nustatykite savo `git` globalų vardą:


`git config --global user.name "vardas pavardė"`


2.Nustatykite el. paštą:


`git config --global user.email full@email.com`


3.Patikrinkite nustatymus:


`git config -list`


4. Prisijungti su `ssh` raktu.

Atidarykite `git bash` terminalą sugeneruokite `ssh` raktą:

`ssh-keygen -t rsa -b 4096 -C "email@email.com"`


Atidarykite failą `id_rsa.pub` bet kuriuo teksto redaktoriumi ir jį nukopijuokite.

Eikite į [www.github.com](http://www.github.com/) viršuje dešiniuoju pelės klavišu spustelėkite `profile -> settings -> SSH and GPG keys -> New SSH key`.
Suteikite raktui pasirinktą pavadinimą ir spustelėkite `Pridėti SSH raktą`.


##Ę Kuriate naują projektą? 📃 
Atidarykite [www.github.com](http://www.github.com/) Prisijunkite ir spustelėkite _new project_. Suteikite jam pavadinimą ir spustelėkite _create project_.

##Ę Kaip pradėti dirbti su `git`?

Galimi keli scenarijai:

#### Pirmasis scenarijus

Atidarykite terminalą:

`git clone repository` (klonuoti saugyklą)

sukurkite failą ir patikrinkite, ką `git` gali pasakyti apie failą:

`git status`

Nurodykite `git`, kad pradėtų **sekti** failo pakeitimus:

`git add <filename>`.

Dar kartą patikrinkite būseną:

`git status`

Ar matote skirtumus? Dabar reikia sukurti vadinamajį  `commit'ą` - įrašą, kuris yra tiesiog projekto istorijos taškas, rodantis, kas buvo pakeista, kas ir kada tai padarė. Sukurkime jį!

`git commit -m "first commit"`

Dar kartą patikrinkite būseną:

`git status`

Dabar jau galime siųsti kodą į nuotolinę repozitoriją (push):

`git push`

Sveikiname, dabar sėkmingai sekate pakeitimus ir jie taip pat matomi "GitHub"! Patikrinkite juos.


#### Antrasis scenarijus

Ką daryti, jei jau turite kodų bazę ir dabar staiga norite pradėti ją sekti?
Pasirinktame kataloge inicijuokite `git` projektą.

`git init`

Dabar vėl galite patikrinti `git` būseną:

`git status`

Norėdami pradėti sekti visus failus tiesiog parašykite:

```
git add .
git commit -m "initial commit"
```

Ir štai dabar `git` seka jūsų projektą. Išsaugojam kodo pakeitimus nuotolinėje repozitorijoje:


`git push`


### Pradėkite dirbti su esamu projektu

Iki šiol matėme, kaip sukurti projektą, bet kaip prisijungti prie jau esamo projekto?
Tai paprasta - eikite į projektų `github` puslapį. Paspauskite žalią mygtuką **Code** ir pasirinkite būdą, kuriuo norite gauti kopiją -> `ssh`/ `hhtp`.
Atsidarykite terminalą, eikite į vietą, kurioje norite, kad projektas būtų išsaugotas, ir klonuokite jį:

`git clone <link_to_project>`


Dabar į savo kompiuterį atsisiuntėte kodo kopiją. Būkite atsargūs, nes ji neatnaujinama automatiškai, norėdami parsisiųsti naujausius pakeitimus, turime padaryti:

`git pull`

Tai tiesiog nurodo `git` paimti naujausius pakeitimus iš nuotolinės repozitorijos (remote repository). Atkreipkite dėmesį, kad ši komanda panaši į `git push`, bet atlieka visiškai priešingą veiksmą - atnaujina vietinę kodo bazės kopiją.

### `.gitignore`

Kartais yra failų, kurių nenorime sekti - tai failai su prisijungimo informacija (slaptažodziai, ip adresai), duomenys, didžiuliai failai ir pan.
`Git` turi sekti tik kodo pakeitimus, o ne atskleisti jūsų slaptažodžius pasauliui.

Todėl projekto šakniniame kataloge galite pridėti failą, pavadintą `.gitignore,` ir jame išvardyti failus / aplankus / failų, kurių nenorite sekti, 

Pavyzdys:

```text
# Ignore compiled binaries
*.exe
*.o
*.out

# Ignore log files
*.log

# Ignore virtual environment directories (for Python projects)
venv/
__pycache__/

# Ignore compiled bytecode files (for Python projects)
*.pyc
*.pyo
__pycache__/

# Ignore database files
*.db
*.sqlite

# Ignore editor/IDE-specific files and directories
.vscode/
.idea/

# Ignore environment configuration files with sensitive information
.env

```


### `Readme.md` 📑 

`README.md` failas yra paprasto teksto arba žymėjimo failas, dažniausiai randamas programinės įrangos projektuose ir saugyklose. Pagrindinė jo paskirtis: pateikti svarbiausią informaciją apie projektą, kad naudotojams, bendradarbiams ar lankytojams būtų lengviau suprasti ir naudoti kodo bazę. Dažnai jis tarnauja kaip projekto dokumentacija, kurioje apžvelgiama, koks tai yra projektas, kaip juo naudotis ir kita svarbi informacija.

Pavyzdys:

```text
# My Simple Project

## Overview

My Simple Project is a basic web application that demonstrates a few key features.

## Installation

1. Clone the repository:

   ```bash
   git clone https://github.com/yourusername/simple-project.git


```


## 🧠 Pratimai:
* Sukurkite naują "github" repozitoriją/projektą ir įkelkite fiktyvų kodą. Išbandykite visas šiandien išmoktas komandas.
* Patariame su kiekviena nauja paskaita susikurti naują "github" repozitoriją ir ten saugoti kodą.

## 🌐 Papildomas skaitymas:

* [readme.md sintaksė](https://www.markdownguide.org/basic-syntax/)
* [Git](https://product.hubspot.com/blog/git-and-github-tutorial-for-beginners)

Translated with www.DeepL.com/Translator (free version)
