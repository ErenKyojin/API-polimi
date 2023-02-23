# Cicli nei FSA

>[!esempio]
>```mermaid
>graph LR
>q0 --> q1 --> q2
> q2 --> q6 --> q6
> q6 --> q8
> q3 --> q6
> q1 --> q3 --> q4 --> q1
> i --> q0
>```
>C'è un ciclo tra q1 e se stesso, e tra q6 e se stesso.

Se un ciclo si puó percorrere una volta allora lo stesso ciclo si puó percorrere infinite volte, formalmente:

>[!teorema] Pupmping lemma nei FSA
>Se $x \in L$ e $|x| > |Q|$
> esistono $q \in Q$ e $w \in I^+$ tali che:
> - $x = ywz$
> - $\delta^*(q,w)=q$
> - $\forall n \geq 0, yw^nz \in L$
>
>Posso "pompare" $w$ moltiplicandola $n$ volte

Da questo lemma derivano molte proprietà:

1. $L = \varnothing$? $\exists x \in L \iff \exists y \in L :|y| < |Q|$
Per arrivare allo stato finale sono richiesti $|Q|-1$
2. $|L| = \infty?$ $\exists x \in L, |Q|\leq$