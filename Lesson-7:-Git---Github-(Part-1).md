# Version control systems (git, gitlab, github, bitbucket...)

## What are they?
Put simply it is software that allows you to version your software while working on it with as many people as you wish.

During the course we will be using the most popular Github– [www.github.com](http://www.github.com/). So if you do not have an account yet - register.

Download git bash: [link](https://git-scm.com/downloads)

## What can we achieve with git?

So what does the versioning mean? Well with git we save each an every change everyone is doing and at any given time we can go back into any version of our project, we can revert it into any stage if we want. What is more we can also easily work within a team, you do not have to email chunks of code to each other etc. All the information is beautifully stored on [github](http://www.github.com/) Also modern VSC systems like github or gitlab allow us to also seemlesly deploy, test and do other fantastic things with out codebase.

## setting up git?

open git bash if you are using windows or any terminal on other OS:

1.Setup your name:


`git config --global user.name "name surname"`


2.setup email:


`git config --global user.email full@email.com`


3.Check settings:


`git config --list`


Connecting with ssh key

Open git bash terminal

generate ssh key:

`ssh-keygen -t rsa -b 4096 -C "email@email.com"`


open file id_rsa.pub with any text editor and copy it.

Go to[www.github.com](http://www.github.com/) on top right click on your profile -> settings -> SSH and GPG keys -> New SSH key.

Give the key a name of your choice and paste the key. Click Add SSH Key


## Creating an empty project?
Open [www.github.com](http://www.github.com/) Login and hit Start a project.

Give it a name and click create repository

## How to start working with git?

There are couple of ways to move from here and immediately github will describe opportunities to you if you open your newly created project.

### first scenario

open up terminal:

`git clone repository`

create a file

`git add <filename>`


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