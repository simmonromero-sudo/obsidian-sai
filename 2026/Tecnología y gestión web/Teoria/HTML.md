## ¿Qué es?

HTML (Hypertext Markup Language), hace referencia al lenguaje de marcado predominante para la elaboración de páginas web que se utiliza para describir y traducir la estructura y la información en forma de texto, así como para complementar el texto con objetos ales como imágenes. El HTML se escribe en forma de etiquetas, rodeadas por corchetes angulares (<>). HTML también puede describir, hasta un cierto punto, la apariencia de un documento, y puede incluir un script, el cual puede afectar el comportamiento de navegadores web y otros procesadores HTML.

### Historia

La primera descripción de HTML disponible públicamente fue un documento publicado por Tim Berners-Lee en 1991 (HTML Tags). Describe 22 elementos que incluyen el diseño inicial y relativamente simple de HTML. Trece de estos elementos todavía existen en HTML 4

La primera propuesta oficial para convertir HTML en un estándar se realizó en 1993 por IETF, aunque consiguieron avances significativos, ninguna de las dos propuestas de estándar, llamadas HTML y HTML+ consiguieron convertirse en el estándar.

En 1995, el organismo IETF organiza un grupo de trabajo de HTML y consigue publicar, el 22 de septiembre de ese mismo año, el estándar HTML 2.0 A pesar de su nombre, HTML 2.0 es el primer estándar oficial de HTML.

A partir de 1996, los estándares de HTML los publica otro organismo llamado W3C. La versión HTML 3.2 se publicó el 14 de enero de 1997 y es la primera recomendación de HTML publicada por el W3C. Esta revisión incorpora los últimos avances de las páginas web desarrolladas hasta 1996, como applets de Java y texto que fluye alrededor de las imágenes.

El 24 de Abril de 1998 se publicó  HTML 4.0 y supone un gran salto desde las versiones anteriores. Entre sus novedades más destacas se encuentran las hojas de estilos CSS, la posibilidad de incluir pequeños programas o scripts en las páginas web, mejora de la accesibilidad de las páginas diseñadas, tablas complejas y mejoras en los formularios.  
La ultima especificación oficial de HTML se publicó el 24 de diciembre de 1999 y se denomina HTML 4.01, desde esta versión W3C se detuve y se avoco al desarrollo del estándar XHTML y se organizaron en una nueva asociación llamada WHATWG


#### Lenguaje de etiquetas

HTML es un lenguaje de etiquetas y las páginas web habituales están formadas por cientos o miles de pares de etiquetas. 
La principal ventaja de los lenguajes de etiqueta es que son muy sencillos de leer y escribir por parte de las personas y de los sistemas electrónicos. La principal desventaja es que pueden aumentar mucho el tamaño del documento, por lo que en general se utilizan etiquetas con nombres muy cortos.

Para guardar la info. con formato en archivos digitales, el archivo electrónico almacena tanto los contenidos como la información sobre el formato de esos contenidos. Por ejemplo dividir un texto en párrafo y remarcar algunas palabras

(<)párrafo(>)
Contenido de texto con (<)importante(>) algunas palabras (<)importante(>) resaltadas de forma especial.
(<)párrafo(>)

### Documento HTML

Las páginas HTML se dividen en dos partes: la cabecera y el cuerpo. La cabecera incluye información sobre la propia página. El cuerpo de la página incluye todo sus contenidos, como párrafos de texto e imágenes.

### Atributos

**Atributos básicos:**

Se pueden utilizar en prácticamente todas las etiquetas de HTML.
Hoy en día se usan los atributos class y id de forma masiva.

**Atributos para internalización:** 

Los utilizan páginas que muestran sus contenidos en varios idiomas o aquellas que quieren indicar de forma explicita el idioma de sus contenidos.
En las páginas XHTML, el atributo xml:lang tiene más prioridad que lang y es obligatorio incluirlo siempre que se incluye el atributo lang. 

internalización = i18n

**Atributos de eventos:**

Sólo se utilizan en las páginas web dinámicas creadas con JavaScript.
Cada vez que el usuario hace algo se produce un evento en el navegador.

