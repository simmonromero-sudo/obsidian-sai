
![[Pasted image 20260521134715.png]]

1) **Tecnologías  a utilizar del lado del cliente:**

HTML: estructuración de todos los elementos y etiquetas de la página, proveerá un `<div>` donde se dibujará el gráfico y alojará el botón "Actualizar"

CSS: encargada de todo el diseño visual de la página 

JavaScript: motor de la lógica del cliente. Se encargará de consumir la API, procesar los datos recibidos y usar alguna librería para renderizar el gráfico. También maneja el evento al dar click al botón actualizar.


**Tecnologías del lado del servidor:**

API: el servidor que expone los datos del Bitcoin. Recibe las peticiones del cliente, consulta su base de datos y devuelve la información


**Botón actualizar:**
Cuando el usuario hace clic en "Actualizar", JavaScript intercepta ese evento y realiza una petición HTTP asincrónica a la API del servidor. Mientas tanto, el usuario puede seguir interactuando con la página. Cuando el servidor responde con los datos, JavaScript actualiza el DOM sin necesidad de cargar todo el documento HTML

+------------------------------------+                                        +----------------------------------+
     CLIENTE (Navegador Web)                                                      SERVIDOR (API Externa)    
	                            Petición                                      
  1 HTML (Estructura/Botón)        --------------------------->   1. Backend (PHP, Node, Python)  |
  2 CSS (Estilos)                                                                          2. Base de Datos (Precios BTC)  |
  3 JavaScript (Lógica e Interfaz)    <---------------------------                               
4 Librería Gráfica (ej. ChartJS)                 Respuesta                                      
+------------------------------------+                                          +----------------------------------+


2) 5 bloques fundamentales del Canvas:

1- Segmento de Mercado (Cliente): define quiénes son los diferentes grupos de personas o entidades a los que la empresa dirige sus esfuerzos. Responde a la pregunta: ¿Para quién estamos creando valor?

2- Propuesta de valor: es el conjunto de productos y servicios que crean valor para un segmento de mercado específico. Es la razón por la cual los clientes eligen una empresa sobre otra

3- Canales: describe cómo la empresa se comunica y llega a su segmento de clientes para entregar propuestas de valor.

4- Relaciones con los clientes: define el tipo de relación que la empresa establece con cada segmento de mercado. Puede ser desde asistencia personal, autoservicio, hasta comunidades

5- Fuentes de ingreso: representa el flujo de caja que la empresa genera a partir de cada segmento de clientes


### Practica

1) JavaScript


```

function calcularOperacion(){
	let inputOp = document.getElementById("operacion").value.trim().toUpperCase();
	let inputNum1 = document.getElementById("numero1").valu.trim();
	let inputNum2 = document.getElementById("numero2").valu.trim();
	
	if (input === "" || inputNum2 === "" ){
		return "Amvos campos o uno de ellos está vacio y no puede realizarse ninguna operación"
	}
	
	let num1 = parseFloat (inputNum1);
	let num2 = parseFloat (inputNum2);
	
	if (inputOperacion === "SUMA"){
		return num1 + num2
	} else if (inputOperacion === "RESTA"){
		return num1 - num2;
	} else {
		return `No se puede realizar una operación valida`
	}
}
```


```

<body>
	<h2>Calculadora</h2>

	<div>
		<label for="numero1">Numero 1: </label>
		<input type="text" id="numero1">
	</div>
	
	<div>
		<label for="numero2">Numero 2: </label>
		<input type="text" id="numero2">
	</div>
	
	<div>
		<label for="operacion">Operación: </label>
		<input type="text" id="operación">
	</div>
	
	<button onclick="alert(calcularOperacion())">Calcular</button>
		
</body>

```
