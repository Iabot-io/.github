# Rúbrica editable — explicación de un procedimiento de reciclaje

Borrador para revisión docente, 2026-11-03. Tarea: «explicar un procedimiento de reciclaje a partir del texto aportado». El texto al que se refiere la tarea no está incluido; tampoco hay trabajo anonimizado ni escala acordada. Los descriptores son genéricos, referidos al futuro texto, y no se inventan etapas, materiales o reglas concretas de reciclaje.

## Contradicción de ponderaciones

| Criterio | Peso propuesto | Peso aprobado/aplicado |
|---|---:|---|
| Identificar etapas | 50 | Pendiente |
| Justificar el orden | 30 | Pendiente |
| Explicar un ejemplo | 30 | Pendiente |
| Suma | **110** | Sin total aplicado |

La política exige total **100**. El exceso es **10 unidades de ponderación**. Se conservan 50/30/30 como propuestas y no se normalizan, corrigen o convierten silenciosamente. Ningún peso queda aprobado. El docente debe decidir la distribución antes de calcular una nota. `weights.csv` contiene una fila por criterio para conciliar la suma; los pesos no se suman por nivel de descriptor.

## Criterios y niveles propuestos

Los tres criterios observan resultados diferentes: cobertura de etapas, explicación de precedencias y aplicación mediante un ejemplo. No se añade ortografía, presentación o conocimiento ajeno al texto como criterio. L1/L2/L3 expresan niveles ordinales propuestos, sin equivalencia numérica aprobada. `NE` indica evidencia insuficiente para valorar y no es una nota ni equivale automáticamente a L1.

### identificar etapas

| Nivel propuesto | Evidencia observable |
|---|---|
| L1 | No identifica etapas del procedimiento del texto o menciona solo acciones que no pueden vincularse con el. |
| L2 | Identifica al menos una etapa pertinente, pero omite o confunde otras que el texto permite distinguir. |
| L3 | Identifica las etapas pertinentes del texto y las distingue de ejemplos o comentarios; no se puntua aqui la justificacion del orden. |

### justificar el orden

| Nivel propuesto | Evidencia observable |
|---|---|
| L1 | Presenta un orden sin explicar relaciones de precedencia o da una razon que contradice el texto. |
| L2 | Explica alguna relacion de precedencia con apoyo del texto, pero deja otras relaciones de su explicacion sin razon explicita. |
| L3 | Explica por que las relaciones de precedencia de su procedimiento son necesarias y las apoya en el texto, sin contradicciones; la cobertura de etapas se registra solo en el primer criterio. |

### explicar un ejemplo

| Nivel propuesto | Evidencia observable |
|---|---|
| L1 | No aporta un ejemplo o no muestra como se relaciona con el procedimiento del texto. |
| L2 | Aporta un ejemplo vinculado con el procedimiento, pero deja implicita la relacion entre alguna accion del ejemplo y el paso al que corresponde. |
| L3 | Explica un ejemplo y relaciona explicitamente sus acciones con los pasos pertinentes del procedimiento, sin contradecir el texto. |

## Aplicación y ensayo pendiente

Obtener el texto fuente y concretar con él las etapas y relaciones esperadas antes de aplicar la rúbrica. Aclarar, con una muestra, la frontera entre explicación parcial y completa; si el texto tiene una sola etapa o relación, los niveles deberán revisarse para que sean distinguibles. Registrar evidencia del trabajo en cada criterio, sin deducir una razón a partir de una lista de etapas.

Para evitar duplicar una penalización, una omisión de etapas se documenta en el primer criterio; el segundo valora las razones expresadas, y el tercero la relación explícita del ejemplo con el procedimiento. Las decisiones sobre casos mixtos deben acordarse en el ensayo docente, no improvisarse al calificar.

El ensayo solicitado por la habilidad queda pendiente: no hay texto ni ejemplo anonimizado que permitan probar fidelidad o consistencia entre niveles. No se declara realizada una calibración ni se inventa una respuesta de estudiante. No hay calificación final, promedio ni conversión de niveles a nota. La calificación final y las ponderaciones corresponden al docente.

`registro.csv` conserva nueve descriptores con ponderación aplicada vacía. `results.json` registra total 110, política 100, diferencia +10, pesos aprobados desconocidos y ensayo pendiente.

## Trazabilidad

Fuente ficticia única: `input.json`, selección `#/input`. Revisión de la entrada: SHA-256 `e450c489571da6d1cbee196aabcb83d55b2df2fd0e7ababcd3e352e60494bfcc`. Habilidad: `https://github.com/Iabot-io/education-skills/blob/main/skills/assessment-rubric-design/SKILL.md`, versión 0.1.0, SHA-256 `3c065a1019c827bc64023f23380e9efd49b764e1576b1dbb229259d32e929557`. Se emplea su `assets/registro.csv` conservando todas las columnas y añadiendo los campos necesarios para referencias, revisión y estados. No se consultan servicios externos ni datos de producción.
