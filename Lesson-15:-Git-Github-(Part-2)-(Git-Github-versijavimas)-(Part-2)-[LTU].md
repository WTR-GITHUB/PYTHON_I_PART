## `Šakos, darbas komandose`
Kai dirbame su didesniu projektu, gera praktika yra **NESAUGOTI TIESIOGIAI Į MAIN/MASTER**. Paprastai sukuriame funkcijos šaką (`branch`) ir joje dirbame su savo kodu, o baigę darbą paprašome kolegų peržiūrėti pakeitimus sukurdami `pull request` (netrukus pamatysime, kas tai yra). Kai gauname atsiliepimus ir išsprendžiame visas problemas - mums leidžiama sujungti savo kodų bazę su pagrindinėje šakoje esančia kodo baze.

![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/git_branch.svg)

komanda šakai sukurti yra:

 `git checkout -b <šakos_vardas>``.

Pradėję dirbti ir atlikę pirmąjį kodo perkėlimą, tiesiog įveskite `git push` - `git` išmes klaidą, bet pasiūlys teisingą komandą, kaip nustatyti `upstream` (iš esmės tai reiškia, kad šaką iš mūsų kompiuterio atvaizduojame į šaką, esančią išorinėje platformoje - `GitHub`, `GitLab`, `bitbucket` ar bet kurioje kitoje jūsų naudojamoje sistemoje)

**Pastaba: "git terminal" yra labai naudingas įrankis - jis pateikia pasiūlymų, kai ką nors darote neteisingai. Taigi tiesiog stebėkite terminalo pranešimus!**

## `Užklausos suformavimas`

Kaip minėta anksčiau, kai baigsite dirbti su kodu ir manysite, kad viskas atlikta, turėtumėte sukurti `pull request` užklausą ir informuoti kolegas, kad dabar jie turi peržiūrėti jūsų pakeitimus kode. Taip gausite vyresniųjų kolegų atsiliepimų, galbūt nurodymų, kaip ką nors ištaisyti, įgyvendinti ir pan. Komentarais galite keistis "GitHub" ir kitose populiariose versijų valdymo platformose. Peržiūrėkime trumpą demonstraciją, kaip atrodo tipinė `pull request` užklausa.

## `sujungimo konfliktai (merge conflicts), kaip juos išspręsti`
Tai gana įprastas scenarijus, kai dirbame su šakomis ir, tarkime, jūs ir jūsų kolega pakeičiate tam tikrą kodo dalį. Ir kai bandote sujungti šias kodų bazes, jos gali sukurti sitaciją kai toje pačioje kodo vietoje bandote sujungti dvi skirtingas kdo versijas. Kad ir kaip bauginančiai tai skamba, iš tikrųjų tai yra tipiškas kasdienio gyvenimo scenarijus. Tiesiog nereikia panikuoti, jei pamatysite ką nors panašaus. Tiesiog toliau tikrinkite `git status` ir peržiūrėkite failus, kuriuose atsiranda pakeitimai. Dabar atliksime trumpą demonstraciją:

#### `Praktinė dalis`
Atlikite šiuos veiksmus, kad gautumėte _sujungimo konfliktą_

1. Susiskirstykite į poras po 2 žmones
2. Sukurkite tuščią repozitoriją
3. Pakvieskite vienas kitą bendradarbiauti repozitorijoje.
4. Sukurkite "Python" failą, parašykite porą funkcijų, padarykite pakeitimus ir išsaugokite kodą repozitorije (`git push`).
5. Leiskite kitai šaliai įtraukti naujausius pakeitimus
6. Šioje vietoje svarbu, kad abu darytumėte pakeitimą tame pačiame faile, toje pačioje funkcijoje. Pabandykite ją iš naujo įgyvendinti kokiu nors kitu būdu. Tačiau čia svarbu tai, kad abi šalys turėtų bandyti atlikti pakeitimus toje pačioje failo vietoje.
7. Viena šalis atlieka klasikinį -> `add, commit , push`. Tada kita taip pat bando tai daryti... Ir gauna sujungimo konfliktą
8. Susisiekite su savo kolega, kuri versija yra teisinga ir turėtų likti pradiniame kode.
9. Išspręskite konfliktą.
10.Išsaugokite pakeitimus.

## `Papildomos git komandos`
### `revert`
Komandą `git revert` galima laikyti "atšaukimo" tipo komanda, tačiau tai nėra tradicinė atšaukimo operacija. Užuot pašalinusi pakeitimą iš projekto istorijos, ji sugalvoja, kaip apversti pakeitimo metu padarytus kitimus, ir prideda naują pakeitimą su tokiu apverstiniu turiniu. Tai neleidžia `git` prarasti istorijos, o tai svarbu siekiant užtikrinti peržiūros istorijos vientisumą ir patikimą bendradarbiavimą.

komanda:

`git revert <commit_hash>`

kelių pakeitimų atšaukimas:


`git revert --no-commit HEAD~3..`

`git commit -m "your message regarding reverting the multiple commits"`

### `merge`

Sujungimas yra `git` būdas vėl sujungti kodo išsišakojimą į pagridinę šaką. Komanda `git merge` leidžia paimti nepriklausomas kūrimo eilutes, sukurtas naudojant `git branch`, ir sujungti jas į vieną šaką.

![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/merge.svg)
komanda

`git merge <branch_name>`

### `rebase`

Taip visa funkcijų šaka pradedama nuo pagrindinės šakos galo, veiksmingai įtraukiant visus naujus pagrindinės šakos pakeitimus. Tačiau vietoj to, kad būtų naudojamas sujungimo įsipareigojimas, perskirstant perrašoma projekto istorija, sukuriant visiškai naujus įsipareigojimus kiekvienam pradinės šakos įsipareigojimui.

`git rebase <branch_name>`
![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/rebase.svg)

### `log`

`git log`

paprasčiausiai leidžia matyti visą istoriją, kiekvieną atliktą pakeitimą vieną po kito.
![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/git_log.jpg)

### `restore`
jei po kodo irašymo atlikote tam tikrus pakeitimus, bet tam tikru momentu nusprendėte, kad norite atšaukti, galite tai padaryti:


`git restore <failas_pavadinimas>`

###  `reset`

Komanda `git reset` yra sudėtinga ir universali pakeitimų atšaukimo priemonė. Ji turi tris pagrindines iškvietimo formas. Šios formos atitinka komandinės eilutės argumentus `--soft`, `--mixed`, `--hard`. Kiekvienas iš šių trijų argumentų atitinka tris `git` vidinės būsenos valdymo mechanizmus: "The Commit Tree" (HEAD), "The Staging Index" ir "The Working Directory".

#### `hard`

Tai pati tiesiausia, **pavojingiausia** ir dažniausiai naudojama parinktis. Perdavus `--hard`, vykdymų istorijos nuorodų rodyklės atnaujinamos į nurodytą įvykdymą. Tuomet iš naujo nustatomi `Staging Index` ir `Working Directory`, kad atitiktų nurodyto įsipareigojimo pakitimus. Bet kokie anksčiau neatlikti `Staging Index` ir `Working Directory` pakeitimai iš naujo nustatomi taip, kad atitiktų įsipareigojimų medžio būseną. Tai reiškia, kad bet kokie nebaigti darbai, kurie kabojo `Staging Index` ir `Working Directory`, **bus prarasti**.

#### `mixed`

Tai numatytasis darbo režimas. Atnaujinamos nuorodų rodyklės. Stažuotės rodyklė atstatoma į nurodyto įsipareigojimo būseną. Visi pakeitimai, kurie buvo atšaukti iš `Staging Index`, perkeliami į darbinį katalogą. Tęskime toliau.


#### `soft`

Kai perduodamas argumentas `--soft`, atnaujinamos nuorodų rodyklės ir atstatymas sustabdomas. Etapinė rodyklė ir darbinis katalogas lieka nepaliesti. Tokį elgesį gali būti sunku aiškiai parodyti. Tęskime savo demonstracinę repą ir paruoškime ją `soft` atstatymui.

![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/reset.svg)


### `diff`

komanda paprasčiausiai leidžia pamatyti failo padarytus pakitimus:

`git diff <failas_pavadinimas>`


### `tag`

Programinė įranga, kaip žinome, būna įvairių versijų - Windows 98,2000,7,8,10,11...  Python 2.7, 3.5, 3.6....
Paprastai pavadinimai suteikiami taip:

![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/tag.png)

komanda:


`git tag -a v1.4 -m "mano versija 1.4"`


### `checkout`

Tai daugiafunkcinė komanda, leidžianti atlikti daugybę veiksmų, iš kurių pagrindinės yra šios:
1. Peršokti iš vienos šakos į kitą `git checkout <šakos pavadinimas>`
2. Sukurti šaką `git checkout -b <branch_name>`
3. Gali peršokti į tam tikrą `commit hash` ir apsižvalgyti, patikrinti failus ir t. t. (Tai grąžina `Detached HEAD`, scenarijus parodytas paveikslėlyje toliau).

![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/detached.svg)

## 🧠 Pratimai

1. Sukurkite paprastą projektą dirbant poroje su kolega. Pridėkite šiek tiek kodo ir pabandykite imituoti darbą komandoje pagal pilną git darbo eigą. 
2. Pabandykite išsibandyti visas šioje paskaitoje parodytas komandas.

## 🌐  Extra reading (or watching 📺 ):

* [More on git commands](https://git-scm.com/doc)
***
