# Propuesta de reposición comercial — corte 01/11/2026

Caso ficticio. Política aportada: cubrir demanda observada durante el plazo, seguridad **0** y redondear al múltiplo documentado. Se usa demanda uniforme a efectos de cobertura; no se inventa demanda para referencias con rotura.

| Referencia | Físico | Reservado | Disponible | Demanda diaria | Plazo | Demanda del plazo | Recepciones admitidas | Necesidad neta | Múltiplo | Propuesta |
|---|---:|---:|---:|---:|---:|---:|---:|---:|---:|---:|
| X | 10 | 3 | 7 | 2 | 5 días | 10 | 0 | 3 | 6 | **6 unidades** |
| Y | 0 | 0 | 0 | Desconocida | 5 días | No calculable | Ninguna aportada | No calculable | 1 | Pendiente |

Horizonte de cálculo: cinco días desde el corte del 01/11 hasta el 06/11/2026. La recepción confirmada de X, **5 unidades el 08/11**, es posterior y se conserva como excluida: no aumenta disponible ni reduce necesidad de este horizonte. La convención horaria de la fecha límite necesita confirmación para recepciones en el propio límite; ninguna recepción del caso está en ese límite.

X: `disponible = 10 − 3 = 7`; `demanda_plazo = 2 × 5 = 10`; `necesidad = max(0, 10 + 0 − 7 − 0) = 3`; `propuesta = ceil(3/6) × 6 = 6 unidades`. La cantidad sugerida difiere de la necesidad por el múltiplo, no por un stock de seguridad añadido. La recepción del 08/11 no se cuenta dos veces ni se anticipa al corte.

**Excepción temporal:** X tiene `7/2 = 3,5 días` de cobertura frente a cinco de plazo: déficit equivalente a 3 unidades o 1,5 días antes de una nueva recepción al plazo normal. La propuesta de seis unidades no convierte el pedido en stock disponible hoy ni elimina esa falta previa. Revisar fecha real, alternativas de suministro autorizadas y tratamiento de demanda no atendida antes de decidir; no se ejecuta una urgencia, pedido ni backorder supuesto.

Y: las ventas observadas fueron cero **con rotura todo el periodo**. No prueban demanda cero. Al faltar demanda diaria, quedan desconocidas demanda del plazo, cobertura en días, necesidad y propuesta. La falta de existencias físicas sí es conocida. Obtener demanda no atendida, histórico comparable con stock u otra estimación aprobada; no producir una orden cero por ausencia de ventas.

Sensibilidad matemática, no nueva previsión: para X, manteniendo stock y plazo, `necesidad = max(0, 5 × demanda_diaria − 7)` y `propuesta = 6 × ceil(necesidad/6)`. La propuesta es seis si `1,4 < demanda_diaria ≤ 2,6`; por encima de 2,6 requiere el siguiente múltiplo. Esto no modifica la demanda aportada de dos unidades ni resuelve el desfase temporal. Para Y no se añade una tasa de demanda inventada.

Pendientes: cobertura de datos, daños/bloqueos no aportados, periodo comparable y promociones/estacionalidad; demanda de Y y plan operativo ante el déficit temporal de X. Fuentes: `input.json#/input/items/0`, `/1`, `/policy` y `/as_of`. Habilidad versión 0.1.0, fuente y plantilla conservadas por hashes en `source_manifest.json`. `registro.csv` adapta la plantilla con fecha, horizonte, recepción excluida y fuentes; `results.json` distingue cantidades calculadas y nulos.

Verificados horizonte, exclusión de recepción tardía, reservas, múltiplo y preservación de demanda desconocida. Pedidos creados: **0**.

Laguna observada: la habilidad pide relacionar recepciones y plazo pero no explicita el filtro por fecha ni cómo advertir que un pedido normal llega después de agotarse el disponible. El encargo sí proporciona el filtro. La plantilla no tiene fechas de recepción/horizonte ni fuente; se añadieron. La guarda de no inferir demanda cero durante roturas es explícita y funcionó en este caso.
