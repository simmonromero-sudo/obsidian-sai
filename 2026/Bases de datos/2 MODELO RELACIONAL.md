

El **modelo relacional** es uno de los modelos de datos más utilizados para el diseño e implementación de bases de datos. Fue propuesto por Edgar F. Codd en 19700 y se basa en la organización de datos en estructuras llamadas **relaciones**, que pueden entenderse como tablas.
En este modelo, la información se representa mediante **filas** y **columnas**: 
- Cada **fila** (tupla o registro) representa una instancia de la cantidad
- Cada **columna** (atributo) representa una característica de esa entidad.

#### Permite

- Organizar grande volúmenes de datos de forma eficiente.
- Garantizar la integridad y consistencia.
- Facilitar la consulta mediante lenguaje SQL.

Suele utilizarse como paso posterior al modelo Entidad-Relación (ER):

- ER $\rightarrow$ diseño conceptual
- Relacional $\rightarrow$ implementación lógica

Este modelo propone una forma simple, estructurada y formal de representar datos, donde:

- Los datos se almacenan en tablas
- Las tablas se relacionan entre sí mediante claves
- Se minimiza la redundancia y se mejora la consistencia de la información


### Los componentes básicos son:

- **Relación** (tabla): conjunto de datos del mismo tipo
- **Tupla** (fila): registro individual
- **Atributo** (columna): propiedad de los datos
- **Dominio**: conjunto de valores posibles de un atributo

Cada tabla representa un conjunto de datos sobre una determinada entidad del mundo real, y es fundamental poder **identificar de manera única cada uno de sus tuplas.** Para lograr esto, se utiliza la **clave primaria** (PK).
La **PK** es un atributo, o un conjunto de atributos, que permite distinguir de forma única cada fila adentro de una tabla.
Pueden existir varias alternativas posibles para identificar de manera única a los registros. A estos atributos o conjuntos de atributos se los denomina claves candidatas.

Cuando hay varias claves candidatas, el diseñador debe elegir una de ellas como **PK**. Esta elección no es arbitraria: generalmente se selecciona aquella que sea más simple, más estable en el tiempo (es decir, que no cambie) y que tenga un significado claro.
Las demás claves candidatas que no se eligen como primarias se denominan claves alternativas.
Los DBMS actuales presentan una alternativa de tratamiento para las **PK**, a través del uso de un tipo de dominio denominado Autoincremental. El usuario sólo tiene permitida la operación de consulta sobre la **PK** autoincremental, no la puede generar, borrar ni modificar.

Por otro lado, en una base de datos relacional no solo interesa identificar registros dentro de una tabla, sino también **relacionar información entre distintas tablas.** Aquí es donde aparece el concepto de **clave foránea (FK)**.
Una **FK** es un atributo, o conjunto de atributos, en una tabla que hace referencia a la clave primaria de otra tabla. Su función es establecer un vínculo entre ambas, permitiendo representar relaciones entre entidades.

Por ejemplo, en una tabla de pedidos, puede existir un atributo que indique el cliente que realizó el pedido. Ese atributo será una **FK** que referencia a la **PK** de la tabla de clientes.
De esta manera, la **PK** garantiza la identificación única de los datos dentro de una taba, mientras que la **FK** permite conectar esos datos con otros, asegurando la coherencia y la integridad de la información en toda la base de datos.

#### Conversión de entidades

El proceso de conversión para obtener el esquema físico de una BD comienza con el análisis de las entidades definidas en el modelo de entidad-relación.
El proceso de conversión muestra que cada una de las entidades fuertes y débiles definidas deben transformarse en una tabla del modelo.
El nombre de la tabla suele coincidir con el nombre de la entidad, y sus atributos simples y monovalorados pasan a ser las columnas de la tabla.

![[Pasted image 20260525190847.png]]

momento $\in$ {mañana, tarde, noche, indiferente}

El proceso de conversión genera dos tablas, con las **PK** subrayadas:

Amigo = (<u>DNI</u>, nombre, apellido, email)
Bar = (<u>nombre</u>, dirección)

#### Conversión de atributos compuestos

Estos atributos no se mantienen como una única columna sino que se descomponen en sus componentes básicos, y cada uno de ellas se convierte en un atributo simple dentro de una tabla

![[Pasted image 20260525191115.png]]

Alumno = (<u>nroAlumno</u>, nombre, apellido, DNI, domicilio_calle, domicilio_numero, domicilio_localidad)


#### Conversión de atributos multivalorados


