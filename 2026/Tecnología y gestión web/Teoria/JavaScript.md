
### Introducción 

JavaScript es un lenguaje de programación interpretado, orientado a objetos, imperativo y débilmente tipado.
Se ejecuta principalmente del lado del cliente (en el navegador) para crear interfaces dinámicas y mejorar la interacción.
Su sintaxis es similar a C, pero no tiene relación directa con Java; el nombre fue una estrategia de marketing de Netscape en lo 90'.
La estandarización oficial del lenguaje se maneja bajo el nombre ECMAScript (estándar ECMA-262)

##### Inclusión en documentos XHTML 

Archivo externo: se enlaza usando  `<script type="text/javascript" src="codigo.js"></script>`. Mantiene el código HTML limpio y permite reutilizar el script en varias paginas

En la cabecera: se define el bloque de código entre etiquetas `<script>` dentro del `<head>`. Es útil para sentencias específicas de un solo documento.

En línea (No recomendado): directamente como atributo de un elemento (ejemplo: `onclick="alert('hola')"` ). Ensucia el código y dificulta el mantenimiento posterior.

### Sintaxis y variables

- **Sensibilidad:** JavaScript distingue estrictamente entre mayúsculas y minúsculas
- **Flexibilidad:** Ignora los espacios en blanco y nuevas líneas sobrantes, y no obliga a terminar cada sentencia con punto y coma (aunque es buena practica)
- **Declaración:** se crear mediante la palabra reservada `var`. Si definís una variable sin `var` dentro de una función, esta se convierte automáticamente en una variable global.


### Funciones integradas

| Categoría | Función                       | Descripción                                                                   |
| --------- | ----------------------------- | ----------------------------------------------------------------------------- |
| Cadenas   | `length`                      | Devuelve la cantidad de caracteres de un texto                                |
| Cadenas   | `toUpperCase()/ toLoweCase()` | Transforma el texto a mayúsculas o minúsculas                                 |
| Cadenas   | `indexOf(caracter)`           | Devuelve la primera posición donde se encuentra un carácter (-1 si no existe) |
| Cadenas   | `substring(inicio, final)`    | Extrae una porción de una cadena de texto                                     |
| Cadenas   | `split(separador)`            | Convierte un texto en un array, cortándolo por el separador indicado          |
| Arrays    | `length`                      | Devuelve la cantidad de elementos almacenados en el array                     |
| Arrays    | `shift() / unshift()`         | Elimina o agrega elementos al principio del array respectivamente             |
| Números   | `isNaN()`                     | Comprueba si un valor NO es un Número para proteger la ejecución              |
| Números   | `toFixed(digitos)`            | Devuelve el número redondeado a la cantidad de decimales indacada.            |

### DOM

El DOM transforma el documento web en un árbol jerárquico de nodos interconectados. Los tipos de nodos principales son Document, Element, Attr, Text y Comment.

- Acceso a elementos: se realiza principalmente con `getElementById(), getElementsByTagName() o getElementsByName()`
- Creación de nodos: requiere usar `createElement()` para generar la etiqueta, `createTextNode()` para el contenido textual, y sumarlos a la pagina `appendChild()`.
- Eliminación: Se utiliza la función `removeChild()` invocada siempre desde el nodo padre del elemento a eliminar.

### Eventos y manejadores

Los eventos permiten que la aplicación web reaccione a la interacción del usuario.

Los manejadores son las funciones asignadas a un evento. Pueden definirse de tres maneras
1. Como atributos directamente en el HTML
2. Asignando funciones externas en el HTML
3. De forma semántica en JavaScript `elemento.onclick = funcion;`

**Contexto** (`this`): dentro de un evento, la palabra reservada (this) hace referencia directa al elemnto que disparó ese evento.

### Manejo de formularios y validación

Los navegadores agrupan los formularios de la página en un array llamado `document.forms`, y dentro de cada uno, los campos están en el array `elements`.

**Lectura de datos:** se utiliza la propiedad `value`
- Checkbox/ Radiobuttons: se verifica si están marcados con la propiedad booleana `checked`
- Selects: se combina la propiedad `selectedIndex` con el array `options` para capturar el valor elegido.

**Validación antes del envío:** Sirve para detectar errores del usuario sin depender del servidor.
Se captura el evento en la etiqueta `<form onsubmit="return validacion()">`, si la función `validacion()` devuelve `true`, el formulario se envía al servidor. Si devuelve `false`, el envío se frena y se mantiene e la página actual.

#### JQuery

Es una biblioteca JavaScript de código abierto que simplifica enormemente la manipulación del DOM, el manejo de eventos y las peticiones AJAX. 
Se interactúa pasándole selectores (similares a los de CSS) a la función alias `$() o JQuery()` para obtener conjuntos de nodos.
Se acostumbra asegurar que todo el HTML esté cargado antes de ejecutar código usando la sentencia `$(document).ready()`
