---

---
------
## Dependencias
### Dependencias funcionales

Una dependencia funcional es una restricción que se establece entre dos conjuntos de atributos de una tabla de la BD.

Analizamos siempre primero el <mark style="background:#254">contexto</mark> para determinar la relación entre dos conjuntos.

No todos los datos tienen la misma relevancia, hay datos que se repiten ergo no necesariamente identifican lo que buscamos, por ej. una base de nombre, DNI, color. El dato mas relevante es el DNI ya que es único. 
Esto no funciona en todos los contextos, hay que contextualizarse para diseñar.

La dependencia que se estudia es cual es la importancia del dato que se estudia. 
Esto quiere decir, por ejemplo, que tu nombre depende del DNI, así como casi todos los datos: color de pelo, ojos, etc. 

Esto significa que los valores de **Y** de una tupla r
- dependen de los valores X,
- o están determinados por los valores de X,
- o bien, que los valores de X **determinan** de manera única (o **funcionalmente**) los valores de Y.
- También decimos que hay una dependencia funcional de X a  Y o que Y **depende funcionalmente** de X.

La abreviatura de dependencia funcional es **DF.** En una DF X $\rightarrow$ Y a X se lo denomina <mark style="background:#189d">determinante</mark> y a Y se lo denomina ==consecuente== 


Una dependencia funcional es una propiedad de la semántica o significado de los atributos. Los diseñadores de la BD utilizarán su comprensión de la semántica de los atributos de R (esto es, cómo se relacionan unos con otros) para especificar las dependencias funcionales que deben mantenerse en todos los estados de relación r de R


**EJEMPLO 1:**

Departamentos = (<u>nroDepto</u>, nombreDepto, cantEmpleados)
	* nroDepto $\rightarrow$ nombreDepto
	* nroDepto $\rightarrow$ cantEmpleados
	* nombre $\rightarrow$ cantEmpleados ????

		* Cuando si?
		* Cuando no?

nroDepto, es el candidato ya que ocupa menos espacio en memoria buscar a través de un numero, además es mas robusto a la hora de los errores.

**EJEMPLO 2:**

Empleados  = (<u>nroEmpl</u>, nombre, domicilio, teléfono)
	* nroEmpl $\rightarrow$ nombre
	* nroEmpl $\rightarrow$ domicilio
	* nroEmpl $\rightarrow$ teléfono

**EJEMPLO 3:**

EmpleadoEnProyecto = (<u>nroEmpl</u>, <u>nroProy</u>, horasTrabajadas, nombreEmpleado, nombreProyecto)
- (nroEmpl, nroProy) $\rightarrow$ horasTrabajadas
- nroEmpl $\rightarrow$ nombreEmpleado
- nroProy $\rightarrow$ nombreProyecto

Si continuamos el análisis de la transparencia anterior, por ser CP:
- (nroEmpl, nroProy) $\rightarrow$ nombreEmpleado
- (nroEmpl. nroProy) $\rightarrow$ nombreProyecto

### Dependencia funcional completa

Si A y B son atributos de una relación r, B depende funcionalmente de manera completa de A, di B depende de A pero de ningún subconjunto de A.

En el ejemplo anterior
- (nroEmpl, nroProy) $\rightarrow$ horasTrabajadas
- nroEmpl $\rightarrow$ nombreEmpleado
horasTrabajadas depende de nroEmpl y nroProy pero estos últimos no depende de ningún subconjunto de horasTrabajas, lo mismo con nombre.

### Dependencia funcional parcial

A $\rightarrow$  B es una dependencia funcional parcial si existe algún atributo que puede eliminarse de A y la dependencia continúa verificándose.
- (nroEmpl, nroProy) $\rightarrow$ horasTrabajadas
- nroEmpl $\rightarrow$ nombreEmpleado
La primera es una dependencia <font color="#ffr04">PARCIAL</font>

### Dependencia funcional transitiva

Dados A, B y C atributos de una relación tales que A $\rightarrow$ y B $\rightarrow$ C entonces decimos que C depende transitivamente de A a través de B.

Retomemos la tabla: 
Empleados = (idEmpleado, nombre, salario, fechaIngreso, idDepto, nombreDepto)

- idEmpleado $\rightarrow$ nombre, salario, fechaIngreso, idDepto, nombreDepto
- idDepto $\rightarrow$ nombreDepto

En este ejemplo
- A = idEmpleado
- B = idDepto
- C = nombreDepto
---------
## Normalización

