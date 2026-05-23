# Entidades y atributos
> Cap I: cuadro 25
## Actividad_economica
| Dato | Tipo_dato | Dominio |
|----------|----------|----------|
| id_act_economica    | integer (no nulo)   | PK   |
| Nombre_actividad_economica    | Tipo_actividad_economica (no nulo)   |   {Actividades inmobiliarias,empresariales y de alquiler, Administración publica y defensa; planes de seguridad social, Agricultura, ganadería, caza y silvicultura, Comercio, reparación de vehículos y otros, Construcción, Enseñanza, Explotación de minas y canteras, Hogares privados con servicio doméstico, Hoteles y restaurantes, Industrias manufactureras, Intermediación financiera, Otras actividades de servicios comunitarios, sociales y personales, Organizaciones y órganos extraterritoriales, Pesca, Servicios sociales y de salud, Suministro de electricidad, gas y agua, Transporte, almacenamiento y comunicaciones} |
## Registro_accidente
| Dato | Tipo_dato | Dominio |
|----------|----------|----------|
| id_registro_accidente    | integer (no nulo)   |PK   |
| Tipo_accidente   | Tipo_accidente (no nulo)   | {Accidentes trabajo, Accidentes trayecto, Accidentes de trabajo y trayecto, Enfermedades profesionales}    |
| Cantidad hombres    | integer (no nulo)   | -   |
| Cantidad mujeres    | integer (no nulo)   | -   |
## Accidentes_de_trabajo
| Dato | Tipo_dato | Dominio |
|----------|----------|----------|
| id_acc_trabajo    | integer (no nulo)   |  PK   |
| id_registro_accidente    | FK   | -   |
| id_act_economica    | FK   | -   |
| cantidad    | integer (no nulo)   | -   |
| Tipo_sexo    | Tipo_sexo   | {Hombre, Mujer}   |
> Cap I: cuadro 40
## Accidente
| Dato | Tipo_dato | Dominio |
|----------|----------|----------|
| id_accidente    | integer (no nulo)  | PK   |
| tipo_accidente    | Tipo_accidente   | {Accidente de trabajo, Accidente de trayecto, Accidente (trabajo + trayecto)}   |
## Organismo_administrador
| Dato | Tipo_dato | Dominio |
|----------|----------|----------|
| id_organismo    | integer (no nulo)   | PK   |
| Row 3    | Cell 8   | {Asociación Chilena de seguridad, Mutual de seguridad C.Ch.C, Instituto de seguridad laboral}   |
## Fallecidos_accidente_trabajo
| Dato | Tipo_dato | Dominio |
|----------|----------|----------|
| id_fallecidos    | integer (no nulo)   | PK   |
| id_accidente    | FK   | -   |
| id_organismo    | FK   | -   |
| Año    | year (no nulo)  | -   |
| Cantidad_fallecidos    | integer (no nulo)   | -   |
## Empresa
| Dato | Tipo_dato | Dominio |
|----------|----------|----------|
| Row 3    | Cell 8   | Cell 9   |
| Row 3    | Cell 8   | Cell 9   |
| Row 3    | Cell 8   | Cell 9   |
| Row 3    | Cell 8   | Cell 9   |
| Row 3    | Cell 8   | Cell 9   |
| Row 3    | Cell 8   | Cell 9   |
| Row 3    | Cell 8   | Cell 9   |