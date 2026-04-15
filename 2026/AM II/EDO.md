## Ecuaciones Diferenciales Ordinarias (EDO)

### Definiciones

#### Función incógnita

Sea la función incógnita $y=f(x)$ (donde x es la variable independiente). A continuación, definiremos formalmente una Ec. Diferencial, de la sig. manera:

Una Ecuación Diferencial establece una relación entre una variable independiente, una función incógnita de dicha variable independiente y las derivadas de distinto orden de la función incógnita. La relación es tal que:

- Si la función incógnita $y=f(x)$, es de una sola variable independiente, recibe el nombre de **Ecuación Diferencial Ordinaria**.
- Si la función incógnita es de dos o mas variables independientes, se la denomina **Ecuación Diferencial en Derivadas Parciales**.

#### Orden de una EDO

<font color="#ffff00">Definición</font>: El orden de una Ecuación Diferencial esta dado por el mayor orden de derivación presente en la Ecuación Diferencial.

#### Grado de una EDO

<font color="#ffff00">Definición</font>: El grado de una Ecuación Diferencial esta dado por el mayor exponente de la derivada, que da el orden de la Ecuación Diferencial.

**EJEMPLO 1:** Determinar el orden y el grado de las siguientes EDO.

$$
y´+4y^2=0  
$$
Entonces, la EDO se la clasifica según el orden como: 1° Orden y de 1° Grado.

$$
(y´´)^3 +4y-y=0

$$
Entonces, la EDO se la clasifica según el orden como: 2° Orden y de 3° Grado.

---- 
Es importante destacar que resolver una EDO, implica encontrar la función primitiva (o solución general) que dio origen a la Ecuación Diferencial, es decir, hallar una relación entre las variables conteniendo $n$ constantes arbitrarias independientes, que junto con las derivadas obtenidas de ella satisfaga la Ecuación Diferencial.

La **solución general** representa una familia de funciones (familia de curvas) dependientes de los parámetros.

Si la Ecuación Diferencial es de *<u>orden n</u>*, la solución general tendrá *<u>n constantes arbitrarias e irreducibles</u>*.

Si se asignan a las constantes valores determinados o se ponen condiciones iniciales (donde la Var. Indep. es el tiempo) o condiciones de borde (donde la Var. Indep. es el recorrido, la distancia, etc.) que permita calcula las constantes, se obtiene una *<u><font color="#ffff00">Solución Particular</font></u>*. 
La grafica de una solución particular, es una curva que se llama *<font color="#ff00"><u>Curva Integral</u> </font>*

**EJEMPLO 2:**

$$y´=sen \ x \,\,\,\,\,\,\, o \,\,\,\,\,\,\ y´-sen \ x = 0 $$
Entonces, la EDO se clasifica según el orden como: 1° Orden y de 1° Grado

Planteando:

$$
y´= \frac {dy}{dx}=sen \ x \rightarrow dy=sen \ x \cdot dx
$$
$$
\int dy\int sen \ x \cdot dx
$$
Integrando miembro a miembro, resulta la Solución General:
$$
y(x)=-cos\ x + \textcolor{green} c
$$
La solución General presenta una sola constante irreductible, en correspondencia con el orden de la Educación Diferencial.

Si le asignamos, al ejemplo anterior, una condición de borde $y(0)=1$ a la solución general:

$$y(x)= -cos\ x + \textcolor {green} C \,\,\,\,\, si \,\,\,\,\, y(0)=1$$
$$1=-cos\ 0 + C$$
$$
1+1 = C \rightarrow C=2
$$
Al encontrar el valor de C=2 y reemplazarlo en la Solución General, se obtiene la **Solución Particular:**
$$
y_p (x)=-cos \ x +2
$$

----

### EDO - Método de Variables Separables


Sean $f(x)\ y\ g(y)$ funciones continuas en sus respectivos dominios, donde

*Forma general*    $y´ \cdot g(y)= f(x)$    o    $y´ \cdot g(y)-f(x)=0$

Reemplazando la derivada primera pro su notación de diferenciales, se obtiene:

$$
\frac {dy}{dx} \cdot g(y) = f(x) \rightarrow g(y) \cdot dy = f(x) \cdot dx
$$
Integrando miembro a miembro, la expresión de la igualdad anterior queda:

$$
\int g(y)\cdot dy = \int f(x) \cdot dx + C
$$
Expresión que permite hallar de la solución general de una EDO, donde C es la constante de integración.

----

### EDO - Trayectorias Ortogonales

Definiciones: Dos curvas que se cortan <mark style="background:#274e">son ortogonales</mark>, si las tangentes a las mismas en su punto de intersección son perpendiculares.
Si tenemos una familia de curvas $c_1,c_2,....,c_n$ otra curva C, se dice que es ortogonal esa familia de curvas si C es ortogonal a todas las curvas de la familia.
Sea $F(x,y,C)=0$ es la ecuación de una familia de curvas. Derivando y eliminando el parámetro C se obtiene la Ecuación Diferencial de la familia.
Si $F(x,y,y´)=0$ es la ecuación diferencial de la familia entonces: 
$F(x,y,-1/y´)=0$ será la ecuación Diferencial de las **Trayectorias Ortogonales** 

