
![[Pasted image 20260521153102.png]]

## Teoría

1- **Tecnologías**

Cliente:

HTML: usado para darle cuerpo a toda la interfaz grafica del browser, utilizando tablas o listas para desplegar a los clientes

CSS: agrega diseño visual a toda la interfaz HTML

JavaScript: recibe los datos del servidor y manipula el DOM para inyectar la información de los clientes dentro del HMTL

Usaría peticiones HTTP asincrónicas en segundo plano. Cuando el usuario hace clic en "Ordenar", JavaScript dispara el evento, envía la solicitud al servidor y al recibir la respuesta actualiza  únicamente la sección de HHTML donde está la lista de clientes, necesidad de recargar


2- 

**Utility**

Se basa en el concepto de "pago bajo demanda". En lugar de cobrar una tarifa plana o suscripción mensual fija, se le cobra al usuario o empresa exactamente por la cantidad de recursos o servicios que consume.

**Infomediary**

Estas empresas actúan como intermediarias de información. Recopilan. analizan y estructuran grandes volúmenes de datos sobre consumidores o mercados, y liego venden esta información o análisis a otras empresas. El usuario cede sus datos a cambio de un servicio,



```

<!DOCTYPE html>

<html lang="es">
<head>
	<meta charset="UTF-8">
	<title> Parcial 4 </title>
</head>

<body>
	<header id="datos">
	
	<p class="perso">Nombre: Andres </p>
	<p class="perso">Apellido: Apicultor </p>
	<p class="perso">Legajo: putin </p>	
	</header>

	<div>
		<aside>
			<button onclick="practica()">Practuca </button>
			<button onclick="teoria()">Teoría </button>
		</aside>
	</div>
	
	<main id="main">
		
	</main>
	
<script>
	
	const frase = document.getElementById('main');
	const header = document.getElementById('datos')
	
	function teoria(){
		frase.innerHTML = "<p> TADEO ES GAY </p>";
	}
	
	function practica(){
		header.innerHTML = "<code> header p {color:red;}</code>";
		header.style.color = "red"
	}
	
</script>

</body>
```



```
const frase = document.getElementById('main');
	const head = document.getElementById('datos'); // Tu variable se llama 'head'
	
	function teoria(){
		frase.innerHTML = "<p> TADEO ES GAY </p>";
	}
	
	function practica(){
	
		head.style.color = "red";
	}
```
