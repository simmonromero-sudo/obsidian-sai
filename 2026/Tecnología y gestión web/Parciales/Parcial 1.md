
![[Pasted image 20260521125055.png]]

1) 
```
<link rel="stylesheet" href="estilos.css">
<script src="validar.js"></script>

<body>
	<h2>Formulario de calificaciones</h2>

	<form action="promedio.php" method="POST" onsumbit="retur validar()">  
		<label for="nombre">Nombre:</label>
		<input type="text" id="nombre" name="nombre">
		
		<label for="apellido">Apellido: </label>
		<input type="text" id="apellido" name="apellido">
		
		<label for="materia">Materia</label>
		<input type="text" id="materia" name="materia">
		
		<label for="nota1">Nota 1: </label>
		<select id="nota1" name="nota1">
			<option value="1">1</option> <option value="2">2</option>
			<option value="3">3</option> <option value="4">4</option>
			<option value="5">5</option> <option value="6">6</option>
			<option value="7">7</option> <option value="8">8</option>
			<option value="9">9</option> <option value="10">10</option>
		</select>
		
		<label for="nota2">Nota 2:</label>
		<select id="nota2" name="nota2">
			<option value="1">1</option> <option value="2">2</option>
			<option value="3">3</option> <option value="4">4</option>
			<option value="5">5</option> <option value="6">6</option>
			<option value="7">7</option> <option value="8">8</option>
			<option value="9">9</option> <option value="10">10</option>			
		</select>
		
		<label for="nota3">nota3</label>
		<select id="nota3" name="nota3">
			<option value="1">1</option> <option value="2">2</option>
			<option value="3">3</option> <option value="4">4</option>
			<option value="5">5</option> <option value="6">6</option>
			<option value="7">7</option> <option value="8">8</option>
			<option value="9">9</option> <option value="10">10</option>			
		</select>	
		
		<button type="sumbit">Enviar Notas</button>
	</form>


</body>

```


2) 

```
//Función validar.js

function validar(){

	let nombre = document.getElementById("nombre").value.trim;
	let apellido = document.getElementById("apellido").valu.trim;
	let materia = document.getElementById("materia").value.trim;
	
	
	if (nombre === "" || apellido === "" || materia === ""){
		alert("Error: los campos Nombre, Apellido y Materia no pueden estar vacios");
		return false;
	}
	
	if (nota 1 === 0 || nota2 === 0 || nota3 === 0){
		alert("Error: debe seleccionar una calificación valida");
		return false;
	}
	return true;
}

```

4) Tecnologías del lado del cliente

En el paradigma cliente servidor, el "cliente" es el navegador web (Chrome, Edge, etc.). Las tecnologías del lado del cliente son aquellas que se descargan y ejecutan directamente en el dispositivo del usuario para armar y dar vida a la interfaz. Las principales son;

HTML, es lenguaje de marcado, le da toda la estructura a la pagina. Define los elementos existentes en la misma
CSS, agrega los estilos a los respectivos elementos del HTML
JavaScript, es la capa de comportamiento. Lenguaje que permite reaccionar a eventos del usuario

5) Evolución en tecnologías del cliente

HTML: en sus comienzos era un lenguaje muy rígido, únicamente para compartir documentos académicos con hipervínculos. Con su evolución fue agregando etiquetas, elementos y atributos, haciendo así de este un lenguaje sencillo de escribir e ideal para el diseño web. 

CSS: surgió por la necesidad de separar en un archivo fuera del HTML los estilos de una página ya que hacerlo dentro de las etiquetas del mismo lo hacia una practica tediosa. Con el tiempo evoluciono de ser un modelo muy básico (colores, fuentes, etc.) a CSS3, ofreciendo CSS Grid, Flexbox y otras funcionalidades avanzadas.

JavaScript: Nació como un script básico para hacer pequeñas validaciones o efectos simples en eventos, hoy en día permite crear SPAs completas, consumiendo APIs en tiempo real y manipulando el DOM de forma compleja.

6) Modelo TCP/IP

**Capas**

1. Capa de acceso a la red: es la capa inferior. Define cómo los datos se trasmiten físicamente a través de la red. Trabaja con direcciones MAC
2. Capa de internet: se encarga del direccionamiento lógico y el enrutamiento
3. Capa de transporte: garantiza que los datos lleguen de extremo a extremo, fragmentándolos en segmentos. Puede asegurar que lleguen sin errores y en orden o enviarlos rápidamente sin verificación 
4. Capa de aplicación: es la mas alta y la que interactúa directamente con los programas de software


b) Abrís una web 

1. Capa de aplicación: el navegador genera un mensaje pidiendo la página usando el protocolo HTTP
2. Capa de transporte: ese mensaje HTTO pasa a esta capa, que lo encapsula usando TCP. Le asigna un puerto de destino 
3. Capa de internet: los segmentos bajan a esta capa y se encapsulan en "paquetes". Acá se les añade la dirección IP de origen y destino
4. Capa de acceso a la red: los paquetes se encapsulan en tramas. Se les añade dirección física MAC de tu router para que viajen por el cable de red o Wi-Fi    