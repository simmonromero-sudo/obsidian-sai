
### Los modelos de redes

Los modelos de redes son marcos de referencia que permiten estandarizar as arquitecturas de interconexión de los sistemas de comunicación. Con el tiempo se vio la necesidad de generar un modelo que facilitara la evolución, al tiempo de asegurar la compatibilidad entre diferentes proveedores. El modelos OSI es creado en 1984 por la Organización Internacional para la Estandarización, conocida como ISO, el modelo se baso en modelos de conexión existentes, como la red de Digital Equipment Corporation (DECnet), Systems Network Architecture y TCP/IP a fin de encontrar un conjunto de reglas aplicables de forma general a todas las redes. 

#### Modelo OSI

El modelos OSI divide la comunicación entre dos dispositivos en siete capas. Cada una de ellas, incluye una serie de protocolos para permitir la comunicación. Cabe aclarar que cada dispositivos va a implementar una o más capas siempre comenzando por la capa física. A modo de ejemplo, una computadora va a implementar todas las capas, ya que presenta funcionalidad desde la conexión al medio hasta la capa de aplicación. En cambio, u switch solo va a presentar características de la capa física y de enlace 
![[Pasted image 20260519204511.png]]

Este modelo presenta todas las funciones de l comunicación divididas en diferentes capas. Cada una de ellas recibe peticiones de la capa superior y toma servicios de las capas inferiores.
La **Capa física**, es la que describe el medio físico y la forma en la que se transmite la información sobre dicho medio, por ejemplo los cables UTP que se utilizan para las rede Ethernet. 

La **Capa de enlace de datos** se ocupa del direccionamiento físico, de la topología de red, del acceso al medio, de la detección de errores, de la distribución ordenada de tramas y del control de flujo. Trama se refiere a la unidad de medida de la información sobre esta capa.
Esta capa regula la forma de comunicación sobre una red. Entre otras cosas definiendo el direccionamiento físico de cada dispositivo como direcciones MAC, verificando la integridad de las tramas y corrigiendo errores.

La **Capa de red** se identifica con el direccionamiento lógico y el enrutamiento entre redes. Para esto clasifica dos tipos de protocolos, los enrutables que son lo que definen el direccionamiento, y los enrutados que permiten identificar las rutas. 
El equivalente a la trama en esta capa es el paquete, el cual es trasmitido entre dispositivos.
El router es el dispositivo característico de esta capa, que permite seleccionar las rutas para que los paquetes viajen entre clases.

La **Capa de transporte** se encarga de administrar el transporte de información entre ambos extremos, independizando dicha comunicación de los medios subyacentes. Se definieron dos maneras de realizar esta administración.
La primera, TCP se caracteriza por ser orientado a la conexión. Realiza un control exhaustivo de la información enviada y enviando información a medida que recibe confirmación de lo ya enviado.
La segunda, UDP se caracteriza por ser no orientado a la conexión. No se realiza dicho control, se envía la información sin confirmar que el otro extremo la esté recibiendo correctamente. El control deberá ser implementado por capas superiores para evitar errores en la comunicación.
Por otro lado esta capa define los sockets o puertos, se pueden pensar como enchufes lógicos que permiten conectar el origen y el destino de una comunicación.
El equivalente a la trama y al paquete se lo denomina segmento.

La **Capa de sesión**: se encarga de adaptar las diferentes representaciones de caracteres de los dispositivos. Así en el caso de realizar una comunicación con dispositivos que presenten diferente representación, esta capa se encargará de adaptar las mismas.

Por ultimo, la **Capa de aplicación** incluye los protocolos que utilizan las aplicaciones que se ejecutan entre los dispositivos, los cuales definen entre otras cosas los protocolos de capas de transporte utilizados. Algunos ejemplos son el correo electrónico con el protocolo SMTP (utiliza TCP), la resolución de nombres con el protocolo DNS, los servidores de archivo con el protocolo FTP y la navegación web con el protocolo HTTP. 
En si, cada protocolo sobre esta capa define una aplicación. El proceso de tomar los datos de una capa superior e incluirlos en la inferior se lo denomina encapsulación, así cada capa encapsula el contenido de la capa anterior en el nodo que se encuentra enviando los datos. El nodo que los recibe, debe desencapsular los mismo para poder entenderlos, así cada capa desencapsula lo que le corresponde y envía los datos al nivel superior. 


### Modelo TC/IP

