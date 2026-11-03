# Revisión ficticia de tesorería y ofertas

Ensayo independiente realizado el 03/11/2026, exclusivamente sobre `../input.json`. No se han consultado otros resultados, clientes, servicios externos ni sistemas de producción. No se han ejecutado pagos, pedidos, adjudicaciones ni comunicaciones.

Las fuentes son la entrada y las dos habilidades, versión 0.1.0, junto con sus plantillas `assets/registro.csv`. `source_manifest.json` conserva rutas, hashes SHA-256 y fecha de generación. La entrada no incluye número de revisión: su hash identifica la copia usada. Las referencias `input.json#/...` indican punteros a esa copia.

## Tesorería: 02–15 de noviembre de 2026

**El subtotal de movimientos denominados en EUR deja 1.400 EUR, pero hay además un pago confirmado de 100 USD el 06/11 sin tipo de cambio. No existe un saldo consolidado final numérico completo con estos datos.**

Se interpreta provisionalmente que A = 1.000 EUR y B = 500 EUR corresponden al inicio del 02/11. La fecha efectiva de esos saldos, su conciliación y la fecha de corte de la información están pendientes. El alcance provisional comprende solo A y B; no consta ninguna cuenta USD. Todas las fechas se muestran como fechas previstas aportadas: la entrada no distingue vencimiento contractual y expectativa de ejecución.

| Periodo | Apertura: subtotal EUR sin p2 | Cobros EUR | Pagos EUR | Transferencias internas netas | Pago USD sin convertir | Cierre: subtotal EUR sin p2 |
|---|---:|---:|---:|---:|---:|---:|
| 02–08/11 | 1.500,00 | 600,00 | 700,00 | 0,00 | 100,00 | 1.400,00 |
| 09–15/11 | 1.400,00 | 0,00 | 0,00 | 0,00 | 0,00 nuevos | 1.400,00 |

La obligación de 100 USD de la primera semana sigue afectando al saldo inicial y final de la segunda. Los importes EUR de esta tabla excluyen expresamente ese pago pendiente de valoración; no son saldos disponibles completos. Los ceros de la segunda semana significan «sin movimientos adicionales aportados», sin acreditar exhaustividad.

Detalle y clasificación:

- **Transferencia interna t1-a/t1-b, 03/11:** A pierde 200 EUR y B recibe 200 EUR. Las referencias son recíprocas y la suma consolidada es cero. Tras esa transferencia, y antes de otros movimientos, A tendría 800 EUR y B 700 EUR. El ingreso de B no es un nuevo cobro de clientes.
- **p1, alquiler, 04/11:** pago confirmado de 700 EUR. Saldo EUR aportado tras ese movimiento: 800 EUR. Aunque el concepto sea alquiler, no se inventa una recurrencia no indicada.
- **c1, cliente, 05/11:** cobro confirmado de 600 EUR. Subtotal EUR: 1.400 EUR.
- **p2, proveedor, 06/11:** pago confirmado de 100 USD; su certeza no elimina la falta de cambio. No se trata como cero ni se aplica paridad EUR/USD.
- No hay partidas estimadas identificadas en la entrada. Las hipótesis siguientes son escenarios analíticos y carecen de aprobación.

**Escenario base condicional.** Si p2 se paga desde el alcance EUR y `r` es el coste de 1 USD en EUR, antes de comisiones no aportadas:

`cierre 02–08/11 = 1.500 + 600 − 700 − 100 × r = 1.400 − 100 × r EUR`

`apertura 09–15/11 = cierre 02–08/11; cierre 09–15/11 = 1.400 − 100 × r EUR`

`r` es una variable pendiente, no un tipo estimado. Si existen comisiones de cambio, también reducen el saldo y quedan sin cuantificar. Si el pago se atiende desde otra cuenta, es necesario corregir el alcance y aportar su saldo. No se suman EUR y USD como si fueran la misma moneda.

**Sensibilidad de plazo: c1 se retrasa siete días, del 05/11 al 12/11.** Se conserva su importe de 600 EUR, el resto de fechas y el mismo `r`:

| Periodo | Apertura EUR condicional | Cobros EUR | Pagos EUR | Pago USD | Cierre EUR condicional |
|---|---:|---:|---:|---:|---:|
| 02–08/11 | 1.500 | 0 | 700 | 100 | `800 − 100 × r` |
| 09–15/11 | `800 − 100 × r` | 600 | 0 | 0 nuevos | `1.400 − 100 × r` |

El retraso reduce en 600 EUR la caja al cierre de la primera semana; recupera ese importe en la segunda. No representa una nueva expectativa aprobada del cliente. No se asignan probabilidades.

**Necesidad potencial de caja y pendientes.** Con los movimientos EUR aportados, el saldo baja a 800 EUR el 04/11 antes del cobro. La capacidad de atender p2 y el mínimo consolidado posterior no se pueden cerrar numéricamente sin cambio, comisiones, conciliación y cobertura completa de cobros/pagos. En el escenario de retraso, el pago USD llega antes de c1 y reduce `800 − 100 × r`. Deben revisarse esos datos y las cuentas de cargo/abono; no se propone ni ejecuta financiación por un importe inventado. Los presupuestos de proveedores siguientes no se incorporan como pagos previstos porque no hay compra aprobada ni fechas de pago.

## Comparativa de proveedores

Base indicada: 10 unidades, EUR sin IVA recuperable, IVA del 21% según la entrada. Se asume únicamente, para normalizar, que el precio unitario y la entrega de cada oferta están en EUR y son aplicables a las cantidades mínimas indicadas; la moneda no aparece en cada oferta y conviene confirmarla. La entrada no documenta equivalencia de producto, calidad, plazos, garantías, mantenimiento, uso ni condiciones de pago. Por tanto, se compara el coste documentado de adquisición con entrega; no se afirma disponer de un coste completo de ciclo de vida.

| Oferta | Precio unitario neto EUR | Unidades que exige la compra | Entrega neta EUR | Desembolso neto EUR | IVA de referencia EUR | Total bruto de referencia EUR | Adecuación al alcance |
|---|---:|---:|---:|---:|---:|---:|---|
| A | 100,00 | 10 | 50,00 | 1.050,00 | 220,50 | 1.270,50 | El mínimo permite 10 |
| B | 98,00 | 10 | 0,00 | 980,00 | 205,80 | 1.185,80 | El mínimo permite 10 |
| C | 95,00 | 20 | 0,00 | 1.900,00 | 399,00 | 2.299,00 | Mínimo 20: 10 unidades excedentes |

Fórmulas reproducibles:

- A: `10 × 100 + 50 = 1.050 EUR`.
- B: `118,58 / 1,21 = 98 EUR` por unidad; `10 × 98 = 980 EUR`.
- C: `max(10, 20) × 95 = 1.900 EUR`. El importe `10 × 95 = 950 EUR` no es una compra admitida por esa oferta.
- IVA y total bruto son referencias aritméticas con el tipo proporcionado; no alteran la comparación neta solicitada ni validan la recuperabilidad fiscal.

**Resultado económico condicionado.** Entre A y B, que permiten adquirir exactamente 10, B tiene el menor coste documentado: ahorra 70 EUR netos frente a A (6,67% del coste de A). La preferencia se limita al precio documentado y queda condicionada a equivalencia y requisitos pendientes. No hay adjudicación ni recomendación global de cumplimiento o riesgo.

C queda fuera del cuadro de compra de 10 exactas. Como alternativa explícita, exige 1.900 EUR netos para 20 unidades; supone 920 EUR más de desembolso que B y 10 unidades adicionales. No se asigna valor de reventa, uso futuro, ahorro, coste de almacenamiento ni riesgo a ese excedente sin evidencia. El mínimo 20 no demuestra un fallo de calidad ni impide satisfacer físicamente 10 unidades mediante una compra mayor, si esta se autorizase.

**Cumplimiento y riesgo documentado.** Cantidad mínima, impuestos y entrega son los únicos atributos comparables aportados. Para calidad, plazos, garantías, condiciones contractuales y solvencia, el estado de las tres ofertas es «sin información», no «cumple» ni «incumple». El requisito de comprar exactamente 10 se utiliza para mantener el mismo alcance de comparación, no como una prohibición aprobada de adquirir excedentes.

