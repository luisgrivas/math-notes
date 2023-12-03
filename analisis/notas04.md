# Medidas con signo
_2 de diciembre de 2024_

En esta sección veremos algunos resultados cuando permitimos que las medidas tomen también valores negativos.

> Recuerde que, cuando $a, b \ge 0$, y $\mu, \lambda$ son medidas, entonces $a \mu + b \lambda,$


**Definición**. Sea $(X, S)$ un espacio medible. Una **medida con signo** $\nu$ es una función real (extendida) definida en $S$, tal que
1. $\nu$ solo asume a lo más un valor entre $\infty$ y $-\infty$. 
2. $\nu(\emptyset) = 0$. 
3. $nu( \bigcup E_n ) = \sum \nu(E_n)$, tal que el lado derecho converge absolutamente, si la suma es finita. 

> Recuerde que, si una serie converge absolutamente, entonces converge. Sin embargo, el converso no es cierto: Consisdere la sucesión $a_n = (-1)^n / n$.

> Note que toda medida es también una medida con signo. No obstante, no teoda medida con signo es medida. ¿Cuándo ocurre esto?

Decimos que un conjunto $A$ es **positivo** con respecto a una medida con signo $\nu$, si$A$ es medible y si para todo subconjunto $E$ de $A$ se tiene que $\nu(E) \ge 0$. 
De manera similar definimos a un conjunto **negativo**. Decimos que un conjunto es **nulo** si es positivo y negativo. Un conjunto nulo tiene necesariamente medida cero: $\nu(A)  \le 0$ y $\nu(A) \ge 0$ impilca que $\nu(A) = 0$. No obstante, un conjunto de medida cero no es necesariamente nulo ```puede ser la unión de un conjunto positivo y negativo```.

Los siguientes dos resultados son utilizados para demostrar un importante Teorema de Descomposición. 

**Lema 1**. Todo subconjunto de un conjunto positivo es positivo. La unión numerable de conjuntos positivos es un conjunto positivo.

**Lema 2**. Si $E$ es medible tal que $0 < \nu(E) < \infty$, entonces existe un conjunto positivo $A$ contenido en $E$ tal que $\nu(A) > 0$. 
> Idea: 

**Teorema** (de Descomposición de Hahn). Sea $\nu$ una medida con signo en un espacio medible $(X, B)$. Entonces existe un conjunto positivo $A$ y un conjunto positivo $B$ tal que $X = A \cup B$ y $A \cap B = \emptyset.$
> Note que esto implica que podemos descomponer a la medida con signo en la suma de dos medidas.

_Demostración_: Sin pérdida de generalidad, asuma que $\nu$ no toma el valor $\infty$. Sea $\alpha$ el supremo del conjunto $\{\nu(A): A \text{ es positivo }\}$. Dado que el conjunto vacío es positivo, $\alpha \ge 0$. Sea $\{A_k\}$ una sucesión de conjuntos positivos tales que $\lim_n \nu(A_k) = \alpha$, y sea $A = \bigcup_n A_n$. ```demostraremos que este $A$ es el conjunto positivo deseado```.   

En primer lugar, por el **Lema 1**, $A$ es positivo, por lo que $\nu(A) \le \alpha$. Ahora bien, $A \setminus A_k \subset A$, para toda $k$, por lo que $\nu(A \setminus A_k) \ge 0$, ```el conjunto es subconjunto de un conjunto positivo```.  Entonces
$$\nu(A) = \nu(A_k)  + \nu(A \setminus A_k)$ \ge $\nu(A_k)$ para toda $k$. Aplicando el límite cuando $k \to \infty$, se tiene que $\nu(A) \ge \alpha$. Por tanto $\nu(A) = \alpha < \infty$.  

> Una vez encontrado el conjunto positivo $A$, procederemos a demostrar que $B = X \setminus A$ es un conjunto negativo. 

Suponga que $E$ es un subconjunto positivo de $B$. Entonces $A\cup B$ es positivo y $\nu(E \cup A) = \nu(E) + \nu(A) = \alpha  + \nu(E)$. Luego, por definición de $\alpha$, $\nu(E) = 0$. De manera que $B$ no contiene conjuntos positivos de medida positiva. Por el **Lema 2**, esto implica que $B$ no contiene subconjuntos de medida positiva ```es decir, es un conjunto negativo```. _QED_

Este resultado establece una descomposición de la medida con signo $\nu$ que se le conoce como **descomposición de Hahn**. Note que esta descomposición implica una descomposición de la medida con signo $\nu$ en dos medidas $\nu = \nu^+ + \nu^{-}$ como:
$$\nu^{+}(E) = \nu(E \cap A), \ \ \ \ \nu^{-}(E) = - \nu(E \cap B).$$

Dos medidas $\nu_1, \nu_2$ en $(X, S)$ se dice que son **mutuamente singulares**, y escribimos $\nu_1 \perp \nu_2$, si existen subconjuntos medibles y disjuntos $A, B$ con $X = A \cup B$ y $\nu_1(A) = \nu_2(B) = 0$. Entonces, la descomposición de Hahn establece una descoposición en medidas mutuamente singulares $\nu^{+}\perp \nu^{-}$. A esta descomposición se le conoce como **descomposición de Jordan** de $\nu$. Si $\nu$ es una medida con signo, a la medida $| \nu |$ definida como $|\nu|(E) = \nu^{+}(E) + \nu^{-}(E)$ se le conoce como **variación total** de $\nu$.


