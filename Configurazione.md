
> [!def]
> $$c = <q,x,\gamma>$$
> Con:
> - $q$ stato 
> - $x$ stringa ancora da leggere sul nastro di ingresso
> - $\gamma$ il contenuto della pila
> 

# Transizione tra configurazioni
Definiamo la mossa transizione come $c \vdash c'$
$c = <q, i.y, \beta A>\ \vdash c' <q',x',\beta \alpha>$

- $q \in Q$
- $i \in I$
- $y \in I^*$
- $\beta \in \Gamma^**$
- $A \in \Gamma$

### Caso 1:
$\delta(q,i,A) = (q',\alpha)$ (metti $q$ in $\alpha$ e vai a $q'$) ($\alpha \in \Gamma^*$)
Quindi $c' = <q',y,\beta \alpha>$

### Caso 2:
$\gamma(q,\varepsilon,A) = (q',\alpha)$
Quindi $c'= <q',i.y,\beta \alpha>$ semplicemente non lavoriamo con l'ingresso

>[!oss]
>$$\forall q,A (\delta(q,\varepsilon,A)) \neq \perp \implies \forall i\ \delta(q,i,A) = \perp$$ altrimenti finiremmo in casi [[determinismo|non deterministici]]
>

### [[Chiusura]] riflessiva della transizione

>[!oss]
>Una relazione è riflessiva se
> $$
> c \vdash ^*c
>$$
>Ossia se l'automa non fa niente rimane nella stessa configurazione

### Chiusura transitiva dell transizione
$$
c_{1} \vdash c_{2} \vdash c_{3} \implies c_{1} \vdash c_{3}
$$