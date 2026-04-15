## Teoría

# Software libre

Es aquel que le da a sus usuarios la libertad de:

- Elegir (sin costo)
- Ejecutar
- Estudiar
- Modificar
- Distribuir el software
En otras palabras da la posibilidad de controlar el programa que lo hace.

También significa que el software respeta la libertad de los usuarios y la comunidad
Cuando los usuarios no controlan el programa, el programa controla los usuarios
El programador controla el programa y, a través del programa, controla a los usuarios. Un programa que no es libre, llamado <<privativo>>, es pro lo tanto un instrumento de poder injusto.

 #### Tipos de licencia

**Software libre**
- Dominio publico con código fuente
- Software bajo copyleft
- Software bajo GPL
- Software de fuente abierta

**Software privativo**
- Dominio publico sin código
- fuente
- Software denominado Shareware
- Software de descarga gratuita. (Puede ser Freeware)

#### GNU y Open Source

GNU:
- Es un sistema operativo de software libre y lo podemos ver escrito como GNU/Linux
- GNU no es UNIX
- Programas exclusivamente proyecto GNU
- Programas de terceras partes
- Richard Stallman (Emacs, GCC, GDB, Copyleft, Free Software Foundation, etc.)

Open Source (Código abierto):
- Modelo de desarrollo de software basado en la colaboración abierta
- Acceso al código fuente
- Libre no significa gratuito
- Se utilizo a partir de 1990

**10 puntos de Open Source**
1. Redistribución libre del software (Comercial o no)
2. Código fuente abierto para ser estudiado
3. Obras derivadas deben ser bajo esta licencia
4. Integridad del código fuente del autor, las obras derivadas no deben ser diferenciadas
5. No discriminación contra las personas o grupos
6. No discriminación contra campos de la actividad
7. Distribución de la licencia, todos se benefician 
8. La licencia no debe ser especifica a un producto. Es valida para la distribución
9. La licencia no debe restringir otro software
10. La licencia debe ser tecnológicamente neutral

 #### Distribuciones

- Una distribución es un conjunto de paquetes de software, que incluyen al kernel de Linux, sus interfaces y un conjunto de aplicaciones.
- **Distintos tipos:**
	- Comerciales
	- Organizacionales

# Introducción
- Hardware
	- Procesador, memoria, motherboard
	- Dispositivos E/S, almacenamiento, redes
	- Servidores, HCI
- Software
	- El mismo SO
	- Aplicaciones
	- Compiladores, Shell, GUI, etc.
- Personas
	- Usuarios en general
	- Administradores, llamados **"System Programmer"**
	- Desarrolladores

#### Definiciones de SO

- Un conjunto de programas que actúa de intermediario entre los usuarios y el hardware
- Pertenece al software del sistema
- **Objetivos: **
	- Proveer un entorno para ejecutar aplicaciones
	- Administrar eficientemente los recursos
	- Facilitar la interacción con el computador
	- Facilitar la evolución del software y del hardware
- Un sistema de software cuyo fin es que un sistema informático sea operativo.
- El SO es el software que coordina y dirige todos los servicios y aplicaciones que maneja un usuario en una computadora.

### Modelo de Capas
![[Pasted image 20260225190229.png]]

Podemos decir que si este modelo de capas esta presente en un sistema, podemos decir que algo tiene un SO

**Dos roles principales de SO**
- **Interfaz con el hardware**
	- Añade características no existentes en el HW
	- Oculta características/inconvenientes del HW
	- Ofrece una maquina extendida
- Administrador de recursos
	- Como si fuer un gobierno del hardware
	- Concede recursos de forma segura, justa y eficiente
	- No realiza trabajo productivo o función útil por si mismo

![[Pasted image 20260225190555.png]]

![[Pasted image 20260225190606.png]]

### Interfaz del SO

- Para quien es la interfaz
	- Usuarios en general -> entorno de ejecución
	- Administradores -> entorno de administración
	- Desarrolladores -> interfaz de programación
- **¿Qué aspecto tiene la interfaz?**
	- Texto(CLI = Command Line Interface)
	- Grafica (GUI = Graphical User Interface)
	- Servicios de programación (API)

