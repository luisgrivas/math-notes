# Integración
_fecha: 28 de noviembre de 2023_


La construcción de la siguiente teoría de integración se realiza de manera secuencial, definiendo primero la integral de las funciones medibles _más simples_. Si 
$$\varphi = \sum_{k=1}^{n}{a_i \chi_{A_i}},$$
es una función simple no negativa. Entonces, definimos su integral como
$$\int_E \varphi d\mu = \sum_{k=1}^{n} a_i \mu(A_i \cap E).$$
> Base por altura y sumar.

**Nota**: recuerde que no existe una forma única de representar a una función simple. No obstante, el valor de su integral no cambia.

Argumentos directos muestran que la integral se comporta bien con las funciones simples:
- Monotonía 
- Linealidad

Para una función $f$ no negativa y medible, definimos a la integral de $f$ como 
$$\int f d\mu = \sup \{ \int \varphi d\mu: 0\leq \varphi \leq f, \varphi \text{ simple.}\}.$$

> Definimos la integral, en términos de integrales sencillas. Note que una función simple define una partición del dominio. Esta partición, no obstante, consta de conjuntos medibles, a diferencia de la integral de Riemann, cuyas particiones constaban únicamente de intervalos.  

**Nota**. La propiedad de monotonía en esta definición se "hereda" de las integrales funciones simples. Sin embargo, propiedades como la de linealidad son complicadas de deducir. Se sigue pues, un camino aparentemente más complicado: demostrar teoremas de convergencia.

Primero, el famoso **lema de Fatou**:
$$ \int_E f \liminf \int_E f_n, $$
para sucesiones de funciones medibles no negativas $\{f_n\}$ con $f_n \to f$.

> El teorema no requiere demasiado
_Demostración_: Utilizando la definición queremos demostrar que: para toda función simple no negativa $\varphi$ con $\varphi \leq f$, se tiene que $\int_E \varphi \leq \liminf \int_E f_n$.
> De nuevo, la idea de utilizar funciones simples.

Si $\int_E \varphi = \infty$, entonces existe un conjunto medible $A\subset E$ tal que $\mu(A) = \infty$ y $\varphi > a > 0$ en $A$. Sea
$$A_n = \{x \in E: f_k(x) > a \text{ para todo } k \ge n \}.$$

> Ahora, utilizamos una sucesión de conjuntos medibles

La sucesión $\{A_n\}$ es creciente y su unión contiene a $A$ ```recuerde que f_n converge a f```. Entonces $\lim \mu(A_n) = \infty$. ```la medida se porta bonito con límite de sucesiones crecientes```. Dado que $\int f_n \ge a \mu(A_n)$,  aplicando límites obtenemos que $\lim \int f_n = \infty = \int \varphi$.

Ahora considere el caso $\int \varphi < \infty$. Entonces existe medible $A \subset E$ con $\mu(A) < \infty$ y $\varphi(E \setminus A) = \{0\}$. Sea $M$ el máximo de $\varphi$ ```la función tiene un número finito de valores```y sea $\epsilon > 0$. 

Defina la sucesión $$A_n = \{x \in E: f_k(x) > (1-\epsilon) \varphi(x) \text{ para todo }k \ge n \}$$. Entonces la sucesión $\{A_n\}$ es creciente y su unión contiene a $A$. Sea $\{B_n = A \setminus A_n\}$: es decreciente y su intersección es vacío. Por tanto, $\lim \mu(B_n) = 0$ ```de nuevo, la medida se porta bien con los límites de conjuntos```. Entonces, existe $n \in \mathbb{N}$ tal que $\mu(A \setminus A_k) < 0$. Entonces, para todo $k \ge n$, se tiene que 
$$\int f_k \ge int_{A_k} f_k \ge (1-\epsilon) \int_{A_k} \varphi \ge \int \varphi - \epsilon \left[ \int \varphi  + M \right]$$. 
Por tanto, $\liminf \int f \ge \int \varphi$.  _QED_


El lema de Fatou implica el también importante **Teorema de Convergencia Monótona**.

**Teorema (TCM)**. Sea $\{f_k\}$ una sucesión creciente de funciones medibles y no negativas que convergen a $f$. Entonces $\lim \int f_k = \int f$.
> Podemos intercambiar los límites. O "sacar" los límites de la integral.

_Demostración_: Esta es una consecuencia directa del lema de Fatou. Vea que, el hecho de que sea creciente implica que $f_k \leq f$ para toda $k$. Por lo que $\int f_k \le \int f$, para toda $k$. Luego $\limsup \int f_k  \le \int f$. Por otro lado, el lema de Fatou implica que $\int f \leq \liminf $. Obtenemos pues 
$$\int f \le \liminf \int f_k \leq \limsup \int f_k \le \int f,$$
es decir, $lim \int f_k = \int f$.
