# Espacios medibles

Un **espacio medible** es una pareja $(X, S)$ en la que $X$ es un conjunto y $S$ una sigma-álgebra. Nótese la palabra "medible", señalando la posibilidad de que este espacio se "puede medir". Una sigma-álgebra $S$ es una colección de subconjuntos de $X$ que satisface lo siguiente:
1. Los conjuntos $\emptyset, X$ pertenecen a $S$.
2. Si $A \in S$, entonces $A^c \in S$. Es decir, tenemos cerradura bajo complementos.
3. Si $\{A_k\}$ es una colección numerable de conjuntos en $S$, entonces la unión también lo está:
$$\bigcup_{k=1}^{\infty}{A_k} \in S.$$

A los elementos de $S$ les llamamos **conjuntos medibles**. Veamos algunos ejemplos.

**Ejemplo 0**.  Sea $X$ un conjunto y sea $S = \mathcal{P}(X)$ el conjunto potencia de $X$. Se comprueba que $S$ es una $\sigma$-algebra,  por lo que $(X, \mathcal{P}(X))$ es un espacio medible.

**Ejemplo 1:** $\mathbb{R}$ el conjunto de los reales, y $S$ es la sigma-álgebra de los conjuntos **Borel medibles**. 

**Ejemplo 2:** El caso anterior es particular a una clase de espacios medibles más general. Sea $X$ un conjunto y $\tau$ una **topología** en $X$. Definamos $S(\tau)$ como **la sigma-álgebra más pequeña** que contiene a $\tau$. Entonces $(X, S(\tau))$ es un espacio medible. Claro, para que esto tenga sentido, necesitamos el siguiente resultado.

**Proposición.** Si $\{S_k\}$ es una colección de sigma-álgebras en $X$. Entonces 
$$\bigcap_{k=1}^\infty S_k,$$
es una sigma-álgebra en $X$

> En otras palabras, la intersección de sigma-álgebras es una sigma-álgebra. Por tanto,  tiene sentido hablar de *la sigma-álgebra más pequeña*. 

**Ejemplo 3:** Sea $X$ un conjunto y sea $S$ la colección de subconjuntos $A$ de $X$ tal que $A$ es numerable o $A^c$ es numerable. Los conjuntos $\emptyset$ y $X$ son elementos de $S$, pues $\emptyset$ es finito. Además, por definición, este conjunto es cerrado por complementos. Sea $\{A_k\}$ una colección numerable de elementos en $S$ y sea $A = \bigcup A_k$. Si todos los $A_k$ son numerables, entonces $A$ es elemento de $S$; si algún $A_n$ no es numerable para algún $n$, entonces $A_n^c$ es numerable y $A^c \subset A_n^c$ lo cual implica que $A^c$ es numerable. Por tanto $S$ es una sigma-álgebra en $X$.  ^004e4b

Ya con el concepto de espacio medible a nuestra disposición, podemos hablar de cómo medir estos conjuntos "medibles". 

Una **medida** es una función  definida en una sigma-álgebra  que satisface lo siguiente:
1. $\mu: S \rightarrow [0, \infty]$, es decir, la medida de los conjuntos es no negativa y puede ser infinito. (veremos más adelante algunos ejemplos que no satisfacen esto)
2. $\mu(\emptyset) = 0$. (tiene sentido que el conjunto vacío mida cero)
3. $\mu\left(\bigcup_{k=1} E_k \right) = \sum_{k=1} \mu(E_k),$ para toda colección numerable y disjunta de conjuntos medibles $E_k$. A esta propiedad se le conoce como sigma-aditividad. ^aecc63

