# Revisión de afirmaciones comerciales — caso ficticio

Fecha de revisión: 2026-11-03. Se han revisado las cuatro frases completas de `/product/draft_claims`; la matriz desglosa seis afirmaciones para no perder las promesas combinadas. No hay afirmaciones de precio o certificación en este texto. No se ha publicado contenido ni accedido a analítica, servicios externos o datos reales de clientes.

## Evidencia y vigencia

S1: `input.json`, SHA-256 `6455fdec328b5f1de94eec1a149bdf61d0e0a675d95a9225c171572d630b1d22`. Las capacidades de `/product/verified_capabilities` se aceptan como verificadas únicamente dentro del supuesto ficticio. No se suministran fecha, versión de producto, documentación complementaria, mediciones ni condiciones comerciales. La fecha de revisión no sustituye la fecha de evidencia. No se confirma con ello una capacidad actual del producto real.

## Matriz resumida

| Frase original | Evaluación | Evidencia del caso | Redacción propuesta |
| --- | --- | --- | --- |
| Our AI employees replace every professional with 100% guaranteed accuracy. | Alta: retirar sustitución universal y garantía del 100%; ninguna tiene soporte. | Las capacidades verificadas no incluyen sustitución de profesiones, mediciones ni garantías. | You can assign skills to employees and review their outputs. |
| Installing a skill automatically grants access to all your customer data. | Alta: el automatismo contradice la necesidad de conexiones autorizadas; tampoco se acredita acceso a todos los datos. | `/product/verified_capabilities/1`: tools require authorized connections. | Access through tools requires authorized connections. |
| Every plan includes an unlimited Linux computer. | Alta: la inclusión en todos los planes contradice la dependencia del plan; ilimitado no tiene soporte. | `/product/verified_capabilities/3`: Linux workstation depends on the plan. | Linux workstation availability depends on your plan. |
| You can assign reusable skills and review the resulting work. | Baja: asignación y revisión respaldadas; reusable carece de evidencia explícita. | `/product/verified_capabilities/0` y `/2`. | You can assign skills to employees and review the resulting work. |

La matriz completa `marketing-registro.csv` conserva las ocho columnas de la plantilla y añade identidad y prioridad. Sus filas C1a y C1b cubren ambas promesas del titular; C3a y C3b separan disponibilidad y ausencia de límites.

## Incidencias y resolución

1. Antes de usar la primera frase, revisión comercial y jurídica de cualquier promesa de sustitución o garantía; con la evidencia actual se retiran. No se propone un porcentaje reducido, un testimonio ni una garantía implícita.
2. Producto debe validar la explicación de las conexiones autorizadas. La corrección no afirma permisos concretos, certificaciones, seguridad absoluta ni un mecanismo de autorización no descrito en el input.
3. Comercial debe aportar la tabla vigente de planes y condiciones de uso si se desean concretar la disponibilidad o límites del ordenador Linux. Hasta entonces, la condición del plan permanece dentro de la misma frase.
4. Documentar reutilización si se desea conservar reusable. El núcleo asignar skills y revisar resultados sí está respaldado; la versión propuesta elimina únicamente el calificativo no acreditado.

## Texto consolidado propuesto

> You can assign skills to employees and review the resulting work. Access through tools requires authorized connections. Linux workstation availability depends on your plan.

Es una propuesta de sustitución basada en el supuesto, sin publicación. No conserva las promesas de sustitución universal, precisión garantizada, acceso automático a todos los datos o uso ilimitado.