El modelo TCP/IP fue creado en 1970 por la agencia DARPA, del departamento de defensa de los Estados Unidos.
Al igual que en el caso anterior, el modelo TCP/IP describe un conjunto de guías para el diseño e implementación de protocolos específicos que permita la comunicación entre dos dispositivos.
A diferencia del caso anterior, TCP/IP presenta 4 capas:

1. Enlace:  describe el acceso al medio y representa las capas física y de enlace en el modelo OSI
2. Red: define el direccionamiento y representa la capa de red del modelo OSI
3. Transporte: se identifica con la capa del transporte del modelo OSI.
4. Aplicación: incluye las funcionalidades de las capas de sesión, presentación y aplicación descritas para el modelo OSI.  

#### El direccionamiento

El direccionamiento permite la comunicación entre dos nodos, ya sean dos PCs, una PC y un servidor, una PC y un equipo red, etc. Tal como se describió durante la definición del modelo OSI, podemos encontrar el direccionamiento físico en la capa de enlace y el direccionamiento lógico en la capa de red.
El direccionamiento físico permite la conexión entre dos equipos que estén dentro de la misma red lógica.
Cuando dos nodos se encuentran en la misma red lógica, ellos deberán conocer la dirección MAC del otro par poder comunicarse. Para esto, los nodos utilizan un protocolo conocido como ARP Request enviando la dirección IP del destino. Así todos los nodos dentro de dicha red van a recibir el pedido y el que corresponda va  a responder con un ARP Response informando su dirección física. Como parte de dicho proceso el resto de los nodos van a poder aprender la dirección física y lógica del nodo que envía. Esta información es almacenada en la tabla ARP de los nodos que puede ser vista con el comando ARP. 
Ya con esta información el origen podrá enviar la información al destino y este responder al primero.
El direccionamiento lógico, también denominado direccionamiento IP, permite la comunicación entre redes lógicas configuradas por el usuario.
El formato actual posee 32 bits, se escribe en números decimales y se divide en 4 octetos. Además poseen una máscara de red, la cual permite delimitar la red del identificador de host.
Así la dirección 192.168.1.1/24 (/24 es lo mismo que escribir 255.255.255.0), representa la red 192.168.1.0 y el host 1 dentro de esa red.
Cada octeto (8 bits) va a ser un número entre 0 y 255. Por cada red, la primer dirección de host corresponde al número de red y la última a la dirección de broadcast, dirección utilizada para alcanzar todos los nodos de la red. Así el host 192.168.1.1/24 pertenece a la red 192.168.1.0 con dirección de broadcast 192.168.1.255.

Las direcciones IPs pueden ser utilizadas como classful o classless. 

**Classful**

Presentan 5 clases las cuales dependen del valor de primer octeto

- Clase A es par las direcciones de 0 a 127 y presentan una máscara de 8 bits, de esta manera pueden existir hasta 128 redes con aproximadamente 16 millones de nodos cada una. Así se encuentran desde la dirección 0.0.0.0/8 a las 127.255.255.255/8 
- Clase B es para las direcciones desde 128 a 191 y presentan una máscara de 16 bits, de esta manera pueden existir hasta 16 mil redes con aproximadamente 65 mil nodos cada una. Así se encuentran desde la dirección 128.0.0.0/16 a la 191.255.255.255/16
- Clase C es para las direcciones desde a 192 a 223 y presentan una máscara de 24 bits, de esta manera pueden existir hasta 2 millones de redes con 254 nodos cada una. Así se encuentran desde la dirección 192.0.0.0/24 a la 223.255.255.255/24 
- Continúan las clases D (224 a 239) y E (240 a 255) que no se estudian acá.


Las direcciones sin clases incorpora el concepto de máscara variable. El formato de las direcciones continúa siendo el mismo, aunque la máscara no depende del comienzo de la dirección. Además de la dirección IP es necesario especificar la máscara, para que la red quede identificada. Así se puede encontrar la dirección 10.1.1.1/27, en el caso anterior era una red clase A con mascara /8, mientras que en este caso es una red con hasta 30 nodos. Las direcciones que comienzan con 244-255 siguen consideradas especiales.
Dentro del direccionamiento se reservan un conjunto de direcciones. Entre ellas encontramos las direcciones privadas. Estas direcciones pueden ser utilizadas en el ámbito de una organización, pero no van a ser reconocidas en internet. Esto significa, que si una organización utiliza direcciones privadas internamente, estas tienen que ser traducidas para ser ruteadas a través de internet , a este proceso se lo conoce como NAT. Las siguientes direcciones se encuentran reservadas para el uso privado: 10.0.0.0/8, 172.16.0.0/12, 192.168.0.0/16.

