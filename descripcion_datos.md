# Formato Diccionario de Datos

---

## Relación: Accidente

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| id_accidente | PK | integer |  | Not Null |  |  |
| Tipo_accidente |  | varchar | 50 | Not Null | Tipo_accidente |  |
| cantidad_hombres |  | integer |  | Not Null |  |  |
| cantidad_mujeres |  | integer |  | Not Null |  |  |
| sexo_afectado |  | varchar | 10 | Not Null | sexo |  |
| Cantidad_accidentes |  | integer |  | Not Null |  |  |
| id_actividad | FK | integer |  | Not Null |  | Actividad_Economica (id_actividad) |
| id_organismo | FK | integer |  | Not Null |  | Organismo_administrador (id_organismo) |

---

## Relación: Organismo_administrador

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| id_organismo | PK | integer |  | Not Null |  |  |
| Nombre_organismo |  | varchar | 50 | Not Null | Nombre_organismo |  |

---

## Relación: Fallecidos_accidente_trabajo

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| id_fallecidos | PK | integer |  | Not Null |  |  |
| id_accidente | FK | integer |  | Not Null |  | Accidente (id_accidente) |
| Año |  | year |  | Not Null |  |  |
| cantidad_fallecidos |  | integer |  | Not Null |  |  |

---

## Relación: Empresa

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| id_empresa | PK | integer |  | Not Null |  |  |
| RUT |  | integer |  | Not Null |  |  |
| DV |  | integer |  | Not Null |  |  |
| Razon_social |  | varchar |  | Not Null |  |  |
| fecha_inicio_act_vigentes |  | date |  | Not Null |  |  |
| fecha_termino_giro |  | date |  | Not Null |  |  |
| fecha_primera_inscripcion_act |  | date |  | Not Null |  |  |
| Tipo_termino_giro |  | varchar | 50 | Not Null | Tipo_termino_giro |  |
| R_presunta |  | varchar | 50 | Not Null | tipo_r_presunta |  |

---

## Relación: Empresa_anio

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| id_empresa_anio | PK | integer |  | Not Null |  |  |
| id_empresa | FK | integer |  | Not Null |  | Empresa (id_empresa) |
| cut_reg | FK | integer |  | Not Null |  | Region (cut_reg) |
| id_actividad | FK | integer |  | Not Null |  | Actividad_Economica (id_actividad) |
| id_contribuyente | FK | integer |  | Not Null |  | Contribuyente (id_contribuyente) |
| anio_comercial |  | year |  | Not Null |  |  |
| Tramo_segun_ventas |  | integer | (1,13) | Not Null |  |  |
| numero_trabajadores_dependientes |  | integer |  | Null |  |  |
| tramo_capital_propio_pos |  | integer | (1,10) | Not Null |  |  |
| tramo_capital_propio_neg |  | integer | (1,10) | Not Null |  |  |
| otros_regimenes |  | varchar | 50 | Not Null | otros_regimenes |  |

---

## Relación: Contribuyente

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| id_contribuyente | PK | integer |  | Not Null |  |  |
| Tipo_contribuyente |  | varchar | 100 | Not Null | Tipo_contribuyente |  |
| Sub_tipo_contribuyente |  | varchar | 100 | Not Null | sub_tipo_contribuyente |  |

---

## Relación: Rubro

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| id_rubro | PK | integer |  | Not Null |  |  |
| Rubro_economico |  | varchar | 100 | Not Null | Tipo_rubro_economico |  |
| Subrubro_economico |  | varchar | 100 | Not Null |  |  |

---

## Relación: Actividad_Economica

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| id_actividad | PK | integer |  | Not Null |  |  |
| id_rubro | FK | integer |  | Not Null |  | Rubro (id_rubro) |
| nombre_actividad |  | varchar | 150 | Not Null |  |  |

---

## Relación: Caja_Compensacion

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| id_caja | PK | integer |  | Not Null |  |  |
| nombre_caja_afiliacion |  | varchar | 100 | Not Null | nombre_caja_afiliacion |  |

---

## Relación: Afiliacion

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| id_actividad | PK, FK | integer |  | Not Null |  | Actividad_Economica (id_actividad) |
| id_caja | PK, FK | integer |  | Not Null |  | Caja_Compensacion (id_caja) |
| cant_afiliadas |  | integer |  | Not Null |  |  |

