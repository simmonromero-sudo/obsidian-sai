---

---
------

## Patrones GRASP

Diseño de objetos con responsabilidades

### Responsabilidades de los objetos

- Conocer
	- Conocer sus datos privados encapsulados
	- Conocer sus objetos relacionados
	- Conocer cosas derivables o calculables
- Hacer
	- Hacer algo él mismo
	- Iniciar una acción en otros objetos
	- Controlar o coordinar actividades de otros objetos

La habilidad para asignar responsabilidades es extremadamente importante en el diseño.
La asignación de responsabilidades generalmente ocurre durante la creación de diagramas de interacción.
Los patrones GRASP son pares (problema, solución) con nombre, que codifican buenos consejos y principios que ayudan a la asignación de responsabilidades

<font color="#ffff00">GRASP</font> = <font color="#ffff00">G</font>eneral <font color="#ffff00">R</font>esponsability <font color="#ffff00">A</font>ssignment <font color="#ffff00">S</font>oftware <font color="#ffff00">P</font>atterns

### Patrón Experto en información (Experto)

**Solución:** Asignar una responsabilidad al experto en información (la clase que tiene la información necesaria para realizar la responsabilidad).

**EJEMPLO:** ¿Quién tiene la responsabilidad de conocer el monto total de una venta? La venta

- Expresa la intuición de que los objetos hacen cosas relacionadas con la información que tienen
- Para cumplir con su responsabilidad, un objeto puede requerir de información que se encuentra dispersa en diferentes clases $\rightarrow$ expertos en información "parcial"

### Patrón Creador

**Solución:** Asignar la clase B la responsabilidad de crear una instancia de la clase A si:

- B contiene objetos A (aggregation, composite).
- B registra instancias de A.
- B tiene los dato para inicializar objeto A.
- B usa objetos A en forma exclusiva.

**EJEMPLO:** ¿Quién debe ser el responsable de crear una LineaDeVenta? La venta

La intención del patrón Creador es encontrar un creador que necesite conectarse al objetos creado en alguna situación. Eligiéndolo como el creador se favorece el bajo acoplamiento.

### Patrón controlador

**Solución:** asignar la responsabilidad de manejar eventos del sistema a una clase que representa:

- El sistema global, dispositivo o subsistema
- Un escenario de caso de uso, en el que tiene lugar el evento del sistema

**EJEMPLO:** ¿Quién debe ser el controlador de los eventos ingresarArticulo o finalizarVenta? ProcesarVentaController, SistemaPDV, Registro.

La intención del patrón Controlador es encontrar manejadores de los evento del sistema, sin recargar de responsabilidad a un solo objeto y manteniendo alta cohesión.

### Patrón Bajo Acoplamiento

**Solución:** asignar responsabilidades de manera que el acoplamiento permanezca lo más bajo posible.

El acoplamiento es una medida de dependencia de un objeto con otros.

- El alto acoplamiento dificulta el entendimiento y complica la propagación de cambios en el diseño.
- No se puede considerar de manera aislada a otros patrones, sino que debe incluirse como principio de diseño que influye en la elección de la asignación de responsabilidad.

### Patrón Alta Cohesión

**Solución:** asignar responsabilidades de manera que la cohesión permanezca lo más fuerte posible.
La cohesión es una medida de la fuerza con la que se relacionan las responsabilidades de un objeto, y la cantidad de ellas.

**Ventaja:** clases más fáciles de mantener, entender y reutilizar.

El nivel de cohesión no se puede considerar de manera aislada a otras responsabilidades, y otros principios los patrones Experto y Bajo Acoplamiento.

### Patrón Polimorfismo

**Solución:** cuando el comportamiento varía según el tipo, asigne la responsabilidad para el comportamiento a los tipos para los que varía el comportamiento.

**EJEMPLO:** El sistema PDV debe soportar distintas formas de pago.
Como la autorización del pago varía según su tipo deberíamos asignarle la responsabilidad de autorizarse a los distintos tipos de pagos.

Nos permite sustituir objetos que tienen idéntica interfase.

![[Pasted image 20260407085057.png]]

### Patrón Fabricación Pura

**Solución:** asigne responsabilidades a una clase "de conveniencia" que no representa un concepto del dominio y que soporta alta cohesión, bajo acoplamiento y reutilización.

**EJEMPLO:** El sistema PDV necesita calcular los impuestos asociados a una determinada venta.
Se crea una nueva clase cuya responsabilidad es la de calcular los impuestos a medida que se van incorporando detalles de la venta.

La venta permanece bien diseñada, con alta cohesión y bajo acoplamiento.

### Patrón Indirección

**Solución:** asigne la responsabilidad a un objeto intermedio que medie entre otros componentes o servicios de manera que no se acoplen directamente.

**EJEMPLO:** El sistema PDV necesita almacenar todas las ventas en una base de datos relacional.
Se crea una nueva clase cuya responsabilidad es la de almacenar objetos en algún tipo de medio de almacenamiento persistente.

La clase que se ocupa del almacenamiento persistente de los objetos es un intermediario entre la Venta y la base de datos.
![[Pasted image 20260407085730.png]]

### "No hables con extraños"

Evite crear diseños que recorren largos caminos de estructura de objetos y envía mensajes (habla) a objetos distantes o indirectos (extraños).

Dentro de un método sólo pueden enviarse mensajes a objetos conocidos:

- self
- un parámetro del método
- un objeto que esté asociado a self
- un miembro de una colección que sea atributo de self
- un objeto creado dentro del método

Los demás objetos son extraños (strangers)
![[Pasted image 20260407090014.png]]


## EJERCICIO

Especificación en pseudocodigo (hayCupo())

```
Curso::hayCupo()
return self.horario -> collect(:h| h.aula.getCapacidad) -> min() > self.inscripcion.size() "Flecha es lo mimso que punto"
```

![[calase 3 1.eap]]
