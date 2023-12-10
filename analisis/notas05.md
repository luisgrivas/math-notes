# El Teorema de Radon-Nikodym
_3 de diciembre de 2023_

Sean $\nu, \mu$ dos medidas en un espacio medible $(X, S)$. Recuerde que decimos que $\nu$ y $\mu$ son **mutuamente singulares**, y escribimos $\nu \perp \mu$, si existen conjuntos medibles $A, B$ y disjuntos, tales que $X = A \cup B$ y $\nu(A) = \mu(B) = 0$. Ahora, bien, decimos que $\nu$ es **absolutamente continua** con respecto a $\mu$, si para todo conjunto medible $A$ tal que $\mu(A) = 0$, se tiene que $\nu(A) = 0$. Denotamos a esta propiedad como $\nu \ll \mu$.
> Note que, para toda medida $\mu$, la medida $\nu = \equiv 0$, satisface que $\nu \perp \mu$ y $\nu \ll \mu$.  
> Sean $\nu,\mu$ tales que $\nu \ll \mu$ y $\nu \perp \mu$, entonces $\nu$ es la medida que asigna cero a todos los conjuntos  

Para el caso de medidas con signo, $\nu, \mu$, escribimos $\nu \ll \mu$, si $|\nu| \ll |\mu|$ y $\nu \perp \mu$ si $|\nu| \perp |\mu|$.

Sea $f$ una función medible y no negativa. Defina $\nu: S \rightarrow [0, \infty]$ como 
$$\nu(E) = \int_E f d\mu.$$

Note que, $\nu(\emptyset) = 0$. Sea $\{A_n\}$ una colección numerable y disjunta de conjuntos medibles y sea $A = \bigcup_n A_n$. Considere la sucesión $f_n = \chi_{A_n} f$. Como $\{A_n\}$ es disjunta, $\sum_n f_n = f$. Luego, por un corolario del Teorema de Convergencia Monótona, se tiene que 
$$\nu(A) = \int_A f d\mu = \int \sum_n f_n d\mu = \sum_n \int f_n d\mu = \sum_n \nu(A_n).$$
Por tanto, $\nu$ es una medida en $(X, S)$. Note además, que si $\mu(A) = 0$, entonces $\nu(A) = 0$, es decir, $\nu \ll \mu$.

> Es natural preguntarse, en qué medida esto ocurre de manera general. 

Además, si $f$ es integrable (esto es, $\int f < \infty$). El siguiente teorema establece que el converso es cierto, bajo ciertas restricciones. 

> Solo requerimos que la medida sea sigma-finita. 

**Teorema** (de Radon-Nikodym). Sea $(X, S, \mu)$ un espacio de medida sigma-finita y sea $\nu$ definida en $(X, S)$ una medida absolutamente continua con respecto a $\mu$. Entonces existe una función medible y no negativa $f$, tal que para todo conjunto medible $E$, se tiene que 
$$\nu(E) = \int_E f d\mu.$$
Esta función es **única**, en el sentido de que si existe alguna otra función $g$ con esta propiedad, entonces $f = g$ c.d con respecto a $\mu$.

Para demostrar este resultado, es necesario primero demostrar el siguiente resultado.

**Lema 1**. Sea $D$ un conjunto numerable y para cada $\alpha \in D$, sea $B_\alpha$ un conjunto medible. Si para cualesquiera $\alpha, \beta \in D$ con $\alpha < \beta$ se tiene que $B_\alpha \subset B_\beta$, entonces existe una función medible $f$ tal que $f \le \alpha$ en $B_\alpha$ y $f \le \alpha$ para $X \setminus B_\alpha$.
_Demostración_: Defina toda $x\in X$,  $f(x) = \inf\{\alpha \in D: x \in B_\alpha\}$. ```note que f(x) = infinito, si no existe conjunto B que cubra a x```. Sea $x \in B_\alpha$. Entonces, por definición, $f(x) \le \alpha$. Si $x \notin B_\alpha$, entonces no existe $B_\beta$ con $x \in B_\beta$ y $\beta \le \alpha$, pues de lo contrario, $x \in B_\beta \subset B_\alpha$. Entonces, $f(x) \ge \alpha$. Para ver que $f$ es medible, sea $a \in \mathbb{R}$. Entonces, 
$$f^{-1}((a, \infty)) = \bigcup_{a \leq \alpha} B_\alpha,$$
por lo que es un conjunto medible. Por tanto $f$ es medible.

> El siguiente lema es parte central de la demostración del Teorema de RN

