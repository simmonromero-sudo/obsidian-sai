## Desarrollo de software

**¿Qué es el software?**

"Conjunto de programas, instrucciones y reglas informáticas para ejecutar ciertas tareas en un computadora" 
- **Programas:** instrucciones que ejecuta la computadora
- **Datos:** información que los programas manipulan.
- **Documentación:** manuales, especificaciones, etc.

El desarrollo de software es el proceso de concebir, diseñar, programar, documentar, probar y mantener aplicaciones.

#### Ciclo de vida del desarrollo de software![[Pasted image 20260413082234.png]]

#### SDLC Modelos

**Cascada**
- Proceso lineal y secuencial
- Documentación exhaustiva
- Cada fase debe completarse antes de la siguiente
- Asume que os requerimientos se pueden congelar 
- Es muy difícil volver a cualquier etapa una vez finalizada

**Iterativo**
- Desarrollo iterativo en etapas (mini-cascada)
- Genera valor comercial entre iteraciones
- La división  defunciones y características puede ser compleja
- Riesgo de desviación del objetivo inicial de proyecto

**Ágil**
- Desarrollo iterativo e incremental
- Orientado al despliegue rápido
- Participación continua con el cliente
- Requiere una gran implicación del cliente
- El equipo debe estar cohesionado

### Arquitectura de software

Es  una descripción abstracta de un sistema, que define los componentes que lo conforman, sus responsabilidades, la manera en que interactúan entre si y los principios de diseño que guían estas decisiones.
Como disciplina busca definir una visión técnica y organizativa que sirva como base para el diseño, desarrollo, evolución y mantenimiento de sistemas de software complejo.

#### Aspectos claves

##### Modularidad
Capacidad de un sistema para dividirse en componentes o módulos independientes entre si, pero que trabajan en conjunto. Cada módulo realiza una función específica, lo que facilita la reutilización, el mantenimiento y la comprensión del sistema.

##### Escalabilidad
Capacidad de un sistema para manejar un aumento de carga (usuarios, datos, transacciones, etc.) sin degradar su rendimiento. Puede ser **vertical** (mejorar el hardware) o **horizontal** (agregar mas nodos o instancias) 

##### Mantenibilidad
Facilidad con la que se puede modificar un sistema para corregir errores, mejorar funcionalidades o adaptarlo a nuevos requisitos. Un código limpio, bien documentado y modular mejora la mantenibilidad.

##### Rendimiento
Eficiencia con la que un sistema ejecuta sus tareas. Incluye aspectos como velocidad de respuesta, uso de recursos (CPU, memoria) y tiempos de procesamiento

##### Seguridad
Capacidad de un sistema para protegerse contra accesos no autorizados, manipulación de datos, ataques cibernéticos y otros riesgos. Incluye aspectos como autenticación, autorización, cifrado y validación de datos.

##### Disponibilidad
Grado en que un sistema está operativo y accesible cuando se necesita. Alta disponibilidad implica que el sistema funciona de manera continua, incluso ante fallas.

##### Portabilidad
Facilidad con la que un sistema o software puede ejecutarse en diferentes entornos (hardware, SO, plataformas) con pocas o ninguna modificación.

#### Componentes principales

##### Componentes/ Módulos
Son las unidades funcionales del sistema. Pueden ser clases, servicios, bibliotecas o subsistemas completos.

##### Conexiones
Mecanismos que permiten la comunicación entre componentes, como APIs, eventos, colas de mensajes, sockets, etc. 

##### Estructura
La disposición especifica de los componentes y conectores que conforman una instancia del sistema.

##### Estilos y patrones arquitectónicos
Conjuntos de prácticas y soluciones reutilizables que guían el diseño arquitectónico, como cliente-servidor, microservicios, MVC, capas, event-driven, entre otros. 

### Estilos arquitectónicos

#### Monolítica 

En una arquitectura monolítica, todas las funcionalidades de la aplicación se desarrollan y despliegan como una sola unidad. Todo el código está interconectado y ejecutado en un único proceso.

**<font color="#green">Ventajas</font>**
- Facilidad de desarrollo y despliegue inicial.
- Rendimiento más eficiente debido a la comunicación interna dentro del proceso

<font color="#F000">Desventajas</font>
- Dificultad para escalar componentes individuales.
- Mayor complejidad en el mantenimiento y actualización 
- Riesgo de fallos en toda la aplicación si un componente falla
![[Pasted image 20260413084542.png]]

#### Cliente servidor 

Esta arquitectura divide el sistema en dos componentes principales: el cliente y el servidor.
El cliente envía solicitudes al servidor, que procesa las solicitudes y devuelve las respuestas.

<font color="#green">Ventajas</font>
- Claridad en la separación de responsabilidades
- Facilita la escalabilidad horizontal.

<font color="#fa00">Desventajas</font>
- Dependencia del servidor: si el servidor falla, los clientes no pueden funcionar.
- Escalabilidad limitada a la capacidad del servidor

#### Orientada a servicios (SOA)

