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
> Empresa
## Empresa
| Dato | Tipo_dato | Dominio |
|----------|----------|----------|
| id_empresa    | integer (no nulo)   | -   |
| RUT    | integer (no nulo)   | -   |
| DV    | integer (no nulo)   | -   |
| Razon_social    | varchar(100)   | -   |
| Fecha_inicio_act_vigente    | date   | -   |
| Fecha_termino_giro    | date   | -   |
| Fecha_primera_inscripcion_act    | date   | -   |
| Tipo_termino_giro    | Tipo_termino_giro   | {TERMINO DE GIRO PERSONA JURIDICA, TERMINO GIRO SIMPLIFICADO RES. 41/2002}   |
| R_presunta    | Tipo_r_presunta   | REGIMEN RENTA PRESUNTA, OTRO   |
## Empresa_anio
| Dato | Tipo_dato | Dominio |
|----------|----------|----------|
| id_empresa    | integer (no nulo)   | -   |
| id_ubicacion    | FK   | -   |
| id_actividad    | FK   | -   |
| id_contribuyente    | FK   | -   |
| anio_comercial    | year (no nulo)  |  -  |
| Tramo_segun_ventas    | integer (no nulo)   | *[1,13]   |
| Numero_trabajadores_dependientes    | integer (nulo)  | -   |
| Tramo_capital_propio_pos    | integer (no nulo)   |  *[1,10]  |
| Tramo_capital_neg    | integer (no nulo)  | *[1,10]   |
| Otros_regimenes    | otros_regimenes   | {REGIMEN GENERAL SEMI INTEGRADO (14A), REGIMEN PRO PYME GENRAL (14D), REGIMEN PRO PYME TRANSPARENTE (14D N°8), CONTRIBUYENTES NO SUJETOS AL ARTICULO 14}   |
## Ubicacion
| Dato | Tipo_dato | Dominio |
|----------|----------|----------|
| id_ubicacion    | integer (no nulo)  | -   |
| Region    | region   | {XV Región de Arica y Parinacota, I Región de Tarapacá, II Región de Antofagasta, III Región de Atacama, IV Región de Coquimbo, V Región de Valparaíso, Región Metropolitana de Santiago, VI Región del Libertador General Bernardo O’Higgins, VII Región del Maule, XVI Región de Ñuble, VIII Región del Biobío, IX Región de la Araucanía, XIV Región de los Ríos, X Región de los Lagos, XI Región de Aysén del General Carlos Ibáñez del Campo, XII Región de Magallanes y la Antártica Chilena}   |
| Provincia    | provincia   | {Provincia de Arica, Provincia de Parinacota, Provincia de Iquique, Provincia del Tamarugal, Provincia de Antofagasta, Provincia de El Loa, Provincia de Tocopilla, Provincia de Chañaral, Provincia de Copiapó, Provincia de Huasco, Provincia de Choapa, Provincia de Elqui, Provincia de Limarí, Provincia de Isla de Pascua, Provincia de Los Andes, Provincia de Petorca, Provincia de Quillota, Provincia de San Antonio, Provincia de San Felipe de Aconcagua, Provincia de Marga Marga, Provincia de Valparaíso, Provincia de Cachapoal, Provincia de Cardenal Caro, Provincia de Colchagua, Provincia de Cauquenes, Provincia de Curicó, Provincia de Linares, Provincia de Talca, Provincia de Arauco, Provincia de Biobío, Provincia de Concepción, Provincia de Itata, Provincia de Diguillín, Provincia de Punilla, Provincia de Malleco, Provincia de Cautín, Provincia de Valdivia, Provincia del Ranco, Provincia de Osorno, Provincia de Llanquihue, Provincia de Chiloé, Provincia de Palena, Provincia de Coyhaique, Provincia de Aysén, Provincia de Capitán Prat, Provincia de General Carrera, Provincia de Última Esperanza, Provincia de Magallanes, Provincia de Tierra del Fuego, Provincia de Antártica Chilena, Provincia de Chacabuco, Provincia de Cordillera, Provincia de Maipo, Provincia de Melipilla, Provincia de Santiago, Provincia de Talagante}   |
| Comuna    | comuna   | {Arica, Camarones, General Lagos, Putre, Alto Hospicio, Camiña, Colchane, Huara, Iquique, Pica, Pozo Almonte, Antofagasta, Calama, María Elena, Mejillones, Ollagüe, San Pedro de Atacama, Sierra Gorda, Taltal, Tocopilla, Alto del Carmen, Caldera, Chañaral, Copiapó, Diego de Almagro, Freirina, Huasco, Tierra Amarilla, Vallenar, Andacollo, Canela, Combarbalá, Coquimbo, Illapel, La Higuera, La Serena, Los Vilos, Monte Patria, Ovalle, Paiguano, Punitaqui, Río Hurtado, Salamanca, Vicuña, Algarrobo, Cabildo, Calera, Calle Larga, Cartagena, Casablanca, Catemu, Concón, El Quisco, El Tabo, Hijuelas, Isla de Pascua, Juan Fernández, La Cruz, La Ligua, Limache, Llaillay, Los Andes, Nogales, Olmué, Panquehue, Papudo, Petorca, Puchuncaví, Putaendo, Quillota, Quilpué, Quintero, Rinconada, San Antonio, San Esteban, San Felipe, Santa María, Santo Domingo, Valparaíso, Villa Alemana, Viña del Mar, Zapallar, Alhué, Buin, Calera de Tango, Cerrillos, Cerro Navia, Colina, Conchalí, Curacaví, El Bosque, El Monte, Estación Central, Huechuraba, Independencia, Isla de Maipo, La Cisterna, La Florida, La Granja, La Pintana, La Reina, Lampa, Las Condes, Lo Barnechea, Lo Espejo, Lo Prado, Macul, Maipú, María Pinto, Melipilla, Ñuñoa, Padre Hurtado, Paine, Pedro Aguirre Cerda, Peñaflor, Peñalolén, Pirque, Providencia, Pudahuel, Puente Alto, Quilicura, Quinta Normal, Recoleta, Renca, San Bernardo, San Joaquín, San José de Maipo, San Miguel, San Pedro, San Ramón, Santiago, Talagante, Tiltil, Vitacura, Chépica, Chimbarongo, Codegua, Coinco, Coltauco, Doñihue, Graneros, La Estrella, Las Cabras, Litueche, Lolol, Machalí, Malloa, Marchigüe, Mostazal, Nancagua, Navidad, Olivar, Palmilla, Paredones, Peralillo, Peumo, Pichidegua, Pichilemu, Placilla, Pumanque, Quinta de Tilcoco, Rancagua, Rengo, Requínoa, San Fernando, San Vicente, Santa Cruz, Cauquenes, Chanco, Colbún, Constitución, Curepto, Curicó, Empedrado, Hualañé, Licantén, Linares, Longaví, Maule, Molina, Parral, Pelarco, Pelluhue, Pencahue, Rauco, Retiro, Río Claro, Romeral, Sagrada Familia, San Clemente, San Javier, San Rafael, Talca, Teno, Vichuquén, Villa Alegre, Yerbas Buenas, Bulnes, Chillán, Chillán Viejo, Cobquecura, Coelemu, Coihueco, El Carmen, Ninhue, Ñiquén, Pemuco, Pinto, Portezuelo, Quillón, Quirihue, Ranquil, San Carlos, San Fabián, San Ignacio, San Nicolás, Trehuaco, Yungay, Alto Biobío, Antuco, Arauco, Cabrero, Cañete, Chiguayante, Concepción, Contulmo, Coronel, Curanilahue, Florida, Hualpén, Hualqui, Laja, Lebu, Los Álamos, Los Ángeles, Lota, Mulchén, Nacimiento, Negrete, Penco, Quilaco, Quilleco, San Pedro de la Paz, San Rosendo, Santa Bárbara, Santa Juana, Talcahuano, Tirúa, Tomé, Tucapel, Yumbel, Angol, Carahue, Cholchol, Collipulli, Cunco, Curacautín, Curarrehue, Ercilla, Freire, Galvarino, Gorbea, Lautaro, Loncoché, Lonquimay, Los Sauces, Lumaco, Melipeuco, Nueva Imperial, Padre Las Casas, Perquenco, Pitrufquén, Pucón, Purén, Renaico, Saavedra, Temuco, Teodoro Schmidt, Toltén, Traiguén, Victoria, Vilcún, Villarrica, Corral, Futrono, La Unión, Lago Ranco, Lanco, Los Lagos, Mafil, Mariquina, Paillaco, Panguipulli, Río Bueno, Valdivia, Ancud, Calbuco, Castro, Chaitén, Chonchi, Cochamó, Curaco de Vélez, Dalcahue, Fresia, Frutillar, Futaleufú, Hualaihué, Llanquihue, Los Muermos, Maullín, Osorno, Palena, Puerto Montt, Puerto Octay, Puerto Varas, Puqueldón, Purranque, Puyehue, Queilén, Quellón, Quemchi, Quinchao, Río Negro, San Juan de la Costa, San Pablo, Aisén, Chile Chico, Cisnes, Cochrane, Coyhaique, Guaitecas, Lago Verde, O'Higgins, Río Ibáñez, Tortel, Antártica, Cabo de Hornos, Laguna Blanca, Natales, Porvenir, Primavera, Punta Arenas, Río Verde, San Gregorio, Timaukel, Torres del Paine}   |
## Contribuyente
| Dato | Tipo_dato | Dominio |
|----------|----------|----------|
| id_contribuyente    | integer (no nulo)  | -   |
| Tipo_contribuyente    | Tipo_contribuyente   | {SIN PER. JURIDICA, PERSONA JURIDICA COMERCIAL, ORG. SIN FINES DE LUCRO, SOCIEDADES EXTRANJERAS, ORGANISMOS INTERNACIONALES, INSTITUCIONES FISCALES, MUNICIPALIDADES}   |
| Sub_tipo_contribuyente    | sub_tipo_contribuyente   | {Agencia, Asoc. Gremial, Club deportivo, Comunidades de edificios, Cooperativa, Corporación, Corporación educacional ley 20845, Empr. individual resp. ltda., Entidad sin residencia, Fundación, Junta de vecinos, org. comunitaria, Ministerios, Org. administración publica, Org. ministerio salud, Org. ministerio defensa, Org. ministerio justicia, Organismos internacionales, Organismo autónomo del estado, Org. educación superior, Ostra OSFL, Otras organizaciones sin p. jurídica, Otro establecimiento permanente, Otro org. municipal, Presidencia regional, Sindicato, Soc. plataforma art 41 d, Soc. responsabilidad limitada, Socieda colectiva civil, Sociedad extranjera res 5412/2000, Sociedad por acciones, Sociedades anónimas abiertas, Sociedades anónimas cerradas, Sociedades de hecho, Sucesiones o comunidades hered, Liceo o colegio municipal}   |
## Actividades
| Dato | Tipo_dato | Dominio |
|----------|----------|----------|
| Row 3    | Cell 8   | Cell 9   |
| Row 3    | Cell 8   | Cell 9   |
| Row 3    | Cell 8   | Cell 9   |
| Row 3    | Cell 8   | Cell 9   |
| Row 3    | Cell 8   | Cell 9   |
| Row 3    | Cell 8   | Cell 9   |
| Row 3    | Cell 8   | Cell 9   |
| Row 3    | Cell 8   | Cell 9   |
| Row 3    | Cell 8   | Cell 9   |
| Row 3    | Cell 8   | Cell 9   |