**Entorno de trabajo del SO**
- El SO suele proporcionar utilidades básicas para que el usuario pueda realizar tareas comunes:
	- Trabajar con archivos y discos
	- Ejecutar aplicaciones **cargador de programas**
	- Imprimir
	- Administrar el sistema: *backups, usuarios, etc.*

**¿Qué ganamos interponiendo esta interfaz entre los programas y el hardware?**

- **Usabilidad**: La interfaz es mas cómoda que el HW
- **Seguridad**: Se ocultan vulnerabilidades del interior del hardware
- **Portabilidad**: Independencia del hardware
- **Interoperabilidad**: Podemos compartir información con otros sistemas que usen la misma interfaz
- **Mantenibilidad**: Podemos hacer mejoras o adaptaciones dentro del SO sin obligar a hacer cambios en los programas de usuario
- **Productividad**: Por todo lo anterior

#### El SO como administrador de recursos

- **Procesos y Recursos**
	- Procesos: Es una entidad dinámica
	- Recursos: Puede ser algo físico o virtual, (requiere de un proceso)
- **Los recursos son escasos**, los procesos compiten e/ ellos
- **El SO actúa como arbitro/mediador**, asigna recursos en forma segura y eficiente
- El So debe determinar a quien le entrega recursos, cantidad, en que momento, por cuanto tiempo
- Por estos puntos debemos tener, **Política de gestión de recursos**.

### Criterios a cumplir de las políticas del SO

- Optimizar el rendimiento del sistema
- Justicia en el reparto, evitar acaparamiento de algún recurso
- Garantizar la seguridad del sistema (confidencialidad, integridad, disponibilidad)

No podemos dar el máximo rendimiento y al mismo tiempo dar un reparto justo

**Los 3 conceptos sobre la seguridad**
- Confidencialidad: intimidad, privacidad, etc.
- Integridad: que la información sea la correcta, que no se corrompa
- Disponibilidad: que el sistema este siempre prestando servicios.

# Historia

<**Multiprocesamiento**>

También llamado **Multiprogramación** o **Multitarea**, consecuencia del lanzamiento de la IBM 360, primer computadora con sistema operativo

- **CPU** controlaba los periféricos
- **CPU** mucho mas rápida que los periféricos

Nacen las <**Unidades <de control> **>
- Lo que llamamos **Controladores**
- Tienen electrónica
- Pueden ejecutar instrucciones 

### Procesos

- Se produce un mecanismo de rotación
- La CPU puede ejecutar varios procesos
**Concurrencia**, no simultaneidad

![[Pasted image 20260225193408.png]]
![[Pasted image 20260225193415.png]]

**Tres grandes familias**
- Mainframe (IBM) -> Sistemas propios 
- Servidores (HP, Lenovo, Dell) -> Unix/Linux/ Windows Server
- Workstation -> Windows/ Linux

# Estructuras y servicios

### Estructura de los SO

**Componentes del Sistem**

- Administracion de procesos
- Administración de la RAM
- Administración del sistema de E/S
- Administración del almacenamiento secundario
- Operación en red
- Sistema de protección
- Sistema de interprete de comando

### Servicios del SO

El SO es un proveedor de servicios:

- Administra el HW
- Facilita el uso de los programas de usuario
- Ejecución de programas
- Interfaz
- Operaciones de E/S 
- Manipulación del sistema de archivos
- Comunicaciones
- Detección de errores
- Asignación de recursos
- Contabilidad
- Protección y seguridad

### Ejecución

**- El SO debe poder cargar un programa**
	Genera un proceso
	Ese proceso necesita recursos
	Debe poder terminar ese proceso
![[Pasted image 20260225194243.png]]

### Interfaz

- Texto (CLI = Command Line Interface)
	- Unix/Linux (sh, bash, csh, rsh, etc.)
	- Microsoft (command.com, cmd, power shell)
	- Equipos de comunicaciones
- Grafica (GUI = Graphic User Interface)

### Operaciones E/S

- Traer datos del disco rígido
- Hacer una operación sobre la red
- El usuario no puede controlar el dispositivo
- Grabar datos en una cinta

