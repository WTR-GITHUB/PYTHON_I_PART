# Šakos, darbas komandose
Kai dirbame su didesniu projektu, gera praktika yra **NESAUGOTI TIESIOGIAI Į MAIN/MASTER**. Paprastai sukuriame funkcijos šaką ir joje dirbame su savo funkcija, o baigę darbą paprašome kolegų peržiūrėti pakeitimus su "Pull Request" (netrukus pamatysime, kas tai yra). Kai gauname atsiliepimus ir išsprendžiame visas problemas - mums leidžiama sujungti savo kodų bazę su pagrindinėje šakoje esančia.

![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/git_branch.svg)

komanda šakai sukurti yra:

šakos pavadinimas: `git checkout -b <šakos_vardas>``.

pradėję dirbti ir atlikę pirmąjį perkėlimą, tiesiog įveskite `git push` - git iškels klaidą, bet pasiūlys teisingą komandą, kaip nustatyti upstream (iš esmės tai reiškia, kad šaką iš mūsų kompiuterio atvaizduojame į šaką, esančią nuotoliniu būdu - GitHub, GitLab, bitbucket ar bet kurioje kitoje jūsų naudojamoje sistemoje)

**Pastaba: "git terminal" yra labai naudingas - jis pateikia pasiūlymų, kai ką nors darote neteisingai. Taigi tiesiog stebėkite terminalo pranešimus!**

# Užklausos suformavimas

Kaip minėta anksčiau, kai baigsite dirbti su funkcija ir manysite, kad viskas atlikta, turėtumėte sukurti "Pull Request" užklausą ir informuoti kolegas, kad dabar jie turi peržiūrėti jūsų pakeitimus. Taip gausite vyresniųjų kolegų atsiliepimų, galbūt nurodymų, kaip ką nors ištaisyti, įgyvendinti ir pan. Komentarais galite keistis "GitHub" ir kitose populiariose versijų valdymo platformose. Peržiūrėkime trumpą demonstraciją, kaip atrodo tipinė "Pull Request" užklausa.

## sujungimo konfliktai, kaip juos išspręsti
Tai gana įprastas scenarijus, kai dirbame su šakomis ir, tarkime, jūs ir jūsų kolega pakeičiate tam tikrą kodo dalį. Ir kai bandote sujungti šias kodų bazes, jos atsiduria susijungimo konflikte. Kad ir kaip bauginančiai tai skamba, iš tikrųjų tai yra tipiškas kasdienio gyvenimo scenarijus. Tiesiog nereikia panikuoti, jei pamatysite ką nors panašaus. Tiesiog toliau tikrinkite `git status` ir peržiūrėkite failus, kuriuose atsiranda pakeitimai. Dabar atliksime trumpą demonstraciją, kad pademonstruotume šį scenarijų.

#### Praktinė dalis
Atlikite šiuos veiksmus, kad gautumėte sujungimo konfliktą

1. Susiskirstykite į poras po 2žmones
2. sukurkite tuščią repą
3. pakvieskite vienas kitą bendradarbiauti
4. sukurkite "Python" failą, parašykite porą funkcijų, padarykite pakeitimus ir stumkite.
5. leiskite kitai šaliai traukti naujausius pakeitimus
6. Šioje vietoje svarbu, kad abu darytumėte pakeitimą tame pačiame faile, toje pačioje funkcijoje. Pabandykite ją iš naujo įgyvendinti kokiu nors kitu būdu. Tačiau čia svarbu tai, kad abi šalys turėtų bandyti atlikti pakeitimus toje pačioje failo vietoje.
7. Viena šalis atlieka klasikinį -> add, commit , push. Tada kita taip pat bando tai daryti... Ir gauna sujungimo konfliktą
8. Susisiekite su savo šalimi, kuri versija yra teisinga ir turėtų likti pradiniame kode.
9. išspręskite konfliktą.
10. stumkite pakeitimus.

# Papildomos git komandos
## revert
Komandą `git revert` galima laikyti "atšaukimo" tipo komanda, tačiau tai nėra tradicinė atšaukimo operacija. Užuot pašalinusi pakeitimą iš projekto istorijos, ji sugalvoja, kaip apversti pakeitimo metu padarytus pakeitimus, ir prideda naują pakeitimą su tokiu apverstiniu turiniu. Tai neleidžia "Git" prarasti istorijos, o tai svarbu siekiant užtikrinti peržiūros istorijos vientisumą ir patikimą bendradarbiavimą.
komanda:
`git revert <commit_hash>``
kelių pakeitimų atšaukimas:


