# Kit de entrevista estructurada — operador de inventario

Borrador para revisión humana, 2026-11-03. Se vincula únicamente con las tres funciones y competencias aportadas. `conditions_confirmed` es `false`: no se presentan como acordadas las condiciones del puesto, instrucciones operativas, escala, tiempos o umbrales de evaluación.

La nota no revisada de preferencia por edad se excluye de preguntas, rúbrica, puntuación y decisiones porque no es una competencia o función del puesto. No se solicitan edad ni datos personales ajenos a la tarea. Se conserva su referencia de origen en `results.json`, sin reproducirla como condición válida.

## Guion y rúbrica propuestos

Los escenarios son preguntas diseñadas para este kit, no hechos observados de una candidatura ni instrucciones aprobadas de un almacén. Los niveles 1–3 son una propuesta ordinal previa a las entrevistas; no se agregan ni se usan para decidir contratación. `NE` significa que no hay evidencia suficiente y no equivale al nivel 1.

### Q1 — precision de recuento

Función: recuento de existencias.

Pregunta: En un recuento aparecen dos resultados distintos para una misma referencia y ubicacion. Explica como comprobarias el recuento y dejarias trazabilidad antes de comunicar la diferencia.

Evidencia esperada: Metodo de comprobacion, separacion de registros originales y resultados verificados, y trazabilidad de referencia/ubicacion y cantidades sin inventarlas.

| Nivel propuesto | Descriptor observable |
|---|---|
| 1 | Da por valido uno de los resultados sin explicar una comprobacion ni conservar los datos de partida. |
| 2 | Describe una repeticion del recuento y compara resultados, pero no explica como vincular la comprobacion con el registro original. |
| 3 | Describe una comprobacion ordenada y conserva por separado datos originales, resultado verificado y referencia/ubicacion; no corrige sin evidencia. |

### Q2 — seguimiento de instrucciones

Función: uso de lector de codigos.

Pregunta: Durante una lectura aparece un codigo ilegible o distinto del esperado. Como actuarias para seguir las instrucciones del puesto sin dar una lectura dudosa por valida?

Evidencia esperada: Reconocimiento de una lectura no confirmada, consulta de la instruccion aplicable y canal autorizado; sin inventar botones, permisos o un procedimiento del centro.

| Nivel propuesto | Descriptor observable |
|---|---|
| 1 | Acepta una lectura dudosa o propone omitir la comprobacion sin remitirse a instrucciones. |
| 2 | Detiene la validacion de la lectura y consulta la instruccion o ayuda autorizada antes de continuar. |
| 3 | Ademas explica como comprobar correspondencia de articulo/codigo segun la instruccion, registrar la excepcion y escalarla si sigue sin resolverse, sin asumir permisos. |

### Q3 — comunicacion de diferencias

Función: registro de incidencias.

Pregunta: Prepara oralmente o por escrito un modelo breve de incidencia para una diferencia entre recuento fisico y registro. Indica que datos incluirias y como separarias hechos de una causa aun no confirmada.

Evidencia esperada: Referencia/ubicacion, cantidades o evidencias que realmente se conozcan, diferencia descrita, incertidumbre separada y pasos pendientes; sin completar datos ausentes.

| Nivel propuesto | Descriptor observable |
|---|---|
| 1 | Comunica solo una conclusion o una causa no acreditada, sin identificar los hechos que sustentan la incidencia. |
| 2 | Separa hechos y causa pendiente e indica referencia/ubicacion y datos de la diferencia que deberian registrarse. |
| 3 | Ademas vincula hechos con su evidencia/fecha cuando exista y explicita comprobaciones y canal pendientes, sin completar valores o causas desconocidos. |

## Aplicación y hoja de evidencias

Usar las mismas tres preguntas, criterios y oportunidades de respuesta para todas las candidaturas una vez aprobado el kit. Acordar antes las aclaraciones neutras, el tiempo y el modo de respuesta. Las adaptaciones de accesibilidad deben conservar la competencia evaluada; no se penaliza la necesidad de una adaptación ni un estilo de expresión que no sea requisito de la función.

Registrar por separado citas textuales o hechos observados, impresiones del entrevistador y nivel razonado. No rellenar hechos a partir de impresiones. Si no se realizó una pregunta o no se pudo obtener evidencia comparable, usar NE y dejar el motivo; no asignar el mínimo por defecto. No hay ponderaciones, nota total, umbral de selección ni clasificación de candidaturas aprobados.

`registro.csv` contiene los nueve descriptores del borrador. `evidence-sheet.csv` ofrece tres filas vacías con campos separados para hechos, citas, impresiones y valoración; ningún candidato ha sido evaluado. El revisor queda sin asignar.

Pendiente: confirmar condiciones y perfil, instrucciones de recuento y lector, formato y tiempos de entrevista, criterios y escala finales y revisión de RR. HH. Las decisiones laborales corresponden a las personas responsables; el kit no recomienda una contratación.

## Trazabilidad

Fuente ficticia única: `input.json`, selección `#/input`. Revisión de la entrada: SHA-256 `40b72807bb94ad6f7b20ace07ce4e37fab73d634d13bd5c1d25d9eab7cb8af26`. Habilidad: `https://github.com/Iabot-io/human-resources-skills/blob/main/skills/structured-interview-kit/SKILL.md`, versión 0.1.0, SHA-256 `0e3cade9cd8d9a97203032d45582722c988cb77f231936c5b27beb93140c4778`. Se emplea su `assets/registro.csv` conservando todas las columnas y añadiendo los campos necesarios para referencias, revisión y estados. No se consultan servicios externos ni datos de producción. La nota excluida está en `#/input/unreviewed_notes/0`.
