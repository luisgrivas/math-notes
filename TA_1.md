### Notas 1.0 

Nuestra experiencia nos indica que existen sistemas algebraicos conformados por dos operaciones: multplicación y suma.  Los $\mathbb{Z}$ son un ejemplo de estos sistemas. 

¿Qué podemos hacer con los enteros? Forman un grupo abeliano bajo la suma. Además, la multiplicación es asociativa y conmutativa. Además existe un neutro multiplicativo (el $1​$).

Los enteros serán nuestro sistema tipo de la estructura algebraica que deseamos estudiar: **los anillos**.

#### Contexto histórico

Históricamente, el estudio de los anillos se inicio al tratar de resolver el **Último Teorema de Fermat (1637):** para $n>2​$ no existen enteros positivos $x, y, z​$ que satisfagan la ecuación

$$ x^n + y^n = z^n​$$

 En 1847, el matemático [Gabriel Lamé](https://es.wikipedia.org/wiki/Gabriel_Lam%C3%A9) declaró que había encontrado una demostración del **UTF**. La idea central de su demostración es la utilización de la siguiente ecuación: 

$$ x^n + y^n = (x+y)(x+ay)(x+a^2y) \cdots (x + a^{n-1} y)​$$,

donde $a \in \mathbb{C}$, $a^n = 1$ y $a \neq \pm 1$. 

Sin embargo esta demostración dependía de una descomposición única de primos. Anteriormente, [Kummer](https://es.wikipedia.org/wiki/Ernst_Kummer) había demostrado que esta descomposición única en primos fallaba, lo que implicaba que la demostración de Lamé era incorrecta. 

En un intento por "arreglar" la demostración, Kummer introdujo el concepto de *números complejos ideales*, el cual utilizó para demostrar el UTF para $n<100$ excepto para  $n=37, 59, 67, 74$.

Fue [Richard Dedekind](https://es.wikipedia.org/wiki/Richard_Dedekind) quién extrajo las propiedades importantes de estos "números ideales" y definió el concepto de **ideal**.; introdujo el concepto de **ideales primos** como una generalización a los números primos; definió el concepto de **campo** como un anillo conmutativo donde cada elemento distinto de cero tiene un inverso; y estableció la conexión entre anillos y su respectivo anillo de polinomios. 

El término **anillo** se debe a David Hilbert.



#### Definiciones 

*Definición Anillo*. Conjunto no vació $R$ con dos operaciones binarias, $ + $ y $ \cdot $, suma y producto tales que $(R, +)$ es un grupo abeliano, $R$ con $\cdot$ es asociativo  y las operaciones suma y producto satisfacen las propiedades distributivas.

Cabe señalar que existen autores que además incluyen como axioma la existencia de un elemento neutro para la multiplicación. No existe concenso.

El estudio de los anillos se separa en dos: los anillos conmutativos y los no conmutativos. 

*Definición Subanillo*. Subconjunto no vació de un anillo $R$ que también es anillo con las mismas operaciones.

#### Ejemplos

1. Los conjuntos $\mathbb{Z}, \mathbb{Q}, \mathbb{R}, \mathbb{C}​$ son todos anillos conmutativos con elemento unitario con las operaciones usuales de suma y multiplicación.

2. Los **enteros gaussianos** $\mathbb{Z}[i]$ forman un anillo.

3. Podemos generalizar el concepto anterior, definiendo $\mathbb{Z}[\alpha]$ como el subanillo _mas peqeño_ de $\mathbb{C}$ que contiene al complejo $\alpha$. Este subanillo esta descrito por los complejos de la forma $ a_n \alpha^n + \cdots + a_1 \alpha + a_0$ con $a_i \in \mathbb{Z}$. (:-O)

4.  Si $R$ es un anillo, las matrices $n \times n$ con entradas en $R$ forman un anillo.

5. Si $R$ es un anillo, los ponimios $R[x]$ forman un anillo.

6.  El conjunto de funciones continuas con valores reales y variable real $x​$ forma un anillo bajo las operaciones

   $$ [f + g] (x) = f(x) + g(x) $$ y $$ [fg] (x) = f(x) g(x)$$.

7. Los entero módulo $6$ , $\mathbb{Z}_6$, forman un anillo conmutativo con elemento unitario.

8. Los **cuaterniones** son un anillo **no conmutativo ** con **división**. 



#### PREGUNTAS

 ¿Cómo construyo anillos a partir de otros?

¿Qué subanillos son relevantes?

¿Qué relación existe entre un anillo $R$ y su anillo de polinomios $R[x]$?

etc