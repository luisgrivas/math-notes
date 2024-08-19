#### Relaciones en un anillo

El concepto de ideal y de anillo cociente puede entenderse como la introducción de relaciones en un anillo. 

Para esta discusión, consideremos el anillo de los enteros $\mathbb{Z}$ bajo las operaciones usuales. Supongamos que queremos introducir la relación $3 = 0$, es decir, de alguna manera queremos hacer que el elemento $3$ sea el nuevo cero del anillo $\mathbb{Z}$; más aún, al introducir esta relación, queremos conservar la estructura de anillo de $\mathbb{Z}$. 

Veamos primero, cuáles son las consecuencias al introducir esta relación.

Una primera consecuencia es que $3 r = 0$ para todo $r \in \mathbb{Z}$ . Recordemos, el $3$ es el nuevo cero: si multiplicamos algo por cero me da cero. 

Una segunda consecuenta es que $b + 3 = b$ para todo $b \in \mathbb{Z}$. Como el $3$ es cero, este actúa como neutro aditivo. 

Podemos reunir las dos consecuecias anteriores como $b + 3r = b $ para todo $b, r \in \mathbb{Z}$. 

En conclusión, si queremos que en nuestro anillo se satisfaga $3=0$, entonces se tiene que satisfacer $b + 3r = b$ para todo $b, r \in \mathbb{Z}$.

¿Qué estructura toma $\mathbb{Z}$ al introducir esta relación?

Primero consideremos $b=0​$. Por la anterior, los números $ \{0, \pm 3, \pm 6, \pm 9, \ldots \} ​$ deben ser cero (solo sustituya $b=0​$ en $b + 3r = b​$ ). Esto quiere decir que la _tabla_ del $3​$ se ___mapea___ al cero.

Para $b=1​$, se tiene que los números $\{\ldots, -5, -2, 1, 4, \ldots \}​$  se mapean al $1​$. 

Para $b=2$, los números $ \{\ldots, -4, -3, 2, 5, \ldots \}$ se mapean al $2$. 

¿Y para $b=3$ ? Si observamos con cuidado, todos los enteros quedaron distribuidos en los tres subconjuntos anteriores. Por tanto, esperamos que este caso coincida con alguno de los tres antes descritos (¡verifíquese!).

Por tanto, si introducimos la relación $3=0$ en los enteros, entonces estos se mapean al $0$ al $1$ o al $2$. ¿Qué relación tiene lo anterior con los ideales y anillos cociente?

Observemos que la tabla del $3$, $3\mathbb{Z} =  \{0, \pm 3, \pm 6, \pm 9, \ldots \}$ es un ideal de $\mathbb{Z}$. Entonces, podemos formar el anillo cociente $\mathbb{Z} / 3\mathbb{Z} = \{  3\mathbb{Z}, 1 +  3\mathbb{Z}, 2 +  3\mathbb{Z} \}$ . Este anillo consiste precisamente de los tres subconjuntos antes mencionados. 

Podemos decir más, existe un homomorfismo $\phi:  \mathbb{Z} \rightarrow \mathbb{Z} / 3\mathbb{Z}​$ definido como $\phi(a) = a + 3\mathbb{Z}​$; es decir, podemos mapear todo entero a algún elemento de $\mathbb{Z} / 3\mathbb{Z} ​$. **Esto es precisamente lo que realizamos al introducir la relación $3 = 0​$**. 

¿Qué podemos concluir de la discusión anterior? Al introducir la relación $3=0$, el anillo $\mathbb{Z}$ colapsó en tres elementos, $ 3\mathbb{Z}, 1 +  3\mathbb{Z}, 2 +  3\mathbb{Z}$: cada entero se mapeó en alguno de estros tres. Pero este nuevo conjunto de tres elementos conservó una estructura algebraica, el anillo cociente $\mathbb{Z} / 3\mathbb{Z}$, es decir, colapsó de forma ***bonita*** conservando ciertas propiedades algebraicas del anillo $\mathbb{Z}$. 

Ahora bien, no tiene nada de especial la relación $3 = 0$; esta fue escogida por conveniencia. Pudimos haber establecido cualquier otra relación $n = 0$ y concluir que $\mathbb{Z} $ colapsa en $\mathbb{Z} / n \mathbb{Z}$ (los enteros módulo $n$ ).

 Pero todavía podemos hacer más,  ¿qué sucede si queremos establecer $m​$ relaciones $a_1 = a_2 = \ldots = a_m = 0​$ ?  En este caso tendríamos que para todo $b, r_1, \ldots, r_m ​$ enteros, $b + (r_1 a_1 + \ldots + r_m a_m  ) = b​$. Y como ya sabemos, esto lo podemos analizar considerando el ideal $(a_1, \ldots, a_m ) = \{r_1 a_1 + \ldots, + r_m a_m \mid r_1, \ldots r_m \in \mathbb{Z}\} ​$ y ver qué anillo se forma $\mathbb{Z} / (a_1, \ldots, a_m ) ​$.

Como nota aparte, para los que recuerden sus clases de teoría de números, sabemos que el conjunto $(a_1, \ldots, a_m )  = d \mathbb{Z}$, donde $d$ es el máximo común divisor de los números $a_1, \ldots, a_m​$. Entonces lo anterior no es tan complicado como parece. 