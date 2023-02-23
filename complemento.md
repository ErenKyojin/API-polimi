$$A \cup B = \neg(\neg A \cap \neg B) $$
```mermaid
graph LR
	q0 -->|1| q1((q1)) -->|1| q0
	q1 -->|0| q1
	q0 -->|0| q0
	i --> q0
	
```
Che diventerebbe

```mermaid
graph LR
	q0 --->|1| q1((q1))
	q0 -->|0| q0
	q1 -->|0| q1
	i-->q0
```
quanti zeri vogliamo, ed **un solo uno** a differenza di quello precedente che poteva accettarne infiniti, in questo caso $\delta$ è parziale, ed abbiamo quindi un problema, manca il collegamento, risolviamo aggiungendo un caso di errore:


```mermaid
graph LR
	q0 --->|1| q1((q1))
	q0 -->|0| q0
	q1 -->|0| q1
	q1 -->|1| qe((qe))
	qe -->|1| qe
	qe -->|0| qe
	i-->q0
```
Otteniamo cosí un automa con [[funzione di transizione]] totale