Resolviendo la última ecuación se obtiene las trayectorias ortogonales. Se dice que las curvas de dos familias son mutuamente ortogonales y forman una **red ortogonal**


## Ec. Diferenciales Exactas y Reducibles a Exactas

### Ecuaciones Diferenciales Exactas

$M(x,y) dx+N(x,y)dy=0$ (1) $\rightarrow Forma\ general$
Las funciones $\textcolor{blue} {M(x,y)}$ y $\textcolor {blue} {N(x,y)}$ son dos funciones de dos variables definidas en una región R ubicada en el plano horizontal con una frontera cerrada que no se corta a si misma; y además ambas funciones tienen derivadas parciales primeras continuas en la región R. 

La ecuación diferencial de la ec. (1) es exacta, si su primer miembro es igual al diferencial total, o exacto, de una función escalar de dos variables independientes $u(x,y)$.
$$
du(x,y) = \frac {∂u}{∂x}\ dx\ + \frac {∂u}{∂y}dy \,\,\, (2) \rightarrow \text{Def. del diferencial Total du de una función escalar}  
$$

Por lo tanto si el primer miembro de la ec. (1) debe ser igual al segundo miembro de la ec. (2), entonces:

$$
du=0 \rightarrow u(x,y)=K
$$
$u(x,y)$ es una función constante

Para que el primer miembro de la ec. (1) sea igual al segundo miembro de la ec. (2) deben cumplirse las siguientes igualdades:
$$
\frac {∂u(x,y)}{∂x}= M(x,y) \,\,\, (3) \ ; \ \,\,\, \frac {∂u(x,y)}{∂y} = N(x,y) \,\,\, (4)
$$
Derivando parcialmente por segunda vez la ec. (3) respecto de la variable "y", y también la ec. (4) derivándola parcialmente por segunda vez con respecto a "x", entonces se tienen las siguientes expresiones:
$$
\frac {∂M(x,y)}{∂y}= \frac {∂^2u(x,y)}{∂y∂x} \,\,\,; \,\,\, \frac {∂N(x,y)}{∂x}= \frac {∂^2u(x,y)}{∂x∂y}
$$
Donde los segundos miembros de las dos igualdades anteriores son las derivadas parciales segundas cruzadas que, en las condiciones indicadas precedentemente, son iguales. Resultando:

$$
\frac {∂M(x,y)}{∂y}=\frac {∂N(x,y)}{∂x} \,\,\, (5)
$$
El cumplimiento de la igualdad de la ec. (5), por parte de las funciones $M(x,y)$ y $N(x,y)$ nos asegura que la EDO de primer orden indicada en la ec. (1), es <font color="#dda22">Diferencial Exacta</font>


### Ecuaciones Diferenciales Reducibles a Exactas


$P(x,y)dx + Q(x,y)dy=0$  (11) $\rightarrow$ *Forma general*

$P(x,y)\ y\ Q(x,y)$ son similares a $M(x,y)$ y $N(x,y)$, sin embargo no cumplen la condición (5). Vale decir que: 
$$
\frac {∂P(x,y)}{∂y} \neq \frac {∂Q(x,y)}{∂x} \,\,\, (12) 
$$
Por lo tanto la ec. (11) no es una Ec. Diferencial Exacta.

No obstante, multiplicando la ec. (11) por una función de una o de dos variables independientes, según el caso, puede ser reducida a diferencial exacta. La función $F(x,y)$, para el objeto del estudio en desarrollo será un dato del ejercicio, se la denomina como el Factor Integrante.

Sea $F(x,y) \neq 0$, el Factor Integrante. Entonces:
$$
	\textcolor{red}{F(x,y)}\cdot P(x,y)dx + \textcolor{red}{F(x,y)}\cdot Q(x,y)dy= 0 \,\,\, (13)
$$

Redefiniendo a: 

$$
F(x,y) \cdot P(x,y) = M(x,y) \,\,\, (14) \,\, ; \,\, F(x,y) \cdot Q(x,y)=N(x,y) \,\,\, (15)
$$

Entonces, se obtiene una EDO análoga a la ec. (1), que debe cumplir con la igualdad planteada en al ec. (5)

Una vez determinada la expresión de la ec. (13), el procedimiento para hallar la Solución General, es el mismo que se utilizó Ec. Dif. Exactas.

**EJEMPLO 4:** $sen \ y\ dx + cos\ y\ dy = 0$

### Ecuaciones diferenciales de Primer orden Lineales

Si $\textcolor{red}{r(x)=0}\,\ \forall\ x$ en el dominio de $r(x) \Rightarrow$ queda:
$$
y´(x)+f(x)y(x)=0 \,\,\ (2)
$$
Y la EDO (2) recibe el nombre de *homogénea.*
En cambio, si $\textcolor{red}{r(x) \neq 0}\,\ \forall x$ en el dominio de $r(x) \Rightarrow$ queda la expresión (1)
$$
y´(x)+f(x)y(x)=\textcolor{red}{r(x)} \,\, (1)
$$
#### Método General

