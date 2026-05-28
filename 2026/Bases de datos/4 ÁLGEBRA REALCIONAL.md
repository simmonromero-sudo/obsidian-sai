Un modelo de datos debe incluir un conjunto de operaciones para manipular la base de datos junto con los conceptos necesarios para la definición de su estructura y restricciones.
El conjunto de operaciones básicas del modelo relacional es el **álgebra relacional,** el cual permite al usuario especificar las peticiones fundamentales de recuperación.
El resultado de una recuperación es una nueva relación, la cual puede estar constituida por una o más relaciones.
Por consiguiente, las operaciones de álgebra producen nuevas relaciones que pueden ser manipuladas más adelante usando operaciones del mismo álgebra.
Una secuencia de operaciones de álgebra relacional conforma una expresión de álgebra relacional, cuyo resultado será también una nueva relación a la base de datos (o una petición de recuperación).
El álgebra relacional es muy importante por varias razones:

1. Proporciona un fundamento formal para las operaciones del modelo formal.
2. Se utiliza como base para la implementación y optimización de consultas en los RDBMS (Sistemas de administración de bases de datos relacionales). 
3. Algunos de sus conceptos se han incorporado al lenguaje estándar de consultas SQL para los RDBMS.

Aunque ninguno de los RDBMS comerciales actuales proporciona una interfaz para las consultas de álgebra relacional, las funciones y operaciones centrales de cualquier sistema relacional están basadas es estas operaciones.
Las operaciones pueden dividirse en dos grupos. Uno de ellos incluye el conjunto de operaciones de la teoría matemática de conjuntos, las cuales son aplicables porque cada relación está definida de modo que sea un conjunto de tuplas en el modelo relacional formal.

- Estas operaciones incluyen UNIÓN, INTERSECCIÓN, DIFERENCIA Y PRODUCTO CARTESIANO.
- El otro grupo está constituido por las operaciones desarrolladas específicamente para las bases de datos relacionales, como la SELECCIÓN, PROYECCIÓN y otras.
<mark style="background:#fd0">Toda operación sobre una o más relaciones devuelve una relación</mark>

### Tipos de Operadores Básicos
**Unarios**: operan sobre una sola relación
- Selección($\sigma$)
- Proyección($\Pi$)
- Renombre($\rho$)

**Binarios**: operan sobre dos relaciones:
- Producto cartesiano ($X$) 
- Unión ($U$)
- Diferencia (-)

### Base de datos Empresa (EJEMPLO)

**Empleados** = (<u>DNI</u>, Nombre, Apellido, FechaNac, Dirección, Sueldo DNI Supervisor, Depto)
- DNISupervisor FK de Empleados
- Depto FK Departamentos 
**Departamentos** = (<u>NroD</u>, Nombre, DNIdirector, FechaIngresoDir)
- DNIDirector FK de Empleados
**UbicaciónDeptos** = (<u>NúmeroDepto, LocalidadD</u>)
- NúmeroDepto FK de Departamentos 
**Beneficiarios** = (DNIemple, DNIBenef, NombreBen, Relación)
- DNIemple FK de Departamentos
**TrabajaEn** = (DNIemple, NumProy, Horas)
- DNIemple FK de Empleados
- NumProy FK de Proyectos
**Proyectos** = (NroP, Nombre, LocalidadP, NumDeptoP)
- NumDeptoP FK de Empleados

#### Posible estado de la BD Empresa
![[Pasted image 20260416090754.png]]

### Selección ($\sigma$)

- Se emplea para seleccionar un subconjunto de las tuplas que satisfacen un predicado.
- Se puede considerar esta operación como un filtro que mantiene sólo las tuplas que satisfacen una determinada condición.
$$
\sigma_p(Relación)
$$
**EJEMPLO:** obtener los empleados del departamento 4 o cuyo salario sea mayor a 6000


```
σ_(Depto = 4) or (Sueldo > 6000)
```

### Proyección ($\Pi$)
- Permite presentar los atributos especificados de una relación y no presentar el resto.
- Esta operación selecciona ciertas columnas de la tabla y descarta otras.
$$
\Pi_{atributos}(Relación)
$$
**EJEMPLO:** Listar nombre, apellido y sueldo de cada empleado

$$
\Pi_{nombre, \ apellido, \ sueldo}\ \  (Empleados)
$$
- Listar los sueldos que da la empresa
$$
\Pi_{sueldo} \ \ (Empleados)
$$

### Renombrar ($\rho$)

- Define un alias para una relación.
- Útil para evitar ambigüedades cuando una relación aparece más de una vez en una consulta.
- Esta operación aplicada a una relación R de grado  n aparece denotada de cualquiera de estas tres formas:
	$\rho_s$ (Relación)
	$\rho_{s(B1, B2, ..., Bn)}$ (Relación)
	$\rho_{B1, B2,...,Bn}$ (Relación)

Donde S es el nombre de la nueva relación y $(B_1,B_2,....,B_n)$ son los nuevos atributos.