Se crea una nueva tabla independiente, que contiene: 
- El atributo multivaluado
- La **PK** de la entidad a la que pertenece, que actúa como **FK**

La **PK** de la nueva tabal se forma con todos sus atributos.

![[Pasted image 20260525191357.png]]

Empleado = (<u>legajoEmpleado</u>, nombre, apellido, DNI)
Hijo = (<u>legajoEmpleado, nombreeHijo</u>)

#### Conversión de atributos derivadas

En general, estos atributos no se almacenan físicamente e la base de datos, ya que hacerlo podría generar inconsistencias. En su lugar, se calculan cuando es necesario mediante consultas o procesos.
La decisión de almacenar o no un atributo derivado también responde a criterios de diseño. En algunos casos, puede optarse por almacenarlo para mejorar el rendimiento de las consultas o evitar cálculos repetitivos, especialmente cuando el valor se utiliza con frecuencia.
Por este motivo, durante la conversión al modelo relacional, los atributos derivados suelen omitirse, aunque su inclusión dependerá de las necesidades específicas del sistema  de las decisiones de diseño adoptadas.

#### Conversión de relaciones

Participación 0...1 - 1...1

![[Pasted image 20260525191830.png]]

La clave primaria de Usuario se almacena en la tabla de Canal YouTube como un atributo. El atributo id_usuario que se añade en la tabla Canal_YouTube es una clave ajena o foreign key (FK) de la tabla Usuario.

Usuario = (<u>idUsuario</u>, nombre, apellido, email, password)

Canal_YouTube = (<u>id</u>, fecha_creacion, descripción, <mark style="background:#9254de">idUsuario</mark>)

**Participación 1..1 - 1..1**
![[Pasted image 20260525192232.png]]

En este caso, como la participación de las dos entidades es 1..1 podemos resolverlo de tres formas.

1. La **PK** de Presidente se almacena en la tabla de País como un atributo y pasa a ser una **FK**
	Presidente = (<u>DNI</u>, nombre, apellido)
	País = (<u>idPais</u>, nombre, cantidad_habitantes, DNI)
2. La **PK** de País almacena en la tabla Presidente como un atributo y pasa a ser **FK**
	País = (<u>idPais</u>, nombre, cantidad_habitantes)
	Presidente = (<u>DNI</u>, nombre, apellido, País)
3. Unir ambas entidades en una sola tabla.
	País = (<u>idPais</u>, nombre_pais, cantidad_habitantes, DNI_Presidente, nombre_presidente, apellido)

¿Cómo elegir la mejor opción?

Depende del contexto.

- Si las entidades tienen sentido independiente $\rightarrow$ usar FK
- Si están fuertemente ligados $\rightarrow$ fusionarlas
- Si una "depende más" de la otra $\rightarrow$ ubicar ahí la FK

**Participación 0...1 - 0...1**

En este tipo de relaciones, como ambas participaciones son opcionales, el modelo relacional debe permitir ausencia de vínculo, ya sea mediante claves foráneas nulas o mediante una tabla intermedia que registre únicamente las asociaciones existentes. 

**Participación 1...1 - 0...N (1...N)**

![[Pasted image 20260525193156.png]]

En este caso se almacena la clave primaria en la tabla con participación 1..1

Usuario = (<u>idUsuario</u>, nombre, apellido, DNI, email, password)
Video = (<u>idVideo</u>, nombre, descripción, duración, idUsuario)

**Participación 0...N - 0...N (1..N)**

![[Pasted image 20260525193340.png]]

En este caso se crea una nueva tabla donde se almacenan las claves primarias de las dos entidades que participan en la relación. Las claves primarias en las entidades en conjunto serán la clave primaria de la nueva tabla. Si la relación contiene algún atributo, se deberán añadir a la nueva tabla.

Alumno  = (<u>nroAlumno</u>, nombre, apellido, DNI)
Examen_teórico = (<u>idExamen</u>, fecha) 
Alumno_hace_examen_teórico = (<u>nroAlumno, idExamen</u>, nota)

Habrá casos donde los atributos de la relación también formarán parte de la clave primaria de la nueva tabla. Estos casos aparecerán cuando en la relación existan atributos de tipo fecha y sea necesario almacenar un histórico de las relaciones entre las dos entidades en función de las fechas. Estos casos también pueden resolverse añadiendo un nuevo identificador de tipo entero con autoincremento en lugar de utilizar una clave primaria compuesta por varias columnas.

![[Pasted image 20260525193954.png]]

¿Cómo quedará formada la **PK** para la tabla **Suministra** para poder permitir que un proveedor suministre piezas con el mismo id en fechas diferentes?

