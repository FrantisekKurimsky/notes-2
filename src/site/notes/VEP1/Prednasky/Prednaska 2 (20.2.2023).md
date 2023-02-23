---
{"dg-publish":true,"permalink":"/vep-1/prednasky/prednaska-2-20-2-2023/"}
---

### Pristupy k testovaniu

- staticke - appka nebezi => fault
	- nespusta sa SW
	- robene na dokumentacii, kode
	- rychle najdenie chyb
	- revizie, inspekcie, rekapitulacia
	- reviews - od seniora
		- technical reviews -variable with undefined values\
		- statement coverage
	- static analysis (linter, formating) - vyuzitie nastroja


- dynamicke - appka bezi => failure
	- zahrna exekuciu softweru
	- tesovanie komponentov
	- zlyhania sposobene zlyhaniami
	- Black-box 
		- aplikacia na testingu, nevidim do kodu, pristup cez UI
		- specification-based
	- White-box
		- vidi strukturu kodu
		- skumanie kodu
	- Model based
		- testing na zaklade modelu softveru, UML diagramy

### Testovanie v ramci zivotneho cyklu SW
- SDLC - Software system development life cycle
![Legal systems](/img/user/VEP1/assets/SDLC.png)

#### Waterfall model (Sequential Model)
- poziadavky
- analyza
- dizajn
- kod
- test
- deployment

Test levels
- component unit tests
- integration tests
- system tests
- acceptance tests

![V-model](assets/v-model.webp)


#### Interaktivny-inkrementalny model vyvoja SW
![V-model](/img/user/VEP1/assets/ii.png)


#### Agile model

##### Scrum

problem s regresnym testovanim

Vyhody
- refactoring od zaciatku
- cely tim zodpovedny
- unit testy od zaciatku

pri DEVOPS ide o cross-functional time, uz developer testuje, cely tim testuje

automaticovanie testovania

### Fundametalny proces testovania
- kazda dev aktivita je testovana

 ![V-model](/img/user/VEP1/assets/fpt.png)

### Unit testy
- teestovanie modulu
- overenie spravania
- co najlepsie pokrytie modulu
- testujeme aj platne aj neplatne vstupy
- podmienkou je kvalina specifikacia
- najpr test, potom implementacia
- Mock data, 
- rychle vytvorenie, lahky debug, overenie regresie, redukcia costu

### Integracne testy
- testovanie spojeni, rozhrani, integracii
- komponenty, funkcne celky applikacii

### Systemove testy
- sys ako celok
- ziadne mock data
- zatacove testy
- doraz na spojenie s okolim

### Akceptacne testy
- Formalne odobrenie zakaznikom
- mozeme odovzdat? rizika, zavazky splnene?
- pouzitelnost, validacia
- formy
	- UAT
	- OAT
	- Alfa Beta
		- zapojenie koncovych pouzivatelov
		- alfa - nova funkcionalita vo vyvoji, testuje sa na pracovisku, zname prostredie
		- beta - nova zostavena funkcionalita, tesstuje sa u pouzivatela, nezname prostredie

### Typy testov podla ISTQB

- funkcne testovanie **CO?**
	- systematicke overenie
	- dodavatel z pohladu zakaznika
	- existuje pozadovana funkcnost?
	- mame korektne vysledky?
	- korektna reakcia na neplatne vstupy?
- nefunkcionalne testovanie **AKO?**
	- testovanie charakteristiky SW produktu
	- performance test
	- overenie vykonnosti
		- rychlost odozvy
		- priepustnost siete
		- spotreba zdrojov
	- stress testing
	- **monitoring**
		- odhalenie - botteneck
- zalozene na strukture **White box**
- Change based testing
	- Re-testovanie
		- opakovane vykonanie testu
		- potvrdenie odstranenia defektu
	- regresne testovanie
		- overenie ci sa zmenou nezavliekli chyby
		- sada testov
		- automaticke spustanie po testoch novej funkcionality
		- vyzaduje udrzbu
		- cim viac pridavania, tym lepsie automaticke testovanie

### Poziadavky na SW

- funkcnost
- performance
- usability
- reliabilty
- security
 **ISO 9126** perfum

### Summary

- avoid failures
- best quality
- ASAP testovanie
- ANALYSE time, risk, money
- test - report - retest