Nótese que la [[notas01#^aecc63|tercera propiedad]] implica **aditividad finita**. Es decir, 
$$\mu\left(\bigcup_{k=1}^N E_k\right) = \sum_{k=1}^N \mu(E_k).$$

> Solo haga $E_k = \emptyset$, para $k > N$. 

**Ejemplo 4**: La medida exterior es una medida en el espacio $(\mathbb{R}, \mathit{B})$, donde $\mathit{B}$ es la sigma-álgebra de los conjuntos Borel medibles.
Recordemos que, la medida exterior de un conjunto de números reales $A$, se define como 
$$m^\ast(A) = \inf \{ \sum_n l(I): A \subset \bigcup_n I_n \text{ donde cada } I_n \text{ es un intervalo abierto.}\}$$
**Ejemplo 5**: Sea $(X, S)$ el espacio medible del [[notas01#^004e4b|ejemplo 3]] con $X$ no numerable. Definamos $\mu$ como $\mu(A) = 0$ si $A$ es numerable y $\mu(A) = 1$ si $A^c$ es numerable.
1. Claramente, el rango de $\mu$ se encuentra contenido en $[0, \infty]$.
2. Puesto que $\emptyset$ es finito, $\mu(\emptyset) = 0$.
3. Sea $\{A_n\}$ una sucesión disjunta de elementos de $S$. Si todos los $A_n$ son numerables, entonces $A$ es numerable y se satisface que $\sum \mu(A_n) = \sum 0 = 0 = \mu(A)$. Por otro lado, suponga que no todos los elementos de la sucesión son numerables. Por lo expuesto anteriormente, se tiene que $A^c$ es numerable, por lo que $\mu(A) = 1$. Suponga que $A_1$ y $A_2$ son no numerables (reordenando los índices en caso de ser necesario). Puesto que $A_1 \cap A_2 = \emptyset$, $A_1^c \cup A_2^c = X$; pero $A_1^c$ y $A_2^c$ son numerables por definición, por lo que $X$ es numerable, lo cual es una contradicción. Así pues, hemos encontrado que si algún elemento de la sucesión $\{A_n\}$ es no numerable, este es único. Por lo que $\sum_n \mu(A_n) = 1 = \mu(A)$

> ¿Cuántas medidas podemos definir en este espacio? _????tantas como los reales????_

**Ejemplo 6**: Sea $(X, S)$ un espacio medible. Definamos $\mu(E) = |E|$ si $E$ es finito y $\mu(E) = \infty$ si $E$ es infinito. Entonces $\mu$ es una medida en este espacio. A esta medida se le conoce como **medida de contar**. ^39907e

Es importante señalar que la [[notas01#^aecc63|sigma-aditividad]] implica **monotonía**. Es decir, si $A, B\in S$ y $A \subset B$, entones $\mu(A) \leq \mu(B)$. Para ver esto, haga $B = (B \setminus A) \cup A$. Luego, $\mu(B) = \mu(B \setminus A) + \mu(A)$. Lo cual implica $\mu(A) \leq \mu(B)$. 

A continuación, una forma bonita de calcular medidas de **sucesiones decrecientes**.

**Teorema** Si $\{E_k\}$ es una colección decreciente de conjuntos medibles y $\mu(E_1) < \infty$ ❗, entonces
$$\mu\left(\bigcap_k E_k\right) = \lim_k \mu(E_k).$$
*Demostración:* Haga $E = \bigcap E_k$ y note que $E_1 = E \cup \bigcup_k (E_k \setminus E_{k+1})$ es una unión disjunta. Entonces (todo jala),  $\mu(E_1) = \mu(E) + \sum_{k=1} \mu(E_k \setminus E_{k+1}) = \mu(E) = \lim \mu(E_k)$. 

También, en general tenemos la siguiente desigualdad: 
$$\mu(\bigcup_k E_k) \leq \sum_{k} \mu(E_k).$$
Haga $A_k = E_k \setminus (\bigcup_{i=1}^{i < k} E_i)$. La sucesión $\{A_k\}$ es disjunta y 
$A_k \subset E_k$. Entonces
$$\mu\left(\bigcup_k E_k \right) = \sum_k \mu(A_k) \leq \sum_k \mu(E_k) $$

> **Nota:** La hipótesis $\mu(E_1)< \infty$ no se puede eliminar. Considere la sucesión $E_k = [k, \infty)$ con $k\in \mathbb{Z}$. Esta sucesión es decreciente, y $\bigcap_k E_k = \emptyset$, por lo que su medida es cero. No obstante, $\mu(E_k) = \infty$ para todo $k$. 

De manera análoga, tenemos un resultado para sucesiones crecientes.

**Teorema.** Sea $\{E_k\}$ una sucesión creciente de conjuntos medibles. Entonces

$$\mu\left( \bigcup_{k=1}^{\infty}{E_k} \right) =  \lim_{k \to \infty} \mu(E_k).$$

*Demostración*: Considere $A_k = E_k \setminus (\bigcup_i E_i)$ (hasta $i < k$) y repita el argumento anterior.

**Definición**. Decimos que una medida $\mu$ es **finita** si $\mu(X) < \infty$. Decimos que una **medida es sigma-finita**, si  existe una sucesión $\{A_k\}$ de conjuntos medibles tal que $X = \bigcup A_k$ y $\mu(A_k) < \infty$. 

**Ejemplo 7**. Los reales con la descomposición $[n, n+1]$ con $n\in \mathbb{Z}$ muestra que la medida de Lebesgue en $\mathbb R$ es sigma-finita. 

**Ejemplo 8**. Considere el [[notas01#^39907e|ejemplo 6]] cuando $X$ es no numerable. Entonces la medida de contar no es sigma-finita❗ (la unión numerable de conjuntos finitos es numerable) 

De manera similar a lo anterior, podemos definir conjuntos de **medida finita** y conjuntos de  **medida sigma-finita**. Una noción más débil que sigma-finitud es el de **medida semifinita**. Una medida es semifinita si todo conjunto de medida infinita contiene conjuntos medibles con medida arbitrariamente grande.  

**Definición**. Un **espacio de medida** es la tripleta $(X, S, \mu)$, donde $X$ es un conjunto, $S$ es una sigma-álgebra en $X$ y $\mu$ es una medida en $(X, S)$. 

**Definición**. Un espacio de medida es **completo**, si todo subconjunto de conjuntos de medida cero son medibles. Es decir, si $A \subset B$ y $\mu(B) = 0$, entonces $A \in S$.

**Ejemplo 9**. El espacio de Lebesgue es un espacio completo.

**Teorema**. Todo espacio de medida se puede completar. ❗

Sea $(X, S, \mu)$ un espacio de medida. Decimos que un _conjunto_ $E$ en $X$ es **localmente medible** si $E \cap B$ es medible para toda $B$ medible con $\mu(B) < \infty$. Es decir, puedo medir a $E$ con conjuntos medibles (por lo menos localmente). Una medida es **saturada** si todo conjunto localmente medible es medible.

**Teorema**. La colección de conjuntos localmente medibles es una sigma-álgebra que contiene a $S$.

**Teorema**. Toda medida sigma-finita puede extenderse a una medida saturada.
