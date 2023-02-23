---
{"dg-publish":true,"permalink":"/stu/prednasky/prednaska-2-21-2-2023/"}
---

[[STR_UC_slides_P02.pdf]]

## Strojové ucenie Booleovské formuly a reprezentácie

### Uvod
- ucime sa :D jak psy, holuby a potkany => Pavlov reflex atd ...
---------------------------------------------------------
- Konceptový priestor, $C$ - domáce zvieratá (DZ) 
- Abeceda $Σ$ - popis prvkov patriacich do konceptu, ${0, 1}$
- Atribúty konceptu - 4 nohy, rohy, nos, usi, oci, ústa, chvost, zerie, pije; pocet atribútov $n$; 
- Príkladový priestor - koza=(1,0,1,1,1,1,0,1,1), pes=((1,0,1,1,0,1,0,1,1); 
- Tréningová vzorka s - $((1,0,1,1,1,1,0,1,1),1), ((1,0,1,1,1,1,0,0,0),0), \dots ;$ dlzka tréningovej vzorky $m$; 
- Hypotézový priestor, $H$ - napríklad Booleovské funkcie

--------------------------------------------------------------

- Uciaci algoritmus pre $(C, H)$ - akceptuje tréningové vzorky pre koncepty v $C$ a výstupmi sú hypotézy v $H$. 
- Hypotéza $h \in H$ je konzistentná s tréningovou vzorkou s alebo súhlasí s s, ak $h(x_i) = b_i$ , pre $1 \leq i \leq m$. 
- Uciaci algoritmus L je konzistentný - ak kazda hypotéza $L(\overline{s})$ je konzistentná s tréningovou vzorkou $\overline{s}$
- Učenie pomocou konstrukcie 
- Učenie ocislovanim

---------------------

### Ucenie pomocou konstrukcie

$X$ je prikladovy priestor
$X^+, X^+ \subseteq X$ je mnozina kladnych prikladov
$t$ je cielovy koncept
$m$ je dlzka treningovej vzorky

Metoda ucenia hypotezy
- skonstruovat mnozinu $X^+$ explicitne

```
set h(x) = 0 for all x in X; 
for i: = 1 to m do if bi = 1 then set h(xi ) = 1; 
L(s) = h;
```



---------------
### Ucenie ocislovanim

$H$ - hypotezovy priestor
explicitne ocislovanie hypotez $H - \{ h^{(1)}, h^{(2)}, \dots \}$

![ocislovanim.png](/img/user/STU/assets/ocislovanim.png)

------------------
### Ucenie booleovskych funkcii PRIKLADY

Dana treningova vzorka
(1 1 1 0 0 0 1, 1) 
(1 0 1 1 0 1 1, 1) 
(1 1 0 1 0 0 0, 0) 
(1 1 1 0 1 1 0, 1) 
(1 1 1 1 1 1 1, 1) 
(1 1 1 1 0 0 1, 0)

Ulohou je najst algoritmus ktor bude hladat hypotezu v tvare Booleovskej funkcie

#### Valiant 1984

**Monoclen** je konjukcia literalov
$h_u: u_1\overline{u_1}u_2\overline{u_2}u_3\overline{u_3}u_4\overline{u_4} \dots u_n\overline{u_n}, U = \{u_1,\overline{u_1} \dots \}$


```
begin 
set U = {u1, u¯1, . . . , un, u¯n};
for i:=1 to m do 
	if bı=1 then 
		for j:=1 to n do 
			if (xı) j = 1 then delete u¯j from U 
						  else delete uj from U; 
L(s) = hU ;
end;

```

predpokladame hypotezu, ze sa vyskytuje kazdy literar

(000111,1)
(101010,1)
(111110,1)
(000110,0)

mame
$h_u: u_1\overline{u_1}u_2\overline{u_2}u_3\overline{u_3}u_4\overline{u_4}u_5\overline{u_5}u_6\overline{u_6}$

po prejdeni algoritmom v postupne skrtame, a ostalo nam 
$h_u: u_5$

(0001||1||1,1)
(1010||1||0,1)
(1111||1||0,1)
(0001||1||0,0)

1 => 1
1 => 0

mame spornu treningovu vzorku

#### Ucenie disjunkcii malych monoclenov

$n=6$
$k=2$
$x_1x_2 \vee x_1x_3 \vee \overline{x_2}x_4 \vee x_5 \vee \overline{x_5}$

![ucenie-disjunkcii.png](/img/user/STU/assets/ucenie-disjunkcii.png)

$M_{6,2}$ Kolko prvkov??


### Linearne prahove jednotky

### Konzistencia



(u1 and u2) or (u1 and u3) or (u1 and u4) or (u2 and u3) or (u2 and u4) or (u3 and u4)

![konzistencia-priklad.png](/img/user/STU/assets/konzistencia-priklad.png)

![prednaska2-priklad.jpg](/img/user/STU/assets/prednaska2-priklad.jpg)

