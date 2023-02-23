Diamo la possiblità agli [[Automa a stati finiti|FAS]] di scrivere in nastri di scrittura e di leggere da nastri di lettura, quindi potranno fare mosse in funzione di:
- Simbolo letto dal nastro di lettura
- Simbolo letto dalla pila
- Stato dell'organo di controllo:
	- Cambia stato
	- Sposta di una posizione la testina di lettura
	- Sostituisce al simbolo A una stringa $\alpha$
	- Se [[traduttore]] scrive una stringa nel nastro di uscita

Non sono necessariamente real time, puó decidere di sospendere le operazioni per lavorare sulla pila.



```
```

Possiamo sfruttare la pila per leggere le stringhe di tipo $a^nb^n$, 


# Automa traduttore a pila
![[Pasted image 20230223095250.png]]


>[!def]
>Automa traduttore a pila: $<Q,I,\Gamma, \delta, q_{0},Z_{0},F[, O, \eta]>$
>
>$Q, i,q_{0}$ ed $F[O]$ come per gli [[Automa a stati finiti|FSA]]
>$\Gamma$ alfabeto di pila
>$Z_{0}$ simbolo iniziale di pila
>$\delta: Q \times (I \cup \left\{ \varepsilon \right\})\times \Gamma \to Q \times \Gamma^*$, osserviamo che $\delta$ è parziale
>$\eta: Q \times (I \cup  \left\{ \varepsilon \right\}) \times \Gamma \to O^*$, osserviamo che $\eta$ è definita dove $\delta$ è definita.
>
> [[push]] -> $<p,\alpha> =\delta(q,I,A)$
> [[pop]] -> $w = \eta(q,I,A)$
>
>```mermaid
>graph LR
>	A(q) --->|i,A/alpha,w| B((p))
>```

## Configurazione
$$c = <q,x,\gamma>$$
Con:
- $q$ stato 
- $x$ stringa ancora da leggere sul nastro di ingresso
- $\gamma$ il contenuto della pila


### Transizione tra configurazioni
$c = <q, i.y, \beta A>\ \vdash c'$

- $q \in Q$
- $i \in I$
- $y \in I^*$
- $\beta \in \Gamma^**$
- $A \in \Gamma$

#### Caso 1:
$\delta(q,i,A) = (q',\alpha)$ (metti $q$ in $\alpha$ e vai a $q'$) ($\alpha \in \Gamma^*$)
Quindi $c' = <q',y,\beta \alpha>$

#### Caso 2:
$\gamma(q,\varepsilon,A) = (q',\alpha)$
Quindi $c',i.y,\beta \alpha($