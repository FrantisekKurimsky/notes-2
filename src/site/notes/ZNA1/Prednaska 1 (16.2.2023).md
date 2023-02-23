---
{"dg-publish":true,"permalink":"/zna-1/prednaska-1-16-2-2023/"}
---

# Formal concept analysis
1980s
### formalny kontext 

objektovo atributova tabulka, trojica $(B,A,R)$, kde $B$ = objekty(konecna mnozina objektov), $A$ = atributy, vlastnosti objektov, $R \subseteq A \times B$ ($R : B \times A \to \{True, False\}$)  

### Priklad
B = {a,b,c,d,e} = {adam, barbora, cyril, david, eva}
A = {m,f,ch,b,aj,sj} = {matematika, fyzika, chemia, biologia, anglicky jazyk, slovensky jazyk}

![Legal systems](/img/user/ZNA1/assets/priklad1.png)


### formalny koncept

dvojica mnozin $<X,Y>$ $X \subseteq B$, $Y \subset B$ , kde $X \times Y \subseteq R$

{b,d} x {f, ch, b,sj}
![Legal systems](/img/user/ZNA1/assets/priklad1-2.png)

{b,d,e} x {ch, b}
![Legal systems](/img/user/ZNA1/assets/priklad1-3.png)

mensia vzorka objektov, vacsi prienik vlastnosti, ak mame malo vlastnosti, vieme definovat konkretnejsie objekty

Kreslime mnozinu {a,b,c,d,e}, vytvorime si hasseho diagram
![Legal systems](/img/user/ZNA1/assets/priklad1-hasseho-diagram.png)

pridame do diagramu mnoziny vlastnosti, koncepty

![Legal systems](/img/user/ZNA1/assets/priklad1-koncepty.png)

prepojenia robime podla mnoziny vlstnosti, tak aby sme sa vedeli dostat zhora dole

![Legal systems](/img/user/ZNA1/assets/priklad1-prepojenia.png)


**Def. Derivacne operatory, alebo tie concept forming operatory**

$\uparrow P(B) \to P(A)$ |  $X \subseteq B \uparrow(X) = \{ a \in A |(\forall b \in X )(b,a) \in R \}$
$\downarrow P(A) \to P(B)$ |  $Y \subseteq B \downarrow(Y) = \{ b \in B |(\forall a \in Y )(b,a) \in R \}$

![Legal systems](/img/user/ZNA1/assets/galois-1.png)


![Legal systems](/img/user/ZNA1/assets/galois-2.png)


![Legal systems](/img/user/ZNA1/assets/galois-3.png)


Formalny koncept

$(X,Y)$ kde $X \subseteq B , Y \subseteq A$
$\uparrow(X) = Y \& \downarrow(Y) = X$


