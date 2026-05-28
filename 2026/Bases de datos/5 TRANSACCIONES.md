
Los sistemas de procesamiento de transacciones son sistemas con grandes BD y cientos de usuarios concurrentes ejecutando transacciones de bases de datos.
Requieren una alta disponibilidad y una respuesta rápida para cientos de usuarios simultáneos.
Un criterio que sirve para clasificar un sistema de BD es el número de usuarios que lo pueden utilizar al mismo tiempo.


- Un **DBMS** es <mark style="background:#9254de">monousuario</mark> si sólo lo puede utilizar un usuario a la vez (principalmente restringidos a los sistemas de computación personal) 
- - Un **DBMS** es <mark style="background:#9254de">multiusuario</mark> si varios pueden utilizar el sistema (y, por tanto, acceder a la base de datos) simultáneamente. 
- A la BD pueden acceder simultáneamente múltiples usuarios debido a la **multiprogramación**, que permite al computador ejecutar varios proccesos al mismo tiempo. Si solo hay una CPU, realmente sólo se ejecuta un proceso a la vez.

Sin embargo los SO multiprogramación con una CPU ejecutan algunos comandos de un proceso, después suspende ese proceso y ejecutan algunos comandos del siguiente proceso, y así sucesivamente. El proceso se reanuda en el mismo punto en que se suspendió, siempre que consiga turno para utilizar de nuevo la CPU. Por lo tanto, la ejecución de procesos realmente es **interpolada**.
Si el computador tiene varias CPUs, es posible el procesamiento paralelo de varios procesos.

### Transacción

Es una unidad lógica de procesamiento de la BD que incluye una o más operaciones de acceso a la BD, que pueden ser de inserción, eliminación, modificación o recuperación.

**EJ:** transferencia de dinero de una cuenta a otra

$$
T_x\begin{cases}
Leer(saldoA)\\
SaldoA:=saldoA-100\\
Escribir(saldoA)\\
Leer(saldoB)\\
saldoB:=saldoB+100\\
Escribir(saldoB)
\end{cases}
$$

Una transacción se inicia por la ejecución de un programa de usuario escrito en un lenguaje de manipulación de dato de alto nivel o en un lenguaje de programación de datos de alto nivel en un lenguaje de programación (SQL, Java) y está delimitado por instrucciones **begin transaction** y **end transaction**.
Un programa de aplicación puede contener más de una transacción si contiene varios límites de transacción.
Si las operaciones de BD de una transacción no la actualizan, sino que únicamente recuperan datos, se dice que la transacción es de sólo lectura.

- El modelo de una BD que utilizaremos para entender transacciones es muy simplificado.
- Una BD está representada básicamente como una colección de **elementos de datos con nombres**.
- Las operaciones básicas de acceso a la BD que una transacción puede incluir son:
	- <font color="#ffff00">Leer/Read</font> (X): transfiere el dato X de la base de datos a una memoria intermedia local perteneciente a la transacción que ejecuta la operación leer.
	- <font color="#fa11">Escribir/Write</font> (X): transfiere el dato X desde la memoria intermedia local de la transacción que ejecuta la operación escribir a la base de datos.

**¿Por qué es necesario controlar la concurrencia?**

Cuando las transacciones se ejecutan de manera incontrolada pueden surgir algunos problemas:
- Actualización perdida.
- Lectura sucia.
- Análisis inconsistente 


#### Actualización perdida

Ocurre cunado dos transacciones que intentan modificar un elemento de datos, ambas leen el valor antiguo del elemento, una de ellas (T1) actualiza el dato, pero esa actualización se pierde dado que la otra transacción (T2) sobrescribe ese valor sin siquiera leerlo

| $T_1$                                    | $T_2$                                            |
| ---------------------------------------- | ------------------------------------------------ |
| Leer(B)<br>B:= B + 25<br><br>Escribir(B) | <br>Leer(B)<br><br><br>B:=B + 100<br>Escribir(B) |
T2 sobrescribe el valor del elemento B escrito por T1.

#### Dependencia no confirmada

Ocurre cunado una transacción T1 lee o actualiza un elemento de datos que ha sido actualizado por otra transacción T2 que aún no ha sido confirmada. Por lo tanto, existe la posibilidad de que se deshaga T2 y T1 haya visto un valor que ya no existe. T1 opera sobre una suposición falsa.


| $T_1$                                            | $T_2$                                                            |
| ------------------------------------------------ | ---------------------------------------------------------------- |
| <br><br><br>Leer(A)<br>A:= A + 25<br>Escribir(A) | Leer(A)<br>A:= A -100<br>Escribir(A)<br><br><br><br><br>ROLLBACK |
T1 lee un valor del elemento de datos A, que ya no existe.
ROOLBACK $\rightarrow$ se deshace la transacción.