---

## Relación: Region

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| cut_reg | PF | integer |  | Not Null |  |  |
| nombre_reg |  | varchar |  | Not Null |  |  |

---

## Relación: Provincia

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| cut_prov | PK | integer |  | Not Null |  |  |
| cut_reg | FK | integer |  | Not Null |  | Region (cut_reg) |
| nombre_prov |  | varchar |  | Not Null |  |  |

---

## Relación: Comuna

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| cut_com | PK | integer |  | Not Null |  |  |
| cut_prov | FK | integer |  | Not Null |  | Provincia (cut_prov) |
| nombre_com |  | varchar |  | Not Null |  |  |

---

## Relación: Establecimiento

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| codigo_vigente | PK | integer |  | Not Null |  |  |
| codigo_antiguo |  | varchar | 50 | Null |  |  |
| nombre_oficial |  | varchar | 255 | Not Null |  |  |
| cut_com | FK | integer |  | Not Null |  | Comuna (cut_com) |
| codigo_dependencia | FK | integer |  | Not Null |  | Dependencia_jerarquica (codigo_dependencia) |
| id_tipo_establecimiento | FK | integer |  | Not Null |  | Tipo_establecimiento (id_tipo_establecimiento) |
| pertenencia_snss |  | varchar | 100 | Not Null | pertenencia_snss |  |
| ambito_funcionamiento |  | varchar |  | Not Null | ambito_funcionamiento |  |
| certificacion |  | varchar |  | Null | certificacion |  |
| dependencia_administrativa |  | varchar |  | Not Null | dependencia_administrativa |  |
| nivel_atencion |  | varchar |  | Null | nivel_atencion |  |
| via |  | varchar |  | Null |  |  |
| numero |  | varchar |  | Null |  |  |
| direccion |  | varchar | 255 | Not Null |  |  |
| telefono |  | varchar | 50 | Null |  |  |
| fecha_inicio_funcionamiento |  | date |  | Null |  |  |
| tiene_servicio_urgencia |  | varchar | 15 | Not Null | tiene_servicio_urgencia |  |
| tipo_urgencia |  | varchar | 50 | Null | tipo_urgencia |  |
| clasificacion_sapu |  | varchar | 50 | Null | clasificacion_sapu |  |
| latitud |  | Float4 |  | Null |  |  |
| longitud |  | Float4 |  | Null |  |  |
| tipo_prestador |  | varchar | 100 | Not Null | tipo_prestador |  |
| estado_funcionamiento |  | varchar | 50 | Null | estado_funcionamiento |  |
| nivel_complejidad |  | varchar | 50 | Null | nivel_complejidad |  |
| tipo_atencion |  | varchar | 100 | Not Null | tipo_atencion |  |

---

## Relación: Dependencia_jerarquica

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| codigo_dependencia | PK | integer |  | Not Null |  |  |
| nombre_dependencia |  | varchar | 255 | Not Null | nombre_dependencia |  |

---

## Relación: Tipo_establecimiento

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| id_tipo_establecimiento | PK | integer |  | Not Null |  |  |
| nombre_tipo |  | varchar | 150 | Not Null |  |  |

---

## Relación: Red_Dependencia

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| id_red | PK | integer |  | Not Null |  |  |
| codigo_madre_nuevo |  | integer |  | Not Null |  |  |
| codigo_madre_antiguo |  | varchar |  | Null |  |  |
| codigo_vigente | FK | integer |  | Not Null |  | Establecimiento (codigo_vigente) |

---

## Relación: Reporte_rem07

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| id_reporte | PK | integer |  | Not Null |  |  |
| codigo_vigente | FK | integer |  | Not Null |  | Establecimiento (codigo_vigente) |
| mes |  | smallint |  | Not Null | mes |  |
| anio |  | smallint |  | Not Null |  |  |
| fecha_reporte |  | date |  | Not Null |  |  |

---

---

## Relación: Especialidad_medica

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| id_especialidad | PK | integer |  | Not Null |  |  |
| nombre_especialidad |  | varchar | 150 | Not Null | nombre_especialidad |  |
| area |  | varchar | 100 | Null |  |  |
| requiere_subespecialidad |  | boolean |  | Not Null | requiere_subespecialidad |  |

---

