# Funciones medibles
_fecha: 27 noviembre 2023_

La definición de **función medible** es similar al de función continua: deseamos que la función conserve cierta propiedad mediante imágenes inversas. Sea $(X, S, \mu)$ un espaciode mdida y sea $f: X \rightarrow \mathbb{R}$ una función. Se dice que $f$ es medible, si $f^{-1}((a, \infty))$ es un conjunto medible para toda $a \in \mathbb{R}$. Esta definición es equivalente a pedir que los siguientes conjuntos sean medibles para toda $a$ en los reales: 

1. $f^{-1}([a, \infty))$
2. $f^{-1}((\infty, a))$
3. $f^{-1}((\infty, a])$


Se puede demostrar que las funciones medibles se comportan bien con las operaciones usuales de funciones.
**Teorema**. Si $c$ es una constante real y $f, g$ son funciones medibles, entonces
* $f + c$, $cf$, $f+g$ y $f \cdot g$ son medibles.
* $\max\{f, g\}$ y $\min \{f, g\}$ son medibles. 
* Si $\{f_k\}$ es una sucesión de funciones medibles, entonces
    $$\sup f_k, \inf f_k, \limsup f_k , \liminf f_k$$ 
son medibles.

Una **función simple** es una función de la forma
$$\varphi(x) = \sum_{i=1}^{k}{a_i \chi_{A_i}(x)},$$
donde $a_i$ son constantes y $\chi_{A_i}$ son las **funciones características** en $A_i$.

Las funciones simples juegan un papel central dentro de la teoría de la medida. Por ejemplo, **toda función medible no negativa puede ser aproximada mediante funciones simples**. Además, esta aproximación puede hacerse de manera monótona. 
> Idea: realicemos una partición del intervalo $[k, k+1)$ en partes iguales de tamaño $1/2^n$.

Considere los siguiente:
$$E_{n,k} = \{x: k 2^{-n} \leq f(x) < (k+1) 2^{-n}\},$$
y 
$$\varphi = 2^{-n} \sum_{k=0}^{2^{2n}}{k \chi_{E_{n,k}}},$$
y deduzca.

**Proposición**. Si $\mu$ es una medida completa y $f$ es medible, entonces $f = g$ a.e. implica que $g$ es medible.
> La propiedad de "medible" se conserva bajo la relación a.e.
_Demostración_: Denote $A:=\{x : f(x) \neq g(x) \}$. Note que, para toda $\alpha$ real, se tiene que $g^{-1}((\alpha, \infty)) = f^{-1}((\alpha, \infty)) \cup \{x\in A: g(x) > \alpha\} \setminus \{x\in A: g(x) \leq \alpha\}$. Por hipótesis, $A$ es medible. Puesto que $\mu$ es completa, los dos últimos conjuntos de la derecha de la última ecuación son medibles (son subconjuntos de un conjunto medible de medida cero). Por tanto, $g^{-1}((\alpha, \infty))$ es medible, lo que muestra que $g$ es medible. 🤢

