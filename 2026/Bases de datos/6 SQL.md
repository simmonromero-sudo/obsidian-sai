### Tipos de datos

**Numéricos exactos**

| bigint  | numeric    |
| ------- | ---------- |
| bit     | smallint   |
| decimal | smallmoney |
| int     | tinyint    |
| money   |            |

Numéricos aproximados

| float | real |
| ----- | ---- |

**Fecha y hora**

| date      | datetimeoffset |
| --------- | -------------- |
| datetime2 | smalldatetime  |
| datetime  | time           |
**Cadenas de caracteres**

| char | varchar |
| ---- | ------- |
| text |         |
**Cadenas de caracteres Unicode**

| nchar | nvarchar |
| ----- | -------- |
| ntext |          |
**Cadenas binarias**

| binary | varbinary |
| ------ | --------- |
| image  |           |
**Otros tipos de datos**

| cursor      | timestamp        |
| ----------- | ---------------- |
| hierarchyid | uniqueidentifier |

| Tabla       | Tipos espaciales |
| ----------- | ---------------- |
| sql_variant | xml              |
### Sentencias de creación y eliminación

**Crear BDD**
La creación de bases de datos directamente desde la línea de comando, puede tener un sinnúmero de opciones, pero lo usual, a niveles básicos con escribir:


```
CREATE DATABASE [NombreBaseDatos];
```

Esta sentencia, dejará los setos posibles en sus valores por defecto, lo que en principio no nos causará inconvenientes, y cuyos valores y parámetros podremos configurar y modificar a futura desde código, como desde el entorno gráfico SSMS.

#### Crear tabla

La sentencia básica para la creación de tablas se puede definir como:


```
CREATE TABLE NombreTabla;

	(Campo1 int PRIMARY KEY NOT NULL
	Campo2 varchar(25) NOT NULL,
	Campo3 money NULL,
	...
	CampoN text NULL)
GO

```

**Adicionar columna**
Una tabal se puede modificar desde código con la sentencia ALTER TABLE de la siguiente manera


```
ALTER TABLE NombreTabla ADD column_b VARCHAR(20) NULL, column_c INT NULL;
```

**Quitar columna**


```
ALTER TABLE dbo.doc_exb DROP COLUMN column:b;
```

**Eliminar tabla**


```
DROP TABLE NombreTabla;
```

### Sentencias sobre los datos


**Agregar datos**


```
INSERT INTO table 
(column1, column2, ... ) 
VALUES 
(expression1, expression2, ... ), 
(expression1, expression2, ... ), 
...; 
INSERT INTO table 
(column1, column2, ... ) 
SELECT expression1, expression2, ... 
FROM source_table 
[WHERE conditions];

```

**Modificar datos**


```
SET { column_name = { expression | NULL } } [ ,...n ]   
[ FROM from_clause ]   
[ WHERE <search_condition> ]    
[ OPTION ( LABEL = label_name ) ]   
[;]
```

**Eliminar datos**


```
DELETE  
[ FROM [database_name . [ schema ] . | schema. ] table_name ]    
[ WHERE <search_condition> ]    
[ OPTION ( <query_options> [ ,...n ]  ) ]   
[; ]  
```


### Sentencias y cláusulas de consulta

**Seleccionar filas**


```
SELECT Campo1, Campo2, Campo3, ... , CampoN FROM NombreTabla
```

Permite la utilización del operador * que representa {TODO}. Puede utilizarse solo o acompañado del nombre de la tabla {NombreTabla * }

**La cláusula WHERE**

Aplica criterios de selección para la devolución de selecciones de datos.
Va especificando luego de la cláusula FROM de un SELECT


```
SELECT Campo1, Campo2, Campo3, ..., CampoN FROM NombreTabla

WHERE [criterios de seleccion]

```

Para los criterios de selección, se pueden utilizar las operaciones lógicas tradicionales, o funciones especiales concatenadas por operadores AND, OR, XOR, etc. Según corresponda.

- = Es el operador que se utiliza para probar la igualdad entre dos expresiones.
- <> Es el operador que se utiliza para probar si dos expresiones no son iguales entre si.
- != Es el operador que se utiliza para probar si dos expresiones no son iguales entre si.
- > Es el operador que se utiliza para probar si una expresión es mayor a la otra.
- >= Expresión mayor o igual
- !> Operador que se utiliza para probar si una expresión no es mayor que la otra
- < Operador para menor
- <= Menor igual
- !< Una expresión no es menor que la otra

**Intervalos de valores**

Para indicar que deseamos recuperar los registros según el intervalo de valores de un campo emplearemos el operador Between cuya sintaxis es:


```
campo [Not] Between valor1 And valor2 (la condición Not es opcional)
```

