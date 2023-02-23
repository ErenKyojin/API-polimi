## Elementi di un linguaggio

- **Alfabeto**, coincide matematicamente con il vocabolario, è un [[insieme]] **finito** di simboli
	  - Lettere latine minuscole: alfabeto
	  - Note musicali: alfabeto
	  - Parole italiane: alfabeto
	  - Caratteri ASCII: alfabeto
	>[!oss]
	>In un alfabeto, i singoli elementi sono detti simboli


- **Stringa** su un alfabeto A, sequenza ordinata e finita di elementi di A, anche con eventuali ripetizioni
- **Lunghezza** di una stringa
  $|a|=1, |ab|=2$
- **Stringa nulla**, $\varepsilon : |\varepsilon| = 0$
- **A\*** è l'insieme di tute le stringhe, $\varepsilon$ inclusa, su A, e si dice monoide libero
  - A = {0,1}, A* = {$\varepsilon$, 0, 1, 00, 01, 10, 11, ...}
- **Operazioni su stringe**, 
	- concatenazione x.y:
>[!esempio]
>
>x = abb, y = baba, => x.y = abbbaba,
>- è associativa: (x.y).z = x(.y.z)
>- non è commutativa: x.y != y.x
>  

- **Potenza di una stringa**
  >[!esempio]
  >$a^3 = aaa$, $(ab)^3 = ababab$, $a^0 = \varepsilon$
	

>[!oss]
>A* è costruito su A semplicemente usando la concatenazione.
>Tuttavia se A fosse l'insieme delle parole italiane, A* sarebbe un insieme di parole a caso concatenate, se vogliamo seguire una **logica** è necessario ottenerne un sottoinsieme tramite una grammatica formale


>[!def]
>**Linguaggio**: $L$ sottoinsieme di $A^*$: $L \subseteq A^*$



# Operazioni tra linguaggi

- **Concatenazione tra linuaggi**:
$L_{1}.L_{2} = \left\{ x.y | x \in L_{1}, y \in L_{2} \right\}$

>[!esempio]
>$L_{1} = \left\{ 0,1 \right\}^*, L_{2} = \left\{ a,b \right\}^*$
>$L_{1}.L_{2} = \left\{ \varepsilon, 0,1,0a,11b,10ba, \dots \right\}$, In questo linguaggio non rientrano stringe del tipo $ab1$, o lettere seguita da numeri in generale, otteniamo un sottoinsieme di A*


- **Potenza di linguaggi**:
  $L^0 = \left\{ \varepsilon \right\}, L^i = L^{i-1}.L$, si risolve quindi in modo ricorsivo
>[!esempio]
>$L = \{aba,bb,a\}$
>$L^2 = \left\{ abaaba, ababb, abaa, bbaba, bbbb, bba, aaba, abb, aa \right\}$
- **Unione**, quando l'asterisco si riferisce ad un linguaggio e non ad una alfabeto si ha che:
$$L^* =\bigcup_{n=0}^\infty L^n$$
Ossia l'insieme di tutte le potenze del linguaggio, inclusa la stringa nulla ($n=0$)

- $L^+$ o anche $A^+$ per un alfabeto, si esclude la stringa nulla ($n=1$), quindi
  $$
L^+ = \bigcup_{n=1}^\infty L^n\qquad A = \left\{ 0,1 \right\} , A^+ = \left\{ 0,1,00,01,10,\dots \right\} 
$$

>[!quote]
 >Il linguaggio è lo strumento di espressione di un [[problema]]
>- $x \in L$?
>- Un programma è corretto?
>- Un messaggio è corretto?
>- $y = x^2$?
>- $z = \det(A)$?