**<u>Caso a:</u>** Sea $r(x)=0\ \forall x$ en el dominio de $r(x)$. Se debe resolver la (2)
$$
y´(x)+f(x)y(x)=0 \,\,\ (2)
$$
Se trata de un caso a resolver mediante el método de *<font color="#abc">Variables Separables</font>* 
$$
y´(x)=-f(x)\cdot y(x)
$$
$$
\frac {dy}{dx} = -f(x)\cdot y(x)
$$
$$
\frac {dy}{y(x)}=-f(x)\cdot dx \,\, (3)
$$
Integrando ambos miembros en la ec. (3) respecto de x queda:

$$
ln|y|= - \int f(x) + \textcolor{lightblue} {C_1}= - \int f(x)dx + \textcolor {lightblue}{ln|C_2|} \, con \ C_1 = ln|C_2|
$$
$$
ln|y|-ln|C_2|=-\int f(x)dx
$$
$$
ln|\frac {y}{C_2}|= -\int f(x)dx
$$
Aplicando a ambos miembros la función exponencial se obtiene: 
$$
\textcolor{lightblue}e^{ln|\frac{y}{C_2}|}=\textcolor {lightblue}e^{-\int f(x)dx}= \frac {y}{C_2}
$$
$$
y(x)= \pm C_2 \textcolor{lightblue} e^{-\int f(x)dx}\ \ (4)
$$

