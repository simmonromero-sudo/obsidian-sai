Hay que armar constructores dentro de la clase en la que hacemos el controller, para crear el objeto
### Asignación de responsabilidad

<mark style="background:#9254de">Existen patrones</mark>

#### Control
Se agrega un controller a cada entidad que sea necesario, un solo controller que maneje todo implica que todas las acciones de usuario impacten en alguna operación del mismo.

Cualquier clic en la interfaz grafica hace que se ejecute una operación en el controller.
Las operaciones de los controllers necesitan parámetros. 

#### Intermediario

Cuando hay componentes que necesitan de algo en el medio entre su relación, se le agrega una clase intermediaria, en este caso se usa por ej. entre el sistema y la base de datos (modelado en el EA)


### Ejercicio de clase

![[calase 3.eap]]

**Parámetros del ejercicio de la clase**

```
InscripcionController::altaInscripcion(alumno:Persona, curso:Curso)
	InscripcionBD.persistir(Inscripcion.crear(alumno, curso))
```

**Desarrollo del persistir**
En esta línea estamos persistiendo la creación del objeto inscripción

**Definición del crear**
```
Inscripcion::crear(alumno:Persona, curso:Curso)
	i = self.new()
	
	i.setCodigo(InscripcionBD.ultimoCodigo()+1)
	i.setFecha(setDate())
	i.setEstado(InscripcionEstado.Cursando)
	i.setCurso(curso)
	i.setAlumno(alumno)
	
	return i
```

**Desarrollo del persistir**

En esta línea estamos persistiendo la creación del objeto inscripción

