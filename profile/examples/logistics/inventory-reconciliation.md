# Conciliación de inventario — prueba ficticia

Corte declarado: **2026-11-05 18:00:00 +01:00**. La fuente agrupa los recuentos bajo ese corte, pero no aporta marcas individuales del recuento o del inventario teórico. Las diferencias son provisionales hasta confirmar que ambos estados corresponden al mismo instante.

Se mantiene la referencia A y la unidad `piece`; no se convierten unidades. No se aportan lotes y no se presupone que todas las existencias sean intercambiables. Las ubicaciones permanecen separadas.

| Referencia / ubicación | Teórico | Físico | Diferencia físico − teórico | Causa | Candidato para revisión |
|---|---:|---:|---:|---|---|
| A / L1 | 5 | 8 | +3 piezas | No acreditada | +3, retenido hasta comprobación y aprobación |
| A / L2 | 2 | 2 | 0 piezas | Coincidencia aritmética | Ningún ajuste |
| Suma descriptiva de filas | 7 | 10 | +3 piezas | Sin causa global acreditada | No es una compensación entre ubicaciones |

## Movimientos y corte

El único movimiento aportado, R1, registra cantidad 3 para A/L1 el 2026-11-06 a las 09:00 +01:00: **15 horas después del corte**. Se clasifica como posterior y se conserva por separado. En la evidencia aportada hay 0 movimientos anteriores o en el corte, 1 posterior y 0 sin fecha válida; esto no acredita que el historial esté completo.

R1 no se incorpora al saldo del 5 de noviembre ni se usa como explicación de la diferencia +3 por coincidir su cantidad. No constan su tipo (recepción, expedición o traslado), unidad, lote o evidencia operativa; no se infiere su efecto por el signo de `quantity`. No se aplica +3 al teórico ni se modifica el físico para forzar igualdad.

## Revisión pendiente

Confirmar el corte efectivo de cada estado, repetir o verificar el recuento de L1, identificar lotes, comprobar movimientos hasta el corte y su completitud, y documentar la causa con el responsable. Sólo después podrá valorarse el candidato aritmético +3 de L1. L2 no compensa la diferencia de L1. No hay claves repetidas SKU/ubicación/unidad en las dos filas aportadas, pero faltan evidencias para descartar dobles lecturas u otras ubicaciones omitidas.

No se ha accedido a un ERP ni ejecutado ajustes. `registro.csv` conserva las diferencias por ubicación; `results.json` mantiene los ajustes confirmados y la causa como desconocidos.

## Trazabilidad

Fuente ficticia única: `input.json`, selección `#/input`. Revisión de la entrada: SHA-256 `d415fb763f189ba9d611cd048d9a9d46ebe47068cd68e9480b98de950281a936`. Habilidad: `https://github.com/Iabot-io/logistics-skills/blob/main/skills/warehouse-inventory-reconciliation/SKILL.md`, versión 0.1.0, SHA-256 `c8cf4f21d94eae1378d96fb30876b8b7a56d92a7335d1c9f41348fbccc591138`. Se emplea su `assets/registro.csv` conservando todas las columnas y añadiendo los campos necesarios para referencias, revisión y estados. No se consultan servicios externos ni datos de producción. El movimiento R1 está en `#/input/movements/0`.