**EJEMPLO:** Renombrar la tabla UbicaciónDeptos con el alias Ubicación
$$
\rho_{Ubicación}\ \ (UbicaciónDeptos)
$$
**EJEMPLO:** Renombrar los atributos de la tabla UbicaciónDeptos con los valores A1 y A2.
$$
\rho_{A1, A2}\ \ (UbicaciónDeptos)
$$
### Producto Cartesiano (X)

- El producto cartesiano es una operación que, a partir de dos relaciones vincula cada tupla de una de las relaciones con cada tupla de la otra relación.
- La operación aplicada es, por si misma, absurda. Es útil cuando va seguida por una selección que correlacione los valores de los atributos procedentes de las relaciones componentes.
$$
RXS
$$
- Número de columnas de R x S = Cols. e R + Cols. de S
- Número de tuplas de R x S = Tuplas de R * Tuplas de S
- Para evitar ambigüedades: Usar sintaxis tabla.columna

**EJEMPLO:** Combinar la relación Departamentos con la relación Proyectos 
$$
Departamentos\ \ X \ \ Proyectos
$$
![[Pasted image 20260416092956.png]]

**EJEMPLO:** Obtener los nombres de los proyectos correspondientes para cada NI de director.

$$
\Pi_{Departamentos.DNIdirector,\ Proyectos.Nombre}{\sigma_{Departamentos.NroD=Proyectos.NumDeptoP}}^{(Departamentos \ \ X \ \ Proyectos)}
$$
![[Pasted image 20260416093342.png]]

### Unión (U)

- Equivale a la unión matemática de conjuntos.
- Las tuplas repetidas son eliminadas.
- Las relaciones a unir deben ser compatibles.

Igual numero de atributos
Dominios iguales dos a dos

A U B


**EJEMPLOS:** Obtener los nombres de personas que aparecen en la empresa

$$
(\Pi_{Nombre}(Empleados))\ \ U \ \ (\Pi_{NombreBen}(Beneficiarios))
$$

### Diferencia (-)
- Equivale a la diferencia matemática de conjuntos
- Incluye tuplas que están en una relación pero no en la otra.
R - S

- R - S incluye las tuplas que están en R y no están en S.

![[Pasted image 20260416093833.png]]

**EJEMPLO:** Nombres de beneficiarios que no son nombres de empleados.

$$
(\Pi_{NombreBen}(Beneficiarios)) \ - \ (\Pi_{Nombre}(Empleados))
$$

## Operaciones adicionales

- Producto natural $(\bowtie)$
- Intersección $(\cap)$
- Asignación $(\leftarrow)$
- División $(\div)$

## Producto Natural $(\bowtie)$

- Combina los elementos de la primera relación que se relacionan con los elementos de la segunda relación.
- Es una reunión con el operador de igualdad para combinar los atributos comunes de las relaciones.
- Se fusionan automáticamente las columnas con el mismo nombre.
- No especifica explícitamente se hace en base a los campos comunes.

$$
A \bowtie B
$$
**EJEMPLO:** Obtener el nombre y apellido del director de cada departamento

$$
\Pi_{Departamentos.NroD, Empleados.Nombre, Empleados.Apellido}(Departamentos) \bowtie
$$

## Intersección ($\cap$)

- Equivale a la intersección matemática de conjunto.
- Incluye tuplas que están en R y S.

**EJEMPLO:** Nombres de empleados que también son nombres de beneficiarios.

$$
(\Pi_{Nombre}(Empleados)) \ \cap \ (\Pi_{NombreBen}(Beneficiarios))
$$
### Asignación ($\leftarrow$)

- Crea una nueva relación a partir de otra.
- Lo que se asigna puede ser una relación existente o el resultado de una operación.

$$
Nueva \ \leftarrow \ Expresión \ de \ AR
$$
### División ($\div$)

- Retorna aquellos elementos de la primera relación que se relacionan con todos los elementos de la segunda relación.
- $A\div B$ retorna los elementos de A que se relacionan con todos los elementos de B, donde las columnas de B deben estar incluidas en las columnas de A.

**EJEMPLOS:** Conocer los nombres de los alumnos que cursan todas las materias obligatorias

$$
Inscripción \ \div \ Materias\_obligatorias
$$
### Actualizaciones:

- Altas_ a través de la operación de unión (U) y la operación de Asignación $(\leftarrow)$ 
$$
\textcolor{red}{Inscripción \leftarrow Inscripción \ U \ {('Luis','SO'),('Ema', 'IA')}}
$$
- Bajas: a través de la operación de diferencia (-) y la operación de Asignación.

$$
\textcolor{red}{R \leftarrow R-\sigma_{condición}(R)} 
$$
- Modificación: Se realiza combinando selección, proyección, unión y diferencia. Se construye como:
$$
\textcolor{red}{Relación \leftarrow(Relación-tuplas\ viejas \ U \ tuplas nuevas)}
$$

  
