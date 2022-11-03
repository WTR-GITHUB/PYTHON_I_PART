## Kas tai yra?
Versijų valdymo sistemos (angl. Version Control System arba VCS) seka bendrų projektų, kuriamų grupės žmonių, pokyčių istoriją

Naudosime vieną populiariausių versijų valdymo sistemą GIT – [www.github.com](http://www.github.com/) (dar yra GitLab, Bitbucket)

## Ką leidžia VCS (GIT)?
Saugoti visus kodo pakeitimus ir nesunkiai gražinti kodą į norimą, prieš tai buvusią padėtį
Su tuo pačiu kodu lygiagrečiai dirbti (keisti) daugeliui žmonių
Lengvai dalintis, rodyti, leisti peržiūrėti kolegoms parašytą kodą per specialią svetainę (pvz. [www.github.com](http://www.github.com/))
Nuolat išsaugoti paskutinius pakeitimus ne tik lokaliai, bet ir serveryje
Lengviau pateikti kodą į produkciją (pvz., publikuoti sukurtą svetainę internete, skelbti pakeitimus)
## Kaip įdiegti GIT Windows sistemoje?
Užsiregistruoti svetainėje [www.github.com](http://www.github.com/).
Įdiegti GIT programą iš https://git-scm.com/downloads (diegiant visuomet spausti „Next“).
Patikrinti ar veikia, Windows konsolėje (Win + c, m, d + Enter) įrašius „git“ (jei išmeta pagalbos informaciją apie git, reiškia veikia).
## Kaip nustatyti GIT?
Windows konsolėje (Win + c, m, d + Enter):

Nustatyti vardą:


`git config --global user.name "Vardas Pavarde"`


Nustatyti el. pašto adresą:


`git config --global user.email el@pastas.com`


Patikrinti ar pasikeitė:


`git config --list`


Kaip susieti kompiuterį su GitHub (per SSH raktą)?
Atidaryti programą Git Bash (Win + g, i, t, , b, a, s, h + Enter).

Sugeneruoti SSH raktą paleidus šią komandą:

`ssh-keygen -t rsa -b 4096 -C "el@pastas.com"`


(galima visas užklausas patvirtinti nieko nevedant, tik spaudžiant Enter).

Su bet kokiu teksto redaktoriumi atidaryti sugeneruotą rakto failą id_rsa.pub, pažymėti kodą komanda CTRL+C.

Svetainėje [www.github.com](http://www.github.com/) spausti ant vartotojo ikonos viršutiniame dešiniajame kampe, pasirinkti Settings, tuomet SSH and GPG keys. Tada spausti mygtuką New SSH key.

Laukelyje Title įrašyti norimą pavadinimą, pvz. Namų kompiuteris, pele pažymėti lauką key ir paspausti CTRL+V (bus įklijuotas 3 žingsnyje nukopijuotas SSH kodas), galiausiai spausti Add SSH Key.

## Kaip sukurti tuščią GitHub projektą (repozitoriją)?
Pagrindiniame [www.github.com](http://www.github.com/) puslapyje (prisijungę savo vardu ir slaptažodžiu) spauskite Start a project.

Laukelyje Repository name įrašykite norimą projekto pavadinimą (be tarpų) ir spauskite mygtuką Create repository. Atsidariusiame lange pamatysite komandas, reikalingas pridėti failus į repozitoriją

## Kaip pridėti failą į Git repozitoriją?
Atidarykite Windows konsolę (Win + c, m, d + Enter), atidarykite vietą, kur kursite projekto failus (norėdami dirbti Windows darbastalyje, konsolėje įveskite cd Desktop ir spauskite Enter).

Norimoje vietoje sukurkite naują failą, pavyzdžiui, suvesdami komandą:

`echo "# test" >> README.md`


Sustatykite šią vietą, kaip stebimą su GIT, įvesdami komandą:
`git init`


Pridėkite į repozitoriją sukurtą failą, paleisdami komandą:
`git add README.md`


arba:
`git add .`


Patikrinkite, ar failas buvo pridėtas, paleisdami komandą:
`git status`


Užfiksuokite pakeitimus, paleisdami komandą:
`git commit -m "pirmas commit"`


Kaip išsaugoti pakeitimus į [www.github.com](http://www.github.com/)?
Nustatyti nuotolinės repozitorijos, į kurią bus keliami pakeitimai, kelią, pvz.:
`git remote add origin git@github.com:DonatasNoreika/test.git`
(kelią rasite užėję į norimą projektą [www.github.com](http://www.github.com/) svetainėje).

Užfiksuokite pakeitimus, paleidę komandą:
git push -u origin master
(į klausimą are you sure you want to continue connecting (yes/no)?, atsakykite įvesdami yes ir spausdami Enter)

## Kaip pridėti failą į GIT repozitoriją?
Projekto kataloge sukurkite naują failą, pvz. paleisdami komandą:
`echo "# naujas" >> failas2.txt`
Pridėkite į repozitoriją sukurtą failą, paleisdami komandą:
`git add failas.txt`
arba:
`git add .`
Užfiksuokite pakeitimus, paleisdami komandą:
git commit -m "pridetas antras failas"
Užfiksuokite pakeitimus į GitHub, paleidę komandą:
git push -u origin master.
Padarę vieno iš repozitorijos failo pakeitimą ir pakartoję 2-4 žingsnius, galite taip pat užfiksuoti šiuos pakeitimus į GitHub.

## Kaip panaikinti paskutinius pakeitimus?
Paredaguokite norimą failą, pvz. failas2.txt. Įvedę šią komandą matysite, kuriame faile buvo atlikti pakeitimai:
`git status`
Atšaukite paskutinius pakeitimus, įvedę komandą:
`git checkout failas2.txt`
Patikrinkite, ar pakeitimai buvo atlikti, įvedę:
`git status`
## Kaip sukurti GitHub repozitorijos kopiją kompiuteryje?
Atidarykite Windows konsolę (Win + c, m, d + Enter), atidarykite vietą, kur kursite projekto failus (norėdami dirbti Windows darbastalyje, konsolėje įveskite cd Desktop ir spauskite Enter).

Padarykite nutolusios repozitorijos kopiją, paleisdami komandą:

`git clone git@github.com:DonatasNoreika/test.git`
(norimos repozitorijos adresą galite rasti nuėję į jos puslapį [www.github.com](http://www.github.com/) ir paspaudę mygtuką Clone or download).

Užduotys
Savarankiškai išbandyti visus GIT veiksmus, aprašytus šios pamokos skaidrėse
Sukurti programą, fiksuojant visus kodo pakeitimus GitHub (galima kurti norimą programą arba panaudoti bet kurią iš buvusių paskaitų)