DF - CodigoPostal_ciudad -> nombreciudad, cant_hab_ciudad, codProv, nomProv

**Ejercicio 2**
a)
```
DF codigosuscrip -> DNIsusc, nombre, domicilio, DNI_per_rec
RECOMENDADOS (/codigosuscriptor/, -DNI_per_rec-)
S=(-codsuscrip-, DNIsuscrip, nombre, domicilio)
R=(-codigoRevista-, nombreRevista, codEditor, codigoSuscrip)
suscripciones(-codigoRevista, codigoSuscrip-)
```

```
2FN)  idReparacion codRep -> cant_rep__repa
idReparacion -> cantTotalRep, cantMensualRepUsados, cantDiasRep, finRep

codRepuesto -> descRep, stockRep, costoMensRep

reparaciones (idReparacion, idInmueble, dirInmueble, legajoReparador, nombreReparador, fechaIngreso, montoTotalReparacion)

repuestos(codrepu, descrip, stockrep, cantvecesdiariausada)

usos(idreparacion, codrep, dia, mes, año, cantrepusados)





```
