OCL es un lenguaje formal. Describe expresiones sobre modelos UML, forma parte del estándar UML, fue desarrollado en IBM.
La evaluación de expresiones OCL no afecta el estado del sistema en ejecución.
Es un lenguaje declarativo (qué y no cómo) y tipado, complementa los modelos para refinarlos, representando la realidad en forma más precisa. No es un lenguaje de programación sino de especificación, es de expresión puro. No modifica el estado ni la estructura del modelo.

#### Motivación

- Lenguaje natural conduce a ambigüedades.
- Los métodos formales no son usados masivamente.
- UML no tiene expresividad suficiente para precisar ciertas restricciones.
- Pasa de expresiones en notas a expresiones más formales y precisas.
- Especificar condiciones para lograr modelos bien formados
- Posibilita expresar restricciones semánticas de un sistema, que no pueden expresarse de otra manera.

#### Aplicación

- La entidad de aplicación se llama clasificador y puede ser una clase, una interfaz, atributos de una clase, un componente
- Puede usarse como lenguaje de consulta
- Para expresar condiciones invariantes en clases y tipos
- Para definir pre y post condiciones en operaciones de clase e implementación de métodos en interfaces.
- Especificar reglas del negocio
- Especificar condiciones para un modelo bien formado
- Para escribir guardas (Diag. Estados)
- Para especificar condiciones (Diag. Secuencias)
- Permite definir el cuerpo de operaciones de consulta
- Para expresar reglas de derivación

![[Pasted image 20260506082909.png]]
![[Pasted image 20260506082918.png]]
![[Pasted image 20260506083019.png]]

**Contexto de una expresión**

El vínculo entre una entidad de un diagrama UML y la expresión OCL define el ámbito de aplicación.
![[Pasted image 20260506083151.png]]

También se puede ampliar el contexto describiendo el modelo, paquete de pertenencia del clasificador y un nombre a la expresión.
![[Pasted image 20260506083234.png]]
```
modelo ModeloAdmHotel
	paquete GestionReservas
			context Habitacion
				inv CupoMaximo: self.numero_de_camas <= 5
			finPaquete
		finModelo
```

### Invariante

Una expresión con etiqueta invariante INV es una condición que deberá ser verdadera para todas las instancias del tipo especifico, clasificador (Ej. clase Habitación de un Hotel que tiene 3 pisos) (**TIENE QUE DAR TRUE O FALSE**)
![[Pasted image 20260506083559.png]]

```
context Habitacion
inv:self.numero_piso > 0 and self.numero_piso <= 3

context Habitacion
inv: numero_piso > 0 and numero_piso <= 3

context h:Habitacion
inv: h.numero_piso > 0 and h.numero_piso <= 3
```
Tres formas de escribir la misma expresión

### Pre y Post condiciones

![[Pasted image 20260506083936.png]]
```
context CuentaBancaria::extraer(monto float)
pre:monto > 0 
pre:self.saldo >= monto
post: self.saldo = self.saldo@pre -monto
```

En el diseño por **Contratos** se especifican las **Responsabilidades** de las clases. Un objeto brinda servicios (obligaciones) en base a condiciones que debe alcanzar (derechos)

Derechos $\rightarrow$ precondiciones
Obligaciones $\rightarrow$ postcondiciones

Una expresión con etiqueta PRE o POST representa una condición que debe ser verdadera antes (pre) y después (post) de ejecutar una operación, $\rightarrow$ su contexto de aplicación es una operación, deberá incluir clase y la operación (signatura). Post especifica el valor de retorno por medio de la palabra reservada RESULT

Forma genérica de la expresión:

```
context Calse::operación (param1: tipo1, ....):tipoRetorno
pre: (condiciones de param1)
post: (condicion)
post: result = (objeto retorno)
```
Solo en una postcondición se puede hacer referencia al valor inicial de algún atributo o parámetro agregando @pre al final del elemento en cuestión.

### Valores iniciales y Derivados

Una expresión con etiquete INIT establece el valor inicial de un atributo o extremo de una asociación.

**Ejemplo:** el salario inicial de todo empleado es 5000$

```
context Persona::salario Integer
init: 5000
```

**Ejemplo:** se incrementa en 120$ por casa año de antigüedad

```
context Persona::salario Integer

derive: self.salario + (120 * self.antiguedad)
```

### Consulta

Una expresión etiquetada como BODY nos indica el resultado de una operación de consulta. Sirve como implementación preliminar de un método

![[Pasted image 20260506084852.png]]

```
context Habitacion::obtenerCantidadDeHuespedes() :integer
body: self.huespedes -> size()

context Persona::nombreParejaActual() : String
body: if self.conyuge -> notEmpty() then self.conyuge ->
lat().nombre
else null
endif
```

### Let y Def

Usamos LET para definir una variable local con validez en el context, mientras que DEF define un atributo derivado y define la regla de derivación.

```
context Persona
let: hoy : Date = now()
def: edad :Integer = (hoy - self.fechaNacimiento).mod(365)


```

Observación: como resultado de una navegación un objeto puede ser tratado como una colección de dimensión 1 Ej. Persona tiene 0...1 cónyuge

```
context Persona
inv: self.conyuge -> isEmpty() and self.sexo = Sexo::hombre implies "No tiene esposa a cargo"
```

### Navegación

Permite referirse a objetos relacionados a través de asociaciones 

Navegaciones simples y combinadas

![[Pasted image 20260506085621.png]]