**Manipulación del sistema de archivos**

- Crear un archivo
- Borrar un archivo
- Crear un directorio

### Comunicación

Necesita intercambiar información con otros procesos, que estén tanto en una misma computadora como en distintos sistemas

- **Pasaje de mensaje**
- **Memoria compartida**

### Detección de errores

- El SO debe estar preparado ante un eventual error
- Al leer un dispositivo
- Ante una operación que realiza la CPU

### Asignación de recursos

**En un sistema con multiprogramación**
- Asignar CPU a los procesos
- El SO tiene rutinas de planificación
- Asigna tiempos a los procesos
- Asignar cualquier dispositivos periféricos
-
### Contabilidad

- El SO lleva un registro de uso de CPU
- Uso de sistema de cómputos en general
- Estos registros pueden ser usados para fines comerciales

### Protección

- Proteger los datos
- Proteger la memoria
- En un sistema donde los procesos se ejecutan en forma concurrente, que no interfieran procesos de otros usuarios o del propio sistema
- Se definen usuarios y contraseñas
- Se determinan permisos (por ejemplo a los directorios o archivos)

### Llamadas al sistema

- Son las interfaces entre el programa del usuario y el SO
- Es lo llamamos System Calls
- Programadas en ensamblador, C, C++, etc.
- En Windows las llamamos API (Interfaz del programador de Aplicaciones)

**Se pueden agrupar en 5 categorías: **

- Control de procesos
![[Pasted image 20260225195336.png]]

1. Manipulación de archivos:
	- create
	- delete
	- read
	- write
	- etc

2. Manipulación de los dispositivos de E/S
	- request
	- release
	- open
	- close
	- Linux (mediante nombre archivo)

3. Mantenimiento de la informacion
Hace referencia preferentemente a la transferencia de información entre el programa de usuario y el SO

	- date
	- time
	- uname
	- free

4. Comunicaciones (Dos modelos)
Pasaje de mensajes (ge hostid, get processid)
![[Pasted image 20260225195632.png]]

5. Comunicaciones (map memory)
![[Pasted image 20260225195729.png]]}

### Modo dual 

Para asegurar la protección de SO
Hay dos modos de ejecución:

- **Modo supervisor** (Kernel, Monitor)
- **Modo usuario**

Para llevar a cabo esto:

Se agrega un bit de modo al HW

**Bit = 0** Estamos en modo supervisor
**Bit = 1** Estamos en modo usuario
![[Pasted image 20260225195911.png]]

# Diseño y estructura

Dos ramas

- **Sistemas operativos de Propósito General**
- **Sistemas operativos de Propósito especifico**

### SO de propósito general

- Mundo Unix
- Mundo Windows

Los sistemas administrativos o científicos por lo general lo hacen sobre estos SO

### SO de propósito especifico 

Los SO de **Tiempo Real**, los podemos dividir en 

- Tiempo real estricto
- Tiempo real no estricto

Acá tenemos que hacer una distinción en cuanto a los
- **Objetivos de diseño**
- **Políticas**
- **Mecanismos**
- **Implementación**

### Diseño y estructura de los SO

- Simple
- Microkernel
- Monolítico
- Por capas
- Modular

#### Simple
![[Pasted image 20260225200941.png]]

Es el diseño mas básico, todo el sistema de esta en un solo bloque de código.
No hay separación clara entre partes del sistema.



#### Microkernel
![[Pasted image 20260225200954.png]]

Se reduce el kernel a sus funciones mínimas (comunicación, planificación, manejo de interruptores). Todo lo demás se ejecuta en **modo usuario** como procesos separados. 
Mas seguro y modular pero algo mas lento por la comunicación entre proceso

#### Monolítico
![[Pasted image 20260225201012.png]]

Todo el núcleo (Kernel) esta en un solo programa grande que corre en modo privilegiado.
Los servicios del sistema están integrados en el mismo espacio de kernel

#### Por capas
![[Pasted image 20260225201028.png]]

El sistema se divide por capas jerárquicas, cada capa usa solo los servicios de la capa inferior y provee funciones a la superior.

