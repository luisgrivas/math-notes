# Espacios medibles

Un **espacio medible** es una pareja $(X, S)$ en la que $X$ es un conjunto y $S$ una sigma-álgebra. Nótese la palabra "medible", señalando la posibilidad de que este espacio se "pude medir". Una sigma-álgebra $S$ es una colección de subconjuntos de $X$ que satisface lo siguiente:
* Los conjuntos $\emptyset, X$ pertenecen a $S$.
* Si $A \in S$, entonces $A^c \in S$. Es decir, tenemos cerradura bajo complementos.
* Si $\{A_k\}$ es una colección numerable de conjuntos en $S$, entonces la unión también lo está:
$$ \bigcup_{k=1}^\infty A_k \in S.$$

A los elementos de $S$ les llamamos **conjuntos medibles**. Veamos algunos ejemplos.

**Ejemplo 1:** $\mathbb{R}$ el conjunto de los reales, y $S$ es la sigma-álgebra de los conjuntos **Borel medibles**. 

**Ejemplo 2:** El caso anterior es particular a una clase de espacios medibles más general. Sea $X$ un conjunto y $\tau$ una **topología** en $X$. Definamos $S(\tau)$ como **la sigma-álgebra más pequeña** que contiene a $\tau$. Entonces $(X, S(\tau)$ es un espacio medible. Claro, para que esto tenga sentido, necesitamos el siguiente resultado.

**Proposición.** Si $\{S_k\}$ es una colección de sigma-álgebras en $X$. Entonces 
$$\bigcap_{k=1}^\infty S_k,$$
es una sigma-álgebra en $X$

> En otras palabras, la intersección de sigma-álgebras es una sigma-álgebra.

Por tanto, **la sigma-álgebra más pequeña** tiene sentido. 

**Ejemplo 3:** Sea $X$ un conjunto y sea $S$ la colección de subconjuntos $A$ de $X$ tal que $A$ es numerable o $A^c$ es numerable. Claramente, $\emptyset$ y $X$ son elementos de $S$, pues $\emptyset$ es finito. Este conjunto es cerrado por complementos por definición. Sea $\{A_k\}$ una colección numerable de elementos en $S$ y sea $A = \bigcup A_k$. Si todos los $A_k$ son numerables, entonces $A$ es elemento de $S$; si algún $A_n$ no es numerable para algún $n$, entoces $A_n^c$ es numerable y $A^c \subset A_n$, lo cual implica que $A^c$ es numerable. Por tanto la propiedad 3 se sastisface y $S$ es una sigma-álgebra en $X$. 

Ahora bien, tenemos el concepeto de espacio medible, pero, ¿cómo lo medimos? Necesitamos el concepto de **medida**. Una medida es una función $\mu$ definida en una sigma-álgebra $S$ que satisface lo siguiente:

1. $\mu: S \rightarrow [0, \infty]$, es decir, la medida de los conjuntos es no negativa y puede ser infinito. Veremos más adelante algunos ejemplos que no satisfacen esto.
2. $\mu(\emptyset) = 0$; lo cual, tiene sentido.
3. $mu\left(\bigcup_{k=1}^\infty E_k\right) = \sum_{k=1}^\infty \mu(E_k),$ para toda colección numerable y disjunta de conjuntos medibles $E_k$. A esta propiedad se le conoce como sigma-aditividad.

Nótese que la tercera propiedad implica **aditividad finita**. Es decir, 
$$\mu\left(\bigcup_{k=1}^N E_k\right) = \sum_{k=1}^N \mu(E_k).$$

Solo haga $E_k = \emptyset$, para $k > N$. 

**Ejemplo 4**: La medida exterior es una medida en el espacio $(\mathbb{R}, \mathit{B})$, donde $\mathit{B}$ es la sigma-álgebra de los conjuntos Borel medibles.

**Ejemplo 5**: Sea $(X, S)$ el espacio medible del **Ejemplo 3** con $X$ no numerable. Definamos $\mu$ como $\mu(A) = 0$ si $A$ es numerable y $\mu(A) = 1$ si $A^c$ es numerable.
Entonces $\mu$ es una medida en este espacio. ¿Cuántas medidas podemos definir en este espacio? 

**Ejemplo 6**: Sea $(X, S)$ un espacio medible. Definamos $\mu(E) = |E|$ si $E$ es finito y $\mu(E) = \infty$ si $E$ es infinito. Entonces $\mu$ es una medida en este espacio. A esta medida se le conoce como **medida de contar**. Es claro que solo necesitamos verificar sigma-aditividad. Sea $\{E_k\}$ una colección numerable y disjunta de elementos en $S$. Si alguno de estos $E_k$ es infinito, entonces claramente se satisface la propiedad 3.BLABLA 

Es importante señalar que la propiedad 3 implica **monotonía**. Es decir, si $A, B\in S$ y $A \subset B$, entones $\mu(A) \leq \mu(B)$. Para ver esto, haga $B = (B \setminus A) \cup A$. Luego, $\mu(B) = \mu(B \setminus A) + \mu(A)$. Lo cual implica $\mu(A) \leq \mu(B)$. 

También, una forma bonita de calcular medidas de **sucesiones decrecientes**. Si $\{E_k\}$ es una colección decreciente de conjuntos medibles, entonces
$$\mu(\bigcap_k E_k) = \lim_k \mu(E_k).$$
> Idea: serie telescópica
Haga $E = \bigcap E_k$ y note que $E_1 = E \cup \bigcup_k (E_k \setminus E_{k+1})$ es una unión disjunta. Entonces (todo jala), 
$\mu(E_1) = \mu(E) + \sum_{k=1}^\infty \mu(E_k \setminus E_{k+1}) = \mu(E) = \lim \mu(E_k)$. 

También, en general tenemos la siguiente desigualdad: 
$$\mu(\bigcup_k E_k) \leq \sum_{k} \mu(E_k).$$
Haga $A_k = E_k \setminus (\bigcup_{i=1}^{i < k})$. La sucesión $\{A_k\}$ es disjunta y 
$A_k \subset E_k$. Entonces
$$\mu\left(\bigcup_k E_k \right) = \sum_k \mu(A_k) \leq \sum_k \mu(E_k) $$


En lo siguiente, presentaremos cierta terminología que utilizaremos en notas posteriores.En primer lugar, decimos que una medida $\mu$ es **finita** si $\mu(X) < \infty$. Decimos que una **medida es sigma-finita**, si  existe una sucesión $\{A_k\}$ de conjuntos medibles tal que $X = \bigcup A_k$ y $\mu(A_k) < \infty$. 

**Ejemplo 7**. Los reales con la descomposición $[n, n+1]$ con $n\in \mathbb{Z}$ muestra que la medida de lebesgue en $\mathbb R$ es sigma-finita. 

**Ejemplo 8**. Considere el caso del **Ejemplo 6** cuando $X$ es no numerable. Entonces la medida de contar no es sigma-finita! (la unión numerable de conjuntos finitos es numerable) 

De manera similar a lo anterior, podemos definir conjuntos de **medida finita** y conjuntos de  **medida sigma-finita**. Una noción más débil que sigma-finitud es el de **medida semifinita**. Una medida es semifinita si todo conjunto de medida infinita contiene conjuntos medibles con medida arbitrariamente grande.  

Un **espacio de medida** es la tripleta $(X, S, \mu)$, donde $X$ es un conjunto, $S$ es una sigma-álgebra en $X$ y $\mu$ es una medida en $(X, S)$. 

Un espacio de medida es **completo**, si todo subconjunto de conjuntos de medida cero son medibles. Es decir, si $A \subset B$ y $\mu(B) = 0$, entonces $A \in S$.

**Ejemplo 9**. El espacio de Lebesgue es un espacio completo.

**Teorema**. Todo espacio de medida se puede completar.

Sea $(X, S, \mu)$ un espacio de medida. Decimos que un _conjunto_ $E$ en $X$ es **localmente medible** si $E \cap B$ es medible para toda $B$ medible con $\mu(B) < \infty$. Es decir, puedo medir a $E$ con conjuntos medibles (por lo menos localmente). Una medida es **saturada** si todo conjunto localmente medible es medible.

**Teorema**. La colección de conjuntos localmente medibles es una sigma-álgebra que contiene a $S$.

**Teorema**. Toda medida sigma-finita puede extenderse a una medida saturada.
