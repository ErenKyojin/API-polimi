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