**<u>Caso b</u>**: sea $r(x) \neq 0$. Entonces se trata de resolver la EDO no homogénea
$$
\textcolor{lightblue}{y´(x)}+f(x)y(x)=r(x) \ \ (1)
$$
Conviene re-escribir la (1) de la siguiente manera:
$$
\textcolor{lightblue}{\frac {dy}{dx}}+f(x)\cdot y(x)=r(x)
$$
Reordenando la expresión anterior queda:
$$
\textcolor{red}{[f(x)y(x)-r(x)]}dx+1\cdot dy = 0 \ \ (5)
$$
En apariencia es similar a una EDO de primer orden, exacta, si se considera:
$$
P(x,y)=\textcolor{red}{[f(x)y(X)-r(x)]}\ ;\ Q(x,y)=1
$$
Pero: 
$$
\frac {∂P(x,y}{∂y}=f(x) \ ; \ \frac {∂Q(x,y)}{∂x}=0
$$
como $f(x) \neq 0 \ \Rightarrow$ no se cumple la condición para que la (5) sea exacta.

El *factor Integrante* puede ser una función de una o de dos variables independientes como se vio en la clase anterior.
En este caso existe una función de una sola variable $F(x) \neq 0$ que depende sólo de la variable independiente x, denominada Factor Integrante, que convierte a la (5) en EDO exacta. Por lo tanto multiplicando la (5) por el Factor Integrante queda:  
$$
\textcolor{lightblue}{F(x)\cdot [f(x)y(x)-r(x)]}\cdot dx + \textcolor{lightblue}{F(x)}\cdot dy =0 \ \ (6)
$$
Expresión en la cual puede asociarse:
$$
M(x,y)=\textcolor{lightblue}{F(x)\cdot [f(x)y(x)-r(x)]}\ ; \ N(x,y) = \textcolor{lightblue}{F(x)}
$$
Por lo tanto si se cumple que:
$$
\frac{∂M(x,y)}{∂y}= \frac {∂N(x,y)}{∂x}
$$
Calculando ambas derivadas parciales deberá ser:
$$
F(x)\cdot f(x)=\frac {dF(x)}{dx} \ \ (7)
$$
Reordenando la igualdad anterior se tiene: 
$$
\frac {dF(x)}{F(x)}=f(x)\cdot dx
$$
Integrando ambos miembros se obtiene:
$$
ln|F(x)|=\int f(x)dx
$$
Por lo tanto el *Factor Integrante* $F(x)$ será:
$$
F(x)=e^{\int f{x}dx} \ \ (8)
$$
*<u>Nota:</u> en la exp. del F.I no se considera la cte. de integración C.*
Determinando el Factor Integrante, se multiplica la EDO (1) por $F(x):$
$$
\textcolor{lightblue}{F(x)}\cdot [y´(x)+f(x)y(x)]=\textcolor {lightblue}{F(x)}\cdot r(x)
$$
$$
\textcolor{lightblue}{e^{\int f(x)dx}[y´(x)+f(x)y(x)]}=e^{\int f(x)dx}r(x) \ \ (9)
$$
El primer miembro de la (9), indicado en color, no es otra cosa que la derivada de un producto de funciones de la variable x.

$$
e^{f(x)dx}[y´(x)+f(x)\cdot y(x)]= \frac {d}{dx}[\textcolor{lightblue}{y(x)\cdot e^{\int f(x) dx}}] \ \ (10)
$$
Reemplazando el segundo miembro de la (10) como primer miembro de la (9) la igualdad queda: 
$$
\frac {d}{dx}[y(x)\cdot e^{\int f(x)dx}] = e^{\int f(x)dx}\cdot r(x)
$$
Reordenando obtenemos:
$$
d[y(x)\cdot e ^{\int f(x)dx}]=e^\int f(x)dx \cdot r(x)\cdot dx \ \ (11)
$$
Integrando la (11) queda:
$$
y(x)\cdot e^{\int f(x)dx}= \int e^{f(x)dx}\cdot r(x)\cdot dx + C \ \ (12)
$$
Es importante destacar que la cte. de integración C queda fuera de la integral. Despejando $y(x)$ de la (12) se llega, finalmente a la solución general:

$$
\boxed{y(x)= e^{-\int f(x)dx}[\int e^{\int f(x)dx} \cdot r(x)\cdot dx + \textcolor{lightblue}{C}]} \ \ (13)
$$
-----
#### Método de Lagrange.

Se trata de hallar la solución general de la misma EDO lineal no homogénea indicada como (1)
$$
y´(x)+f(x)\cdot y(x)=r(x) \ \ (1)
$$
Cabe mencionar que una misma EDO no puede tener diferentes soluciones según el método que se utilice. Por lo tanto, mediante el Método de Lagrange, más sencillo, se deberá llegar a la misma expresión (13) obtenida en el apartado anterior.
Joseph Lagrange propone como solución general de la (1) el producto de dos funciones de x, una de las cuales es la solución de la EDO homogénea.
Si se denominan como $\textcolor{lightblue}{u(x)}$ y $\textcolor{lightblue}{v(x)}$ a ambas funciones, entonces la solución general de (1) será de la forma:
$$
y(x)=u(x)\cdot v(x) \ \ (14)
$$
Sea $u(x)$ la solución general de la EDO homogénea:
$$
y´(x)+f(x)\cdot y(x)=0
$$
Vale decir que deberá cumplirse:
$$
u´(x)+f(x)\cdot u(x)=0 \ \ (15)
$$
Que se resuelve en Variables separables. No es indispensable repetir el procedimiento ya desarrollado precedentemente. Sólo se indica el valor de $u(x)$:
$$
\boxed {u(x)=e^{-\int f(x)dx}}
$$
Ahora bien, derivando (14) respecto de x se tiene:
$$
y(x) = u(x) \cdot v(x) \ \ (14)
$$
$$
y´(x)=u´(x)\cdot v (x) + u(x)\cdot v´(x) \ \ (16)
$$

Reemplazando la (14) y la (16) en la (1) queda:
$$
\textcolor{red}{y´(x)}+f(x)\cdot \textcolor{lightblue}{y(x)}= r(x) \ \ (1)
$$
$$
\textcolor{red}{u´(x)\cdot v(x)+u(x)\cdot v´(x)}+f(x)\cdot \textcolor{lightblue}{u(x)\cdot v(x)}=r(x)
$$
$\textcolor{red}{v(x)}$ es factor común de dos términos; por ello reordenando la ecuación tenemos:
$$
\textcolor{red}{v(x)}[\underbrace{\textcolor{lightblue}{u´(x)+f(x)\cdot u(x)} }_{=0}]+ u(x)\cdot v´(x)=r(x)
$$
$$
v´(x)=\frac{dv}{dx}=\frac {r(x)}{u(x)}=\frac{r(x)}{e^{-\int f(x) dx}}=e^\int f(x)dx \cdot r(x)
$$
Por lo tanto:
$$
\boxed{v(x)=\int e^{\int f(x)dx }\cdot r(x)dx+C}
$$
Finalmente, reemplazando las funciones halladas para $\textcolor{lightblue}{u(x)}$ Y $\textcolor{lightblue}{v(x)}$ en (14) queda:
$$
y(x)=u(x)\cdot v(x)\Rightarrow \boxed{y(x)=\underbrace{e^{-\int f(x)dx}}_{u(x)} [\int\underbrace{e^{\int f(x)dx}\cdot r(x)\cdot dx + C}_{v(x)}]}
$$
#### EDO Bernoulli

La forma general de una ecuación diferencial de Bernoulli es la siguiente:

$$
\boxed{y´(x)+f(x)\cdot y(x)=r(x)\cdot y^a(x)} \ \ (17)
$$
Expresión en la cual el exponente $\textcolor{lightblue}{a\in R}$ 
<u>Caso 1:</u> Si $\textcolor{red}{a=0}$ el segundo miembro de (17) es igual a: $\textcolor{lightbue}{r(x)\cdot \underbrace {y^0 (x)}_{=1}}$ 
Ya que cualquier función elevada a la potencia 0 es = 1
Quedaría: 
$$
y´(x)+f(x)\cdot y(x)=\color{lightblue}{\boxed{r(x)}}$$
Ya estudiada anteriormente.

<u>Caso 2:</u> Si $\textcolor{red}{a=1}$ el segundo miembro de (17) es igual a: $\textcolor{lightblue}{r(x)\cdot y^1 (x)}$ y la ecuación (17) puede escribirse de la siguiente manera:
$$
y´(x)+f(x)\cdot y(x)=\color{blue}{\boxed{\textcolor{white}{r(x)\cdot y(x)}}}
$$
$$
y´(x)+[f(x)-r(x)]\cdot y(x)=0
$$

<u>Caso 3:</u> Si la constante a es: 
$$
\begin{cases}
a \neq 0 \\
a\neq 1
\end{cases}
$$
Partiendo de la expresión (17):
$$
y´(x)+f(x)\cdot y(x)=r(x)\cdot y^a (x) \ \ (17)
$$
Se divide la (17) por $y^a(x)$ lo que equivale a multiplicar por $y^{-a}(x) \Rightarrow$
$$
\textcolor{red}{y^{-a}(x)} \cdot y´(x)+f(x)\cdot \textcolor{red}{y^{-a}(x)}\cdot y(x) = r(x)
$$
$$
y^{a}(x)\cdot y´(x)+f(x)\cdot \underbrace{\boxed{y^{-a+1}(x)}}_{z(x)}=r(x) \ \ (18)
$$
La transformación propuesta por Bernoulli, que permite linealizar la (18) consiste en llamar como $z(x)$ a:
$$
z(x) = y^{-a+1}(x) \ \ (19)
$$
Derivando implícitamente $z(x)$ respecto de x se obtiene:
$$
z´(x)=(-a+1)\cdot[y^{-a}(x)]\cdot y´(x)
$$
Expresión de la que se puede despear $y´(x) \Rightarrow$ 
$$
y´(x)=\frac{z´(x)}{(-a+1)\cdot [y^{-a}(x)]} \ \ (20)
$$
Reemplazando las igualdades de (19) y (20) en la (18) se obtiene:

$$
\frac {z´(x)}{(-a+1)\cdot \cancel{[y^{-a}(x)]}}\cdot \cancel{[y^{-a}(x)]}+f(x)\cdot z(x)=r(x) \ \ (21)
$$
Simplificando (21) tenemos:
$$
\frac {z´(x)}{(-a+1)}+f(x)\cdot z(x) = r(x) \ \ (22)
$$
Multiplicando (22) por $\textcolor{lightblue}{(-a+1)}$ y reordenando queda:
$$
\frac{\cancel{\textcolor{lightblue}{(-a+1)}}\cdot z´(x)}{\cancel{(-a+1)}}+\textcolor{lightblue}{(-a+1)}\cdot f(x)\cdot z(x)= \textcolor{lightblue}{(-a+1)}\cdot r(x)
$$
Simplificando la expresión anterior finalmente se llega a:
$$
\boxed{z´(x)+(1-a)\cdot f(x)\cdot z(x)=(1-a)\cdot r(x)}\ \ (23)
$$
La ec. (23) es una EDO lineal no homogénea en $\textcolor{lightblue}{z´(x)}$ y $\textcolor{lightblue}{z(x)}$; se resuelve por el Método de Lagrange desarrollado en filminas anteriores.
Una vez obtenida la solución general $\underline{z(x)}$ de la (23) se reemplaza en la expresión (19) para obtener la $\textcolor{red}{Solción\ general\ \underline{y(x)}\ de \ la\ EDO\ original.}$


**EJERCICIO DE LA CLASE**

1) Var. separables
$$
y´=\frac {6e^{2x}}{e^y}
$$
## Ec. Diferenciales de Segundo Orden Lineales Homogéneas