## Relación: Programa_policlinico

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| id_programa | PK | integer |  | Not Null |  |  |
| nombre_programa |  | varchar | 255 | Not Null | nombre_programa |  |

---

## Relación: Profesional_salud

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| id_profesional | PK | integer |  | Not Null |  |  |
| nombre_profesion |  | varchar | 150 | Not Null | nombre_profesion |  |

---

## Relación: Consulta_especialidad

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| id_consulta | PK | integer |  | Not Null |  |  |
| id_reporte | FK | integer |  | Not Null |  | Reporte_rem07 (id_reporte) |
| id_especialidad | FK | integer |  | Not Null |  | Especialidad_medica (id_especialidad) |
| id_rango | FK | integer | 50 | Not Null |  | Rango_etario (id_rango) |
| sexo |  | varchar | 10 | Not Null | sexo |  |
| tipo_consulta |  | varchar | 1 | Not Null | tipo_consulta |  |
| origen_derivacion |  | varchar | 50 | Null | origen_derivacion |  |
| tipo_consulta_nueva |  | varchar | 100 | Null | tipo_consulta_nueva |  |
| atendido_por_medico_general |  | boolean |  | Not Null | atendido_por_medico_general |  |
| cantidad |  | integer |  | Not Null |  |  |

---

## Relación: Eventos_especialidad

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| id_evento | PK | integer |  | Not Null |  |  |
| id_rango | FK | integer |  | Not Null |  | Rango_etario (id_rango) |
| id_reporte | FK | integer |  | Not Null |  | Reporte_rem07 (id_reporte) |
| id_especialidad | FK | integer |  | Not Null |  | Especialidad_medica (id_especialidad) |
| origen |  | varchar | 50 | Null | origen |  |
| cantidad |  | integer |  | Not Null |  |  |
| tipo_evento |  | varchar | 255 | Not Null | tipo_evento |  |

---

## Relación: Atencion_programa

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| id_atencion_programa | PK | integer |  | Not Null |  |  |
| id_reporte | FK | integer |  | Not Null |  | Reporte_rem07 (id_reporte) |
| id_programa | FK | integer |  | Not Null |  | Programa_policlinico (id_programa) |
| id_rango | FK | integer | 50 | Not Null |  | Rango_etario (id_rango) |
| sexo |  | varchar | 10 | Null | sexo |  |
| cantidad |  | integer |  | Not Null |  |  |

---

## Relación: Atencion_otro_profesional

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| id_atencion_prof | PK | integer |  | Not Null |  |  |
| id_reporte | FK | integer |  | Not Null |  | Reporte_rem07 (id_reporte) |
| id_profesional | FK | integer |  | Not Null |  | Profesional_salud (id_profesional) |
| id_rango | FK | integer |  | Not Null |  | Rango_etario (id_rango) |
| paciente_pacto |  | boolean |  | Not Null | paciente_pacto |  |
| sexo |  | varchar | 10 | Not Null | sexo |  |
| cantidad |  | integer |  | Not Null |  |  |
| pueblo_originario |  | boolean |  | Not Null | pueblo_originario |  |
| migrante |  | boolean |  | Not Null | migrante |  |
| paciente_oncologico |  | boolean |  | Not Null | paciente_oncologico |  |

---

## Relación: Atencion_its_vih

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| id_atencion_its | PK | integer |  | Not Null |  |  |
| id_reporte | FK | integer |  | Not Null |  | Reporte_rem07 (id_reporte) |
| id_profesional | FK | integer |  | Not Null |  | Profesional_salud (id_profesional) |
| id_rango | FK | integer |  | Not Null |  | Rango_etario (id_rango) |
| tipo_atencion_its |  | varchar | 50 | Not Null | tipo_atencion_its |  |
| trans_identidad |  | varchar | 50 | Null | trans_identidad |  |
| sexo |  | varchar | 10 | Not Null | sexo |  |
| pueblo_originario |  | boolean |  | Not Null | pueblo_originario |  |
| migrante |  | boolean |  | Not Null | migrante |  |
| ninos_sename |  | boolean |  | Not Null | ninos_sename |  |
| ninos_mejor_ninez |  | boolean |  | Not Null | ninos_mejor_ninez |  |
| cantidad |  | integer |  | Not Null |  |  |

---