**Puntuaciones y sensibilidad.** No se aportan criterios de evaluación, pesos ni escala de puntuación aprobados. No se inventan puntuaciones, un total de pesos ni una sensibilidad a pesos. Sí pueden mostrarse sensibilidades económicas explícitas, sin tratar sus hipótesis como autorizadas:

- Manteniendo la entrega de A en 50 EUR y las condiciones de B, A empata con B si su precio unitario neto baja a `(980 − 50) / 10 = 93 EUR`. Por debajo de 93 EUR, A tendría menor coste documentado.
- Si la demanda hipotética fuese 20 unidades y se mantuviesen las tarifas y entregas sin descuentos adicionales, A costaría 2.050 EUR, B 1.960 EUR y C 1.900 EUR. En ese alcance hipotético C sería el menor coste documentado. La demanda real aportada sigue siendo 10.

Pendientes antes de una selección global: confirmar moneda por oferta y equivalencia técnica; completar requisitos, plazos, garantías, pagos y costes de ciclo de vida pertinentes; aprobar criterios/pesos si se desea puntuación; y decidir expresamente si se autoriza una compra excedentaria. No se han solicitado aclaraciones a proveedores ni emitido pedidos.

## Comprobación y observaciones sobre las habilidades

`calculate.py` reproduce normalización de IVA, cantidades mínimas, sumas, transferencias enlazadas y continuidad semanal. Sus aserciones terminan correctamente. No genera tipos de cambio, pesos ni adjudicaciones. Los registros adaptan las dos plantillas, añadiendo moneda y otros campos necesarios sin retirar las referencias originales. `cash_weekly.csv` distingue subtotales conocidos y fórmulas condicionales.

No se ha detectado una instrucción que impida completar este caso con incertidumbre explícita. Las dos habilidades permiten conservar datos pendientes y adaptar sus plantillas. Estas son ambigüedades concretas observadas al ejecutarlas, sin modificar las fuentes:

1. La habilidad de caja no prescribe cómo rotular un saldo parcial en varias monedas ni el sentido del tipo de cambio. Fue necesario distinguir «subtotal EUR sin p2» de saldo completo y definir `r` en EUR por USD. Su plantilla original carece de columna de moneda; se añadió para evitar sumar USD y EUR.
2. La habilidad de caja pide saldo conciliado y fechas contractuales/esperadas, pero no especifica si se debe detener todo el trabajo cuando faltan. Se entregó un cálculo provisional con apertura y fechas explícitamente pendientes, sin afirmar conciliación.
3. La habilidad de ofertas pide pesos visibles y sensibilidad, pero no detalla una salida cuando faltan pesos aprobados. Se omitieron puntuaciones y sensibilidad ponderada, manteniendo una comparación económica y escenarios identificados.
4. La habilidad de ofertas exige normalizar cantidades y alcance, pero no desarrolla los mínimos de compra. Se aplicó el mínimo real de C y se separó su alternativa de 20 unidades. Su plantilla no incluye cantidad ni base fiscal; se añadieron esos campos para hacer la diferencia revisable.

Son decisiones reversibles de presentación y cálculo, no fallos de seguridad ni errores numéricos de las habilidades observados en este caso. Los datos ausentes del caso se han mantenido como ausentes.

## Archivos de entrega

- `review.md`: revisión legible con fórmulas, evidencia y pendientes.
- `cash_registro.csv`: saldos y movimientos, adaptado de la plantilla de caja.
- `cash_weekly.csv`: previsión de dos semanas y escenario de retraso.
- `supplier_registro.csv`: matriz de costes, evidencia, exclusiones y pendientes.
- `results.json`: resultados estructurados y estado de incertidumbre.
- `source_manifest.json`: identidad de fuentes, versiones y hashes.
- `calculate.py`: reproducción local de cálculos y verificaciones; solo lee las fuentes enumeradas y escribe estos resultados en el directorio de salida.
