
![[IMG-20250530-WA0001.jpg]]

1- 

[CLIENTE] -------- Petición HTTP ----> [SERVIODR]
        <------- Respuesta HTTP ----

Tecnologías de lado del cliente (ya descritas antes)

**Lado del servidor**

 - Lenguajes de servidor: PHP, Python, Java, Node.js
 - Bases de datos: MySQL, MongoDB. Almacenan la información persistente
 - Servidor web: Apache, Nginx. Escucha y responde peticiones


La interacción a través del HTTP: el cliente realiza una Request mediante un método como GET o POST. El servidor procesa esto y devuelve una response que incluye el código de estado

Características:

Stateless: el protocolo no guarda información sobre peticiones anteriores. Cada solicitud es independiente 

Independiente del medio: puede transmitir cualquier tipo de dato, gracias a que especifica el tipo de contenido.

Basado en texto: sus encabezados son legibles en formato texto plano.


La relación del hipertexto con el origen de la web:
El hipertexto es el concepto fundamental sobre el que se creo la World Wide Web. Consiste en texto que contiene enlaces a otros textos. Tenia como objetivo principal la divulgación científica

Web 1.0: Era web estática de solo lectura. Los creadores publicitaban contenido

Web 2.0: Se centró en la participación del usuario. Nacieron las redes sociales, los blogs y las wikis. El usuario paso a ser el consumidor y el medio de producción.

Web 3.0: Se enfoca en que las máquinas puedan "entender" el significado de los datos. Incluye la integración de IA, bases de datos descentralizadas.


## Practica


```

function validarApellido(){
	let ape = document.getElementById("apellido")
	
	if (ape === ""){
		alert("El campo esta vacío");
		return false;
	} else {
		alert("Apellido completado");
		return true;
	}
}

```

CSS


```
contenedor{
	background-color: yellow;
}

#menu{
	float: left;
	width: 30%;
}

#contenido{
	float: right;
	width: 70%;
}

#header h1{
	font-size: 20px;
}

#menu a {
	color: green;
	font-weight: bold;
}

#contenido h2{
	color: gray;
	font-size: 15px;
}

#footer {
	background-color: black;
	border: 2px solid blue;
	clear: both;
}

.mail {
	color: red;
}

```