## Relación: Actividad_enlace_ecicep

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| Id_actividad_enlace | PK | integer |  | Not Null |  |  |
| id_reporte | FK | integer |  | Not Null |  | Reporte_rem07 (id_reporte) |
| id_rango | FK | integer |  | Not Null |  | Rango_etario (id_rango) |
| tipo_actividad |  | varchar | 100 | Not Null | tipo_actividad |  |
| nivel_riesgo |  | varchar | 20 | Not Null | nivel_riesgo |  |
| sexo |  | varchar | 10 | Not Null | sexo |  |
| procedencia_derivacion |  | varchar | 100 | Null | procedencia_derivacion |  |
| pueblo_originario |  | boolean |  | Not Null | pueblo_originario |  |
| modalidad_atencion |  | varchar |  | Not Null | modalidad_atencion |  |
| migrante |  | boolean |  | Not Null | migrante |  |
| cantidad |  | integer |  | Not Null |  |  |

---

## Relación: Actividad_cpia

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| id_actividad_cpia | PK | integer |  | Not Null |  |  |
| id_reporte | FK | integer |  | Not Null |  | Reporte_rem07 (id_reporte) |
| Id_rango | FK | integer |  | Not Null |  | Rango_etario (id_rango) |
| tipo_vulneracion |  | varchar | 150 | Not Null | tipo_vulneracion |  |
| sexo |  | varchar | 10 | Not Null | sexo |  |
| n_sesiones |  | smallint |  | Not Null |  |  |
| gestante |  | boolean |  | Not Null | gestante |  |
| migrante |  | boolean |  | Not Null | migrante |  |
| pueblo_originario |  | boolean |  | Not Null | pueblo_originario |  |
| ninos_sename |  | boolean |  | Not Null | ninos_sename |  |
| ninos_mejor_ninez |  | boolean |  | Not Null | ninos_mejor_ninez |  |
| trans_identidad |  | varchar | 50 | Null | trans_identidad |  |
| cantidad |  | integer |  | Not Null |  |  |

---

## Relación: Comite_oncologico

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| id_comite_onco | PK | integer |  | Not Null |  |  |
| id_reporte | FK | integer |  | Not Null |  | Reporte_rem07 (id_reporte) |
| menor_18 |  | boolean |  | Not Null | menor_18 |  |
| cantidad |  | integer |  | Not Null |  |  |
| tipo_caso |  | varchar | 255 | Not Null | tipo_caso |  |

---

## Relación: Terapia_hormonal_genero

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| id_thga | PK | integer |  | Not Null |  |  |
| Id_rango | FK | integer |  | Not Null |  | Rango_etario (id_rango) |
| id_reporte | FK | integer |  | Not Null |  | Reporte_rem07 (id_reporte) |
| cantidad |  | integer |  | Not Null |  |  |
| identidad_genero |  | varchar | 50 | Not Null | identidad_genero |  |
| tipo_atencion_thga |  | varchar | 150 | Not Null | tipo_atencion_thga |  |

---

## Relación: Rango_etario

| Nombre Atributo | PF y/o FK | Tipo de dato | Largo | Null/Not Null | Nombre Dominio | Relación de Referencia FK |
|---|---|---|---|---|---|---|
| Id_rango | PK |  |  |  |  |  |
| descripcion_rango |  | varchar |  | Not Null | descripcion_rango |  |

---

# Dominios (una tabla para todos los dominios)