**Lema 2**. Sea $C  = \bigcup_{\alpha < \beta} (B_\alpha \setminus B_\beta)$. Entonces $\mu(C) = 0$. Defina $B^\prime_\alpha = B_\alpha \cup C$ ```definimos una nueva familia, para aplicar el lemma 1```. Si $\alpha < \beta$, entonces $B^\prime_\alpha \setminus B^\prime_\beta = (B_\alpha \setminus B_\beta) \setminus C = \emptyset$, en otras palabras, $B^\prime_\alpha \subset B^\prime_\beta$. Por el lema anterior, existe una función medible $f$ tal que $f\le \alpha$ en $B^\prime_\alpha$ y $f\ge \alpha$ en $X \setminus B^\prime_\alpha$. Luego, $f \le \alpha$ en $B_\alpha$ y $f \ge \alpha$ en $X \setminus B_\alpha$ excepto en $C$, cuya medida es cero.  

_Demostración del Teorema de Radon-Nikodym_: Primero asuma que tanto $\nu$ como $\mu$ son medidas finitas. Para cada racional $\alpha$, sea $\nu - \alpha \mu$ ```una medida con signo```. Sea $(A_\alpha, B_\alpha)$ la **descompisición de Hahn** para $\nu - \alpha \mu$y tome $A_0 = X$, $B_0 = \emptyset$.

Ahora bien, note que $B_\alpha \setminus B_\beta = B_\alpha A_\beta$. Por tanto, $(\nu - \alpha \mu)(B_\alpha \setminus B_\beta) \le 0$ y $(\nu - \beta \mu)(B_\alpha \setminus B_\beta) \ge 0$ ```partes, negativas y positivas resp```. Si $\beta > \alpha$, entonces $(\nu - \alpha \mu)(B_\alpha \setminus B_\beta) - (\nu - \beta \mu)(B_\alpha \setminus B_\beta) = (\beta - \alpha) \mu(B_\alpha \setminus B_\beta) = 0$, lo que implica que $\mu(B_\alpha - B_\beta) = 0$. Aplicando el **Lema 2**, podemos encontrar una función medible $f$ tal que $f \ge \alpha$ en $A_\alpha$ ```recuerda que este es el complemento de B``` y $f \le \alpha$ en $B_\alpha$. Dado que $B_\beta = \emptyset$, podemos escoger a $f$ no negativa.   

> Demostraremos que esta $f$ es la que funciona.

Sea $E$ un conjunto medible. Considere la siguiente sucesión 
$$E_k = E \cap \left(B_{(k+1)/N} \setminus B_{k / N} \right), \ \ \ E_\infty = E \setminus \bigcup_k B_{k /N}$$

Note que $E = E_\infty \cup \bigcup_k E_k$ es una unión disjunta, por lo que 
$$\nu(E) = \nu(E_\infty) + \sum_k \nu(E_k).$$

Dado que $E_k \subset B_{(k+1)/N} \cap A_{k/N}$, se tiene que $k/N \le f \le (k+1)/N$ en $E_k$, y por monotonía de la integral
$$ k/N \mu(E_k) \le \int_{E_k} f \mu \le (k+1)/N \mu(E_k).$$

Dado que $k/N \mu(E_k) \le \nu(E_k) \le (k+1)/N \mu(E_k)$, ```recuerde que estos están en término de B, hay que recordar las desigualdades del inicio```, se tiene que 
$$\nu(E_k) - 1/N \mu(E_k) \le \int_{E_k} f d \mu \le \nu(E_k) + 1 / N \mu(E_k).$$
```juntar con la desigualdad anterior```

> Queremos demostrar que $\nu$ y la integral de $f$ coinciden en el conjunto $E_\infty$.

En $E_\infty$, se tiene que $f = \infty$ ```f es mayor a todo k+1/N con k en los naturales```. SI $\mu(E_\infty) > 0$, $\nu(E_\infty) = \infty$, dado que $(\nu - \alpha \mu)(E_\infty) $ es positvo para toda $\alpha$. Si $\mu(E_\infty) = 0$, entonces $\nu(E_\infty) = 0$, por tener $\nu \ll \mu$ ```aquí es el único lugar donde hemos utilizado esta hipótesis?```. En ambos casos se tiene que 
$$ \nu(E_\infty) = \int_{E_\infty} f d\mu$$

> Teorema de Convergencia Monótona...

Por lo que 
$$\nu(E) - 1/N \nu(E) \le \int_E f d\mu \le \nu(E) + 1/N \mu(E).$$

Como $\nu(E)$ es finito y $N$ es arbitraria, $\nu(E) = \int_E f d\mu$.

A la función $f$ del Teorema de Radon - Nikodym se le conoce como **la derivada Radon-Nikodym** de $\nu$. Frecuentemente se le denota como
$$\left[ \frac{d\nu}{d\mu} \right].$$
