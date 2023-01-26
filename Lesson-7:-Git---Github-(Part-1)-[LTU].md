# Versijų valdymo sistemos (git, GitLab, GitHub, bitbucket...)

## Kas tai?
Paprasčiau tariant, tai programinė įranga, leidžianti jums versijuoti savo kodą dirbant su ja kartu su tiek žmonių, kiek norite.

Kurso metu naudosime populiariausią "GitHub" - [www.github.com](http://www.github.com/). Taigi jei dar neturite paskyros - užsiregistruokite.

Atsisiųskite "git bash": [nuoroda](https://git-scm.com/downloads).

## Ką galime pasiekti naudodami git? 🗺️ 

Taigi, ką reiškia versijų valdymas? Naudodami git išsaugome kiekvieną kiekvieno atliktą pakeitimą ir bet kuriuo metu galime grįžti prie bet kurios projekto versijos, galime ją grąžinti į bet kurį etapą, jei norime. Be to, taip pat galime lengvai dirbti komandoje, nereikia siųsti vienas kitam kodo dalių elektroniniu paštu ir pan. Visa informacija gražiai saugoma [github] (http://www.github.com/) Be to, šiuolaikinės VSC sistemos, tokios kaip github ar gitlab, taip pat leidžia mums sklandžiai diegti, testuoti ir daryti kitus fantastiškus dalykus su mūsų kodų baze.

## "git" nustatymas 🧰 

atsidarykite git bash, jei naudojate windows arba bet kurį terminalą kitoje OS:
1. Nustatykite savo vardą:


`git config --global user.name "vardas pavardė"`


2.nustatykite el. paštą:


`git config --global user.email full@email.com`


3.Patikrinkite nustatymus:


`git config -list`


4. Prisijungti su ssh raktu. Atidarykite git bash terminalą

sugeneruokite ssh raktą:

`ssh-keygen -t rsa -b 4096 -C "email@email.com"`


atidarykite failą id_rsa.pub bet kuriuo teksto redaktoriumi ir jį nukopijuokite.

Eikite į [www.github.com](http://www.github.com/) viršuje dešiniuoju pelės klavišu spustelėkite savo profilį -> nustatymai -> SSH ir GPG raktai -> Naujas SSH raktas.
Suteikite raktui pasirinktą pavadinimą ir įklijuokite raktą. Spustelėkite Pridėti SSH raktą


## Kuriate naują projektą? 📃 
Atidarykite [www.github.com](http://www.github.com/) Prisijunkite ir spustelėkite _new project_. Suteikite jam pavadinimą ir spustelėkite _create project_

## Kaip pradėti dirbti su git?

Yra pora būdų, kaip judėti toliau, ir iš karto github jums aprašys galimybes, jei atsidarysite savo naujai sukurtą projektą.

#### pirmasis scenarijus

Atidarykite terminalą:

`git clone repository` (klonuoti saugyklą)

sukurkite failą ir patikrinkite, ką git gali pasakyti apie failą:


`git status`

pasakykite git, kad pradėtų sekti failo pakeitimus:

`git add <pavadinimas>``.

dar kartą patikrinkite būseną
`git status`

Kas šį kartą skiriasi? Dabar reikia sukurti commit'ą , kuris yra tiesiog projekto istorijos taškas, rodantis, kas buvo pakeista, kas ir kada tai padarė. Sukurkime jį!

`git commit -m "first commit"`

dar kartą patikrinkite būseną
`git status`

Dabar jau galime siųsti(pushinti):

`git push`

Sveikiname, dabar sėkmingai sekate pakeitimus ir jie taip pat matomi "GitHub"! Patikrinkite juos.


#### Antrasis scenarijus

Ką daryti, jei jau turite kodų bazę ir dabar staiga norite pradėti ją sekti? Ne problema.
Pasirinktame kataloge inicijuokite git projektą.


`git init`

dabar vėl galite patikrinti git būseną:

`git status`

norėdami pradėti stebėti visus failus tiesiog:

```
git add .
git commit -m "initial commit"
```

Ir štai dabar turite gito stebimą projektą. Tačiau kaip pasidalinti šia informacija su kolegomis? Jis dar nėra prijungtas prie "GitHub
Taigi šiam projektui sukurkite naują GitHub projektą. Dabar jums tereikia paimti origin nuorodą, kurią rasite sukurtame "GitHub" projekte.


`git remote add origin https://github.com/vychiokas/test.git`

Dabar turime "išstumti" jį į nuotolinį:


`git push`



## Pradėkite dirbti su esamu projektu

Iki šiol matėme, kaip sukurti projektą, bet kaip prisijungti prie jau esamo projekto?
Tai paprasta - eikite į projektų github puslapį. Paspauskite žalią mygtuką **Code** ir pasirinkite būdą, kuriuo norite gauti kopiją -> ssh/ hhtp
atsidarykite terminalą, eikite į vietą, kurioje norite klonuoti projektą, ir klonuokite jį:

Klaida: `git clone <link_to_project>`


Dabar į savo kompiuterį atsisiuntėte kodo kopiją. Būkite atsargūs, nes ji neatnaujinama automatiškai, norėdami pull'inti naujausius pakeitimus, turime padaryti:

reikia: `git pull`

Tai tiesiog nurodo git "pullinti" naujausius pakeitimus iš remote (github), atkreipkite dėmesį, kad ši komanda panaši į `git push`, bet atlieka visiškai priešingą veiksmą - atnaujina vietinę kodo bazės kopiją.

## .gitignore

Kartais yra failų, kurių nenorime sekti - tai failai su prisijungimo informacija (slaptažodziai, ip adresai), duomenys, didžiuliai failai ir pan.
Git turi sekti tik kodo pakeitimus, o ne atskleisti jūsų slaptažodžius pasauliui.

todėl projekto šakniniame kataloge galite pridėti failą, pavadintą .gitignore, ir jame išvardyti failus / aplankus / failų, kurių nenorite sekti, šablonus, o git net nerodys pakeitimų ar tų failų `git status`. Išbandykite patys!


## Readme.md 📑 

Tai yra titulinio puslapio informacija apie jūsų projektą, pagrindinis dokumentas, kurį mato lankytojas, apsilankęs jūsų projekte, paprastai iš jo gana aiškiai matyti, ar net projekto savininkui jis rūpi, nes paprastai norime, kad kuo daugiau žmonių susidomėtų ir skleistų gerą žinią apie mūsų darbą.  Nedvejodami pridėkite čia paaiškinimus apie savo projektą, kaip jį paleisti, kas tai yra