Las direcciones públicas son asignadas por la organización IANA y en la actualidad existen muy pocas direcciones disponibles. Así existe un proyecto para reemplazar la versión actual del proyecto a una nueva con 128 bits.

### El ruteo

Cuando dos nodos se encuentran en redes lógicas separadas, se necesitan dispositivos que conecten más de una red para poder comunicarlos. No necesariamente tiene que ser un solo dispositivo, sino que por el contrario pueden existir una gran cantidad de redes entre ellas, siempre y cuando existan dispositivos que vayan conectando cada una.
![[Pasted image 20260519215122.png]]

Al dispositivo que conecta dos redes se lo conoce como router, ya que enruta el tráfico entre ellas. El conocimiento de las rutas puede ser de manera estática o dinámica, en el último caso utilizando protocolos de enrutamiento. Así internet, es un conjunto de routers, con un protocolo llamado Border Gateaway Protocol (BGP) el cual ayuda a los mismo a conocer la ubicación de cada una de las redes. Para tener un orden de magnitud del tamaño actual, las tablas actuales de internet presentan alrededor de 450.000 entradas, o sea redes.

Por lo general los dispositivos presentan una o más rutas especificas para un direccionamiento, y una ruta genérica conocida como default gateaway que se identifica por 0.0.0.0 y es utilizada cuando no se tiene una ruta específica para el destino buscado. Todos los equipos de red que implementen la capa de red poseen rutas.

### Conectividad extremo a extremo

Cuando un nodo necesita conectarse con otro, primero evalúa el direccionamiento lógico del segundo. Si el mismo se encuentra en la misma red, analizará la tabla ARP para conocer si la dirección física es conocida ya que de lo contrario deberá enviar un ARP request.
Si la red no es local, buscará en la tabla de ruteo una ruta específica para dicho destino, en el caso de no existir continuará por la ruta por defecto.
Así el tráfico será enviado hacia el primer router el cual repetirá el proceso, chequeando si la red destino es local y en caso de no serla evaluando la tabla de ruteo. El proceso se repetirá hasta alcanzar el router que posea el destino directamente conectado, allí el router identificará la IP en la tabla ARP y en caso de no encontrar la misma realizará la petición ARP para posteriormente conectarse con el nodo directamente

### Protocolo TCP

Trabaja en la capa de transporte dentro del modelo OSI y TCP/IP. Este protocolo ayuda a establecer la conexión entre dos extremos y a administrar la misma. Además provee un socket.
Los sockets, también conocidos como puertos, poseen números del 0 al 65535. De estos, la organización IANA reservó los primeros 1023 para aplicaciones conocidas. Así encontramos el puerto 21 para FTP, 22 SSH, entre otros.
Se denomina servidor al equipo que tiene una aplicación corriendo de manera permanente y escuchando en un determinado puerto. A modo de ejemplo un servidor SSH, el cual tiene la aplicación SSH corriendo permanentemente y escuchando en el puerto 22. Se denomina cliente al equipo que tiene una aplicación que puede ser corrida para establecer una conexión  contra un servidor (IP) en un puerto específico. 
Cuando un cliente tiene que conectar un servidor, primero reserva un puerto local o enchufe para realizar dicha conexión Este puerto va a tener un número al azar mayor al puerto 1023 y menor al 65535. A continuación va a enviar un pedido de inicio de conexión a la dirección del servidor al puerto correspondiente. El proceso de inicio de conexión se lo conoce como "3-Way Handshake", durante el mismo el cliente y el servidor intercambian números de secuencia que utilizan para asegurar la conexión.

### Resolución de nombres, DNS

El servicio de resolución de nombres DNS, es un protocolo que realiza la conversión de nombres en direcciones IP. Es utilizado por múltiples aplicaciones para evitar el uso de IPs. Esto disminuye las configuraciones requeridas en clientes. Por ejemplo, al cambiar la IP del servidor se puede cambiar la resolución de nombres sin tener que reconfigurar la IP de los clientes.
El servicio funciona tanto sobre los protocolos de transporte TCP como UDP, en ambos casos utilizando el puerto 53. Las consultas de nombre se realizan sobre UDP, excepto que superen los 512 bytes donde son realizadas sobre TCP. Esto sucede por lo general en las transferencias de zonas entre servidores DNS, para la sincronización de las mismas.
Los servidores de DNS pueden ser configurados manualmente en los clientes u obtenidos de forma automática de un servidor DHCP durante la autoconfiguración de la IP.
Así para realizar una consulta, el cliente selecciona un puerto al azar entre 1023 y el 65535, y envía la misma vía UDP a la IP del servidor de nombres configurado en el puerto 53. Al recibir la consulta el servidor buscará en su base de datos por el nombre requerido. En caso contrario, evaluará si las consultas recursivas están permitidas para el cliente, donde el servidor realizará una consulta a otro servidor para identificar la IP. En caso de no obtener la respuesta el servidor retornará al cliente que el registro no existe.