### Definición 

Técnica de diseño de BD que comienza examinando las relaciones que existen entre los atributos (dependencias funcionales). La normalización identifica el agrupamiento óptimo de estos atributos, con el fin de identificar un conjunto de relaciones que soporten adecuadamente los requisitos de datos de la organización.

### Propósito

Producir un conjunto de relaciones (tablas) con una serie de propiedades deseables partiendo de los <u>requisitos de datos</u> de una organización

---
La normalización es un mecanismo que permite que un conjunto de tablas, que integran una BD, cumpla una serie de propiedades deseables. Estas propiedades consisten en evitar:

- Redundancia de datos:
- Anomalías de actualización 
- Pérdida de integridad de datos

#### Redundancia y anomalías de actualización

- El objetivo principal es minimizar la redundancia de información
- Por ej., cuando generamos una nueva tabla con las CP de las dos entidades que relaciona, hay información repetida. Sin embargo, esta redundancia es necesaria para representar la relación en el modelo físico.
- Existen otros caso de redundancias <<no deseadas>>, que generan anomalías. Se clasifican en:
	1. Anomalías de inserción
	2. Anomalías de borrado
	3. Anomalías de modificación
-  Anomalías de inserción: Supongamos que se dispone de la siguiente tabla:
	Empleados = (<u>idEmpleado</u>, nombre, salario, fechaIngreso, idDepto, nombreDepto)
- Si se agrega un nuevo empleado, se debe indicar toda la información, incluyendo repetir el nombre del depto. donde trabaja, aunque sea un depto. ya existente en la tabla. Se debe tener especial cuidado en escribir el nombre del depto. De la misma forma como fue ingresado antes
 ![[Pasted image 20260407115410.png]]

- Anomalías de borrado: Para el mismo ejemplo anterior, borremos Ema Dru. Al borrar esa tupla, en la misma operación se borra información del departamento donde trabaja, y como es la única empleada registrada para ese depto., se pierde a Ventas como departamento de la organización.
- Anomalías de modificación: Continuando con el mismo ejemplo, supongamos que el depto. de Electrónica y Computación pasa a llamarse depto. de Tecnología. Deberían cambiarse en todas las tuplas.


- El proceso de normalización, tal y como fue propuesto en un principio por Codd, hace pasar un esquema de relación por una serie de comprobaciones para "certificar" que satisface una determinada **forma normal.** 
- Los esquemas de relación insatisfactorios que no cumplan con las **pruebas de formas normales**, se descomponen en esquemas de relación más pequeños que cumplan esas pruebas y que, por consiguiente, cuentan con las propiedades deseables.


La **forma normal** de una relación hace referencia a la condición de forma más alta que cumple y de este modo, indica el grado al que ha sido normalizada.
Los diseñadores de BD no tienen que normalizar hasta la forma más alta posible. Las relaciones pueden dejarse en formas normales inferiores por razones de rendimiento.

#### Proceso $\rightarrow$ incremental $\rightarrow$ cada vez más restrictivo

- Comienza con la BD de forma NO normal.
- A mediad que se avanza, las relaciones (tablas) tienen un formato cada vez más restringido y son menos vulnerables a anomalías de actualización
- En general, 1 FN se aplica siempre
- El resto puede ser opcional, las 2FN y 3FN normalmente se aplican también.

**Repasando**
Una **clave** es el conjunto de uno o más atributos que cumple con las propiedades de unicidad e irreductibilidad. Pueden haber más de una y en este caso, cada una de ellas se denomina **clave candidata**. Una de las claves candidatas se designa arbitrariamente como **clave primaria (PK)**.
Un atributo de una relación R se denomina **atributo primo** de R si es miembro de alguna clava candidata de R. Un atributo es **no primo** si no es miembro de ninguna clava candidata.
En la relación **EmpleadoEnProyecto** (<u>DNI</u>, <u>númeroProy</u>, horas, nombreEmp, nombreProy, localizaciónProy), tanto DNI como númeroProy son atributos primos y el resto no.

### Primera Forma Normal (1FN)

- Establece que el dominio de un atributo debe incluir sólo valores atómicos (simples, indivisibles) y que el valor de cualquier atributo en una tupla debe ser un valor individual proveniente del dominio de ese atributo.
- Un modelo estará en 1FN si para toda relación r del modelo (tabla) cada uno de los atributos que la forman es si y solo sí monovalente.