#### Modular 
![[Pasted image 20260225201135.png]]

El kernel esta dividido en módulos independientes que pueden cargarse  o descargarse dinámicamente. Puede actualizar partes del sistema sin reiniciar.

### Maquinas virtuales

El concepto de virtualización hace referencia a una tecnología que permite la ejecución de varias maquinas virtuales sobre una maquina física con el objetivo de aprovechar al máximo los recursos de un sistema y que su rendimiento sea mayor.

A cada VM le podemos asignar dinámicamente:
- Core
- Ram
- Espacio en disco
- Etc.


### Contenedores

- Docker es una plataforma de código abierto para crear, implementar y gestionar aplicaciones en múltiples contenedores
- La idea es que estos contenedores sean portables para las aplicaciones de software
- Que estos contenedores puedan ser ejecutados en cualquier maquina que tenga instalado el Docker
- Es algo autocontenido en si, que se puede llevar de un lado a otro de forma independiente, es portable.

### Entornos informáticos

- **Sistemas de cliente servidor**

Modelo de diseño de software donde las tareas se reparten en lo que seria el proveedor de recursos o servicios **Servidor** y el que pide recurso o servicio llamado **Cliente**

![[Pasted image 20260225202127.png]]

Componentes:
- Red
- Cliente
- Servidor
- Servicios
- Protocolos
- Base de Datos

Existen otros conceptos:

- Frontend
- Backend
![[Pasted image 20260225202226.png]]

**Otros entornos informáticos**
- Sistemas entre iguales: intercambio de archivos peer-2-peer (Napster)
- Sistemas basados en web

### Interrupciones

Es la suspensión temporal de la ejecución de un proceso, para pasar a ejecutar una subrutina de servicio de interrupción, la cual por lo general, no forma parte del programa, sino que pertenece al sistema operativo o al BIOS. Una vez finalizada dicha subrutina, se reanuda la ejecución del programa.
Las interrupciones surgen de la necesidad que tienen los dispositivos periféricos de enviar información al procesador principal.

- Técnica de **polling**
- Técnica de **Interrupciones**
**Procesamiento de las mismas**
- Terminar la ejecución en curso
- Salvar el valor del PC, registros, etc.
- la CPU salta a la dirección donde esta la ISR
- Termina la rutina, se restauran valores de la pila

#### Tipos de interrupciones

- Hardware
- Software
- Excepciones

# Procesos

### ¿Qué es un proceso?

- Un programa en ejecución
En realidad es mucho mas que eso

- Una entidad dinámica (Cambia con el tiempo) compuesta por el: Código del programa ejecutable, los recursos necesarios para su ejecución y el tiempo

En cambio el código del programa fuente es una entidad estática

- Se crea
- Se ejecuta
- Termina

**Ciclo de vida de un proceso**
![[Pasted image 20260225203417.png]]

![[Pasted image 20260225203544.png]]

- Usuario
- SO
- Otro proceso

La información de cada proceso esta en una estructura llamada **PCB (Process Control Block)**

**Parte de la información que contiene la PCB**
- ID del proceso
- Estado del proceso
- Contador de programas
- Registros de la CPU
- Información del planificador
- Información de la administración de memoria

### Planificación de procesos

El SO debe seleccionar los procesos de las distintas colas. Esta selección las realizan los: **Planificadores**

- **Planificadores de largo plazo:** Selecciona procesos para cargar en memoria 
- **Planificador de corto plazo:** Selecciona procesos de la cola de listo
- **Planificador de Mediano Plazo:** Puede descargar procesos de la memoria

![[Pasted image 20260225204035.png]]

- **Procesos independientes:** Si no es afectado por otros procesos en ejecución.
- **Procesos cooperativos: ** Si pueden ser afectados por otros procesos en ejecución, las razones pueden ser: **Compartir información** y para esto es necesario que los procesos se comuniquen entre ellos, lo pueden hacer a través de pasaje de mensajes y memoria compartida.

### Comunicación entre procesos 

- **Directa:** Tienen que estar referenciados
	- Sincrónica (Ambos se nombran)
	- Asincrónica (Solo el emisor nombra)
