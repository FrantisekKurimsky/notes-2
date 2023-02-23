---
{"dg-publish":true,"permalink":"/zna-1/prednaska-2-23-2-2023/"}
---

## Formalna konceptova analyza

- Formal Kontexnt => BAR $(B, A, R)$, kde $R \subseteq B \times A$
- objektovo atributova tabulka

#### Derivacne operatory $(\uparrow, \downarrow)$
$\uparrow P(B) \to P(A)$ |  $X \subseteq B \uparrow(X) = \{ a \in A |(\forall b \in X )(b,a) \in R \}$
$\downarrow P(A) \to P(B)$ |  $Y \subseteq B \downarrow(Y) = \{ b \in B |(\forall a \in Y )(b,a) \in R \}$

![assets/max-obdlznik.png](/img/user/ZNA1/assets/max-obdlznik.png)

#### Formalny koncept
Dvojica uzavretych mnozin prepojenych derivacnymi operatormi

X=> extent rozsah
Y => intent hlbka

$(X,Y)$ kde $X \subseteq B , Y \subseteq A$
$\uparrow(X) = Y \& \downarrow(Y) = X$

$X_1 \subseteq X_2 \leftarrow \{ a \in A |(\forall b \in X_1 )(b,a) \in R \} \supseteq \{ a \in A |(\forall b \in X_2 )(b,a) \in R \}$
$\uparrow(X_1)  \supseteq \uparrow(X_2)$

$\bigcap\limits_{b\in X} \uparrow(\{b\}) = \bigcap\limits_{b\in X}\{a\in A | (b,a) \in R\}$

$\uparrow(X_1) = \bigcap\limits_{b\in X_1} \uparrow(\{b\}) \supseteq \bigcap\limits_{b\in X_2} \uparrow(\{b\}) = \uparrow(X_2)$ => vlastnost prienikov, antiton

Veta:
$X \subseteq \uparrow \downarrow(X) ? (\forall X \subseteq B)$
Dokaz sporom:

![assets/pred-2-1.jpg](/img/user/ZNA1/assets/pred-2-1.jpg)

![assets/pred-2-2.jpg](/img/user/ZNA1/assets/pred-2-2.jpg)







$\uparrow(X) = \bigcap\limits_{(b \in X)} \uparrow(\{b\})$ => prienik riadkov
- kladny intent je defacto prienik nejakych riadkov
- algoritmus object intersection
	- vyraba postupne vsetky prieniky nad mnozinou riadkov

1. $C = \{A\}$ kde $A = \uparrow\downarrow(A)$ => cela monozina je uzavreta 

![assets/object-intersection.png](/img/user/ZNA1/assets/object-intersection.png)

![assets/object-intersection-alg.jpg](/img/user/ZNA1/assets/object-intersection-alg.jpg)

Odkrokujme si to teda :D 

|  | 1 | 2 | 3 | 4|
| ----- | ----- | ----- | ----- | ----- |
| **x** | x | x |  |  |
| **y** |  | x |  | x |
| **z** | x |  | x |  | 
| **w** |  | x | x | x |

![assets/pred2-3.png](/img/user/ZNA1/assets/pred2-3.png)

Jagard / Jagardova vzdialenost

$\rho (Y_1, Y_2) = 1 - \frac{|{Y_1 \cap Y_2}|}{|{Y_1 \cup Y_2}|}$ 
$\rho (Y, Y) = 0$ 
$\rho (Y_1, Y_2) = 1  \rightarrow (Y_1 \cap Y_2 = \{\})$ 


![assets/RICESIF.jpg](/img/user/ZNA1/assets/RICESIF.jpg)

![assets/postup.jpg](/img/user/ZNA1/assets/postup.jpg)


### Domaca uloha

Naprogramovat obidva alg. 
