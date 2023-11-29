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

Primero, el famoso **Teorema de Fatou**:
$$ \int_E f \liminf \int_E f_n, $$
para sucesiones de funciones medibles no negativas $\{f_n\}$ con $f_n \to f$.

> El teorema no requiere demasiado
_Demostración_: Utilizando la definición queremos demostrar que: para toda función simple no negativa $\varphi$ con $\varphi \leq f$, se tiene que $\int_E \varphi \leq \liminf \int_E f_n$.
> De nuevo, la idea de utilizar funciones simples.

Si $\int_E \varphi = \infty$, entonces existe un conjunto medible $A\subset E$ tal que $\mu(A) = \infty$ y $\varphi > a > 0$ en $A$.

