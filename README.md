```
Diccionario de Datos – Eventos
Ver. 20231206 - 01
```
### Manual Chasis:

**Diccionario de clasificación de alertas mecánicas**

Código: Código de alerta mecánica (Identificador único)

Descripción: Descripción de que representa la alerta mecánica

Clasificación: Nivel de criticidad de la alerta (incremental de gris, amarillo a rojo)

### Manual Motor:

**Diccionario de clasificación de alertas mecánicas complementario**

Código: Código de alerta mecánica (Identificador único)

Descripción: Descripción de que representa la alerta mecánica

Clasificación: Nivel de criticidad de la alerta (incremental de gris, amarillo a rojo)

### MNP_POTENCIA_V2:

**Información de detenciones asociadas a fallas del sistema de potencia, la idea es trabajar con este
dataset para el desafío**

Equipo: Nombre del equipo que tuvo la detención

Código: Categorización de la detención por el sistema de despacho

Inicio: Fecha en la cual se inició la detención

Fin: Fecha en la cual finalizó la detención

Comentario: Comentario por el cual se identificó que esta detención está asociada al sistema de potencia

### mnp_caex_v1:

**Historial de detenciones, usar como referencia al desafío, ya que el dataset MNP_POTENCIA_V2 fue
generado a partir del estudio de este archivo, en el cual a través de diferentes análisis se determinaron
las asociaciones a diferentes tipos de falla, para quien desee profundizar y encontrar relaciones a otros
tipos de fallas.**

_id: Identificador único de la base de datos A2G (omitir)

Awhen: Fecha en la cual el dato fue recibido en la base de datos A2G (omitir)

Status: Tipo de detención (En este caso todas son mantención)

StatusSymbol: Tipo de categoría de estado en el sistema de despacho

Reason: Código general asociado a la detención

Equipment: Código de equipo que tuvo la detención

Fleet: Flota del equipo

Equipment_Type: Tipo de equipo

Location: Ubicación en la mina (Sector) en donde ocurrió la detención

ShiftName: Turno en el cual ocurrió la detención (A = Dia, B = Noche)

StartLocal: Hora en la cual inicio la detención en hora UTC

EndLocal: Hora en la cual finalizó la detención en hora UTC (Nota, en el caso de este sistema de despacho,
los eventos se cortan a nivel lógico cuando termina el turno, ej: 8 AM y 8PM, por lo que será parte de las
actividades consolidar estas detenciones en un único registro, esto se aprecia cuando hay cortes a las
00:00 o 23:00 o 11:00 o 12:00 dependiendo de la fecha, por favor consideren que en Chile existe horario
de verano y por ende al estar estas horas en formato UTC el offset de tiempo varía entre -4 y -3).

Crew: Nombre del grupo asociado al registro (GRUPO 1, 2, 3 y 4), denominados también coordinaciones,
que están a cargo del mantenimiento

Pay_Number: Id del oeprador que estaba en el equipo (omitir)

Id: Identificador del primer registro asociado a la falla (esto está relacionado con los cortes que el sistema
de despacho hace al extenderse la falla más allá del turno de doce horas).

Comment: Comentario ingresado asociado a a la detención.

Symbol: Clasificación de la detención

Name: Tipo de detención

### TBO:

**Historial de cambios de componentes (partes) en CAEX**

Componente: Tipo de componente según fabricante

Nro Interno: Identificador del Componente instalado en el CAEX

Equipo: Nombre del equipo que se instaló el componente

Estado: Motivo de cambio de componente

Fecha: Fecha en la cual se realizó el cambio de componente en UTC

Horas Equipo: Cantidad de horas acumuladas de operación del equipo

Horas Comp.: Cantidad de horas acumuladas de operación del componente

TBO: Horas esperadas de operación del componente (vida útil)

### Telemetría:

**Información de signos vitales de CAEX**

_id: Identificador único de la base de datos A2G (omitir)

Awhen: Fecha en la cual el dato fue recibido en la base de datos A2G (omitir)

Serie: Nombre del equipo CAEX

Modelo: Tipo de Flota (CAEX)

Tipo: Tipo de Datos (omitir)

Id_Data: Identificador del tipo de datos de telemetría

Tip: Referencia de datos (omitir)

Data_Name: Nombre de la variable de telemetría

Unidad: Unidad de medida de la variable de telemetría

Valor: Valor registrado para la variable de telemetría

SMR_Value: Horómetro del equipo al momento de la muestra de telemetría

Fecha: Fecha de la muestra de telemetría en UTC

FechaRecepción: Fecha en la cual el dato fue recibido en la base de datos del fabricante (omitir) en UTC

### Alertas:

**Información de alertas mecánicas acontecidas en el equipo**

_id: Identificador único en la base de datos de A2G (omitir)

Awhen: Fecha en la cual el dato fue recibido en la base de datos A2G (omitir)

Serie: Nombre del equipo CAEX

Modelo: Tipo de Flota (CAEX)

Tipo: Tipo de datos (omitir)

Codigo: Identificador único de la alerta mecánica

Descripción: Descripción de la alerta mecánica (que representa)

Fecha1: Fecha en la cual se registró la alerta mecánica en UTC

Valor1: Valor registrado asociado a la alerta mecánica

Fecha2: Fecha en la cual se terminó la alerta mecánica (dependiendo del tipo, puede ser un valor por
defecto, se recomienda omitir) en UTC

Valor2: Valore registrado al fin de la alerta mecánica (dependiendo del tipo, puede ser un valor por
defecto, se recomienda omitir)

Cont: Cantidad de veces que se detectó la condición durante la vida de la alerta

FechaRecepción: Fecha en la cual fue recibido el dato en la base de datos del fabricante en UTC
