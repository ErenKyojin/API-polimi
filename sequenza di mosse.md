$$\delta^* : Q \times I^* \to Q$$ viene definita induttivamente attraverso la [[funzione di transizione]] $\delta$:
- $\delta^*(q,\varepsilon) =q$
- $\delta^*(q,y.i) = \delta(\delta^*(q,y),i)$

definiamo poi:
- uno stato iniziale $q_{0}$
- uno stato finale / di accetazione $F \subseteq Q$
	- $x \in L \leftrightarrow \delta^*(q_{0},x) \in F$