----
La forma general de una EDO de segundo orden lineal es la siguiente:
$$
\boxed {y´´(x)+f(x)y´(x)+g(x)y(x)=r(x)} \ \ \ (1)
$$
La ec. Diferencial (1) se la denomina lineal porque los términos $\textcolor{lightblue}{y´´(x), y´(x)}  \ e \ \textcolor{lightblue}{ y(x)}$ están elevados a la primera potenica.

Se trata de hallar la solución general de la EDO (1) suponiendo que las funciones $f(x), \ g(x)\ y \ r(x)$ son continuas en un cierto intervalo I de x.

<u>Estudio de la ecuación diferencial homogénea</u>

Si:

- $\textcolor{lightblue}{r(x)=0}\ \forall x$ en el dominio de $r(x) \Rightarrow$ queda:
$$
\boxed {y´´(x)+f(x)y´(x)+g(x)y(x)=0}\ \ (2)
$$
Y la EDO (2) recibe le nombre de homogénea.

- $r(x) \neq 0 \Rightarrow$ queda la expresión (1)
$$
\boxed{y´´(x)+f(x)y´(x)+g(x)y(x)=\color{lightblue}{r(x)}} \ \ (1)
$$
Y la EDO se denomina no homogénea.

Si $f(x)=\textcolor{lightblue}{a} \ y \ g(x)=\textcolor{lightblue}{b}$, ambas constantes, la ecuación diferencial de segundo orden queda:
$$
\boxed{y´´(x)+\textcolor{lightblue}{a}y´(x)+\textcolor{lightblue}{b}y(x)=r(x)}  \ \ (3)
$$
La EDO (3) se denomina Ecuación diferencial de segundo orden a <font color="#drr00">COEFICIENTES CONSTANTES</font>, que podrá ser <font color="#drr00">HOMOGÉNEA</font> o <font color="#drr00">NO HOMOGÉNEA</font> según el valor de la función r(x)

#### Estudio de la Ec. Dif. de segundo orden lineal a coeficientes constantes homogénea
$$
\boxed{y´´(x)+\textcolor{lightblue}{a}y´(x)+\textcolor{lightblue}{b}y(x)=0}\ \ (4)
$$
En la que los coeficientes de a y b son constantes reales.

