
## Modelado 

El modelado de datos es un proceso que permite descubrir, diseñar, visualizar, estandarizar e implementar activos de datos de alta calidad a través de una interfaz gráfica intuitiva. Un modelo de datos adecuado sirve como plano visual para diseñar e implementar bases de datos que aprovechen las fuentes de datos para respalda un mejor desarrollo de aplicaciones e impulsar mejores decisiones.

### Modelo Entidad - Relación

El modelo Entidad - Relación (ER) es un modelo de datos conceptual y semántico que permite representar la estructura de un dominio del mundo real, basado en la identificación de objetos fundamentales, llamados **entidades**, y de las **relaciones** que existen entre ellos, con el objetivo de reflejar el significado de los datos y su interconexión.

**¿Qué significa que es un modelo de datos conceptual y semántico?**

- Conceptual $\rightarrow$ se usa en una etapa inicial del diseño, sin pensar todavía en cómo se implementa (no depende de tablas ni SQL)
- Semántico $\rightarrow$ Representa el significado de los datos, no solo su forma.

O sea, describe qué cosas hay y qué significan en el dominio.
No se enfoca en cómo se guarda, sino en qué significa lo que se guarda.

**¿Qué significa qué el modelo ER está basado en entidades y relaciones?**

El modelo ER propone una forma de representar la realidad a partir de dos conceptos fundamentales:
- Entidades: objetos del mundo real con existencia propia.
- Relaciones: vínculos o asociaciones entre esas entidades.

El modelo intenta responder:
- ¿Qué cosas existen en el dominio? $\rightarrow$ entidades
- ¿Cómo se vinculan entre si? $\rightarrow$ relaciones

**EJEMPLOS:**

- Entidades: Cliente, Producto
- Relación: Compra


**"Reflejar el significado de los datos y su interconexión"**
No solo importa el dato en sí, sino:
$\rightarrow$ Qué representa
$\rightarrow$ Cómo se conecta con otros

**EJEMPLO:**
- "Juan" no es solo un dato, es un Cliente llamado Juan que realizó compras

En el modelo ER, las entidades permiten identificar los objetos relevantes de un dominio; sin embargo, por solas no resultan suficientes para describir completamente la realidad que se desea modelar. Para lograr una representación más precisa y significativa, es necesario incorporar **atributos**

Los atributos son las propiedades o características que describen a las entidades y las relaciones, permitiendo detallar la información que se desea almacenar sobre cada objeto. Gracias a ellos, es posible distinguir instancias de una misma entidad y aportar contenido semántico a los datos.

Por ejemplo, reconocer la entidad Cliente no es suficiente si no se especifican sus atributos, como nombre, DNI, dirección. Estos atributos permiten no solo describir al cliente, sino también diferenciarlos de otros.
Además los atributos son fundamentales para: 
- Individualizar entidades (mediante claves o identificadores)
- Almacenar información relevante del dominio
- Facilitar consultas y procesamiento de datos

En este sentido, los atributos complementan a las entidades y relaciones, haciendo posible una representación más completa del mundo real. Sin ellos, el modelo sería incompleto, ya que solo se conocería la existencia de los objetos y sus vínculos, pero no sus características ni los datos necesarios para su gestión.

#### Atributos

Los atributos pueden ser:
- Simples y compuestos. Los simples no pueden subdividirse. Los compuestos, en cambio, se pueden dividir en subpartes (es decir, en otros atributos). Por ejemplo, una dirección puede estar compuesta por los atributos calle, número y localidad.
- Monovalorados y multivalorados. Los monovalorados tienen un valor sólo para una entidad; por ejemplo, el atributo número-préstamo. El atributo número-teléfono para cualquier empleado puede tener cero, uno  o más números de teléfono. Este tipo de atributo se llama multivalorado. 
- Derivados: El valor para este tipo de atributo se puede derivar de los valores de otros atributos o entidades relacionados. Por ejemplo, si la entidad cliente tiene le atributo fecha-nacimiento y edad, la edad deriva de la fecha de nacimiento. Si la entidad cliente tiene un atributo cantidad-préstamos,, se puede derivar contando el número de entidades préstamo asociadas con ese cliente.

Supongamos:
- Entidad fuerte: Pedido (con ID propio)
- Entidad débil: Detalle Pedido

El DetallePedido:
- No existe sin el Pedido
- No se identifica sólo (puede haber muchos ítems similares)

Se identifica con:
- ID Del Pedido
	- Número de ítem


## DIAGRAMA ENTIDAD - RELACIÓN


Expresa gráficamente estructura lógica general de una base de datos.
Consta de los siguiente componentes principales:

- Rectángulos, que representa entidades.
- Elipses, que representan atributos (el atributo <u>clave</u> se subraya).
- Rombos, que representan relaciones.
- Líneas, que unen atributos a conjuntos de entidades y entidades a relaciones. 
- Elipses dobles, que representan atributos multivalorados
- Elipses discontinuas, que denotan atributos derivados.
- Rectángulos dobles, que representan conjuntos de entidades débiles
- mín...máx, que representa la cardinalidad

La cardinalidad en el modelo indica cuántas ocurrencias de una entidad pueden o deben estar asociadas con otra a través de una relación.

Se expresa con dos valores: mín...máx

La cardinalidad mínima indica la cantidad mínima de participaciones de una entidad en una relación

Valores posibles:
0 (Participación opcional)
1 (Participación obligatoria)

La cardinalidad máxima indica la cantidad máxima de participaciones posibles.

Valores típicos:
1 (a los sumo una)
$* \ \rightarrow$ muchas  