# Funciones medibles

La definición de **función medible** es similar al de función continua: deseamos que la función conserve cierta propiedad mediante imágenes inversas. Sea $(X, S, \mu)$ un espaciode mdida y sea $f: X \rightarrow \mathbb{R}$ una función. Se dice que $f$ es medible, si $f^{-1}((a, \infty))$ es un conjunto medible para toda $a \in \mathbb{R}$. Esta definición es equivalente a pedir que los siguientes conjuntos sean medibles para toda $a$ en los reales: 

1. $f^{-1}([a, \infty))$
2. $f^{-1}((\infty, a))$
3. $f^{-1}((\infty, a])$


Se puede demostrar que las funciones medibles se comportan bien con las operaciones usuales de funciones.
**Teorema**. Si $c$ es una constante real y $f, g$ son funciones medibles Entonces
* $f + c$, $cf$, $f+g$ y $f \cdot g$ son medibles.
* $\max\{f, g\}$ y $\min \{f, g\}$ son medibles. 
* Si $\{f_k\}$ es una sucesión de funciones medibles, entonces
    $$\sup f_k, \inf f_k, \limsup f_k , \liminf f_k$$ 
son medibles.

Una **función simple** es una función de la forma
$$\varphi(x) = \sum_{i=1}^{k}{a_i \chi_{A_i}(x)},$$
donde $a_i$ son constantes y $\chi_{A_i}$ son las **funciones características** en $A_i$.

Las funciones simples juegan un papel central dentro de la teoría de la medida. Por ejemplo, **toda función medible no negativa puede ser aproximada mediante funciones simples**. Además, esta aproximación puede hacerse de manera monótona. 

Sea $f$ una función medible y no negativa. Para toda $n \in \mathbb{N}$, sea $E_n = \{  