Organiza una aplicación como un conjunto de servicios autónomos, que se comunican a través de una red.
Cada servicio realiza una función específica y puede ser reutilizada en diferentes aplicaciones.

<font color="#green">Ventajas</font>
- Reusabilidad de los servicios.
- Flexibilidad en la integración de diferentes tecnologías y sistemas.

<font color="#fa00">Desventajas</font>
- Complejidad en la gestión de servicios.
- Potenciales problemas de rendimiento debido a la comunicación entre servicios.

#### Microservicios

En esta arquitectura, la aplicación se divide en pequeños servicios independientes que se encargan de una tarea específica, cada uno con su  propia lógica y base de datos.

<font color="#green">Ventajas</font> 
- Escalabilidad y flexibilidad: cada servicio se puede escalar de manera independiente.
- Mejor mantenimiento y despliegue continuo.
- Aislamiento de fallos: un fallo en un microservicio no afecta a los demás.

<font color="#fa00">Desventajas</font>
- Complejidad en la gestión de múltiples servicios.
- Comunicación entre servicios puede introducir latencia y complicaciones.
- Requiere una infraestructura más compleja (monitoreo, orquestación).

### Arquitectura multicapa 

Es un patrón que organiza el sistema en niveles jerárquicos, donde cada capa tiene una función bien definida.
El objetivo es mejorar las organizaciones del código y la interacción entre los distintitos componentes.

**Modularidad:** Cada capa tiene una función específica.
**Escalabilidad:** Permite escalar componentes de forma independiente.
**Mantenibilidad:** Facilita localizar y corregir problemas.
**Reutilización:** Posibilita reutilizar componentes en diferentes aplicaciones
**Testing:** Facilita la implementación de pruebas unitarias.
**División del trabajo:** Permite que distintos equipos trabajen en diferentes capas. 

**<font color="#fA00">DESVENTAJAS</font>** 

**Complejidad inicial**
Requiere mas diseño y planificación.

**Posible sobrecarga**
La comunicación entre capas puede generar sobrecarga.

**Curva de aprendizaje**
Mayor complejidad para nuevos desarrolladores.

-----
Todas las capas se colocan de forma horizontal, de tal forma que cada capa solo puede comunicarse con la capa que está inmediatamente por debajo.
![[Pasted image 20260413090212.png]]

#### Capa de presentación

La capa de presentación es la encargada de la interfaz de usuario (UI)

- Es la capa con la que interactúa el usuario final.
- Muestra info. y captura datos de entrada.
- Interactúa con la capa de negocio a través de APIs o servicios.

**Aspectos claves**
- Diseño visual
- Interactividad
- Experiencia de usuario (UX)

**Funciones principales**
- Mostrar información
- Recibir entradas del usuario
- Validación básica de datos
- Formateo de datos

**Tecnologías**

- Navegadores web (HTML, CSS, JavaScript)
- Frameworks frontend: React, Angular, vue.js
- Aplicaciones móviles

#### Capa de negocios

Es la capa responsable de implementar las reglas y la lógica que rigen el funcionamiento de la aplicación.
Se sitúa entre la capa de presentación (la interfaz de usuario) y la capa de persistencia

**Funciones principales**
- **Implementación de reglas de negocio:** Define y ejecuta las reglas que determinan cómo se deben procesar los datos y realizar las operaciones.
- **Procesamiento de datos:** recibe, transforma, envía datos entre las capas adyacentes.
- **Coordinación de acciones:** coordina interacciones entre las diferentes capas de la aplicación. Controla el flujo de información y asegura que las operaciones se realicen en el orden correcto.
- **Validación de datos:** valida los datos recibidos, asegurando que cumplan con las reglas de negocio, antes de ser enviados a la capa de persistencia.

**Tecnologías**

- Lenguajes del lado del servidor: JavaScript (node.js), Java, PHP, C#, Python
- Frameworks backend: EXpress.js. Laravel, Spring, Django.

#### Capa de persistencia

Se encarga de interactuar el sistema de almacenamiento de datos, ya sea una base de datos o cualquier otro.

**Funciones principales**
- **Abstracción del acceso a datos:** oculta detalles de la implementación del sistema de almacenamiento. Proporcionando una interfaz uniforme para acceder a los datos.
- **Operaciones CRUD:** implementa las operaciones básicas de creación (Create), lectura (Read), actualización (Update) y eliminación de datos (Delete).
- **Mapeo objeto-relacional (ORM):** en muchos casos, la capa de persistencia utiliza un ORM para mapear los objetos de la aplicación a las tablas de la base de datos. Simplificando el acceso a los datos y reduciendo la cantidad de código necesario.
- **Gestión de transacciones:** Se encarga de gestionar las transacciones de la base de datos, asegurando la integridad de los datos

**Tecnologías**

- Bases de datos: MySQL, PostgreSQL, MongoDB, Redis
- ORMs y herramientas: Sequelize, Mongoose, Knex.js, Hibernate, Doctrine

## JavaScript




``` 

```