### Protocolo HTTP

HTTP (Hypertext Transfer Protocol) es el principal protocolo utilizado en la web. El mismo define la sintaxis y la semántica que utilizan los elementos de la arquitectura web para comunicarse, es decir los clientes, servidores, proxies, etc.
Al cliente, se lo conoces como user agent. 
A la información transmitida se la conoce como recurso y se la identifica por una URL (Localizador Uniforme de Recursos). Estos pueden ser archivos, el resultado de la ejecución de un script, etc.
HTTP es stateless. 

HTTP funciona sobre el protocolo de transporte TCP, el servidor escucha en el puerto 80 y allí es donde se conecta con el navegador por defecto cuando se ingresa una dirección. En una conexión HTTP tanto el pedido como la respuesta son enviados en texto claro; así si la misma es interceptada se puede tener acceso a lo que el usuario está navegando.
Cuando las direcciones comienzan con HTTPS, el navegador va a intentar realizar la conexión al puerto 443 del servidor y además va cifrar la misma antes de comenzar a enviar datos, de esta manera si la conexión es interceptada entre los mismo, no podrá ser interpretada.
Se le puede especificar al servidor a utilizar puerto diferentes a los default, indicando los mismo al final de la dirección o el nombre 

### Métodos HTTP

La versión 1.1 del protocolo HTTP define 8 métodos:

1. HEAD
	Es similar al GET pero no devuelve contenido, solo las cabeceras. 
2. GET
	Solicita un determinado recurso y no debería ser utilizado por aplicaciones que causen efectos ya que transmite información a través de la URL agregando parámetros a la URL
3. POST
	Envía datos al servidor para que sean procesados por el recurso identificando. Los mismo serán incluidos en el cuerpo de la petición y no en el recurso. La respuesta enviada al cliente, puede ser un recurso no identificable mediante una URL.
4. PUT
	Permite guardar el contenido enviado en el recurso definido por la URL. Si dicha URL no existe el servidor considera que es un nuevo recurso, mientras que si existe actualiza el contenido como una nueva versión.
5. DELETE
	 Utilizado para que el servidor elimine un determinado recurso
6. TRACE
	Se puede utilizar para saber si existe el receptor de un mensaje y utilizar dicha información como diagnóstico.
7. OPTIONS
	Representa una petición de información sobre las opciones de comunicación disponibles para el recurso especificador 
8. CONNECT

Los dos métodos mas comúnmente utilizados por los navegadores son GET y POST, y son los dos generalmente aceptados por los servidores.

### Navegadores WEB

El navegador Web es una aplicación cliente que tiene como propósito conectarse a un servidor para realizar un pedido y mostrar la respuesta se lo denomina renderizado y se encarga de interpretar los diferentes recursos obtenidos, los cuales incluyen tecnologías del lado del cliente.
Algunos navegadores comparten el motor de renderizado, por lo que se espera que el comportamiento de un sitio sea el mismo.


### Servidores WEB

El servidor web es una aplicación que corre de manera permanente en el servidor, respondiendo por defecto conexiones de clientes en el puerto 80.
La lista de servidor es mucho más reducida que los clientes analizados anteriormente. 
La importancia de los servidores web radica no solo en la implementación del protocolo y la respuesta, sino también en las extensiones que ellos proveen. Es decir, en la característica que ofrezcan para conectarse con otros servicios como servidores de base de datos, lenguajes de scripting, etc. 

El método estándar para extender un servidor web y delegar la generación de contenidos en otros lenguajes, se lo conoce como CGI (Common Gateaway Interface). Así cuando el servidor reconoce un código que requiere una aplicación externa, prepara el entorno y llama a la aplicación que pueda entender dicho código, capturando la salida estándar. Finalmente cuando dicha aplicación se completa, el servidor retorna el resultado al cliente.
En el caso de Apache, el mismo presenta una arquitectura modular, que permite reemplazar dicha interface con módulos específicos. Existe una gran cantidad de módulos que permiten diversas funcionalidades, entre ellas encontramos la posibilidad de generar conexiones seguras SSL, autenticación vía LDAP, programación con Perl, PHP, etc.


