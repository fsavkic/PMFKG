# Lista komandi
U ovom fajlu se nalazi lista komandi koje su spominjane na vežbama iz predmeta `Operativni sistemi 1`.
***
Informacije o nekoj komandi `comm`:</br>
`man comm`
***
Prikaz stabla procesa
`pstree`

Prikaz grane stabla koja počinje od procesa sa pid-om `pid`:</br>
`pstree pid`

Komanda `pstree` grupiše identične grane tako što ih postavlja u uglaste zagrade ispred kojih stoji broj njhovog ponavljanja. Niti nekog procesa su grupisane po istom principu s tim što se oko one predstavljaju imenom tog procesa okruženog vitičastim zagradama.

Neki od korisnih argumenata komande `pstree` su:</br>
* `-a` - prikaži argumente komandne linije. Isključuje zbijanje procesa, ali ne i niti
* `-c` - isključuje zbijanje identičih podstabala
* `-h` - ističe trenutni proces i njegove naslednike (neki terminali ne podržavaju to isticanje)
* `-H` - Slično kao -h, samo što ističe naveden proces
* `-p` - prikaži PID svakog procesa. Isključuje zbijanje procesa

Primer primene:</br>
`pstree -apH 3210` - prikazuje stablo procesa, gde je za svaki proces naveden njegov PID i argumenti komandne linije, pored toga, proces sa pidom `3210` je istaknut
***
Ispis svih signala:</br>
`kill -l` ili `kill --list`

Pošalji signal `sig` procesu sa pid-om `pid`:</br>
`kill -sig pid` ili `kill --signal sig`
***
Prikaz svih procesa, statistike o njihovom korišćenju resursa i ostalih informacija u realnom vremenu:</br>
`top`
***
Prikaz trenutno aktivnih procesa:</br>
`ps -ef`
`ps aux`
***
Prikaz informacija međuprocesne komunikacije:</br>
`ipcs`

Prikaz sumiranih informacija o statusu međuprocesne komunikacije:</br>
`ipcs -u`

Prikaz svih redova za poruke:</br>
`ipcs -q`

Korisni argumenti:</br>
* `-m` ili `--shmems` - prikazuje informacije o aktivnim segmetima deljene memorije
* `-q` ili `--queues` - prikazuje informacije o aktivnim redovima za poruke
* `-s` ili `--semaphores` - prikazuje informacije o aktivnim semaforima

* `-c` ili `--creator` - prikazuje informacije o kreatori i vlasniku
* `-l` ili `--limits` - prikazuje informacije o ograničenjima
* `-p` ili `--pid` - prikazuje PID-ove kreatora i poslednjeg procesa koji je izvršio pristup
* `-t` ili `--time` - prikazuje vreme poslednje kontrolne informacije. Kod redova za poruke se odnosi na poslednje operacije funkcija `msgsnd` i `msgrcv`
* `-u` ili `--summary` - prikazuje sumirane informacije o statusu
* `--human` - prikazuje veličinu i formatu koji je lako razumljiv **utiče samo na `-l` i `--limits`**

Obriši neki objekat međuprocesne komunikacije čiji je id `objID`:</br>
`ipcrm objID`
***