`git revert --no-commit HEAD~3..`

`git commit -m "jūsų pranešimas dėl kelių pakeitimų atšaukimo"`

## merge

Sujungimas yra "Git" būdas vėl sujungti šakutės istoriją. Komanda git merge leidžia paimti nepriklausomas kūrimo eilutes, sukurtas naudojant git branch, ir sujungti jas į vieną šaką.

![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/merge.svg)
komanda


`git merge <šakos_pavadinimas>`

## rebase

Taip visa funkcijų šaka pradedama nuo pagrindinės šakos galo, veiksmingai įtraukiant visus naujus pagrindinės šakos pakeitimus. Tačiau vietoj to, kad būtų naudojamas sujungimo įsipareigojimas, perskirstant perrašoma projekto istorija, sukuriant visiškai naujus įsipareigojimus kiekvienam pradinės šakos įsipareigojimui.


`git rebase <šakos pavadinimas>`
![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/rebase.svg)

## log

`git log`

paprasčiausiai leidžia matyti visą istoriją, kiekvieną atliktą pakeitimą po kito.
![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/git_log.jpg)

## restore
jei po įsipareigojimo atlikote tam tikrus pakeitimus, bet tam tikru momentu nusprendėte, kad norite atšaukti, galite tai padaryti:


`git restore <failas_pavadinimas>`

Ne tai, kad taip negalima atkurti įvestų pakeitimų

## atkurti 

Komanda `git reset` yra sudėtinga ir universali pakeitimų atšaukimo priemonė. Ji turi tris pagrindines iškvietimo formas. Šios formos atitinka komandinės eilutės argumentus --soft, --mixed, --hard. Kiekvienas iš šių trijų argumentų atitinka tris "Git" vidinės būsenos valdymo mechanizmus: "The Commit Tree" (HEAD), "The Staging Index" ir "The Working Directory".

### Sunku

Tai pati tiesiausia, pavojingiausia ir dažniausiai naudojama parinktis. Perdavus --hard Įvykdymų istorijos nuorodų rodyklės atnaujinamos į nurodytą įvykdymą. Tuomet iš naujo nustatomi Staging Index ir Working Directory, kad atitiktų nurodyto įsipareigojimo rodiklius. Bet kokie anksčiau neatlikti Staging Index ir Working Directory pakeitimai iš naujo nustatomi taip, kad atitiktų įsipareigojimų medžio būseną. Tai reiškia, kad bet kokie nebaigti darbai, kurie kabojo Staging Index ir Working Directory, bus prarasti.

#### Mišrus

Tai numatytasis darbo režimas. Atnaujinamos nuorodų rodyklės. Stažuotės rodyklė atstatoma į nurodyto įsipareigojimo būseną. Visi pakeitimai, kurie buvo atšaukti iš Staging Index, perkeliami į darbinį katalogą. Tęskime toliau.


#### Minkštas

Kai perduodamas argumentas --soft, atnaujinamos nuorodų rodyklės ir atstatymas sustabdomas. Etapinė rodyklė ir darbinis katalogas lieka nepaliesti. Tokį elgesį gali būti sunku aiškiai parodyti. Tęskime savo demonstracinę repą ir paruoškime ją minkštajam atstatymui.

![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/reset.svg)


## diff

komanda paprasčiausiai leidžia pamatyti failo skirtumus.
komanda:
`git diff <failas_pavadinimas>`


## žyma

Programinė įranga, kaip žinome, būna įvairių versijų - Windows 98,2000,7,8,10,11...  Python 2.7, 3.5, 3.6....
Paprastai pavadinimai suteikiami taip:

![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/tag.png)

komanda:


`git tag -a v1.4 -m "mano versija 1.4"`


## checkout

tai daugiafunkcinė komanda, leidžianti atlikti daugybę veiksmų, iš kurių pagrindiniai yra šie:
1. Peršokti iš vienos šakos į kitą `git checkout <šakos pavadinimas>`
1. Sukurti šaką `git checkout -b <branch_name>``
1. Gali peršokti į tam tikrą commit hash ir apsižvalgyti, patikrinti failus ir t. t. (Tai grąžina Detached HEAD, scenarijus parodytas paveikslėlyje toliau).

![IMG](https://github.com/CodeAcademy-Online/python-new-material/blob/master/images/detached.svg)

## 🧠 Pratimai

1. Sukurkite projektą
1. Pabandykite žaisti su visomis šioje paskaitoje parodytomis komandomis
1. Jei kas nors neaišku - https://git-scm.com/doc