- **Indirecta:** Se reciben a traes de buzones o puertos (Se produce un enlace entre procesos si tienen un buzón compartido)
	- Puede ser univoco entre dos proceso
	- Puede estar asociado a mas de dos procesos
	- Varios enlaces y cada uno a un buzón
	**Puede ser propiedad del proceso**
	**Puede ser propiedad del SO** (no estaría ligado a un proceso en particular, el SO debe proporcionar mecanismos para que el proceso puede crear, borrar o compartir buzón)

### Comando para crear procesos

Usamos la sentencia **fork()** para procesos padre e hijo
**Declaración: ** pid_t pidf=fork(void)
- Crea un nuevo proceso llamado -hijo-
- El proceso hijo es un duplicado del "padre"
- Los dos procesos (padre e hijo)
	- Tienen identificadores (PIDs) diferentes
	- Corren en espacios de memoria diferentes

Cuando se crea el hijo los espacios de memoria como las variables tienen los mismo valores, a partir de acá, cada uno modifica las variables en forma independiente

**Retorno del fork()**
Al padre se le retorna el valor del PID del hijo y al hijo se le retorna 0
Si hay algún problema en la creación del hijo devuelve el valor -1 

### Hilos

El concepto viene de lo que llamamos procedimientos o rutinas
![[Pasted image 20260225205217.png]]

A partir de que tenemos mas de una CPU, como potenciamos esto?
Habíamos desarrollado el concepto de **Procesos cooperativos**

Ahora si al tener 2 CPU puedo, ejecutar simultáneamente 2 procesos, también podría ejecutar simultáneamente dos partes del código del mismo proceso.

Entonces ahora tendríamos en lugar de un numero de procesos cooperativos, habría un solo proceso ejecutando varios **Subprocesos**

Donde cada subproceso es el equivalente a uno de los tantos procesos cooperativos.

Por lo tanto ahora cambia la idea de la definición de proceso.
Contenedor de recursos y múltiples entidades dinámicas muchos mas pequeñas denominadas **Hilos**

**Beneficios: **
- Grado de respuesta: Mas rápido, cada hilo se puede ejecutar en CPU diferentes.
- Compartir recursos: Por defecto comparte la memoria y los recursos del proceso que lo genero
- Economía: Menos memoria y recursos
- Utilización de arquitecturas multinúcleos

La información de cada proceso esta en una estructura llamada PCB
Ahora vamos a dividir esto que llamábamos proceso en pequeñas entidades llamadas hilos.
Por lo tanto dentro de cada PCB vamos a tener pequeñas unidades llamadas
**TCB (Thread Control Block)**

![[Pasted image 20260225205936.png]]

Proceso con varios hilos
Ahora el programador va a crear subprocesos 
![[Pasted image 20260225210022.png]]

En la década del 80 nacen los SO Multi thread
Este usa el modelo **Uno-a-Uno**, cada vez que nace uno a nivel de usuario nace uno a nivel de kernel 
![[Pasted image 20260225210132.png]]

Ventajas: cada hilo **K** atiene a un hilo de **U**
Desventajas: Consume muchos recursos

Se pensaron en otras alternativas, por el lado del mundo Unix lanzaron el modelo **Muchos a uno**
![[Pasted image 20260225210309.png]]

La empresa SUN para su SO Solaris implemento lo que se denomino el modelo **Muchos  a Muchos**
![[Pasted image 20260225210345.png]]

En definitiva hoy en día se utiliza el modelo **Uno-a-Uno**, salvo algunas versiones muy duras de UNIX
Aunque cada SO tiene su propia librería que maneja esto.

### Planificación de la CPU

Cuando nace la multiprogramación, lo que vamos a tener es el:

**Uso compartido de la CPU entre múltiples proceso/ hilos**

Tipos de procesos:
- Orientados a la CPU (Ráfagas largas)
- Orientados a la E/S (Ráfagas cortas)
- Intermedios (sobre dispositivos rápidos) 

