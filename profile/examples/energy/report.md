# Normalización y conciliación energética — periodo original 2026-10

Caso ficticio. **F2 sustituye a F1: los documentos vigentes son F2 y F3.** El subtotal energético documentado en kWh es **120 kWh para A**. El dato de B, **70 kW**, tiene dimensión de potencia y no puede sumarse como energía. El consumo energético de B y el total de energía de todos los suministros quedan pendientes.

| Documento | Suministro | Periodo original | Estado | Dato original | Energía admisible kWh | Potencia: dato dimensional kW | Coste etiquetado energía | Otros | Impuestos | Total |
|---|---|---|---|---|---:|---:|---:|---:|---:|---:|
| F1 | A | 2026-10 | Sustituido por F2, excluido | 100 kWh | 100, solo histórico | — | 20,00 | 5,00 | 2,50 | 27,50 |
| F2 | A | 2026-10 | Vigente, reemplaza F1 | 120 kWh | 120 | — | 24,00 | 5,00 | 2,90 | 31,90 |
| F3 | B | 2026-10 | Vigente; concepto/unidad pendiente | 70 kW | Desconocida | 70, atribución pendiente | 14,00 | 3,00 | 1,70 | 18,70 |

La columna de potencia conserva el valor por la dimensión de su unidad; no afirma que sea potencia contratada o un concepto de potencia facturada verificado. La fuente lo entrega en un campo llamado `energy`, incompatible con kW como unidad de energía. Se pide confirmar si el campo o la unidad es erróneo. No se cambia silenciosamente a kWh ni se calcula energía sin tiempo y perfil de uso.

La moneda **no consta en ninguna factura**. Los importes se conservan en su escala original, sin etiquetarlos EUR ni afirmar comparabilidad monetaria. Cada documento sí cuadra internamente:

- F1: `20 + 5 + 2,5 = 27,5`; diferencia 0.
- F2: `24 + 5 + 2,9 = 31,9`; diferencia 0.
- F3: `14 + 3 + 1,7 = 18,7`; diferencia 0.

Solo bajo la hipótesis pendiente de confirmar de **una misma moneda y base monetaria**, la suma nominal vigente es `31,90 + 18,70 = 50,60`, formada por coste etiquetado energía 38,00, otros 8,00 e impuestos 4,60. No se presenta como total consolidado en una moneda conocida. F3 conserva sus 14,00 en «coste etiquetado energía» tal como figura; la inconsistencia dimensional impide reinterpretarlo como un coste de potencia confirmado. La suma de los tres documentos, 78,10, duplicaría F1; se excluyen sus 27,50 y se obtiene la suma nominal condicional 50,60.

La rectificación documenta `100 → 120 kWh` y `27,50 → 31,90` para A; no son dos consumos ni dos costes acumulables. La diferencia aritmética es 20 kWh y 4,40 unidades monetarias nominales. Se conserva F1 como rastro de auditoría. La relación `replaces` se toma como sustitución completa por la solicitud y la entrada, no como nota de abono adicional.

Pendientes: moneda y base de importes; aclaración del 70 kW de F3; identificación de contadores; fecha inicial/final exacta; tipo de lectura medida, estimada o regularizada; contratos y desglose real de potencia, peajes y servicios. `2026-10` se conserva como periodo original, sin inventar días de lectura. No se infieren lectura real ni consumo cero de B. No hay evidencia suficiente para garantizar que no existan huecos u otros solapes fuera de los documentos aportados.

Fuentes: `input.json#/input/bills/0`, `/1`, `/2`. Habilidad versión 0.1.0, entrada y plantilla identificadas por hashes en `source_manifest.json`. `registro.csv` adapta la plantilla con estado vigente, moneda pendiente y valor/unidad originales, conservando las tres facturas. Los agregados solo usan las vigentes; `results.json` distingue subtotal kWh, consumo total desconocido y suma nominal condicionada.

Comprobaciones locales: sustitución válida dentro del mismo suministro/periodo; ningún doble cómputo; componentes e importe de cada factura conciliados; kW y kWh separados. No se han modificado documentos ni ejecutado operaciones.

Observación de la habilidad: sus guardas cubren expresamente rectificaciones y dimensiones. La plantilla no incluye estado vigente, moneda ni fuente, ni resuelve qué hacer cuando el nombre del campo contradice su unidad. Se añadieron esas referencias y la incidencia, sin inventar semántica ni una moneda. No se detectó un bloqueo de la tarea.
