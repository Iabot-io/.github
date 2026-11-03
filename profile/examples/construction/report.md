# Propuesta de certificación para revisión — octubre de 2026

Caso ficticio. **Propuesta provisional sin firma ni aprobación.** Moneda: EUR. El subtotal que puede presentarse para revisión sin incorporar la corrección P2 es **150,00 EUR antes de conceptos contractuales/fiscales pendientes**. No es un importe líquido a pagar ni una certificación aprobada.

| Partida | Unidad | Acumulado anterior aportado | Actual aportado | Diferencia del periodo | Precio contractual aportado EUR | Importe calculado EUR | Tratamiento |
|---|---|---:|---:|---:|---:|---:|---|
| P1 | m2 | 30 | 45 | 15 | 10,00 | 150,00 | Incluido en subtotal provisional para revisión |
| P2 | m | 12 | 10 | −2 | 8,00 | −16,00 | Corrección pendiente; no incluida en subtotal propuesto |

Fórmulas: `P1 = (45 − 30) × 10 = 150 EUR`; `P2 = (10 − 12) × 8 = −16 EUR`. La propuesta usa el incremento del periodo, nunca los 45 m2 completos otra vez. Tampoco se suman m2 y m como una cantidad común.

La cantidad negativa P2 se conserva y explica: no se elimina, no se convierte en cero ni se incorpora como descuento autorizado. `p2_correction_authorized` es nulo. Hay que aclarar si existe error de medición, reclasificación o rectificación, aportar la medición anterior y actual y documentar su aprobación. No se ha elegido una causa sin evidencia.

Comprobación de acumulados: P1 `30 + 15 = 45`; P2 `12 − 2 = 10`. Con los mismos precios, el acumulado anterior aritmético es `30 × 10 + 12 × 8 = 396 EUR` y el actual, `45 × 10 + 10 × 8 = 530 EUR`. Su diferencia es **134 EUR**, igual a `150 − 16`. Este agregado es exclusivamente aritmético y solo sería una base revisable incluyendo P2 si su corrección y las mediciones se validasen. No es el subtotal provisional de 150 EUR ni una certificación emitida. Si se retiene P2 pendiente, el subtotal provisional no puede presentarse como una conciliación íntegra del acumulado actual.

Se han utilizado únicamente los precios contractuales etiquetados en la entrada. No consta contrato identificable, revisión de precios ni copia de las certificaciones anteriores; `previous_cumulative` se usa como acumulado anterior aportado, sin afirmar que haya sido efectivamente certificado o aprobado. No hay documentación de modificados ni partidas fuera de contrato: se dejan sin evaluar.

**Deducciones e impuestos:** no se aportan reglas de anticipos o retenciones y `tax_rule` es nulo. Permanecen separados y sin cuantificar; no se aplica un IVA supuesto ni se interpreta «desconocido» como cero. No se puede cerrar total fiscal, líquido ni pago.

Fuentes por fila: `input.json#/input/lines/0` y `/1`; periodo, moneda y autorización: `input.json#/input`. Identidad y revisión se conservan por hashes en `source_manifest.json`; skill versión 0.1.0. `registro.csv` adapta la plantilla original, conserva el importe calculado de P2 y añade un campo separado de importe propuesto y estado. `results.json` conserva los totales y nulos pendientes.

Comprobaciones locales: incrementos/acumulados y valoraciones cuadran; la corrección no autorizada queda excluida de la propuesta; impuestos y líquido permanecen desconocidos. No se ha aprobado, firmado, contabilizado ni enviado nada.

Observación de la habilidad: establece mantener pendientes las discrepancias, pero no concreta la presentación de acumulados decrecientes. La plantilla tampoco distingue importe matemático e importe propuesto. Se añadieron esas columnas para impedir que una suma automática convierta −16 EUR pendientes en una deducción aprobada. No se detectó un bloqueo de la tarea.