**Atributos para los elemento que pueden obtener el foco:**

Cuando el usuario selecciona un elemento de la interfaz de la aplicación, se dice que "el elemento tiene el foco del programa". Si por ej. un usuario pincha con su ratón sobre un cuadro de texto y comienza a escribir, ese cuadro tiene el foco del programa, llamado "focus" en inglés.

### Elementos HTML

Además de etiquetas y atributos, HTML define el término elemento para referirse a las partes que componen los documentos HTML.
Un elemento esta formado por:

- Una etiqueta de apertura
- Cero o más atributos
- Texto encerrado por la etiqueta (opcional)
- Una etiqueta de cierre


```
<p class=”normal”>Esto es un parrafo</p>
```

El lenguaje HTML clasifica a todos los elementos en dos grupos: elementos en línea y elementos en bloque,
La principal diferencia entre los dos tipos de elementos es la forma en la que ocupan el espacio disponible en la página. Los elementos de bloque siempre empiezan en una nueva línea y ocupan todo el espacio disponible hasta el final de la línea, aunque sus contenidos no lleguen hasta el final de la línea. 
Los elementos de línea sólo ocupan el espacio necesario para mostrar sus contenidos.
La mayoría de elementos de bloque pueden contener en su interior elementos en línea y otros elementos de bloque. Los de línea solo de línea o texto

Los elementos pueden clasificarse en:

- Básicos
- Texto
- Enlaces
- Listas
- Imágenes
- Tablas
- Formularios
- Embebidos
![[Pasted image 20260520135446.png]]


### Estructura HTML

Se agrupa los elementos de la página en diferentes divisiones en función de su finalidad: la cabecera, la zona de contenidos, la zona lateral para el menú y otras secciones menores, la zona de pie de página, etc.

Se usa la etiqueta "div" para agrupar los elementos que forman cada zona o división de la página

- Contenedor (wrapper)
- Cabecera (header)
- Contenido (content)
- Menú (menu)
- Pie (Footer)
- Lateral (sidebar)


```
<div id="contenedor">
	<div id="cabecera">
	...
	</div>
	<div id="contenido">
		<div id="menu">
		...
		</div>
		...
	</div>
	<div id="pie">
	...
	</div>
</div>


```



##### Metainformación

Las páginas y documentos HTML incluyen más información de la que los usuarios ven en sus pantallas. Estos datos adicionales siempre están relacionados con la propia página. Se incluye en la sección de cabecera (head)

**Estructura de la cabecera**


```
<head>
	<!-- Zona de etiquetas META -->
	<meta http-equiv="Content-Type" content="text/HTML; charset=UTF-8" />
	<!-- Zona de título -->
	<title>El título del documento</title>
	<!-- Zona de recursos enlazados (CSS, RSS, JavaScript) -->
	<link rel="stylesheet" href="#" type="text/css" media="screen" />
	<link rel="stylesheet" href="#" type="text/css" media="print" />
	<link rel="alternate" type="application/rss+xml" title="RSS 2.0" href="#" />
	<script src="#" type="text/JavaScript"></script>
</head>

```


##### Metadatos

Una de las partes más importantes de la metainformación de la página son los metadatos, que permiten incluir cualquier información relevante sobre la propia página.
Cada página tiene libertada absoluta para definir los metadatos que considere adecuados, la etiqueta por definición es (meta).

#### Doctype

El estándar XHTML deriva de XML.
Uno de los conceptos fundamentales de XML es la utilización del DTD o Document Type Definition.
Un DTD es un documento que recoge el conjunto de normas y restricciones que deben cumplir los documentos de un determinado tipo.
El conjunto de normas obligaciones y restricciones que se deben seguir al crear un documento de un determinado tipo, se recogen en su correspondiente DTD. El estándar XHTML define el DTD que deben seguir las páginas y documentos XHTML. En este documento se definen las etiquetas que se pueden utilizar, los atributos de cada etiqueta y el tipo de valores de cada atributo. Se emplea una etiqueta llamada doctype, único elemnto incluido fuera de la etiqueta HTML.