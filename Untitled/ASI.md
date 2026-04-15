## Historia de usuario

- Una historia de usuario es una descripción corta y simple de un requerimiento de un sistema, que se escribe en lenguaje común del usuario y desde su perspectiva.
- Son utilizadas en las metodologías de desarrollo agiles para la especificación de requerimientos
- Se acompañan de las discusiones con los usuarios y las pruebas de validación

#### Formato 3W (Who, What, Why)

- **Como** [Rol del usuario]
- **Quiero** [Objetivo]
- **Para** [Beneficio/valor]

#### EJ.
![[Pasted image 20260226175356.png]]
![[Pasted image 20260226175405.png]]
![[Pasted image 20260226175417.png]]
![[Pasted image 20260226175432.png]]

### Principio INVEST

- I - Independent: Independiente de otras historias
- N - Negotiable: Negociable, no rígida
- V - Valuable: Aporta valor al usuario
- E - Estimable: Se puede estimar su esfuerzo
- S - Small: De tamaño manejable
- T - Testable: Se puede probar con criterios claros

MAL: "Como estudiante quiero un sistema académico completo" -> No es pequeña ni estimable

BIEN: "Como estudiante quiero descargar mi constancia de alumno regular en PDF"

### Gherkin

**Escenario:** [Numero de escenario] [Titulo del escenario]
**Dado que:** [Contexto] y adicionalmente [Contexto] 
**Cuando:** [Evento]
**Entonces:** [Resultado/ comportamiento esperado]

### Criterios de aceptación

**Como:** Cliente
**Quiero:** Retirar dinero del cajero automático
**Para:** Poder evitar ir al banco a hacer cola

**Escenario 1:** La cuenta tiene saldo suficiente.
**Dado** que la cuenta tiene saldo y que la tarjeta es valida y que el cajero tiene dinero disponible
**Cuando:** El cliente pide dinero
**Entonces:** La cuenta es debitada y el dinero es entregado al cliente y el cliente recupera su tarjeta

**Escenario 2:** La cuenta tiene saldo insuficiente
**Dado** que la cuenta tiene saldo insuficiente y que la tarjeta es valida
**Cuando** el cliente pide dinero
**Entonces** el cajero muestra un mensaje negando el pedido y el cliente recupera su tarjeta

- Formaliza la confirmación del modelo 3C
- Permite pruebas objetivas automatizables
- Los enunciaremos en forma bien especifica, para que sirvan como casos de prueba

**Escenario 1:** Elección exitosa de un curso
**Dado** que el matriculado 1111 no esta inscripto en "UML 2.0" y que dicho curso tiene 4 inscriptos y el cupo es de 30.
**Cuando** el matriculado ingresa la matricula 1111 y selecciona el curso "UML 2.0" y solicita la inscripcion. 
**Entonces** el sistema redirige al usuario al pago de inscripción con tarjeta de crédito.

**Escenarios 2:** Elección fallida porque el alumno ya esta inscripto.

**Dado** que el matriculado 1111 ya esta inscripto en "UML 2.0" y que dicho curso tiene 5 inscriptos y el cupo es de 30
**Cuando** el matriculado ingresa la matricula 1111 y selecciona el curso "UML 2.0" y solicita la inscripcion
**Entonces** el sistema informa que ya esta inscripto en el curso

**Escenario 3:** Elección fallida por falta de cupo 
**Dado** que el matriculado 1111 no esta inscripto en "UML 2.0" y que dicho curso tiene 30 inscripto y el cupo es de 30
**Cuando** el matriculado ingresa la matricula 1111 y selecciona el curso "UML 2.0" y solicita la inscripcion
**Entonces** el sistema informa que no hay cupo curso

### Ambulancias YA

 1. **Afiliar individuo**
	**Como** empleado de "Ambulancias YA"
	**Quiero** afiliar a una persona particular
	**Para** que pueda recibir los servicios de asistencia domiciliaria de la empresa

	**Escenario 1:** Afiliación exitosa
		**Dado que** solamente existe el afiliado "Rubén Guerrieri" con DNI 33.333.333 y domicilio "XXX" 
		**Cuando** ingreso al afiliado "Mirta Peñalva" con DNI 22.222.22 y domicilio "ZZZ" 
		**Entonces** el sistema lo guarda y le asigna un numero de afiliado y muestra un mensaje de éxito

	**Escenario 2:** Afiliación fallida por afiliación ya existente
		**Dado** que ya existe un afiliado con DNI 33.333.333
		**Cuando** ingreso al afiliado "Rubén Guerrieri" con DNI 33.333.333 y domicilio "XXX"
		**Entonces** el sistema informa que no se pudo guardar el afiliado porque ya existe.