La solución general de la ec. (4) será la combinación lineal de dos funciones $y_1 (x)$ e $y_2(x)$, cada una de las cuales separadamente es solución de la EDO (4) y además son linealmente independientes, por lo cual deberá cumplirse que la razón entre ambas soluciones no sea una constante numérica.
$$
\frac {y_2(x)}{y_1(x)}\neq \ constante
$$
Cumpliéndose estas condiciones, las funciones $y_1(x)$ e $y_2(x)$ constituyen una base o sistema fundamental de soluciones de la EDO (4) y la solución general se describe de la siguiente manera:
$$
y(x)=c_1 y_1(x)+c_2y_2(x)
$$
Donde $C_1$ y $C_2$ son constantes independientes, arbitrarias e irreductibles, ya que no pueden reducirse a una sola o a ninguna.

#### Determinación de la solución general

Para hallar la base o sistema fundamental de soluciones de la ec. (4) se aplica la solución propuesta por Jean D´ Alembert, la cual, considera la forma  de la solución como una función exponencial: 
$$
\begin{cases}
y(x)=e^{rx}\\
y´(x)=re^{rx}\ \ \ \ (5) \ \ \ \ \ y´´(x)+\textcolor{lightblue}{a}\ y´(x)+\textcolor{lightblue}{b}\ y(x)=0 \ \ \ (4)\\ 
y´´(x)=r^2e^{rx}
\end{cases}
$$
Reemplazando (5) en (4)
$$
r^2e^{rx}+rae^{rx}+ b \ e^{rx}=0
$$
$$
e^{rx}(r^2 + ar +b)=0 \ \ (6)
$$
Como la función exponencial no puede ser nula para valores finitos de la variable $x\Rightarrow e^{rx}\neq 0$

Por lo tanto, deberá ser nula la expresión entre paréntesis
$$
(r^2 + ar + b)=0 \ \ (7)
$$
La ec. (7) recibe el nombre de **Ecuación característica** asociada a la ecuación diferencial dada. Se trata de una ecuación cuadrática igualada a cero, cuyas raíces determinarán la forma de la solución general.
Aplicando la Fórmula Bhaskara se tiene:
$$
y_1(x)=e^{r_1x} \ \ \ \ ; \ \ \ \ y_2(x)=e^{r_2x}
$$
Finalmente la solución general de la EDO (4) adopta la siguiente forma:
$$
y(x)=C_1e^{r_1x}+C_2 e^{r_2x} \ \ \ (8)
$$

**<u>CASO 1</u>**: Raíces reales y distintas $(r_1\neq r_2)$ 

Se analizan en las expresiones de las raíces $r_1 \ y \ r_2$, los radicandos de los segundos sumando de las ec. de la Bhaskara.
En este caso el radicando deberá ser positivo
$$
a^2 - 4ab > 0
$$
$$
a^2 > 4ab
$$

Por lo tanto, las funciones de la Base serán:
$$
y_1(x)=e^{[\frac{(-a+\sqrt{a^2-4ab})}{2}]x} \ \ \ \ ; \ \ \ \ y_2(x)=e^{[\frac{(-a-\sqrt{a^2-4ab})}{2}]x}
$$
Entonces, la Solución General queda expresada como:
$$
y(x)=C_1 e^{[\frac{-a+\sqrt{a^2 -4ab}}{2}]x} + C_2 e^{\frac{(-a-\sqrt{a^2-4ab})}{2}x} \ \ \ (9)
$$
La solución general resultante, es la combinación lineal de dos funciones exponenciales
$$
\boxed {y(x)=C_1 e^{r_1x}+C_2 e^{r_2x}}
$$
Por lo tanto, ambas funciones constituyen una Base o Sistema Fundamenta de soluciones de la EDO de la ec. (4)

**<u>CASO II:</u>** Raíces reales e iguales $(r_1=r_2)$

Analizando nuevamente las ec. de la Bhaskara, donde $r_1=r_2$, obtenemos que el radicando en los segundos sumando es nulo:
$$
a^2 - 4ab=0
$$
$$
a^2 = 4ab
$$
Por lo tanto, ambas funciones $y_1(x)\ e\ y_2(x)$ serán iguales y no se dispone de una Base o Sistema fundamental de soluciones de la ec. (4)
$$
y_1(x)=y_2(x)=e^{-\frac12a}x
$$
Para ello, debe determinarse otra función, que agregada a la anterior, constituya la Base de soluciones buscada.
Por lo que se propone a la función $y_2(x)$, como el producto de las funciones $y_1(x)$ por otra función incógnita $u(x)$:
$$
y_2(x)=y_1(x).u(x) \ \ \ (10)
$$