| Nombre Dominio | Tipo de dato | Largo | Valores del Dominio |
|---|---|---|---|
| Tipo_accidente | varchar | 50 | {Accidentes trabajo, Accidentes trayecto, Accidentes de trabajo y trayecto, Enfermedades profesionales} |
| sexo | char | 10 | {Hombre, Mujer} |
| Nombre_organismo | varchar | 50 | {Asociación Chilena de seguridad, Mutual de seguridad C.Ch.C, Instituto de seguridad del trabajo, Instituto de seguridad laboral} |
| Tipo_termino_giro | varchar | 50 | {TERMINO DE GIRO PERSONA JURIDICA, TERMINO GIRO SIMPLIFICADO RES. 41/2002} |
| tipo_r_presunta | varchar | 50 | {REGIMEN RENTA PRESUNTA, Pro Pyme Transparente, Pro Pyme General, Régimen General} |
| otros_regimenes | varchar | 50 | {REGIMEN GENERAL SEMI INTEGRADO (14A), REGIMEN PRO PYME GENRAL (14D), REGIMEN PRO PYME TRANSPARENTE (14D N°8), CONTRIBUYENTES NO SUJETOS AL ARTICULO 14} |
| Tipo_contribuyente | varchar | 100 | {SIN PER. JURIDICA, PERSONA JURIDICA COMERCIAL, ORG. SIN FINES DE LUCRO, SOCIEDADES EXTRANJERAS, ORGANISMOS INTERNACIONALES, INSTITUCIONES FISCALES, MUNICIPALIDADES} |
| sub_tipo_contribuyente | varchar | 100 | {Agencia, Asoc. Gremial, Club deportivo, Comunidades de edificios, Cooperativa, Corporación, Corporación educacional ley 20845, Empr. individual resp. ltda., Entidad sin residencia, Fundación, Junta de vecinos, org. comunitaria, Ministerios, Org. administración publica, Org. ministerio salud, Org. ministerio defensa, Org. ministerio justicia, Organismos internacionales, Organismo autónomo del estado, Org. educación superior, Ostra OSFL, Otras organizaciones sin p. jurídica, Otro establecimiento permanente, Otro org. municipal, Presidencia regional, Sindicato, Soc. plataforma art 41 d, Soc. responsabilidad limitada, Socieda colectiva civil, Sociedad extranjera res 5412/2000, Sociedad por acciones, Sociedades anónimas abiertas, Sociedades anónimas cerradas, Sociedades de hecho, Sucesiones o comunidades hered, Liceo o colegio municipal} |
| Tipo_rubro_economico | varchar | 100 | {ACTIVIDADES DE ATENCIÓN DE LA SALUD HUMANA Y DE ASISTENCIA SOCIAL, TRANSPORTE Y ALMACENAMIENTO, INDUSTRIA MANUFACTURERA, ACTIVIDADES DE ALOJAMIENTO Y DE SERVICIO DE COMIDAS, OTRAS ACTIVIDADES DE SERVICIOS, COMERCIO AL POR MAYOR Y AL POR MENOR; REPARACIÓN DE VEHÍCULOS AUTOMOTORES Y MOTOCICLETAS, ACTIVIDADES INMOBILIARIAS, VALOR POR DEFECTO, ACTIVIDADES PROFESIONALES, CIENTÍFICAS Y TÉCNICAS, ACTIVIDADES DE SERVICIOS ADMINISTRATIVOS Y DE APOYO, AGRICULTURA, GANADERÍA, SILVICULTURA Y PESCA, INFORMACIÓN Y COMUNICACIONES, ENSEÑANZA, CONSTRUCCIÓN, ACTIVIDADES ARTÍSTICAS, DE ENTRETENIMIENTO Y RECREATIVAS, SUMINISTRO DE AGUA; EVACUACIÓN DE AGUAS RESIDUALES, GESTIÓN DE DESECHOS Y DESCONTAMINACIÓN, ACTIVIDADES FINANCIERAS Y DE SEGUROS, ADMINISTRACIÓN PÚBLICA Y DEFENSA; PLANES DE SEGURIDAD SOCIAL DE AFILIACIÓN OBLIGATORIA, ACTIVIDADES DE ORGANIZACIONES Y ÓRGANOS EXTRATERRITORIALES} |
| nombre_caja_afiliacion | varchar | 100 | {De los Andes, La Araucana, Los Héroes, 18 de Septiembre} |
| pertenencia_snss | varchar | 100 | {Perteneciente al Sistema Nacional de Servicios de Salud, No perteneciente al Sistema Nacional de Servicios de Salud} |
| ambito_funcionamiento | varchar |  | {Establecimiento de Salud, Unidad de Atención, Programa de Atención} |
| certificacion | varchar |  | {No Aplica, Centro de Salud Familiar, Autogestionado en Red (EAR), Invitados a ser EAR, No certificado como CESFAM} |
| dependencia_administrativa | varchar |  | {Servicio de Salud, Fuerzas Armadas y de Orden (FFAA), Municipal, Privado, SEREMI de Salud, Otra Institución, Delegados, Gendamería, Corporación Municipal, MINSAL} |
| nivel_atencion | varchar |  | {Primario, Secundario, Terciario, No Aplica} |
| tiene_servicio_urgencia | varchar |  | {SI, NO, No Aplica} |
| tipo_urgencia | varchar |  | {No Aplica, Urgencia Hospitalaria (UEH), Urgencia Ambulatoria (SAPU), Urgencia ambulatoria (SAR), Urgencia Ambulatoria (SUR), Urgencia ambulatoria privada, Ambulatoria Especializada, Hospitalaria Especializada} |
| clasificacion_sapu | varchar |  | {No Aplica, Corto, Largo, Avanzado, Verano} |
| tipo_prestador | varchar |  | {Público, Privado, Fuerzas Armadas y de Orden, Delegados} |
| estado_funcionamiento | varchar |  | {Vigente en operación habitual, Vigente en operación transitoria} |
| nivel_complejidad | varchar |  | {Alta Complejidad, Mediana Complejidad, Baja Complejidad, No Aplica} |
| tipo_atencion | varchar | 100 | {Atención Cerrada-Hospitalaria, Atención Abierta-Ambulatoria, No Aplica, Atención Abierta y Cerrada, Atención Abierta} |
| nombre_dependencia | varchar |  | {Servicio de Salud Arica, Servicio de Salud Iquique, Servicio de Salud Antofagasta, Servicio de Salud Atacama, Servicio de Salud Coquimbo, Servicio de Salud Valparaíso San Antonio, Servicio de Salud Viña del Mar Quillota, Servicio de Salud Aconcagua, Servicio de Salud Metropolitano Norte, Servicio de Salud Metropolitano Occidente, Servicio de Salud Metropolitano Central, Servicio de Salud Metropolitano Oriente, Servicio de Salud Metropolitano Sur, Servicio de Salud Metropolitano Sur Oriente, Servicio de Salud Del Libertador B.O'Higgins, Servicio de Salud Del Maule, Servicio de Salud Ñuble, Servicio de Salud Concepción, Servicio de Salud Arauco, Servicio de Salud Talcahuano, Servicio de Salud Biobío, Servicio de Salud Araucanía Norte, Servicio de Salud Araucanía Sur, Servicio de Salud Valdivia, Servicio de Salud Osorno, Servicio de Salud Del Reloncaví, Servicio de Salud Chiloé, Servicio de Salud Aysén, Servicio de Salud Magallanes} |
| mes | smallint |  | {1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12} |
| nombre_especialidad | varchar | 150 | {Pediatría, Medicina Interna, Neonatología, Enfermedad Respiratoria Pediátrica (Broncopulmonar Infantil), Enfermedad Respiratoria de Adulto (Broncopulmonar), Cardiología, Mastología, Endocrinología Pediátrica, Endocrinología Adulto, Gastroenterología Pediátrica, Gastroenterología Adulto, Genética Clínica, Hematología, Medicina del adolescente, Nefrología Pediátrica, Nefrología Adulto, Nutrición clínica, Medicina Materno Infantil, Reumatología, Medicina Paliativa y de Manejo del Dolor, Dermatología, Infectología, Inmunología, Geriatría, Medicina Física y Rehabilitación, Medicina Reproductiva e Infertilidad, Neurología Pediátrica, Neurología Adulto, Oncología Médica, Psiquiatría Pediátrica y de la Adolescencia, Psiquiatría Adulto, Cirugía Pediátrica, Cirugía General, Cirugía Digestiva (Alta), Cirugía de Cabeza, Cuello y Maxilofacial, Cirugía Plástica y Reparadora, Medicina del Deporte, Coloproctología (Cirugía Digestiva Baja), Cirugía Tórax, Cirugía Vascular Periférica, Neurocirugía, Cirugía Cardiovascular, Anestesiología, Obstetricia y Ginecología, Ginecología oncológica, NeuroRadiologia, Oftalmología, Otorrinolaringología, Traumatología y Ortopedia, Urología, Medicina Familiar, Diabetología, Medicina Nuclear (Excluye Informes), Imagenología, Radioterapia Oncológica} |
| requiere_subespecialidad | boolean |  | {TRUE, FALSE} |
| nombre_programa | varchar | 255 | {ARRITMIAS, DIABETES, CIRUGÍA DE MAMAS, ALTO RIESGO OBSTÉTRICO, TRATAMIENTO ANTICOAGULANTE, CUIDADOS PALIATIVOS, INFERTILIDAD, PATOLOGÍA CERVICAL, PATOLOGÍA DE MAMAS, ADOLESCENCIA, NANEAS, ITS, VIH/SIDA, MEDICINAL OCUPACIONAL (SALUD DEL PERSONAL)} |
| nombre_profesion | varchar | 150 | {Enfermera/o, Matrona/ón, Nutricionista, Psicólogo/a (Excluye SM), Fonoaudiólogo/a, Tecnólogo/a Médico/a, Trabajador/a Social, Terapeuta Ocupacional, Psicólogo/a} |
| tipo_consulta | varchar | 10 | {Nuevas, Controles} |
| origen_derivacion | varchar | 50 | {APS, CAE/CDT/CRS/Hospitalización, Urgencia} |
| tipo_consulta_nueva | varchar | 100 | {Menor 18 años, De 18 y más años} |
| atendido_por_medico_general | boolean |  | {TRUE, FALSE} |
| origen | varchar | 50 | {APS, CAE/CDT/CRS/Hospitalización, Urgencia, Contratados por el Establecimiento o Dirección del Servicio, Especialistas de Hospitales, Red Pública, Privados} |
| tipo_evento | varchar | 255 | {Interconsultas pertinentes según Criterio Clínico, Consultas pertinentes según tiempo establecido en Box, Consultas pertinentes según Criterio Clínico en Box, Contrarreferencia inicial o retorno, Contrarreferencia al alta, Alta de Consulta de Especialidad Ambulatoria, Inasistente a consulta médica NSP, CONSULTA ABREVIADA, Atención Especialista en Sala, Consultas realizadas en APS e informadas, Compra de Servicios, Consultas Médicas por Operativos, Total Interconsultas generadas en APS para derivación Especialidad, Consultorías de Médicos Especialistas otorgadas} |
| paciente_pacto | boolean |  | {TRUE, FALSE} |
| pueblo_originario | boolean |  | {TRUE, FALSE} |
| migrante | boolean |  | {TRUE, FALSE} |
| paciente_oncologico | boolean |  | {TRUE, FALSE} |
| tipo_atencion_its | varchar | 50 | {Consultas ITS, Consultas VIH/SIDA, Control VIH con TAR, Control VIH sin TAR, Controles Salud Sexual Comercio Sexual} |
| trans_identidad | varchar | 50 | {Masculino, Femenino, No Aplica} |
| ninos_sename | boolean |  | {TRUE, FALSE} |
| ninos_mejor_ninez | boolean |  | {TRUE, FALSE} |
| tipo_actividad | varchar | 100 | {Ingreso a Atención de PDE, Seguimiento de PDE, Continuidad en la Gestión (PDE-APS), Actividades de Gestión de PDE, Inasistente a Atención de PDE (NSP)} |
| nivel_riesgo | varchar | 20 | {Riesgo Alto (G3), Riesgo Moderado (G2)} |
| procedencia_derivacion | varchar | 100 | {APS, CAE/CDT/CRS, Hospitalización, Urgencia} |
| modalidad_atencion | varchar |  | {Presencial, Remota} |
| tipo_vulneracion | varchar | 150 | {Análisis de casos, Sospecha de Maltrato Infantil, Maltrato infantil, Sospecha de Abuso Sexual, Abuso sexual infantil, Negligencia, Otras} |
| gestante | boolean |  | {TRUE, FALSE} |
| menor_18 | boolean |  | {TRUE, FALSE} |
| tipo_caso | varchar | 255 | {Confirmación diagnóstica antes del primer tratamiento, Casos totales presentados} |
| identidad_genero | varchar | 50 | {Trans Masculino, Trans Femenina, No Binarie, Otra, Hombre, Mujer} |
| tipo_atencion_thga | varchar | 150 | {Personas en atención, Primera consulta, Control Integral} |
| descripcion_rango | varchar |  | {0 - 4 años, 5 - 9 años, 10 - 14 años, 15 - 17 años, 18 - 19 años, 20 - 24 años, 25 - 29 años, 30 - 34 años, 35 - 39 años, 40 - 44 años, 45 - 49 años, 50 - 54 años, 55 - 59 años, 60 - 64 años, 65 - 69 años, 70 - 74 años, 75 - 79 años, 80 y más años, Menor de 18 años, 18 años y más, 30 años o mas} |