2. **Afiliar Grupo Familiar**
	**Como** empleado de "Ambulancias YA"
	**Quiero** afiliar a un titular y sus dependientes
	**Para** que todos los miembros del grupo puedan recibir los servicios de asistencia domiciliaria de la empresa

3. **Afiliar a través de Obra Social**
	**Como** empleado de "Ambulancias YA"
	**Quiero** afiliar a personas provenientes de una obra social mediante un listado
	**Para** que reciban los servicios de asistencia domiciliaria como corresponde

4. **Actualizar Lista de Precios**
	**Como** gerente de "Ambulancias YA"
	**Quiero** actualizar la lista de precios de las coberturas
	**Para** asegurarme de que los afiliados paguen las cuotas correctas

5. **Realizar Pago Electrónico de Cuota**
	**Como** afiliado particular de "Ambulancias YA"
	**Quiero** pagar mi cuota a través de "Pago Todo" y que el pago que disponible en el sistema.
	**Para** asegurarme de que mi afiliación este al día.

6. **Listar Cuotas no Pagadas** 
	**Como** gerente de "Ambulancias YA"
	**Quiero** listar las cuotas vencidas no pagadas 
	**Para** poder decidir si doy de baja o no  a cada afiliación

7. **Agendar Solicitud de Servicio**
	**Como** empleado de "Ambulancias YA"
	**Quiero** registrar una solicitud de servicio de un afiliado
	**Para** poder proveerle atención medica a domicilio

	**Escenario 1:** Solicitud exitosa
		**Dado que** el afiliado con numero 111 tiene vigente su afiliación y realizo 3 solicitudes en el mes. 
		**Cuando** ingreso al afiliado 111 y solicito un servicio
		**Entonces** el sistema guarda la solicitud como "Iniciada" y muestra un mensaje de éxito

	**Escenario 2:** Solicitud fallida por afiliación dada de baja}
		**Dado que** el afiliado con numero 111 fue dado de baja
		**Cuando** ingreso al afiliado 111 y solicito un servicio
		**Entonces** el sistema informa que la afiliación no esta vigente y que no puede proveerse el servicio 
	**Escenario 3:** Solicitud fallida por superar limite de solicitudes por mes
		**Dado que** el afiliado con numero 111 tiene vigente su afiliación y realizo 10 solicitudes en el mes. 
		**Cuando** ingreso el afiliado 111 y solicito un servicio
		**Entonces** el sistema informa que se ha superado la cantidad máxima de solicitudes por mes y que no puede proveerse el servicio.

8. **Registrar Informe de Atención**
	**Como** medico de "Ambulancias YA"
	**Quiero** registrar un informe de atención realizada
	**Para** completar la solicitud de servicio y documentar la atención brindada

	**Escenario 1:** 
		**Dado que** el afiliado con numero 111 tiene "Iniciada" una solicitud
		**Cuando** ingreso el afiliado 111 y cargo el informe de atención
		**Entonces** el sistema cambia el estado de la solicitud a "Cumplida" y cuenta una solicitud mas en el mes y muestra un mensaje de éxito

	**Escenario 2:** Atención fallida por solicitud no "Iniciada"
		**Dado que** el afiliado con numero 111 no tiene ninguna solicitud "Iniciada"
		**Cuando** ingreso al afiliado 111 y comienzo a cargar el informe de atención
		**Entonces** el sistema informa que no existe ninguna solicitud pendiente para ese afiliado

9. **Cancelar Solicitud de Servicio**
	**Como** empleado de "Ambulancias YA"
	**Quiero** cancelar una solicitud de servicio previamente agendada
	**Para** poder organizar correctamente las atenciones domiciliaras pendientes

	**Escenario 1:** Cancelación exitosa
		**Dado que** el afiliado con numero 111 tiene "Iniciada" una solicitud
		**Cuando** ingreso al afiliado 111 y solicito cancelar el servicio
		**Entonces** el sistema cambia el estado de la solicitud a "Cancelada" y cuenta una solicitud mas en el mes y muestra un mensaje de cancelación exitosa.

	**Escenario 2:** Cancelación fallida por solicitud no "Iniciada" 
		**Dado que** el afiliado con numero 111 no tiene ninguna solicitud "Iniciada"
		**Cuando** ingreso al afiliado 111 y solicito cancelar servicio
		**Entonces** el sistema informa que no existe ninguna solicitud pendiente para ese afiliado.

10. **Generar Estadísticas de Atenciones Domiciliarias**
		**Como** gerente de "Ambulancias YA"
		**Quiero** obtener estadísticas cobre los tiempos de atención de los servicios
		**Para** poder analizar el desempeño y mejorar la eficiencia del servicio





