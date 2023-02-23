---
{"dg-publish":true,"permalink":"/pds/prednaska-2-20-2-2023/"}
---

![DEADLOCK](/img/user/PDS/assets/deadlock.png)

https://en.wikipedia.org/wiki/Systolic_array 


Z prednasky [[pds1.pdf]] od semaforu do konca

# Druha cast 

###### Paralel pc
subor navzajom prepojenych procesov

###### Modely sekvencnych vypoctov
- turing
- random access machine RAM
	- neohranicena postupnost registrov
	- program - postupnost prikazov
	- program moze sam seba vylepsovat
	- nepriama adresacia
	- podmieney skok
- RASP stored program

###### Modely paralelnych vypotov
- booleovske obovdy(and or pospajane, vyhodne napr pre specialny cip pre spravy po sieti, sifrovacie cipy)
- DAG - orientovany acyklicky graf (vypocet na zaklade postupu v grafe, vo vrcholoch su procesory, ktore spracuvavju data, n-dimenzionalne kocky, stomove modely vypoctu)
- **sietovy model (systolicke systemy, data-driven programming)** (pouzivaju sa v sucasnosti v castiach akceleracii vypoctov, maticove operacie, program je riadeny datami)
	- siet jedoduchych procesov
	- minimalna lokalna pamat
	- jednoduche instrukcie
	- vypocet riadeny vstupmi
- na urovni HW
	- pipelining
	- out of order execution
	- superscalar, VLIW (nove procesory robia operacie nad vektormi v jednom kroku, Furier)
	- TPU, praca s vektormi a tenzormi, pomocou systolickych poli
	- GPU, warps(SIMT)
- **modely so zdielanou pamatou** 

##### Model so zdielanou pamatou
###### PRAM model
- parallel random access machine
- model s neobmedzenou zdielanou pamatou
- synchronny model
- SIMD - v kazdom kroku sa vykonava rovnaka instrukcia
- vstup aj vystup v zdielanej pamati
- procesor ma svoje ID a pozna pocet procesov

**PRIKLAD** paralelne vyhladavanie
- n procesov $P_1 \dots P_n$
- vstup - pole $M [ 1 \dots n]$
- $M[n+1]$ hladana hodnota
- Vystup - $M[n+2]$ index prvku pola, ktore obsahuje $M[n+1]$
- je pikladom pristupu do pamate CRCW
- KOD pre i-ty proces

```
global_read(M[n+1], x) // CR
global_read(M[i], y) // ER
if i==1 then global_write(0, M[n+2]) // EW
if x==y then global_write(i, M[n+2]) // CW-arbitary
```

**PRAM pristup do pamate**
- EREW
	- exclusive read exclusive write
- CREW
	- concurrent read exclusive write(sucastne mozeme cita, avsak zapisovat moze len jeden)
- CRCW
	- concurrent read concurrent write ()
	- COMMON - pri zapise sa hodnoty rovnaju, urcite mame rovnaky vysledok
	- ARBITARY - nahodne uspeje jeden pri zapise
	- PRIORITY - uspeje proces s najnizsim/najvyssim indexom (najsilnejsi)
- realne je pristup dozdielanje pamate pomalsi ako pristupdolokalnej pamate

Ak by sme priklad chceli dat do EREW, tak nakopirujeme
procesy mozu dalej ukladat hodnoty ktore precitali, a postupne zapisovat pre dalsi proces akokeby do pamate na dalsie volne miesta, kazdy proces cita zo svojho miesta

##### Vykon paralelnych algoritmov

- p pocet procesorov
- $T^*(n)$ - sekvencny cas, pocet krokov optimalneho sekvencneho algoritmu
- $T_p (n)$ paralelny cas pri p procesoroch
- Span: $T_\infty (n)$
- 