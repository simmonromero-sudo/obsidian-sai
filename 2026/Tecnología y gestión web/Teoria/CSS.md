
La evolución de CHSS, propuesta entre finales de 1994 y 1995 por Lie y Bos.

CSS (Cascading Style Sheets), define estilos para los elementos de HTML, estos fueron añadidos en HTML 4.0

Cuando se añadieron etiquetas font o atributos de color para la especificación HTML el desarrollo se hizo tedioso, para resolver este proceso se creó CSS, los archivos de estilo se almacenan en un archivo independiente CSS.

CSS permite separar el contenido del formato. Este concepto nos permite trabajar de las misma manera que se utiliza para la reutilización de software: si llamamos de muchos lugares diferentes a la misma definición, cono sólo modificar dicha definición, tendrá impacto en todos los lugares donde es llamada.

Se puede incluir el CSS al HTML de varias formas

1. Incluirlo en el mismo documento, esta es la forma menos utilizada y la peor, ya que tiene los mismo problemas que la utilización de etiquetas HTML para dar formato.
2. Incluir CSS en el mismo documento HTML. Los estilos se definen dentro de la cabecera del documento (sección head) y se utiliza la etiqueta (style)
3. Definir CSS en un archivo externo. Todos los estilos CSS se incluyen en un archivo tipo CSS que las páginas HTML enlazan mediante la etiqueta (link) 

#### Sintaxis 

Una regla CSS consta de dos partes principales: un selector y una o más declaraciones 
![[Pasted image 20260520141459.png]]

Se puede aplicar los mismos estilos a más de una etiqueta, se pueden encadenar selectores
```
h1 {
  color: #8A8E27;
  font-weight: normal;
  font-family: Arial, Helvetica, sans-serif;
}
h2 {
  color: #8A8E27;
  font-weight: normal;
  font-family: Arial, Helvetica, sans-serif;
}
h3 {
  color: #8A8E27;
  font-weight: normal;
  font-family: Arial, Helvetica, sans-serif;
}

o de esta forma

h1, h2, h3 {
  color: #8A8E27;
  font-weight: normal;
  font-family: Arial, Helvetica, sans-serif;

```


**Selector Descendente**

Selecciona los elementos que se encuentran dentro de otros elementos. Es decir responde a la jerarquía de los elementos dentro del documento


```
<p>
  ...
  <span>texto1</span>
  ...
  <a href="">...<span>texto2</span></a>
  ...
</p>

```

El selector p span selecciona tanto a texto1 como a texto2. La única condición es que un elemento debe estar dentro de otro elemento, sin importar el nivel de profundidad. Al resto de los elementos span que no estén dentro de p no se les aplicara nada.

##### **Selectores de id y class**

Además de establece un estilo para un elemento HTML, CSS le permite especificar su selector3es propio llamado "id" y "class"

**ID**

El selector ID se utiliza para especificar un estilo para un elemento único y exclusivo, utiliza el atributo id del elemento HTML y se define con un "#"

**Class**

El selector de clase se utiliza para especificar un estilo para un grupo de elementos. Establece un estilo particular para los elementos HTML con una misma clase. Se define con un "."

#### Herencia

Una de las características mas importantes de CSS es la herencia de estilo que obtiene cada elemento. El concepto es similar a la "herencia" en POO. 
El orden para aplicar las "cascadas" de estilos es del elemento al documento en general. Es decir, si tengo una regla general, pero un elemento en particular deseo aplicarle otro estilo, generando una regla para ese elemento se impone sobre el resto.
```
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN"
  "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd">
<html xmlns="http://www.w3.org/1999/xhtml">
<head>
<meta http-equiv="Content-Type" content="text/html; charset=iso-8859-1" />
<title>Ejemplo de herencia de estilos</title>
<style type="text/css">
  body { color: blue; }
</style>
</head>
 
<body>
  <h1>Titular de la página</h1>
  <p>Un párrafo de texto no muy largo.</p>
</body>
</html>
```

### Propiedades

CSS es tan flexible que permite indicar las medidas y colores de muchas formas diferentes.
CSS divide las unidades de medida en dos grupos: absolutas y relativas.


**Absolutas**

- in, pulgadas  (2.54 cm)
- cm, centímetros
- mm, milímetros
- pt, puntos (1/72 in)
- pc, picas (4.23 mm)

Su valor es directamente el valor que se debe utilizar, sin necesidad de realizar cálculos intermedios. Son muy poco flexibles

**Relativas**

- em, relativa respecta del tamaño de la letra del elemento
- ex, relativa respecto de la altura de la letra x del tipo y tamaño de letra del elemento
- px, relativa respecto de la resolución de la pantalla del dispositivo

Tiene como virtud si dinamismo