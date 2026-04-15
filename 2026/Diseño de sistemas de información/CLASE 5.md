
### Principios SOLID

- Single Responsability
	Cada módulo tiene una, y solo una, razón para cambiar - una función + un actor
- Open/close 
	Un artefacto de software debe estar abierto a la extensión pero cerrado a la modificación
- Interface
	Evitar depender de cosas que no utilizamos
- Dependency
	Los sistemas mas flexibles son aquellos en los que las dependencias del código fuente se refieren sólo a abstracciones, no a concreciones.
- Sustitución de Liskov
	Para construir sistemas de software a partir de partes intercambiables, esas partes deben cumplir in contrato que permita sustituirlas una por otra 



```
//Finalizar

Lote::
finalizarLote(){
	self.setEstado('Cumplido')
}
Lote::
apto(){
	if(slef.getCantidad() == self.getProducir()){
	return true
	}
	else return false
}

```


