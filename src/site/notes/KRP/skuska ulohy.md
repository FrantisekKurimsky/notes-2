---
{"dg-publish":true,"permalink":"/krp/skuska-ulohy/"}
---

## Analyzujte protokol vytvorenia relačného kľúča K pre stanice A, B pomocou trvalého kľúča KAB :   
A→B  :  A, NA    
B→A  :  {NA, K}KAB    
A→B  :  {NA}K    
  Popíšte idealizovaný protokol v logike BAN a sformulujte počiatočné predpoklady a ukážte dosiahnutie cieľov: A |≡ (A ↔K B)  a   B |≡ A |≡ (A ↔K B).
Analyzujeme protokol vytvorenia relačného kľúča K pre stanice A a B pomocou trvalého kľúča KAB:
#### Riesenie
1.  A→B : A, NA
    
    -   Stanica A posiela svoje meno (A) a náhodný kľúč (NA) stanici B.
2.  B→A : {NA, K}KAB
    
    -   Stanica B posiela náhodný kľúč (NA) a relačný kľúč (K) zašifrované trvalým kľúčom (KAB) stanici A.
3.  A→B : {NA}K
    
    -   Stanica A posiela náhodný kľúč (NA) zašifrovaný relačným kľúčom (K) stanici B.

Idealizovaný protokol v logike BAN:

1.  Počiatočné predpoklady:
    
    -   Stanice A a B už majú trvalý kľúč KAB.
    -   Stanice A a B sa môžu komunikovať medzi sebou.
2.  Ciele:
    
    -   Stanica A sa môže autentifikovať pred stanicou B.
    -   Stanice A a B vytvoria spoločný relačný kľúč K.
    -   Stanice A a B sa môžu komunikovať medzi sebou zašifrované relačným kľúčom K.
3.  Dosiahnutie cieľov:
    
    -   Stanica A posiela svoje meno (A) a náhodný kľúč (NA) stanici B, čím sa autentifikuje pred ňou.
    -   Stanica B posiela náhodný kľúč (NA) a relačný kľúč (K) zašifrované trvalým kľúčom (KAB) stanici A, čím sa potvrdzuje autentifikácia stanice A.
    -   Stanica A posiela náhodný kľúč (NA) zašifrovaný relačným kľúčom (K) stanici B, čím potvrdzuje, že obdržala relačný kľúč (K) a že sa s ňou komunikuje zašifrované relačným kľúčom.

V tomto protokole, stanice A a B dohodli relačný kľúč K pomocou trvalého kľúča KAB, ktorý bol predtý



## Zapíšte protokol pomocou spi-kalkulu. Zapíšte tiež postup jeho redukcií (aspoň tri kroky) pre jeden konkrétny výber A a B. 
A→B  :  A, NA    
B→A  :  {NA, K}KAB    
A→B  :  {NA}K    
### riesenie
Protokol vytvorenia relačného kľúča K pre stanice A a B v jazyku spi-calculus by mohol vyzerať takto:

`A -> B : A, na B -> A : {na, k}kab A -> B : {na}k`

Postup redukcie:

1.  Krok: Vytvorenie procesu pre stanicu A:

`A = new`

2.  Krok: Vytvorenie procesu pre stanicu B:

`B = new`

3.  Krok: Vytvorenie procesu pre trvalý kľúč KAB:

`kab = new`

Konkrétny výber A a B:

1.  Krok: Vytvorenie procesu pre stanicu A s menom "Alice":

`A = new(alice)`

2.  Krok: Vytvorenie procesu pre stanicu B s menom "Bob":

`B = new(bob)`

3.  Krok: Vytvorenie procesu pre trvalý kľúč KAB, ktorý je známy iba pre Alice a Bob

`kab = new(alice, bob)`

V tomto konkrétnom príklade, Alice sa autentifikuje pred Bobom posielaním svojho mena a náhodného kľúča na Boba. Bob potom potvrdzuje autentifikáciu a posiela relačný kľúč K zašifrovaný trvalým kľúčom KAB na Alice. Alice potom potvrdzuje príjem relačného kľúča K zaslaním náhodného kľúča zašifrovaného relačným kľúčom K na Boba.

Je dôležité mať na pamäti, že táto implementácia je iba ilustračná a v skutočnom prostredí by bolo potrebné zabezpečiť viac bezpečnostných opatrení, ako napríklad kontrolu integrity a autenticity údajov.

## Redukujte nasledujúci postup pre distribúciu tajného kľúča relácie KAB pomocou dôveryhodného centra S na 5 krokovú schému so zachovaním bezpečnosti. Verejný kľúč centra VS je overený pre všetkých klientov. Ostatné verejné kľúče nie sú overené. 
A→S : A, B 
S→A : {B, VB}SS 
A→B : {NA, A}VB 
B→S : B, A, {NA}VS 
S→B : {A, VA}SS, {{B, NA, KAB}VA, KAB}VB 
B→A : {{B, NA, KAB}VA, NB}VA
A→B : {NB}KAB
### riesenie 
Redukcia postupu pre distribúciu tajného kľúča relácie KAB pomocou dôveryhodného centra S na 5 krokovú schému so zachovaním bezpečnosti:

1.  A→S : A, B
    
    -   Klient A posiela svoje meno a meno druhého klienta (B) dôveryhodnému centru S.
2.  S→A : {B, VB}SS
    
    -   Dôveryhodné centrum S posiela meno druhého klienta (B) a jeho verejný kľúč (VB) zašifrovaný svojím vlastným tajným kľúčom (SS) klientovi A.
3.  A→B : {NA, A}VB
    
    -   Klient A posiela náhodný kľúč (NA) a svoje meno (A) zašifrované verejným kľúčom druhého klienta (VB) klientovi B.
4.  B→S : B, A, {NA}VS
    
    -   Klient B posiela svoje meno (B), meno prvého klienta (A) a náhodný kľúč (NA) zašifrovaný verejným kľúčom dôveryhodného centra (VS) dôveryhodnému centru S.
5.  S→B : {A, VA}SS, {{B, NA, KAB}VA, KAB}VB
    
    -   Dôveryhodné centrum S posiela meno prvého klienta (A) a


## Navrhnite protokol pre overenie autenticity hráča A, ktorý sa pripája do online počítačovej hry. Každý hráč zdieľa symetrický kľúč KAS s centrálnym serverom S (kľúč bol vygenerovaný pri registrácii podľa registračného čísla legálnej kópie hry, server S teda pozná identifikáciu hráča A a k nemu priradený kľúč KAS). Hráč sa autentifikuje na hráčskom serveri H, ktorý overí na serveri S či A je registrovaný. Centrálny server S je jediný, hráčskych serverov môže byť niekoľko. Hráčske servery poznajú overený verejný kľúč VS centrálneho servera S a majú od neho certifikát pre svoj verejný kľúč VH. Protokol má byť odolný voči replay útokom bez použitia časových pečiatok. Komentujte kroky navrhnutého protokolu spolu s kontrolami, ktoré potrebné priebežne vykonať.
