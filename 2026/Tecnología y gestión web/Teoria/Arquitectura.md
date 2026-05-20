
### Modelo de redes (OSI vs TCP/IP)

Para que las computadoras se entiendan, la comunicación se divide en "capas". Es como enviar una carta por correo: escribe el mensaje, lo pones en un sobre, le pones la dirección y el cartero lo lleva.

- **Modelo OSI:** Es el modelo teórico de 7 capas. Define desde la señal eléctrica (capa física) hasta las aplicaciones de uso diario.
- **Modelo TCP/IP**: Es el modelo real que usa internet. Es más simple y agrupa las capas superiores en una sola llamada "Capa de aplicación".
- **Datos, segmentos, paquetes, tramas, bits:** Son las nombres que recibe la información a medida que baja por las capas. Un "paquete" es lo que lleva la dirección IP, mientras que un "bit" es el impulso eléctrico. 
#### Direccionamiento IP

Cada dispositivo en internet necesita una dirección única.

Las clases A,B y C son formas de organizar las IPs según el tamaño de la red.
- **Clase A:** Para redes gigantes (como gobiernos)
- **Clase B:** Para empresas medianas/grandes.
- **Clase C:** Para redes hogareñas o pequeñas oficinas.
- **Clases D y E:** Son para usos especiales (multicast y experimentos)

### Protocolo HTTP

HTTP es el producto que permite que tu navegador le pida una página al servidor

**Propiedades:** es "stateless", lo que significa que el servidor no "recuerda" quién sos entre una petición y otra (para eso existen las cookies)

##### HTTP Request

**Estructura** 
- Request
	- GET, POST, PUT, DELETE
- Headers 
	- Información extra (que navegador usas, que idioma preferís)

##### HTTP Response

El servidor responde con un código de estado

- 200 OK: todo salió bien
- 300: Redirección
- 400: Error del cliente (Escribiste mal la URL)
- 500: Error del servidor (La web se rompió internamente)

#### HTTPS

Encripta la comunicación entre el cliente y el servidor

Es HTTP pero cifrado. Nadie en el medio puede leer tus datos.
- Handshake: Antes de enviar datos, el cliente y el servidor se ponen de acuerdo en una "clave secreta" usando certificados digitales.
- TLS/SSL: Son las tecnologías que hacen posible el cifrado. SSL es el nombre viejo, TLS es el actual.

#### Herramientas de análisis

- **Wireshark:** Permite ver los paquetes reales viajando por el cable. Es como poner un micrófono en la línea telefónica.
- **Firebug/DevTools:** Son las herramientas que vienen en el navegador (f12) para ver el código HTML, CSS y las peticiones de red.

#### Clientes y Servidores

- **Navegadores:** El mercado está dominado por Chrome (Blink), seguido por Safari y Firefox. Cada uno tiene su propio motor para dibujar la web.
- **Servidores WEB:** Son los programas que entregan las páginas. Los lideres son Apache (el clásico) y **Nginx** (el moderno y rápido)

#### QUIC

Protocolo inventado por Google, utiliza un protocolo mas rápido para los Request.

#### Arquitectura tradicional

La arquitectura tradicional de la web es el cliente servidor, utiliza ADC, gestiona la peticiones si una página web esta muy cargada la deriva a otro servidor.

##### Contenedores y Api's

Utiliza los recursos propios de la maquina para crear un contenedor que por ej., guarde las imágenes de Linux/ Windows y se compartan dentro del mismo para todo lo que se necesite.

También están los **microservicios**, si una página es monolítica si se cae algo puede romper toda la aplicación, en cambio si la separamos en microservicios nos permite ser mas robusto a errores.
#### Arquitectura moderna: Serverless

No se alquila un servidor, solo subís un pedazo de código y a nube (AWS, Azure) lo ejecuta solo cuando alguien lo necesita. 