En este caso la consulta devolvería los registros que contengan en "campo" un valor incluido en el intervalo valor1, valor2 (ambos inclusive). Si anteponemos la condición Not devolverá aquellos valores no incluidos en el intervalo.


```
SELECT *
FROM
	Pedidos
WHERE
	CodPostal Between 28000 and 28999

```



### El operador LIKE

Se utiliza para comparar una expresión de cadena con un modelo en una expresión SQL. Su sintaxis es:

```
expresión Like modelo
```

En donde expresión es una cadena modelo o campo contra el que se compara expresión. Se puede utilizar el operador Like para encontrar valores en los campos que coincidan con el modelo especificado. Por modelo puede especificar un valor completo (Ana María), o se puede utilizar una cadena de caracteres comodín como los reconocidos por el sistema operativo par encontrar un rango de valores (Like An*)

El operador Like se puede utilizar en una expresión para comparar un valor de un campo con una expresión de cadena. Por ejemplo, si introduce Like C* en una consulta SQL, la consulta devuelve todos los valores de campo que comiencen por la letra C. En una consulta con parámetros, puede hacer que el usuario escriba el modelo que se va a utilizar.

El ejemplo siguiente devuelve los datos que comienzan con la letra P seguido de cualquier letra entre A y F y de tres dígitos:

```
Like 'P[A-F]###'
```

Este ejemplo devuelve los campos cuyo contenido empiece con una letra de la A a la D seguidas de cualquier cadena.


```
Like '[A-D]*'
```

#### Tabla de como usar el operador Like para comprobar expresiones con diferentes modelos.


| Ejemplo      | Descripción                                                           |
| ------------ | --------------------------------------------------------------------- |
| LIKE'A%'     | Todo lo que comience por A                                            |
| LIKE '_NG'   | Todo lo que comience por cualquier carácter y luego siga NG           |
| LIKE'[AF]%'  | Todo lo que comience por A ó F                                        |
| LIKE'[A-F]%' | Todo lo que comience por cualquier otra comprendida entre la A y la F |
| LIKE'[A^B]%' | Todo lo que comience por A y la segunda letra no sea una B            |

En determinados motores de BDD, esta cláusula, no reconoce el asterisco como carácter comodín y hay que sustituirlo por el carácter tanto por ciento (%)

### El operador IN

Este operador devuelve aquellos registros cuyo campo indicado coincide con alguno de los campos en una lista.

```
expresión [Not] In(valor1, valor2,...)
SELECT *
FROMA
	Pedidos
WHERE
	Provincia In ('Madrir', 'Barcelona', 'Sevilla')
```

### La cláusula GROUP BY

Agrupa un conjunto de filas seleccionando en un conjunto de filas de resumen de acuerdo con los valores de una o más columnas o expresiones en SQL Server 2014. Se devuelve una fila para cada grupo. Las funciones de agregado de la lista (select) de cláusula SELECT proporcionan información de cada grupo en lugar de filas individuales.

La expresiones de cláusula GROUP BY pueden contener columnas de las tablas, derivadas o de la vista de la cláusula FROM. No es necesario que aparezcan las columnas en la lista de (selección) de la cláusula SELECT.
Deben incluirse en la lista GROUP BY todas las columnas de la tabla o la vista de cualquier expresión no agregada de la lista de (selección)

**Están permitidas las siguientes instrucciones: **
```
- SELECT ColumnA, ColumnB FROM T GROUP BY ColumnA, ColumnB; 
  
- SELECT ColumnA + ColumnB FROM T GROUP BY ColumnA, ColumnB; 
  
- SELECT ColumnA + ColumnB FROM T GROUP BY ColumnA + ColumnB;
   
- SELECT ColumnA + ColumnB + constant FROM T GROUP BY ColumnA, 
ColumnB;
```

**No están permitidas las siguientes instrucciones:**


```
- SELECT ColumnA, ColumnB FROM T GROUP BY ColumnA + ColumnB; 
  
- SELECT ColumnA + constant + ColumnB FROM T GROUP BY ColumnA + 
ColumnB;

```

Si se incluyen funciones de agregado en la lista de selección de la cláusula SELECT, GROUP BY calcula un valor de resumen para cada grupo. Se conocen como agregados vectoriales. 
Las filas que no cumplen las condiciones especificadas en la cláusulas WHERE se quitan antes de realizar ninguna operación de agrupación.
La cláusula HAVING se usa junto con la cláusula GROUP BY para filtrar los grupos en el conjunto de resultados.
La cláusula GROUP BY no ordena el conjunto de resultados. En su lugar, use la cláusula ORDER BY para ordenarlo .
Si una columna de agrupamiento contiene varios valores NULL, todos ellos se consideran 