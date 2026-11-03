# Cobertura y revisión de reposición de repuestos

Caso ficticio. Se trabaja en **piezas** y periodos de 30 días, sin sustituir referencias ni emitir pedidos. Las existencias disponibles siguientes descuentan solo reservas conocidas; fecha de inventario, material dañado y recepciones no se aportan y necesitan validación.

| Referencia | Stock original | Stock convertido, piezas | Reservas, piezas | Utilizable según entrada | Consumo, piezas/30 días | Plazo, días | Cobertura |
|---|---|---:|---:|---:|---:|---:|---:|
| A | 2 cajas × 10 | 20 | 5 | 15 | 20 | 15 | 22,5 días |
| B | 3 piezas | 3 | 0 | 3 | Desconocido | Desconocido | No calculable |

A: `2 × 10 − 5 = 15 piezas`; consumo medio `20 / 30 = 2/3 pieza/día`; cobertura `15 / (20/30) = 22,5 días`. Bajo consumo uniforme, el plazo de 15 días necesita `15 × 20/30 = 10 piezas`: existen 5 piezas de margen, equivalentes a 7,5 días, antes de cualquier recepción. Es un cálculo con consumo medio, sin afirmar una garantía ante averías.

El objetivo de 30 días equivale a 20 piezas. **Si el objetivo se mide sobre el disponible actual**, la necesidad neta es `20 − 15 = 5 piezas`; el mínimo de compra de 10 eleva la propuesta para revisión a **10 piezas**, equivalentes dimensionalmente a una caja de las descritas. Se separan necesidad 5 y propuesta 10. No se aplica un múltiplo de caja que no figura como política de pedido.

La entrada no precisa si esos 30 días deben mantenerse **a la recepción**, después de consumir durante los 15 días de plazo. Bajo esa otra interpretación: `consumo × (plazo + objetivo) − disponible = (20/30) × 45 − 15 = 15 piezas`; el mínimo 10 permitiría proponer **15 piezas**, si se admiten piezas sueltas. Si se exigiesen cajas enteras de 10, serían 20 piezas, pero esa regla no está aprobada y no se aplica. No hay una cantidad final de compra hasta aclarar el anclaje del objetivo y la unidad efectiva de compra. Una reposición que llegue dentro de 15 días no se trata como recibida hoy.

B: tres piezas físicas utilizables según reservas conocidas. Consumo y plazo nulos en la entrada significan **datos ausentes**, no consumo cero, cobertura infinita ni falta de riesgo. No se calcula cantidad de reposición, aunque el mínimo sea una pieza y el objetivo 30 días.

Sensibilidad sin inventar previsiones: para A, con el consumo medio aportado, el plazo que agota las 15 piezas es 22,5 días; por encima existe déficit antes de recepción. Con plazo 15, el consumo umbral es `15/15 = 1 pieza/día`, equivalente a 30 piezas por periodo: la cobertura sería exactamente el plazo, sin margen. No se afirma que ese aumento o retraso vaya a ocurrir. Para B, la cobertura sería `3 / consumo_diario` si se aportase un consumo positivo.

No se asigna criticidad ni prioridad por seguridad: no hay equipos servidos, impacto, redundancia, compatibilidad ni criterios acordados. La revisión de B debe completar datos; la de A debe aclarar política y condiciones de compra. No se inventan equivalencias con otros repuestos ni alternativas aprobadas.

Fuentes: `input.json#/input/items/0`, `/1` y `input.json#/input/period_days`. Habilidad versión 0.1.0 y fuentes identificadas en `source_manifest.json`. `registro.csv` adapta la plantilla para conservar stock/unidad originales, conversión y necesidad frente a propuesta. `results.json` conserva ambos escenarios de política y los pendientes. Verificados conversión, reservas, cobertura, plazo y mínimo. Pedidos emitidos: **0**.

Laguna observada: la habilidad exige reconstruir niveles desde criterios, pero no especifica el anclaje temporal de un objetivo de cobertura ni la diferencia entre mínimo y múltiplo de compra. La plantilla mezcla consumo/plazo/unidad en campos libres. Se explicitaron las unidades y dos interpretaciones sin escoger una como autorizada. No se detectó un bloqueo para entregar la revisión.
