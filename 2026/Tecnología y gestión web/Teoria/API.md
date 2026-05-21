Application Programming Interface 

Conexión entre dos sistemas. `Ejemplo: comensal<->Mozo<->Cocina 
Interfaz de software que permite comunicar a dos programas. 
Tipos: 

- SOAP
- RCP
- CORBA
- REST
![[Pasted image 20260520150831.png]]

### REST

No es un estándar, son recomendaciones
Paradigma Cliente/Servidor: sistema A realiza HTTP Request a una URL ubicada en sistema B, quien devuelve un HTTP Response
Stateless: No guarda estado. El response debe contener toda la información necesaria para resolver el pedido.
Abstracción: el cliente solicitante no necesita saber qué hay del otro lado.
![[Pasted image 20260520151054.png]]

### RESTful

- Una URL
	- Es el recurso de HTTP
- Un método HTTP
	- Utiliza los métodos de HTTP GET, POST, PUT, DELETE
- Headers HTTP 
	- Información de autenticación o cookies pueden ser incluidas en los headers
- Body Data
	- La información es transmitida en el body (payload) como lo hace un `<form>` en HTML


### Métodos HTTP

| Método HTTP | Create, Read, Updtate, Delete | Acción                          |
| ----------- | ----------------------------- | ------------------------------- |
| GET         | read                          | Devuelve los datos solicitados  |
| POST        | create                        | Crea un nuevo registro          |
| PUT         | update                        | Actualiza un registro existente |
| DELETE      | delete                        | Elimina un registro existente   |
Ejemplos:

Request GET a /usuarios/ devuelve todos los usuarios del sistema

Request POST a /usuarios/123 crea el usuario con ID=123 con la información del body

Request PUT a /usuarios/123 actualiza el usuario con ID=123 con la información del body

Request DELETE a /usuarios/123 elimina el usuario con ID=123 

### Request/ Response

**Request**

- Se realiza un pedido HTTP
- La URL es el recurso
- El método es la acción: GET consulta, POST crear, PUT modifica

Ejemplo:  https://official-joke-api.appspot.com/jokes/programming/random
- Request URL: https://official-joke-api.appspot.com/jokes/programming/random
- Request Method: GET
- Status Code: 200

**Response**

- Se devuelve el estado: status code
- Los datos se cargan en el payload. Lo más usual es JSON

- Status Code: 200
- [{"id":379,"type":"programming","setup":"A programmer puts two glasses on his bedside table before going to sleep.","punchline":"A full one, in case he gets thirsty, and an empty one, in case he doesn’t."}]
