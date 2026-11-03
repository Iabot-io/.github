# Registro revisable de plazos — evidencia ficticia

Revisión: 2026-11-03. Expediente, entidad y jurisdicción: no especificados. Fuente única aportada; no se han consultado fuentes oficiales ni servicios externos. La aplicabilidad y vigencia de la regla requieren revisión profesional con el ámbito y evidencia correspondientes.

**Resultado: vencimiento pendiente, no calculado y no validado.** La fecha de envío no se convierte en notificación válida y las publicaciones no sustituyen el hecho inicial exigido.

| Hecho | Fecha aportada | Tratamiento |
|---|---|---|
| Publicación de notice-v1 | 2026-10-01 | Evidencia de publicación; no acredita notificación válida |
| Publicación de correction-v2 | 2026-10-05 | Evidencia de corrección; no reinicia por sí sola el plazo |
| Envío de notificación | 2026-10-07 | Envío; no se equipara con recepción, acceso o notificación válida |
| Acceso a notificación | No aportado (`null`) | Sin fecha ni evidencia de acceso |
| Notificación válida | No aportada (`null`) | Falta el hecho inicial que exige la regla |
| Emisión del documento | No aportada | No se deduce de su publicación |

## Regla y secuencia de comprobación

1. La regla literal de `notice-v1.rules.deadline` es «15 business days following valid notification»: 15 días hábiles siguientes a una notificación válida. Se conserva la unidad aportada; no se sustituye por días naturales ni se reduce el calendario a lunes-viernes.
2. `correction-v2` declara que sustituye únicamente `notice-v1.required_format` y añade un documento. No consta sustitución expresa de la regla temporal, por lo que ésta se conserva en la lectura de la evidencia ficticia; su aplicabilidad jurídica no se certifica.
3. La fecha de notificación válida y la evidencia que la acredite están pendientes. No se usa 2026-10-07 como inicio ni se infiere una notificación presunta por falta de apertura.
4. `calendar` es `null` y la jurisdicción no se especifica. Faltan el calendario aplicable al procedimiento, festivos, tratamiento del inicio y del vencimiento y, si procede, hora límite y zona horaria. No se elige un ámbito por defecto.
5. No se aportan suspensiones, prórrogas o decisiones que afecten al cómputo. Su ausencia en el archivo no acredita que no existan. No se puede completar la secuencia de cómputo.

El registro CSV conserva los eventos documentados en filas separadas y una fila de plazo. Todas las celdas `fecha_resultado` permanecen vacías. Las fechas de evento no son fechas de vencimiento. No se ofrece una fecha provisional basada en supuestos.

## Pendiente para cerrar el registro

Se requiere que el responsable aporte el expediente y ámbito aplicable, la fecha y evidencia de notificación válida, la regla vigente para el caso, el calendario correspondiente y las eventuales suspensiones, prórrogas e instrucciones sobre vencimiento. El profesional deberá revisar el cálculo antes de marcarlo validado. No se ha creado ni presentado ningún trámite ni se ha declarado presentado material alguno.

## Trazabilidad

Fuente: `input.json`, selecciones `#/documents/0`, `#/documents/1`, `#/notification`, `#/calendar` y `#/jurisdiction`. Revisiones documentales aportadas: `notice-v1` y `correction-v2`, con publicaciones respectivas 2026-10-01 y 2026-10-05. No se acredita su procedencia oficial. Revisión exacta de la entrada: SHA-256 `8e09e532349d151db412b440f49bdf0b2915919f67b1dd2451949065897cbd6d`.

Habilidad: `https://github.com/Iabot-io/legal-tender-skills/blob/main/skills/legal-deadline-register/SKILL.md`, versión 0.1.0, SHA-256 `8715d49f82484b4653e1fbe2a0b89fb2da64043f263362c7103e037e950ce5f1`. Se empleó `assets/registro.csv`, conservando sus columnas y ampliándolas con tipo de registro, unidad, jurisdicción, estado, suspensiones y revisión de fuente. Archivo: `deadline-register.csv`.