**Relaciones de grado 3**

![[Pasted image 20260525194102.png]]

En este caso creamos una tabla. La **PK** de la nueva tabla estará formada por las tres claves de las entidades que participan en la relación.

### Agregaciones

El proceso de conversión puede entenderse en dos etapas.
En primer lugar, se transforma la relación que está siendo agregada como si fuera una relación común. Esta tabla incluirá: 
- Las claves primarias de las entidades que participan en la relación (como claves foráneas)
- Los atributos propios de la relación

De esta manera, la relación original queda materializada como una tabla en el modelo relacional.

En segundo lugar, la relación externa (la que en el modelo ER se vincula con la agregación) se transforma utilizando esa nueva tabla como referencia. Es decir, la tabla que representa la agregación pasa a comportarse como una entidad más, y se la relaciona con la otra entidad involucrada mediante claves foráneas.

![[Pasted image 20260525194529.png]]

Empleado = (<u>legajo</u>, nomApe)
Proyecto = (<u>número</u>, fechaInicio)
Máquina = (<u>código</u>, marca)
Trabaja = (<u>legajo, número</u>)
Utiliza = (<u>legajo, npumero, codigo</u>, n_horas)


### Generalizaciones/ Especializaciones

Básicamente, hay tres opciones para tratar una especialización.

1. Eliminar las subentidades, dejando sólo la entidad padre a la cual se le incorporan todos los atributos de sus hijos. Cada uno de ellos deberá ser no obligatorio.
	![[Pasted image 20260525194941.png]]

2. Eliminar la entidad padre, dejando sólo las subentidades. Con esta solución, lo atributos del padre deberán incluirse en cada uno de los hijos.
	![[Pasted image 20260525194952.png]]

3. Dejar todas la entidades de la jerarquía, convirtiéndolas en relaciones uno a uno entre el padre y cada uno de los hijos.
	![[Pasted image 20260525195002.png]]

Las tres soluciones no son aplicables en todos los casos.
La cobertura es la que determina la solución viable en cada caso.
Si la cobertura fuese parcial, la segunda solución no sería aplicable debido a que la conversión generaría un modelo no equivalente ya que se perdería información.

Si se analiza la cobertura superpuesta, la segunda solución no resulta práctica. Algunos elementos del padre se repiten en varios hijos, esto significa que se deberá repetir información en las subentidades generadas.
Se puede afirmar que la tercera alternativa de solución es la que capta mejor la esencia de la herencia y, por ende, la que resulta más interesante aplicar. Sin embargo, esta solución es la que genera mayor número de entidades y relaciones en el modelo final. Esto podría significar, a futuro, problema de performance en la utilización de la BD.

![[Pasted image 20260525195337.png]]

En este caso sería viable aplicar la opción 2.

#### Diagrama estilo "patas de gallo"

Es una mezcla entre los esquemas relacionales y los entidad/relación.
La cardinalidad máxima * se dibuja con las famosas patas de gallo, la cardinalidad mínima de tipo cero con un círculo y la cardinalidad de tipo uno con una barra vertical ![[Pasted image 20260525195505.png]]

#### Integridad referencial (IR)

Es una regla del modelo relacional que plantea restricciones entre tablas para garantizar la consistencia de los datos entre tablas relacionadas.
Se basa en el uso de claves foráneas, que son atributos en una tabla que hacen referencia a la PK de otra tabla.
Establece que todo valor de una FK debe corresponder a un valor existente de la PK en la tabal referenciada, o bien ser nulo (si la relación lo permite)

Facturas = (<u>nroFactura</u>, fecha, monto, nroCliente (FK))

Clientes = (<u>nroCliente</u>, nombre, dirección)

nroCliente, permite establecer IR entre las tablas


#### Integridad referencial

Cada DBMS presenta escenarios de definición de IR diferentes, pero en general cuando se la define se puede optar entre:
- Restringir la operación: si se intenta borrar o modificar una tupla que tiene IR con otra, la operación se restringe y no se puede llevar a cabo
- Realizar la operación (en cascada): si se intenta borrar o modificar una tupla donde está definida la PK de la IR, la operación se realiza en cadena sobre todas las tuplas de la tabla que tiene definida la FK
- Establecer la K en nulo: si se borra el valor del atributo que es PK, sobre la FK se establece valor nulo. Esta opción no es muy utilizada ni está presente en todos los DBMS
- No hacer nada: en este caso se le indica al DBMS que no es necesario controlar la IR. esta opción es equivalente a no definir restricciones de IR.
- 