**Simple:** se navega a través de una asociación. Ej.: Cantidad de huéspedes alojados en una habitación no debe ser mayor que su capacidad.

```
context Habitacion
inv: self.huespedes -> size() <= self.numero_de_camas
```

#### Navegaciones combinadas

Navegaciones combinadas (encadenadas) admiten varios niveles acceso, a través de varias asociaciones.

EJEMPLO: Controlar la cantidad de pasajeros de acuerdo a la capacidad del avión. (Multiplicidad dinámica)
![[Pasted image 20260506090216.png]]

```
context Vuelo
inv: self.pasajeros -> size() <= self.avion.cant_de_asientos
```

#### Colecciones y Navegaciones combinadas

Los tipos de colecciones deben ser tenidos en cuenta ya que son importantes pues se relacionan con el resultado de navegaciones

- Navegación simple y la multiplicidad de la asociación es > 1 (SET)
- Navegaciones combinadas resultan en BAG si al menos en una de las asociaciones la multiplicidad es > 1 
- Navegación simple en asociación adornada, etiquetada {ordered} resultado en ORDEREDSET
- Navegaciones combinadas en asociaciones adornadas, etiquetadas {ordered} resultan en SEQUENCE
#### Navegaciones y clases de asociación

Se puede navegar desde una clase de asociación a los objetos que participan de la asociación
![[Pasted image 20260506091006.png]]
```
context Job
inv: self.empleado.edad >= 21
```

```
context Compañia::personasQueTrabajn():int
	body: self.empleado -> size()
	
context Compañia::ingenierosQueTrabajan():int
	body: self.job -> select(j| j.titulo='Ingeniero')
		-> size()
```

**Mas navegaciones**

![[Pasted image 20260506091218.png]]

Toda compañía tiene 1 gerente que esta desocupado.
Toda compañía debe tener empleados (al menos 1)

```
context Compañia
inv: self.gerente -> size >= 1 implies self.esDesocupado = false

contet Compañia
inv: self.empleados -> notEmpty 
```
### Colecciones

La colección es un tipo abstracto.

Los tipos concretos son:

- **SET**   Conjunto
- **ORDEREDSET** Conjunto ordenado
- **BAG** Bolsa (admite repetición)
- **SEQUENCE** Subconjunto de un conjunto ordenado

**Operaciones de colecciones:**

```
Size, select, reject (not), collect, forAll, exist, empty, notEmpty, count(), sum(), include(), includeaAll, iterate, union
```

Cada sub-clase tiene operaciones especificas 

### Ejercicios

![[practica dsi OCL.eap]]

Importe total = suma todos los detalles

```
context Venta::importeTotal(): float
derive: self.ventaDetalle -> collect(vd| vd.cantidad * vd.precio)
	-> sum()

```

Solo se le vende a clientes de la plata
```
Context Venta::filtro()

inv: self.cliente.domicilio.localidad.nombre = 'La Plata'
```

```
Context venta

inv: self.cliente.domicilio -> forAll (d|d.localidad.nombre = 'La Plata' ) 
```



```
1) El total de un pedido no puede ser negativo
Context Pedido::total():Float
post: result > 0
inv: precioTotal > 0

2) Un item siempre debe tener una cantidad positiva
Context item
inv: cantidad > 0

3) Para que un cliente sea frecuente, debe tener al menos 5 pedidos   
Context Cliente
inv: frecuente implies self.pedidos -> size()>= 5

4) El metodo total() puede ejecutarse solo si el estado del pedido es distinto de "Cancelado"
   
Context Pedido::total():Float

pre estado <> EstadoPedido::Cancelado

5) Al crear un pedido, su estado inicial debe ser "Pendiente"
   
Context Pedido::new():Pedido
post: self.estado = EstadoPedido::Pendiente

6) Si el pedido tiene envio asociado, entonces debe tener estado "Confirmado"

Context Pedido

inv: envio <> null implies estado = estadoPedido::Confirmado

7) Subtotal de item se calcula automáticamente

Context item::subtoTotal: Float

derive: self.producto.getUnitario()*sel.cantidad

8) Cada pedido debe tener al menos un item

Context Pedido

inv: item -> size() >= 1

9) Si el estado del envio es "Entregado", el estado del pedido debe ser "Enviado"
   
Context Envio:

inv: estado = estadoEnvio::Entregado implies self.pedido.estado = estadoPedido::Enviado

10) Al ejecutar altaEnvio, el envio debe pasar a estado null a un estado inicial

Context Pedido::altaEnvio:: Envio

pre: envio.estado = null
post: result.estado = EstadoEnvioo::En Preparación
```

  ```
  
1) El año de cualquier vehiculo no puede ser posterior al año actual

Context Vehiculo

inv: anio < getDate()

2) Si un camión tiene acoplado, la carga máxima debe ser superior a 10.000kg
   
Context Camion

pre: permiteAcoplado = true
post: TotalCargaMaxima > 10.000

3) Un Auto debe tener exactamente 4 ruedas (cantidadRuedas), mientras que un Motociceta debe tener exactamente 2.
   
Context Vehiculo

inv: self.Auto.cantidadRuedas = 4 and self.Motocicleta.cantRuedas = 2

4) Un Vehiculo solo puede tener un propietario cuya edad sea >= a 16 años. Para ser propietario de un camión se debe tener al menos 21 años.

Context vehiculo

inv: self.propietario.edad >= 16 
inv: self.Camion implies self.Propietario.edad >= 21 

  ```