#### Análisis inconsistente

Se produce cuando una transacción T1, producto de haber leído un dato actualizado por otra transacción T2 ya finalizada, incurre en un análisis inconsistente.


| $T_1$                                                                                                                                                                                                                                                                                                                             | $T_2$                                                                                                                                                                                                                                    |
| --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| $\textcolor{blue}{A = 50}$            Leer(A)<br>$\textcolor{blue}{Suma = 50}$     Suma:= Suma + A<br>$\textcolor{blue}{B=200}$          Leer(B)<br>$\textcolor{blue}{Suma = 250}$   Suma:= Suma + B<br><br><br><br><br><br><br><br>$\textcolor{blue}{C=50}$           Leer(C)<br>$\textcolor{blue}{Suma = 300}$  Suma:= Suma + C | <br><br><br><br>Leer(C)        $\textcolor{blue}{C=150}$<br>C:= C - 100   <br>Escribir(C)   $\textcolor{blue}{C = 50}$<br>Leer(A)        $\textcolor{blue}{A=50}$<br>A:= A + 100<br>Escribir(A)    $\textcolor{blue}{A=150}$<br>FINALIZA |

T1 llega a un análisis inconsistente, devolviendo un resultado erróneo.

Siempre se envía una transacción a un DBS para su ejecución, el sistema es responsable de garantizar que todas las operaciones de la transacción se completen satisfactoriamente y que su efecto se grabe permanentemente en la BD, o de que la transacción no afecte a la BD o a cualquier otra transacción.
El DBMS no debe permitir que algunas operaciones de una transacción T se apliquen a la BD mientras que otras no. Esto puede ocurrir si una transacción falla después de ejecutar algunas de sus operaciones, pero antes de ejecutar todas ellas.

Hay varias razones posibles por las que una transacción pueda fallar en medio de su ejecución:

- **Caída del sistema**
- **Un error de la transacción**
- **Errores locales o condiciones de excepción detectados por la transacción** (no se encuentran los datos)
- **Control de concurrencia**
- **Fallo del disco**
- **Problemas físicos y catástrofes**

Para fines de recuperación, el sistema mantiene un **registro** para hacer el seguimiento de todas las operaciones de las transacciones que afectan a los valores de los elementos de una BD. Por consiguiente, el gestor de recuperación hace un seguimiento de las operaciones:

[**Start_transaction, T**]
[**Write_itme**, T, X, valor_antiguo, valor_nuevo]
[**read_item**, T, X]
[**commit**, T] señala una finalización satisfactoria
[**abort**, T]

#### Estados de ejecución

![[Pasted image 20260430091824.png]]

- Una transacción entra en estado **<mark style="background:#9254de">activo</mark>** inmediatamente después de iniciarse su ejecución; en este estado puede emitir operaciones LEER y ESCRIBIR. Luego de la ultima ejecución de la última instrucción, pasa al **estado de parcialmente confirmada**

- <mark style="background:#9254de">Parcialmente confirmada</mark>, la transacción ya ejecutó su última instrucción Está "a punto" de confirmar, pero todavía no es definitiva. Puede fallar antes de hacer commit.
  Todavía no se garantizó que los cambios queden guardados definitivamente.
- <mark style="background:#9254de">Confirmada</mark>, la transacción terminó correctamente (se realizó commit). Todos los cambios son permanentes en la BD. 
- Una transacción puede entrar en el estado <mark style="background:#9254de">fallo</mark>
	Activa $\rightarrow$ Fallo
		Ocurre un erro (error lógico, deadlock, violación de restricciones) mientras la transacción estaba ejecutándose.
	Parcialmente confirmada $\rightarrow$ Fallo
		Incluso después de terminar las instrucciones, puede fallar antes del commit (por ejemplo, caída del sistema justo antes de confirmar)
- La transacción pasa al estado <mark style="background:#9254de">terminada</mark> (también llamada abortada). Esto implica que:
	- Se hizo rollback
	- Se deshicieron todos los cambios 

#### Propiedades ACID

Atomicidad (A)
Consistencia (C)
Aislamiento (I)
Durabilidad (D)

- **Atomicidad**: Una transacción es una unidad atómica de procesamiento; o se ejecuta en su totalidad o no se ejecuta en absoluto.
- **Conservación de la consistencia**: Una transacción está conservando la consistencia si su ejecución completa lleva a la BD de un estado consistente al otro.
- **Aislamiento**: Una transacción debe aparecer como si estuviera ejecutándose de forma aislada a las demás. Es decir, la ejecución de una transacción no debe interferir con la ejecución de ninguna otra transacción simultánea.
- **Durabilidad:** Los cambios aplicados a la BD por una transacción confirmada deben persistir en la BD. Estos cambios no deben perderse por culpa de un fallo.

### Planificaciones