Derivando una y dos veces la igualdad de la ec. (10), resulta:
$$
\begin{align*}
y_2'(x) &= y_1'(x).u(x) + y_1(x).u'(x) \tag{11} \\[1ex]
y_2''(x) &= y_1''(x).u(x) + y_1'(x).u'(x) + y_1'(x).u'(x) + y_1(x).u''(x) \\[1ex]
y_2''(x) &= y_1''(x).u(x) + 2 y_1'(x).u'(x) + y_1(x).u''(x) \tag{12}
\end{align*}
$$
Reemplazando las expresiones de (10), (11) y (12) en la (4) se tiene:
$$
[
\underbrace{[y_1''(x)u(x) + 2 y_1'(x)u'(x) + y_1(x)u''(x)]}_{\color{blue} y''} + a\underbrace{[y_1'(x)u(x) + y_1(x)u'(x)]}_{\color{blue} y'} + b\underbrace{[y_1(x)u(x)]}_{\color{blue} y} = 0
]
$$
Reordenando la anterior se tiene:
$$
[
u(x) \cdot \underbrace{[y_1''(x) + a.y_1'(x) + b y_1(x)]}_{\substack{\color{blue} = 0 \\ \text{\color{blue}\scriptsize El término encerrado por el corchete es cero, por ser} \\ \text{\color{blue}\scriptsize solución Gral. de la Ec. Dif. de } \color{blue} 2^\circ \text{\color{blue}\scriptsize Orden homogénea}}} + u'(x) \cdot [2 y_1'(x) + a y_1(x)] + u''(x) \cdot y_1(x) = 0
]
$$
$$
u´(x)\cdot[2y_1´(x)+ay_1(x)]+y_1(x)\cdot u´´(x)=0 \ \ \ (12.1)
$$
Analizando el corchete del primer término de la expresión (12.1), uno de los sumandos es $a\cdot y_1(x)$. Luego al derivar sólo la función $y_1 (x)$ con respecto a x, resulta:
$$
y_1(x)=e^{\frac{-ax}2}
$$
$$
y_1´(x)=\frac{-a}2 e^{\frac{-ax}2}
$$
Reemplazando las funciones $y_1$ e $y´_1(x)$ en la expresión (12.1) se tiene:
$$
u´(x)\cdot \{\not{2}[\frac{-a}{\not{2}}e^{\frac{-ax}2}] + ae^{\frac{-ax}{2}}\}+y_1(x)\cdot u´´(x)=0
$$
Finalmente queda:

$$
y_1(x).u´´(x)=0
$$
Como $y_1 = e^{\frac{-ax}{2}}$ es una Función Exponencial, por lo tanto $y_1(x)\neq 0 \Rightarrow$ la función de la derivada segunda $u´´(x)$ será:
$$
u´´(x)=0
$$
Cualquier función de x cuya derivada segunda sea nula es adecuada para la determinación de $y_2(x)$, por lo tanto se trata de la función lineal. La función más sencilla que cumple con esta condición es $u(x)=x$
Por ello, puede considerarse: 
$$
y_2(x)=y_1 (x).u(x)=e^{\frac{-ax}2}\cdot x
$$
La solución general de la ec. (4) quedará:
$$
y(x)=C_1 e^{\frac{-ax}2}+C_2 xe^{\frac{-ax}2}
$$
$$

\boxed{
\begin{array}{l}
y(x) = C_1 e^{r_1 x} + C_2 x e^{r_1 x} \\[1ex]
y(x) = e^{r_1 x} [C_1 + x C_2]
\end{array}
}

$$
$$
\begin{flalign*}
\text{Verificación:} && \frac{y_2(x)}{y_1(x)} &= x \neq \mathit{constante} &&
\end{flalign*}
$$

Por lo tanto ambas funciones constituyen una Base o Sistema Fundamental de soluciones de la EDO (4).

**<u>CASO 3</u>**: Raíces complejas conjugadas $(r_{1,2}= p \pm i \ q )$ 

Si analizamos las expresiones de raíces $r_1 \ y \ r_2$, los radicandos en los segundos sumandos presentes en las ec. (7.1) y (7.2), en este caso el radicando debe ser un número negativo, por lo que las raíces resultan complejas conjugadas.
Cuando:
$$
a^2<4b\Rightarrow a^2 -4ab < 0
$$
Por lo tanto:

$$
r_{1-2} = \frac{-a \pm i\sqrt{4b-a^2}}{2} \ \ \ \text{donde resultan ser} \ \ p=\frac{-a}2 \ \ \ y \ \ \ q=\frac{\sqrt{4ab-a^2}}{2}
$$
De acuerdo al desarrollo precedente se tienen las dos funciones que conforman la Base o Sistema fundamenta de soluciones de la ec. (4)
$$
y_1(x)=e^{\frac{-a+i\sqrt{4b-a^2}}{2}x}=e^{\frac{-ax}2}. e^{\frac{+i\sqrt{4b-a^2}}2x}=e^{px+iqx}\ \ \ (13)
$$
$$
y_2(x)=e^{\frac{-a-i\sqrt{4b-a^2}}{2}x}=e^{\frac{-ax}2}. e^{\frac{-i\sqrt{4b-a^2}}2x}=e^{px-iqx}\ \ \ (14)
$$
La solución general de la EDO de segundo orden lineal homogénea, en este tercer y último caso, queda de la siguiente manera:
$$
y(x)=C_1 y_1(x)+C_2y_2(x)
$$
$$
y(x)=C_1. e^{\frac{-ax}2}.e^{\frac{+i\sqrt{4b-a^2}}2x}+C_2.e^{\frac{-ax}2}.e^{\frac{-i\sqrt{4b-a^2}}2x} \ \ \ (15)
$$
En la expresión (15) se observa el producto entre una función exponencial con exponente real y otra función exponencial con exponente imaginario puro, en ambos sumandos del segundo miembro.

Recordando la Relación de Euler:
$$
e^{ix}=cos\ x + i\ sen \ x \ \ \ ; e^{-ix} = cos \ x - i \ sen\ x
$$
Y operando adecuadamente, se llega a la expresión final de la solución general buscada: 
$$
\boxed {y(x)=e^{px}[C_1 cos\ q \ x+C_2 sen\ q \ x]}
$$
La solución general es la combinación lineal de dos funciones trigonométricas circulares, gobernada por una función exponencial.
Verificación:

$$
\frac{y_2(x)}{y_1(x)}=\frac{e^{\frac{-ax}{2}}.e^{\frac{-i\sqrt{4b-a^2}}{2}x}}{e^{\frac{-ax}{2}}.e^{\frac{+i\sqrt{4b-a^2}}2x}}=e^{-i\sqrt{4b-a^2}}\neq constante
$$
Por lo tanto ambas funciones constituyen una Base o Sistema Fundamental de soluciones de la EDO indicada en la ec. (4).

### Estudio de la Ec. Dif. Lineal no homogénea

Se trata estudiar el caso en que $\textcolor{lightblue}{r(x)\neq 0 \forall x \in I} \Rightarrow$ queda la expresión (1)
$$
y´´(x)+f(x)y´(x)+g(x)y(x)=\textcolor{lightblue}{r(x)} \ \ \ (1)
$$
Y la EDO se denomina no homogénea

Una solución general de la ecuación (1) se obtiene mediante la determinación de la solución general de la EDO homogénea, en la que estarán presentes las dos constantes arbitrarias e irreductibles, a la que se le suma una solución particular de la EDO no homogénea que no contenga constante arbitraria.
Si denominamos $y_{gh}(x)$ es la solución general de la EDO homogénea y denominamos $y_{pc}(x)$ a la solución particular de la no homogénea (llamada también "completa") $\Rightarrow$ se puede escribir
$$
y(x)=y_{gh}(x)+y_{pc}(x) \ \ \ (2)
$$
Por lo tanto, derivando una y dos veces la anterior se tiene:
$$
y´(x)=y_{gh}´(x)+y_{pc}´(x) \ \ \ (3)
$$
$$
y´´(x)=y_{gh}´´(x)+y_{pc}´´(x) \ \ \ (4)
$$
Reemplazando las (2), (3) y (4) en la (1) se tiene:
$$
[y_{gh}´´(x)+y_{pc}´´(x)]+f(x).[y_{gh}´(x)+y_{pc}´(x)]+g(x).[y_{gh}(x)+y_{pc}(x)]=r(x)
$$
Reordenando la igualdad anterior queda:

$$
\textcolor{lightblue}{\underbrace{[y_{gh}´´(x)+f(x)y_{gh}´(x)+g(x)y_{gh}(x)]}_{=0}}+[y_{pc}´´(x)+f(x)y_{pc}´(x)+g(x).y_{pc}(x)]=r(x)
$$

El corchete destacada en color es nulo, porque es la EDO homogénea. Queda la expresión:
$$
[y_pc´´(x)+f(x)y_{pc}´(x)+g(x).y_{pc}(x)]=r(x)
$$
Lo que demuestra que la $y_{pc}(x)$ es la solución de la EDO no homogénea.

#### Método de coeficientes indeterminados

Es un método que nos permite determinar la solución particular de la EDO no homogénea (o completo), que sumada a la solución general de la homogénea nos dará la solución general final (2).
$$
y(x)=y_{gh}(x)+y_{pc}(x) \ \ \ (2)
$$
Consiste en ensayar, como solución particular, una función análoga a la función $\textcolor{purple}{r(x)}$ que aparece en el segundo miembro de (1), determinando cierto número de coeficientes que son incógnitas del problema;  de allí el nombre de "Coeficientes Indeterminados".

Es un método que puede aplicarse toda vez que la función r(x) se de carácter elemental, vale decir: polinomios, funciones exponenciales, funciones trigonométricas $(sen \ x, \ cos\ x)$ o combinaciones de las funciones indicadas.

### Método de Coeficientes Indeterminados

Para hallar $\textcolor{lightblue}{y_{pc}(x)}$ aplicamos las siguientes reglas:

**Primera Regla:** 

Si $r(x)$ es un polinomio de grado n en x $\Rightarrow$ se ensaya como solución particular otro polinomio de grado n en x, llamado $P_n(x)$.
Pero si **CERO** es raíz de orden 1 de la Ecuación Característica, entonces se ensaya como solución particular: 
$$
y_{pc}(x)=x\ P_n(x) 
$$
Generalizando $\textcolor{lightblue}{\text{si CERO es raíz de multiplicidad h}}$ de la Ecuación Característica, ensaya como solución particular.

$$
y_{pc}(x)= x^h P_n(x)
$$

**Segunda Regla:**
Si $r(x)$ es una función exponencial del tipo: $r(x)=A\ e^{ax} \Rightarrow$ se ensaya como solución particular otra función exponencial del tipo:
$$
y_{pc}=B \ e^{ax} \ \ \ \ \text{siendo B el coeficiente indeterminado a calcular }
$$
Pero si el coeficiente "a", del exponente de la función $r(x)$, es raíz de orden 1 de la Ec. Característica, entonces se ensaya como solución particular:
$$
y_{pc}(x)=x\ B \ e^{ax}
$$
Generalizando esta condición, si el coeficiente "a", es raíz de multiplicidad h de la Ec. Característica, ensaya como solución particular:
$$
y_{pc}(x)=x^h\ B \ e^{ax}
$$


 