Otro objetivo de la multiprogramación era lograr el máximo uso de la CPU y para esto tenemos que **Planificar**
![[Pasted image 20260225211035.png]]

- El planificador de corto plazo va a trabajar sobre un conjunto de procesos listos
- Teniendo en cuenta que la CPU trabaja de a ráfaga
- Vamos a tener varios algoritmos de planificación de la CPU
- Distintos criterios 

- Con desalojo
- Sin desalojo
![[Pasted image 20260225211221.png]]

**Algoritmos de planificacion**
- FCFS (First Come First Served) un FIFO
- SJF (Shortest Job First)
- SRTF (Short Remaining Time First)
- Prioridad
- RR (Round Robin)
	Cada proceso tiene un quantum de tiempo fijo, si no termina en ese tiempo se interrumpe y pasa al final de la cola. 
- RR (Round Robin) - Variante
	Hay variante de quantum variable
	Variante que se uso en el kernel Linux
	Doble cola y memoria de lo usado
	Se define un Quantum grande para los proceso
- Multicola
	**Los procesos se clasifican en grupos: **
	- Interactivos 
	- Por lotes 
	- Procesos del sistema
	- Procesos de usuario
	**Planificación colas niveles múltiples y retroalimentación**
	Los procesos se mueven entre distintas colas, separar los procesos con distinta ráfagas de CPU. Las colas tendrían distintas prioridad
	![[Pasted image 20260225211848.png]]


# Comunicación

Habíamos hablado anteriormente de 2 tipos de procesos o 2 formas de caracterizarlo.

- Independientes: No requieren intervención de otros proceso
- Cooperativos: La problemática en lugar de resolverla un solo proceso, lo hacen varios procesos cooperando entre ellos. Tiene como ventaja el solapamiento de tiempos.

### IPC (Comunicación e/ procesos)

El avance de los procesos cooperativos hizo que el modulo fuera creciendo cada vez mas

- Administración de la CPU
- Administración de la memoria
- Administración del sistema de archivos
- IPC (Soporta todos los protocolos de red)
- Seguridad

Los procesos cooperativos pueden afectar o ser afectados por otros procesos incluido compartir información

**Razones para cooperar entre procesos**
- Compartir información
-  Modularidad
- Conveniencia
- Optimización

Los proceso cooperativos necesitan IPC
2 modelos de IPC
- Memoria compartida
- Pasaje de mensajes

### Pasaje de mensajes

Mecanismo de los procesos para comunicarse y sincronizar sus acciones
Los procesos se comunican entre si sin recurrir a variables compartidas
IPC provee dos operaciones:
- send
- receive

si P y Q quieren comunicarse, se necesita:
- establecer una conexión de comunicación entre ellos
- intercambiar mensajes vía send/receive

Implementación de la conexión de comunicación
- física (memoria compartida, hardware bus)
- lógica (propiedades lógicas)


**Comunicacion directa**

Los proceso deben nombrarse entre si explícitamente

Propiedades del link de comunicación

- Se establecen automaticamente
- Un link es establecido exactamente con un par de procesos en comunicacion
- Entre cada par existe exactamente un link
- El link puede ser unidireccional, pero usualmente es bidireccional 

**Comunicacion indirecta**

Los mensajes son dirigidos y recibidos desde buzones
- cada buzón tiene un ID
- los procesos se pueden comunicar solo si compartes buzón 

Propiedades del link de comunicacion:
- El link se establece solo si los procesos comparten buzón
- Un link puede ser asociado con muchos procesos
- Cada par de procesos puede compartir varios links
- El link puede ser unidireccional o bidireccional

Operaciones:
- Crear un nuevo buzón
- Enviar y recibir mensajes vía buzón
- Eliminar un buzón 

Las primitivas se definen como:
- send
- receive

### Sincronización

El pasaje de mensajes puede ser tanto bloqueador como no 

Bloqueador es considerado sincrónico
- Blocking send tiene al emisor bloqueado hasta que el mensajes es recibido
- Non-blocking receive el receptor recibe un mensaje valido o null

## Buffering

Cola de mensajes conectada al link; implementado en una de estas tres formas:
- Capacidad cero - 0 mensajes 
	- El emisor debe esperar al receptor (rendezvous)
