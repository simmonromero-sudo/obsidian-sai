**Dato**:
- Un dato es un valor crudo, sin procesar ni interpretar,  que por si solo o tiene significado completo
- Mínima unidad semántica, 

**Información:**
Conjunto de datos procesado y que tienen un significado (relevancia, propósito, y contexto), y que por lo tanto son de utilidad para quien debe tomar decisiones.

Ejercicio:

a) Datos: hora, vendedor, comprador, cantidad de productos, precio, método de pago
b) 
Diego Pérez hizo 3 ventas

### Conceptos

En una organización que opera en un entorno cada vez mas competitivo, y globalizado, diariamente se generan grandes volúmenes de datos: nombres de clientes, precios, cantidades vendidas, formas de pago. Estos datos, por si solos, son simplemente valores aislados, pequeños bloques sin un significado completo. Sin embargo, cunado estos datos se procesan se pueden llegar a decisiones.

Por ejemple, saber cuanto vendió un vendedor, cuanto gasto un cliente o cuales son las formas de pago mas utilizadas no surge de un dato aislado, sino del procesamiento de muchos datos. Esta información es fundamental, ya que las organizaciones dependen de ella para tomar decisiones correctas. Y en un contexto donde la competencia es alta, tomar buenas decisiones puede determinar la supervivencia de la organización. 

Ahora bien, para que la información sea realmente útil, debe ser oportuna y confiable, lo que implica trabajar con datos precisos. Pero estos datos no solo deben ser correctos, sino que también deben estar organizado de manera tal que sea fácil acceder a ellos y procesarlos. si los datos están desordenados, duplicados o dispersos generar información se vuelve difícil lento e incluso propenso a errores.

En este contexto surge la necesidad de utilizar una base de datos. Una base de datos permite almacenar los datos de manera organizada y estructurada, facilitando su acceso, su actualización y su procesamiento, Gracias a ella, los datos pueden transformarse rápidamente en información confiable, lo que a su vez permite tomar decisiones fundamentadas 

#### Definición de base de datos
Una base de datos (BD) es una colección o conjunto de datos relacionados entre si, almacenados de manera estructurada, que permite su acceso, gestión procesamiento con el objetivo de transformarlos en información útil para la toma de decisiones del mundo real

Una BD se puede mantener manualmente o estar computarizada

#### Tipos de base de datos

##### Manual
Una base de datos manual es un sistema de almacenamiento de datos no informatizado, donde la información se registra y gestiona de forma física.

**Características:**
- Los datos se escriben a mano o se imprimen
- La búsqueda de información es lenta y manual
- Es mas propensa a errores humanos
- Difícil de actualizar y mantener
- Problemas de redundancia 

##### Automatizada
Una base de datos automatizada es un sistema donde los datos se almacenan y gestionan mediante una computadora y un software especifico (DBMS)

**Características:**
- Almacenamiento digital
- Acceso rápido a los datos
- Permite consultas complejas
- Menos redundancia y mayor consistencia
- Mayor seguridad y control
- Facilita el procesamiento para obtener información

#### Definición de DBMS
FALTA, LA PROFESORA VA VOLANDO 
Un sistema de administración de datos es una colección de programas 

##### Capacidades de un DBSM

- Definir una BD implica especificar los tipos de datos, estructuras y restricciones de los datos que se almacenaran en la BS.
- La construcción de la BD es el proceso consistente en almacenar los datos en algún medio de almacenamiento controlado por el DBMS. 
- La manipulación de una BD incluye funciones como la consulta de la BD para recuperar datos específicos, actualizar la BD para reflejar los cambios introducidos en el minimundo y generar informes a partir de los datos.
- Compartir una BD permite que varios usuarios y programas accedan a la BD en forma simultanea.
- Una aplicación accede a la BD enviando consultas o transacciones de datos al DBMS. Una consulta provoca, normalmente, la recuperación de algunos datos; una transacción puede provocar la lectura/escritura de algunos datos de la BD.

Otras funciones importantes ofrecidas por la DBMS son la protección de la BS y su mantenimiento durante un largo periodo de tiempo. La protección incluye protección del sistema contra funcionamiento defectuoso del hardware/software y protección de la seguridad contra acceso no autorizado o malintencionado. El mantenimiento permite la evolución del sistema de BD según cambian los requisitos con el tiempo.

##### Objetivos de una DBMS

- Evitar redundancia e inconsistencia de datos
- Permitir acceso a los datos en todo momento
- Evitar anomalías en el acceso concurrente
- Restricción a accesos no autorizados -> seguridad
- Suministro de almacenamiento persistente de datos
- Integridad en los datos
- Backups

**Ejemplos:**
- Oracle
- MySQL
- Microsoft SQL Server

#### Sistema de bases de datos

Un sistema de bases de datos consiste en una colección de datos interrelacionado y un conjunto de programas para acceder a dichos datos

- Su o VUELA LA FORRAAA

**Como funciona:**

1. El usuario hace una acción
2. El programa de aplicación envía la solicitud
3. El DBMS interpreta la consulta y accede a los datos