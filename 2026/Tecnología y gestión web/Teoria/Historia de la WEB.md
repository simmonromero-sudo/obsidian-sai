### Definiciones
-------
#### Hipertexto

Conjunto estructurado de textos, gráficos, etc., unidos entre sí por enlaces y conexiones lógicas.

#### Web

Servicio que funciona sobre internet y se le considera una interface para utilizar la red.
![[Pasted image 20260519193428.png]]

#### WEB 1.0
- 1994-1997
- Páginas estáticas
- Sitios no interactivos
- Uso de framesets
- Extensiones propias del HTML
- Libros de visitas online
- Botones GIF
- Aplicaciones propietarias

#### WEB 1.5
- 1997-2003
- Páginas dinámicas
- Lenguajes de desarrollo en servidor: PHP, ASP, JSP
- Lenguajes de desarrollo en el cliente: JS, VBScript
- Lenguajes complementarios: XML, XHTML, CSS
- Utilización de BDD

#### WEB 2.0

- 2003-Hoy
- La World Wide Web como plataforma
- Aprovechar la inteligencia colectiva
- La gestión de base de datos como competencia básica
- El fin del ciclo de las actualizaciones de visiones del software
- Modelos de programación ligera. Búsqueda de la simplicidad
- El software no limitado a un solo dispositivo
- Experiencias enriquecedoras del usuario

#### WEB 3.0 / 5.0

- Web Semántica
- Inteligencia artificial
- Evolución al 3D
- HTML5/CSS3

---

#### La era de la IA

Es el avance tecnológico más importante desde la interfaz gráfica de usuario (Presentada en 1980 por Bill Gates).
Una nueva forma de interactuar con el cómputo.

**WEB 1.0**: Web de solo lectura. El software interactuaba simplemente como el papel estático donde los expertos publicaban información.

**WEB 2.0**: El paradigma del prosumidor. El software se convirtió en el cartero o puente que conectaba personas para intercambiar ideas. 

**LLM**: La frontera actual. El software ya no solo enruta el mensaje, lo entiende, sintetiza y genera. Pasamos de conectar personas a conectar ideas.

![[Pasted image 20260519194346.png]]

#### Diferencias entre analizar y crear


| IA Analítica                           | IA Generativa                               |
| -------------------------------------- | ------------------------------------------- |
| Dominio histórico del software         | Creación de nuevo valor                     |
| Detectar fraudes                       | Código, diseño, redacción                   |
| Recomendar videos                      | Reservado previamente a la cognición humana |
| Encontrar patrones en datos existentes |                                             |
### Word2vec: De caracteres a vectores semánticos

Entendiendo la matemática detrás del procesamiento del lenguaje natural (NLP)
#### Enfoque tradicional: Bag of Words (BoW)

Codificamos cada texto extrayendo el vocabulario completo y marcando la frecuencia de aparición. Pasamos de caracteres a una matriz dispersa.
![[Pasted image 20260519194739.png]]

**Puntos ciegos**

Sitios aislados: Los sinónimos son tratados como entidades 100% independientes sin relación matemática.

Perdida de Contexto: "Muy bueno" "NO muy bueno" Al contar palabras aisladas, se destruye el **orden estructural**. La maquina ignora qué palabra está negando el "NO"

#### Embbedings

Se abandona el conteo discreto. Asigna un vector continu0 de 300 dimensiones a cada palabra. En este espacio matemático, las palabras con significados similares tendrán firmas numéricas similares
![[Pasted image 20260519195219.png]]

#### Evolución de la representación del texto


|                     | ASCII          | Bag of Words           | Word2Vec                 |
| ------------------- | -------------- | ---------------------- | ------------------------ |
| Unidad Base         | Carácter       | Documento              | Palabra                  |
| Tamaño de datos     | Fijo por letra | Dinámico (Vocabulario) | Fijo (300 diimensiones)  |
| ¿Entiede contexto?  | No             | No (Destruye el orden) | Si (Aprende del entorno) |
| ¿Captura semántica? | No             | Superficial            | Profunda (Geometría)     |


#### Extracción del oro: los pesos ocultos

La innovación central de la arquitectura: No nos importa la salida de la red. Si "Perro" y "Gato" predicen contextos idénticos, los 300 pesos matemáticos en la Capa Oculta deben ser **Casi idénticos**. Esos 300 pesos se convierten en nuestro Embedding

#### Geometría del lenguajes: Distancia Coseno

En un espacio multidimensional, medimos la similitud semántica mediante ángulos
![[Pasted image 20260519195940.png]]

#### Operaciones semánticas

El resultado más inesperado: los embbedings capturan capturan lógica relacional. Las relaciones de género o geografía pueden ser calculadas algebraicamente.

![[Pasted image 20260519200209.png]]

La revolución actual fue detonada por un cambio radical en el diseño de redes neuronales: la invención de la arquitectura Transformer.
Este modelo prescindió por completo de la recurrencia y la convolución, basado todo el cálculo en un mecanismo puramente matemático llamado Self-Attention (Auto-Atención)