- Capacidad limitada - n cantidad de mensajes
	- El emisor debe esperar si el link esta lleno
- Capacidad ilimitada - longitud infinita 
	- El emisor nunca espera

### Sockets

Un socket es definido como el punto final para la comunicacion
Concatenación de la dirección IP y el puerto
- El socket 161.25.19.8:1625 refiere al puerto 1625 en el host 161.25.19.8
- La comunicacion consiste en un par de sockets
![[Pasted image 20260225215244.png]]

# Sincronización

Los procesos comparten recursos, pueden ser adquiridos por mas de uno.
- Proceso en ejecución concurrente
- Procesos que corren en multi CPU

Supongamos que hay un recurso compartido en un sistema determinado.
Ese recurso es una variables como por e. "Stock-PC"

El resultado de una operación depende del orden que se ejecute, esto se llama **Condición de carrera**
Caso muy serio en programación concurrente

Dentro de la codificación denominamos **Sección critica** a la parte de código del programa en la cual se va a acceder y modificar un recurso compartido.
Para evitar problemas, si un proceso esta en la sección critica otro no puede estar ejecutando esa sección critica que afecta ese recurso. 

Debemos definir un protocolo, debemos saber si estamos en sistemas mono CPU o multi CPU.

- **Exclusión mutua - Mutex** (uno solo en la SC)
	- Necesitamos un protocolo
	- Cerrojo
	- Funciona para una cola FIFO
	- Planteo de Stallings - Tanenbaum
	- Ahora funciona para todos los procesos?
	- Que pasa si el recurso se asigna por prioridad, quienes participan en la decisión.
	- Puede ocurrir un caso de **"inanición"**

- **Progreso:** Solo participan los procesos que están en la cola
- **Espera limitada:** Ningún proceso puede esperar ilimitadamente la entrada a la sección critica

- **Soluciones por software: **
	- Algoritmo de Peterson
- **Soluciones por hardware:** Se implementaron instrucciones a nivel del procesador
	-  Test and set
	- Swap
	-  Realizan en un solo ciclo de instrucción toda la operación
	- No se pueden interrumpir 

Herramientas especificas para esto implementadas a nivel SO:

- Semáforos
- Monitores

# Semáforos

Un semáforo es una variable entera protegida (tipo de dato abstracto) controlada por el SO.
Sirve para coordinar procesos y proteger secciones criticas (bloques de código donde solo un proceso puede entrar a la vez)



|  **Operación**   | **También llamada**    | **Función**    |
| --- | --- | --- |
|   Wait (S)  | Down, P(S)    | Pide el recurso. Si S <= 0, el proceso espera bloqueado. Si S> 0, decrementa S y entra en la SC    |
| Signal (S) | Up, V(S) | Libera el recurso. Incrementa S y despierta a un proceso bloqueado si hay alguno |

**inicialización**
Inicializar_sem(S, valor) donde el valor inicial indica cuantos recursos hay disponibles

**Tipos: **

1. Binario (Mutex):
	- Solo toma valores 0 o 1
	- Controla el acceso exclusivo a un recursos (solo un proceso a la vez)
2. Contador
	- Puede tener valores > 1
	- Permite administrar múltiples instancias del mismo recurso 


### Espera activa

En la forma mas básica, un proceso que ejecuta Wait(S) puede quedarse en bucle activo esperando que S > 0.
Los SO modernos reemplazan esto por bloque y cola de espera, para no consumir CPU.

### Monitores

Un monitor es un tipo abstracto de dato de los lenguajes de alto nivel que encapsula todas las operaciones sobre un recurso compartido
- Solo un proceso puede estar dentro del monitor a la vez
- Garantiza exclusión mutua sin necesidad de usar semáforos directamente
- Las operaciones se invocan como métodos del monitor

**Componentes: **
- Variables locales y globales
- Procedimientos públicos y privados
- Variables especiales llamadas conditions

#### Variables condition

- Solo se declaran dentro del monitor
- Se usan con wait y signal
- Administran la cola de procesos esperando dentro del monitor























 










