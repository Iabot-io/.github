# Ocupación confirmada por noche — 3 al 5 de noviembre de 2026

Caso ficticio. Se calcula exclusivamente con las reservas aportadas: **100%, 100% y 50%**, respectivamente. La fecha/hora de corte no aparece; el resultado representa la confirmación según esta copia, sin acreditar inventario en tiempo real ni previsión de nuevas reservas.

| Noche | Capacidad vendible aportada | Reservas confirmadas | Habitaciones ocupadas confirmadas | Canceladas excluidas | Residual sobre confirmadas | Ocupación confirmada |
|---|---:|---|---:|---:|---:|---:|
| 03/11/2026 | 1 | R1 | 1 | R3: 1 | 0 | 100% |
| 04/11/2026 | 2 | R1, R2 | 2 | 0 | 0 | 100% |
| 05/11/2026 | 2 | R2 | 1 | 0 | 1 | 50% |

Se aplica `llegada ≤ noche < salida`: R1 ocupa las noches del 3 y 4, no la del 5; R2 ocupa las del 4 y 5, no la del 6. R3 está cancelada y no ocupa capacidad confirmada, aunque su intervalo fuese la noche del 3. No se transforma en reserva provisional.

La capacidad ya viene etiquetada `sellable_rooms`; se usa directamente sin descontar bloqueos inventados otra vez. No hay exceso de confirmadas frente a la capacidad aportada. El residual de una habitación el día 5 es aritmético según esta copia, no una promesa de disponibilidad comercial.

Total del intervalo: **4 habitaciones-noche confirmadas / 5 habitaciones-noche vendibles = 80% de ocupación ponderada**. No se usa la media simple de los tres porcentajes porque la capacidad diaria cambia. La unidad es habitación-noche; no se calcula ocupación por huésped o cama.

No se aportan tipos de habitación, por lo que se conserva solo el total sin inventar categorías. No hay reservas provisionales en la entrada; el cero de esa columna se limita a los datos aportados. No se suministra histórico, ritmo de nuevas reservas, hipótesis de cancelación ni fecha de corte: no se añade una previsión de demanda ni escenarios arbitrarios a un encargo limitado a confirmadas. Tampoco se garantiza la cobertura completa del PMS. La única reserva cancelada aportada es R3.

Fuentes: `input.json#/input/capacity/0..2` y `input.json#/input/reservations/0..2`; cada fila del registro identifica sus referencias. Habilidad versión 0.1.0, entrada y plantilla identificadas por hashes en `source_manifest.json`. `registro.csv` adapta la plantilla y añade reservas, exclusiones, residual y fecha de corte; `results.json` conserva las magnitudes y datos pendientes.

Comprobaciones locales: noche de salida excluida; R3 fuera del numerador; porcentajes y ponderación correctos; confirmadas no exceden capacidad. No se consultó ni modificó PMS, canales o reservas.

Observación de la habilidad: fija expresamente la exclusión de la noche de salida. Su procedimiento también pide históricos y escenarios, pero no indica cómo limitarse a confirmadas cuando ese es el encargo y faltan supuestos. Se entregó únicamente el alcance pedido, marcando los datos ausentes. La plantilla no muestra explícitamente cancelaciones o residual; se añadieron columnas. No se detectó un bloqueo de la tarea.
