# Conciliación bancaria provisional para revisión

Caso ficticio. Moneda: EUR. **El extracto cuadra en 1.075 EUR; el registro deja una diferencia de −5 EUR respecto al banco, explicada por B3 sin contraparte en los datos aportados.** Se mantienen pendientes esos 5 EUR; no se crea ningún asiento.

| Movimiento bancario | Concepto/referencia original | Importe EUR | Registro asociado | Importe registro EUR | Diferencia EUR | Estado |
|---|---|---:|---|---:|---:|---|
| B1 | C1 | +100,00 | C1 | +100,00 | 0,00 | Coincidencia única de referencia e importe |
| B2 | P1 | −20,00 | P1 | −20,00 | 0,00 | Coincidencia única de referencia e importe |
| B3 | bank fee | −5,00 | Sin contraparte aportada | — | −5,00 | Pendiente de revisión, sin contabilizar |

Regla aplicada: la referencia bancaria coincide exactamente con el identificador interno y el importe coincide con su signo; la coincidencia debe ser única en esta entrada y un registro no se reutiliza. B1/C1 y B2/P1 satisfacen esas condiciones. No quedan registros internos sin pareja y ningún movimiento se empareja dos veces. El cargo B3 no se fuerza contra P1 ni contra una partida ficticia. Los signos se conservan: abonos positivos y cargos negativos.

Conciliación de saldos:

- Banco: `1.000 + 100 − 20 − 5 = 1.075 EUR`, igual al cierre aportado; diferencia aritmética del extracto: 0 EUR.
- Registro: movimientos netos `100 − 20 = 80 EUR`. Si comparte la misma apertura de 1.000 EUR, su cierre teórico sería `1.080 EUR`.
- Diferencia banco menos registro teórico: `1.075 − 1.080 = −5 EUR`, igual a B3 pendiente.
- Puente explicativo, sin asiento: `1.080 + (−5 pendiente) = 1.075 EUR`.

La apertura y el cierre se interpretan como los saldos del extracto en el alcance de esta entrada. No se ha aportado una apertura contable independiente; por ello 1.080 EUR es un saldo interno **teórico condicionado a la misma apertura**, no un cierre del libro validado.

`bank fee` es la descripción bancaria original, compatible con una posible comisión. No confirma por sí sola la naturaleza contable o fiscal, la cuenta de gasto ni que falte en el registro completo. Revisar justificante del banco y cobertura del libro antes de decidir su tratamiento; no se propone un asiento inventado. B3 sigue como movimiento bancario no emparejado.

Faltan cuenta identificable, periodo, fechas contables y de valor, identidad/revisión original de extracto y libro y conciliación anterior. Se dejan en blanco o «no aportado»; no se usan fechas actuales. Las coincidencias son válidas dentro del conjunto ficticio recibido, sin acreditar igualdad de cuenta/periodo ni una conciliación completa de un libro real.

Fuentes: `input.json#/input/bank/0..2`, `input.json#/input/ledger/0..1` y saldos de `input.json#/input`. Habilidad versión 0.1.0, entrada y plantilla identificadas por hashes en `source_manifest.json`. `registro.csv` conserva las columnas originales y añade moneda, importe del registro, fuente y periodo. `results.json` identifica pares, saldo teórico y diferencia pendiente.

Comprobaciones locales: saldo bancario exacto; signos coherentes; emparejamiento único; ningún registro reutilizado; diferencia −5 EUR explicada sin eliminarla. Asientos creados: **0**. No se accedió a bancos ni contabilidad ni se realizaron operaciones.

Observación de la habilidad: sus instrucciones resuelven adecuadamente la coincidencia y la conservación de pendientes. La plantilla no separa el importe interno del bancario ni incluye fuente, moneda o periodo. Se añadieron esas columnas. La habilidad no concreta cómo presentar un saldo interno cuando solo hay una apertura común no identificada: se conserva como cálculo condicional. No se detectó un bloqueo de la tarea.
