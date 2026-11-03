# Lista administrativa de licitación — evidencia ficticia

Revisión: 2026-11-03. Expediente, lotes, procedimiento y entidad ofertante: no aportados. Se revisa únicamente el inventario ficticio; no hay archivos documentales para comprobar firmas, contenido, vigencias o conformidad técnica PDF/A. La clave `submitted_material` identifica aquí material aportado para revisión y no acredita presentación de una oferta.

**Estado: documentación incompleta; ningún requisito se marca completo ni oferta presentada.** No se envía, firma, convierte ni modifica material.

## Consolidación de versiones

| Fuente | Publicación aportada | Efecto en esta revisión |
|---|---|---|
| notice-v1 | 2026-10-01 | Exige declaración firmada y memoria técnica; formato original PDF; regla de plazo |
| correction-v2 | 2026-10-05 | Sustituye expresamente el formato por PDF/A y añade cuadro de precios |

Se conservan los dos documentos originales y se añade el cuadro de precios: la corrección no sustituye toda la lista. PDF deja de ser el formato exigido en la lectura consolidada; PDF/A es el formato aplicable según la corrección. El campo de formato no contiene una limitación por documento y se aplica a los tres requisitos en esta lectura de la entrada; su alcance deberá contrastarse con el documento oficial. No consta modificación de la regla de plazo. No se ha verificado la publicación oficial, vigencia para el caso ni existencia de otras aclaraciones fuera de lo aportado.

## Checklist

Todos los elementos de la tabla proceden de exigencias expresas de la evidencia, no de recomendaciones añadidas. El responsable de cada requisito está sin asignar; no se inventan cargos o personas.

| Requisito | Evidencia aportada | Formato vigente / aportado | Firma | Estado y pendiente | Vigencia / responsable |
|---|---|---|---|---|---|
| Declaración firmada | `declaration`, inventario 0 | PDF/A / PDF/A declarado | `signed=false` | Incompleto: falta firma. Coincidencia de etiqueta de formato; archivo no validado | Vigencia no aportada / sin asignar |
| Memoria técnica | `technical memo`, inventario 1 | PDF/A / PDF | `signed=null`: desconocida; no consta una exigencia propia de firma | Incompleto: formato declarado no cumple la corrección. No se añade un incumplimiento de firma sin base | Vigencia no aportada / sin asignar |
| Cuadro de precios | `price schedule`, inventario 2 | PDF/A / no aportado | No evaluable; no consta exigencia propia de firma | Pendiente: `present=false`, falta documento | No evaluable / sin asignar |

No se confunde la existencia de una entrada en el inventario con un documento completo, firmado, vigente o presentado. No se inventan solvencia, certificaciones, contenido de la memoria ni importes del cuadro de precios.

## Acciones de preparación pendientes de revisión

1. Designar responsables y obtener los documentos fuente, expediente, lote y entidad para comprobar correspondencia y versiones. Obtener evidencia de las aclaraciones aplicables; esta prueba no consulta servicios externos.
2. Completar la declaración con la firma que corresponda y verificarla en el documento real. Su formato PDF/A sólo está declarado en los datos, no técnicamente validado.
3. Preparar y verificar la memoria técnica en el formato PDF/A exigido. Aclarar las condiciones de firma y presentación sin añadir requisitos no documentados.
4. Obtener el cuadro de precios exigido por la corrección en PDF/A; comprobar contenido y condiciones formales cuando se disponga del documento y de las bases.
5. Resolver el plazo mediante el registro adjunto. Falta notificación válida y calendario, por lo que no se fija una fecha de entrega ni se presume margen disponible.

Estas acciones son preparación documental pendiente de autorización y revisión. No sustituyen una validación jurídica ni declaran lista la oferta.

## Trazabilidad

Fuente: `input.json`, documentos `#/documents/0` (`notice-v1`) y `#/documents/1` (`correction-v2`), y evidencias `#/submitted_material/0..2`. Revisión exacta de la entrada: SHA-256 `8e09e532349d151db412b440f49bdf0b2915919f67b1dd2451949065897cbd6d`. Las fechas de publicación e identificadores se conservan como datos ficticios aportados; no se certifica su oficialidad.

Habilidad: `https://github.com/Iabot-io/legal-tender-skills/blob/main/skills/tender-administrative-checklist/SKILL.md`, versión 0.1.0, SHA-256 `dfa3ba4c5dd04359ba7e80f094f87a20bb85404da6c115d5427c6bd20b249905`. Se empleó `assets/registro.csv`, conservando sus columnas y añadiendo identificador, naturaleza de requisito, formato exigido/aportado, evidencia y revisión de fuente. Archivo: `tender-administrative-checklist.csv`. Registro de plazos relacionado: `deadline-register.md` y `deadline-register.csv`.
