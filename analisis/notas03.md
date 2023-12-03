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
es decir, $\lim \int f_k = \int f$.

Otra forma de presentar los resultados anteriores, es demostrar el TCM y después utilizar este resultado para demostrar Fatou. Si uno observa detenidamente la demostración del lema de Fatou, uno puede repetir los argumentos ahí presentados para demostrar el TCM.   
> ambos teoremas son equivalentes

TCM -> Fatou
Sea $\{f_n\}$ una sucesión de funciones medibles y no negativas que convergen a $f$. Defina la sucesión $g_n = \inf {k\ge n} f_k$.  Entonces $g_n$ es medible y la sucesión $\{g_n\}$ es creciente. Por el TCM, se tiene que 
$$\int f = \int \lim_n \inf_{k \le n} f_k  = \lim_n \int g_n.$$

Por otro lado, $g_n \le f_k$, para toda $k \ge n$, por lo que $\int g_n \le \int f_k$, para toda $k \ge n$. Luego, 
$$\int g_n \leq \lim_{n\to \infty} \inf_{k \ge n} \int f_k,$$
para toda $n$. 
Por tanto, $\int f  = \lim_n \int g_n \leq \lim_n \inf_{k \ge n} \int f_k$ _QED_

Vea que los resultados anteriores nos permiten demostrar linealidad de la integral para el caso en el que $f$ sea no negativa. Recuerde el resultado: 
** Para toda $f$ medible y no negativa, existe una sucesión _creciente_ de funciones simples y no negativas que convergen a $f$**
La linealidad de la integral es fácil de demostrar para el caso en el que las funciones sean simples. Por lo que, aplicando límites, estas propiedades se "heredan". 


**Teorema**. La integral es lineal. 


Otro resultado interesante que se obtiene como resultado del TCM es el siguiente.

**Teorema**. Sea $\{f_n\}$ una sucesión de funciones medibles y no negativas. Entonces $\sum_n \int f_n = \int \sum_n f_n$.  
_Demostración_: haga $g_m = f_1 + f_2 + \cdots + f_m$ y aplique TCM a $\{g_m\}$. _QED_

Llamaremos a una función medible y no negativa $f$ **integrable** si $\int f < \infty$. Una función medible ```en general``` será **integrable** si ambas integrales $\int f^+ $ , $\int f^-$ son finitas ```es decir, ambas f+ o f- son integrables```.  

El último teorema de esta sección, es el **Teorema de Convergencia de Lebesgue**. Note que este es una consecuencia directa del lema de Fatou.

**Teorema**. Sea $g$ una función integrable en $E$ y suponga que $\{f_n\}$ es una sucesión de funciones medibles tales que $\lvert f_n \rvert \le g$, casi siempre en $E$. Si $f_n \to f$, entones
$$\int_E f = \lim_n \int f_n.$$
_Demostración_. Considere las sucesiones $\{g + f_n\}$ y $\{g - f_n\}$. Ambas sucesiones constan de funciones medibles no negativas ```aplique la desigualdad | f_k | <= g ```. El lema de Fatou implica que 
$$ \int g  \pm \int f \leq \liminf \int (g \pm f_n).$$
Por otro lado, $\liminf \int(g + f_n) = \int g + \liminf f_n$ y $ \liminf \int(g - f_n) =\int g - \limsup \int f_n$. Luego
$$ \limsup \int f_n \le \int f \le \liminf \int f_n \limsup \int f_n,$$
y esto solo es posible si $\lim_n \int f_n  =\int f$.