**EJEMPLO:** ¿La siguiente tabla está en Primera forma?
Personas = (<u>DNI</u>, nombre, domicilio, códigosTitúlos)

Se observa que el atributo títulos es polivalente. La solución es sacar el atributo polivalente y armar otra tabla.
Posee = (<u>DNI</u>, códigoTitúlo)

Por lo tanto, la solución es:
Personas = (<u>DNI</u>, nombre, domicilio)
Posee = (<u>DNI</u>, <u>códigoTitúlo</u>)

### Segunda Forma Normal (2FN)

- Una tabla que tenga atributos que dependan parcialmente de otro no está en 2FN.
- Un modelo está en 2FN sí y solo sí está en 1FN y para toda relación r (tabal) del mismo no existen dependencias parciales.

**EJEMPLO:** La siguiente relación está en 1FN, pasar a 2FN
Alquileres = (idCliente, idPropiedad, nombreCliente, nombrePropietario, montoAlquiler, fechaInicio, duración)

Buscamos dependencias parciales:
- idCliente $\rightarrow$ nombreCliente
- idPropiedad $\rightarrow$ nombrePropietario

**SOLUCIÓN**
- Clientes = (<u>idCliente</u>, nombreCliente)
- Propiedades (<u>idPropiedad</u>, nombrePropietario)
- Alquileres = (<u>idCliente</u>, <u>idPropiedad</u>, montoAlquiler, fechaInicio, duración)

### Tercera Formal Normal (3FN)

- Una tabla que tenga atributos que dependan transitivamente de otro no está en 3FN.
- Un modelo está en 3FN sí y solo sí está en 2FN y para toda relación r (tabla) del mismo no existen dependencias transitivas. 

**EJEMPLO:** La siguiente relación está en 2FN, pasar a 3FN
Empleados = (<u>dniEmpleado</u>, nombreEmpleado, nroDepto, nombreDepto)

Buscamos dependencias transitivas:
- dniEmpleado $\rightarrow$ nroDepto y nroDepto $\rightarrow$ nombreDepto

**SOLUCIÓN**
- Empleados = (<u>dniEmpleado</u>, nombreEmpleado, nroDepto)
- Departamentos = (<u>nroDepto</u>, nombreDepto)

**EJERCICIO 3:**

1FN)

Factura = (<u>numeroFactura</u>, fecha, idCliente, domCliente, telCliente, nombreCliente)
Ítems = (<u>numeroFactura</u>, <u>idProducto</u>, descripciónProducto, cantidad, precioUnitario)

2FN) "Factura la cumple xq hay una sola clave"

DP = idProducto $\rightarrow$ descripciónProducto, precioUnitario
Factura(=)
Ítems(<u>numeroFactura</u>, <u>idProducto</u>, precioUnitarioFactura, cantidad)
Productos = (<u>idProducto</u>, descripciónProducto, precioUnitario)

3FN)

Factura(numeroFactura, Fecha, idCliente)
Cliente(idCliente, domCliente, telCliente, nomCliente)
Ítems(=)
Productos(=)

**EJERCICIO 4**
 1FN) 
 Cursada = (<u>materiaCodigo</u>, <u>alumnoLegajo</u>, <u>Cuatrimestre</u>, <u>añoAcademico</u>, matNombre, deptoCodigo, deptoNombre, alumnoApellido, alumnoNombre, telefonos, cursadaResultado)
 Telefonos(<u>idTel</u>, numeroTelefono)
Alumno = (<u>alumnoLegajo</u>, nomAlum, apellidoAlumno, domicilioAlum, nroDoc)
Alumnoxtel (<u>idTel</u>, <u>alumnoLegajo</u>)

2FN)
DP = matCodigo -> matNombre
     deptoCodigo -> nombreDepto

Materias = (<u>matCodigo</u>, matNombre, <u>cuatrimestre</u>, <u>deptoCodigo (foránea)</u>)
Departamentos = (<u>deptoCodigo</u>, deptoNombre)
Cursadas = (<u>materiaCodigo</u>, <u>alumnoLegajo</u>, <u>añoAcademico</u>, cursadaResultado)
Telefonos (=)
Alumnos (=)
Alumnoxtel (=)

3FN)
Cuatrimestre(<u>ID</u>, nombre)
Materias = (<u>matCodigo</u>, matNombre, <u>IDC(foránea)</u>, <u>deptoCodigo (foránea)</u>)










