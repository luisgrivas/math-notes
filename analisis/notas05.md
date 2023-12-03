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
Además, si $f$ es integrable (esto es, \int f < \infty$). El siguiente teorema establece que el converso es cierto, bajo ciertas restricciones. 
> Solo requerimos que la medida sea sigma-finita. 

**Teorema** (de Radon-Nikodym). Sea $(X, S, \mu)$ un espacio de medida sigma-finita y sea $\nu$ definida en $(X, S)$ una medida absolutamente continua con respecto a $\mu$. Entonces existe una función medible y no negativa $f$, tal que para todo conjunto medible $E$, se tiene que 
$$\nu(E) = \int_E f d\mu.$$
Esta función es **única**, en el sentido de que si existe alguna otra función $g$ con esta propiedad, entonces $f = g$ c.d con respecto a $\mu$.

