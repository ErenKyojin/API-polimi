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
2. $|L| = \infty?$ $\exists x \in L, |Q| \leq |x| < 2|Q|$
   Anche in questo caso richiesti $|Q|-1$ passaggi ed inoltre il ciclo massimo è di lunghezza $|Q|$

3. Conseguenza negativa:
   Consideriamo il linguaggio $\left\{ a^nb^n \right\}$, composto da $n$ a seguite da $n$ b, è riconoscibile da un [[Automa a stati finiti]]? 
   Ipotiziamo per assurdo che lo sia, possiamo quindi applicare il pumping lemma ad $x = a^mb^m, m>0$, considerato $x = ywz$ abbiamo tre casi:
   1. $\underbrace{ aaa\dots aabb\dots }_{ y } \underbrace{ bb }_{ w }\underbrace{ b }_{ z } \implies aaa\dots aabb\dots \underbrace{ bbb...b }_{ (bb)^n }b$
      ha ovviamente piú b che ha, quindi non appartiene al [[linguaggio]]
    2. $\underbrace{ aa }_{ y }\underbrace{ a\dots }_{ w }\underbrace{  aabb\dots bbb }_{ z }$ analogo a sopra
    3. $\underbrace{ aaa\dots  }_{ y }\underbrace{ aabb }_{ w }\underbrace{ \dots bbb }_{ z }$ in questo caso diventa $\underbrace{ aaa\dots a }_{ x }\underbrace{ aabb\dots aabb }_{ w^n }\underbrace{ b\dots bbb }_{ z }$

>[!oss]
>È comunque possibile creare FSA in grado di contare questi alfabeti, ma bisogna sempre aggiungere uno stato ad ogni incremento dell'abilità di contare, ed essendo i FSA per definizione a stati finiti, non è possibile generalizzare il caso

Per ovviare questo problema si introducono gli [[Automa a pila|automi a pila]]