Una planificación S de n transacciones $T_1, T_2,...., T_n$ es un ordenamiento global de las operaciones de esas transacciones que respete el orden interno de las operaciones dentro de cada transacción.
Las operaciones de las transacciones $T_j$ pueden interpolarse con las operaciones $T_i$ en S.
Si no se permite la interpolación de operaciones, las operaciones de cada transacción se deben ejecutar consecutivamente.


##### Serie

Una planificación S es **serie** si, por cada transacción T que participa en la planificación, todas las operaciones de T se ejecutan consecutivamente en la planificación; en caso contrario, se dice que la planificación **no es serie**.
Por consiguiente, en una planificación serie, sólo hay una transacción activa al mismo tiempo.

Supongamos las siguientes transacciones de un banco:

| $T_1$                                                                                                                              | $T_2$                                                                                                                                                                   |
| ---------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Leer(CuentaA)<br>CuentaA = CuentaA - 1000<br>Escribir (CuentaA)<br>Leer (CuentaB)<br>CuentaB = CuentaB + 1000<br>Escribir(CuentaB) | Leer(CuentaA)<br>descuento = CuentaA * 0,2<br>CuentaA = CuentaA - descuento<br>Escribir(CuentaA)<br>Leer(CuentaB)<br>CuentaB = CuentaB + descuento<br>Escribir(CuentaB) |
- Una planificación en serie posible es:

| $T_1$                                                                                                                              | $T_2$                                                                                                                                                                                               |
| ---------------------------------------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Leer(CuentaA)<br>CuentaA = CuentaA - 1000<br>Escribir (CuentaA)<br>Leer (CuentaB)<br>CuentaB = CuentaB + 1000<br>Escribir(CuentaB) | <br><br><br><br><br><br><br>Leer(CuentaA)<br>descuento = CuentaA * 0,2<br>CuentaA = CuentaA - descuento<br>Escribir(CuentaA)<br>Leer(CuentaB)<br>CuentaB = CuentaB + descuento<br>Escribir(CuentaB) |


La otra posibilidad es:

| $T_1$                                                                                                                                                              | $T_2$                                                                                                                                                                   |
| ------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <br><br><br><br><br><br><br><br>Leer(CuentaA)<br>CuentaA = CuentaA - 1000<br>Escribir (CuentaA)<br>Leer (CuentaB)<br>CuentaB = CuentaB + 1000<br>Escribir(CuentaB) | Leer(CuentaA)<br>descuento = CuentaA * 0,2<br>CuentaA = CuentaA - descuento<br>Escribir(CuentaA)<br>Leer(CuentaB)<br>CuentaB = CuentaB + descuento<br>Escribir(CuentaB) |
- Planificación no serie posible:


| $T_1$                                                                                                                                                      | $T_2$                                                                                                                                                                                                       |
| ---------------------------------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Leer(CuentaA)<br>CuentaA = CuentaA - 1000<br>Escribir (CuentaA)<br><br><br><br><br><br><br>Leer (CuentaB)<br>CuentaB = CuentaB + 1000<br>Escribir(CuentaB) | <br><br><br><br>Leer(CuentaA)<br>descuento = CuentaA * 0,2<br>CuentaA = CuentaA - descuento<br>Escribir(CuentaA)<br><br><br><br><br><br>Leer(CuentaB)<br>CuentaB = CuentaB + descuento<br>Escribir(CuentaB) |
Una **planificación** S de n transacciones es **serializable** si es equivalente a alguna planificación en serie de las misma n transacciones.
A partir de n transacciones es posible generar n! planificaciones en serie y muchas más planificaciones no serie.
Se pueden formar dos grupos disjuntos con las planificaciones no serie:
- Aquellas que son equivalentes a una (o más) planificaciones en serie y, pro tanto, serializables.
- Aquellas que no son equivalentes a ninguna planificación en serie y, por tanto, no son serializables.

Decir que una planificación S es serializable es equivalente a decir que es correcta, porque es equivalente a una planificación en serie, que se considera correcta.

¿Cuándo se considera que dos planificaciones son equivalente?
Dos planificaciones son **equivalentes por conflicto** si el orden de cualquier par de operaciones en conflicto es el mismo en las dos planificaciones.

Si las instrucciones operan sobre datos diferentes, no generan conflicto. Supongamos I1 e I2 instrucciones de T1 y T2 respectivamente, que operan sobre el dato D. .

- Si I1=READ(D) e I2=READ(D), no hay conflicto
- Si I1=READ(D) e I2=WRITE(D), hay conflicto
- Si I1=WRITE(D) e I2=READ(D), hay conflicto
- Si I1=WRITE(D) e I2=WRITE(D), hay conflicto

En conclusión, dos instrucciones son conflictivas si operan sobre el mismo dato, y al menos una de ellas es una operación de escritura.
