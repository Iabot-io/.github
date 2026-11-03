# Revisión administrativa de capacidad de citas — prueba ficticia

Revisión: 2026-11-03. Agenda: 2026-11-04, zona horaria Europe/Madrid. Se analizan únicamente R1 y R2 y las cuatro citas aportadas, con identificadores mínimos. No se utilizan datos clínicos ni se aplican prioridades de urgencia.

## Reglas y límites

La fuente exige una sala por visita (`one_room_per_visit: true`), ausencia de solapes (`no_overlap: true`) y no autoriza reprogramar (`no_rescheduling_authorized: true`). Cada visita declara una sola sala. No se ha modificado, cancelado, trasladado ni confirmado ninguna cita.

No constan estados de las citas, horarios de apertura y de cada recurso, preparación o limpieza, recursos personales o equipamiento, equivalencia entre salas ni preferencias. Se revisan los intervalos tal como se aportan; la presencia en la lista no acredita confirmación. El criterio mínimo de solape es compartir una sala durante tiempo positivo; dos intervalos que sólo comparten el instante final/inicial no se marcan como solape directo, pero su compatibilidad depende de la preparación que establezca el centro.

## Citas y conflicto

| Cita | Sala | Inicio | Fin | Duración derivada | Estado aportado | Resultado |
|---|---|---|---|---:|---|---|
| V1 | R1 | 09:00 | 09:30 | 30 min | No informado | Se solapa con V2 entre 09:20 y 09:30 |
| V2 | R1 | 09:20 | 09:50 | 30 min | No informado | Se solapa con V1 durante 10 min |
| V3 | R2 | 09:20 | 09:40 | 20 min | No informado | Sin solape de sala en los datos aportados |
| V4 | R1 | 09:50 | 10:10 | 20 min | No informado | Comienza al terminar V2; preparación pendiente |

Hay un conflicto de sala: V1–V2, R1, 09:20–09:30, 10 minutos. Es incompatible con `no_overlap` si ambos intervalos permanecen activos. Se necesita confirmar sus estados para conocer la incidencia operativa. La simultaneidad de V3 en R2 con citas de R1 no constituye un conflicto de sala; faltan datos para valorar si comparten profesional u otro recurso.

## Capacidad observable

Se usa 09:00–10:10 como ventana descriptiva derivada de la primera y última cita, de 70 minutos. No representa el horario de apertura.

| Sala | Suma de duración de citas | Unión de intervalos ocupados | Ventanas sin citas listadas dentro de 09:00–10:10 |
|---|---:|---:|---|
| R1 | 80 min | 70 min | Ninguna; 10 min de doble ocupación |
| R2 | 20 min | 20 min | 09:00–09:20 (20 min); 09:40–10:10 (30 min) |

Los 50 minutos sin citas listadas en R2 son ventanas aritméticas pendientes de validación. No son disponibilidad confirmada: faltan horarios, estados, tiempos de preparación, recursos y reglas de compatibilidad. La ventana de 20 minutos sólo tendría capacidad bruta para una duración de hasta 20 minutos y la de 30 para hasta 30, antes de preparación y demás restricciones. No puede calcularse una capacidad diaria ni una tasa de utilización real de sala con los datos aportados. No se asumen huecos antes de 09:00 o después de 10:10, ni liberación por cancelaciones pendientes.

## Opciones administrativas pendientes de validación

1. Remitir el par V1–V2 al responsable de la agenda para comprobar estado, identidad del recurso y eventual error en el registro. Ninguna de las dos citas se elimina ni se toma como cancelada para resolver el conflicto.
2. Confirmar con el centro los horarios, preparación, duración aprobada, recursos personales, equipamiento y preferencias antes de habilitar cualquiera de las dos ventanas de R2. También debe comprobarse la transición V2–V4 a las 09:50.
3. Solicitar una decisión autorizada del centro sobre el conflicto. La regla actual impide ejecutar una reprogramación. No se presenta un traslado o cambio de hora como alternativa validada: faltan autorización, compatibilidad entre salas y preferencias. Si el centro cambia expresamente la autorización y aporta esas restricciones, se podrán evaluar nuevas asignaciones completas de sala y hora con las mismas reglas.

No hay una propuesta de cambio de cita ejecutable o aprobada con esta fuente. Las opciones anteriores son comprobaciones y escalado administrativo; no priorizan pacientes ni deciden dotación asistencial.

## Trazabilidad

Fuente ficticia única: `input.json`, selección `#/appointments`, con citas en `#/appointments/visits/0..3`. Sin número de revisión aportado; SHA-256 `81d2ea9ba1489cc978815372b505c0d304ba9bc5f6bda4bd0bd422b20c48e498`.

Habilidad aplicada: `https://github.com/Iabot-io/healthcare-operations-skills/blob/main/skills/healthcare-appointment-capacity/SKILL.md`, versión 0.1.0, SHA-256 `2add78e6730851232ad2cbdba7d9548b8f696bd3b03421781312f552e3d3ac94`. Se utilizó su plantilla `assets/registro.csv`, ampliada con identificador, duración y referencias de fuente para no perder trazabilidad.

Registro adjunto: `appointment-capacity-register.csv`. No se consultaron servicios externos, sistemas de producción ni datos de pacientes.
