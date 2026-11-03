# Revisión estructural y temporal del SRT ficticio

**Dos incidencias:** el bloque 2 se solapa **0,200 s** con el 1 y termina **1 s después de la duración declarada de 2 s**. No se aportó archivo de vídeo ni audio. No se ha escuchado audio, verificado la duración física ni certificado sincronía, contenido o accesibilidad.

Se conserva exactamente el SRT recibido en `original.srt`, guardado como UTF-8. Tiene dos bloques con numeración consecutiva, tiempos válidos, duraciones positivas y texto no vacío. El orden de inicio es creciente. No hay saltos positivos entre estos dos bloques: hay un solape. La correspondencia con la versión final del vídeo y el idioma requerido siguen sin comprobar.

| Bloque | Inicio | Fin | Duración | Texto | Incidencia |
|---|---|---|---:|---|---|
| 1 | 00:00:00,000 | 00:00:01,200 | 1,2 s | Hola | Comparte 0,2 s con el bloque siguiente |
| 2 | 00:00:01,000 | 00:00:03,000 | 2 s | Final | Solape 1,000–1,200; termina a 3,000 frente a 2,000 declarados |

Se ejecutó el ayudante de la skill desde su carpeta, con rutas absolutas de entrada/salida y **sin `--duration`**: no hay vídeo con el que comprobar la duración, condición que exige la habilidad para esa opción. `helper_original.json` registra `OVERLAP` y salida 2, esperada porque se detectó la incidencia. No registra `AFTER_MEDIA_END` al no haberse pasado una duración comprobada.

La comparación adicional contra el valor **declarado en input.json**, sin presentarlo como medido, produce `3 − 2 = 1 segundo` de exceso para el bloque 2. El solape se obtiene de `1,2 − 1,0 = 0,2 segundos`. No se necesita escuchar el audio para esas relaciones numéricas. El solape puede ser intencional: se conserva como revisión, no como una prueba automática de mala sincronía.

Se entrega `proposal_structural_unverified.srt`, **candidato estructural pendiente de revisión**, para hacer concreta una posible corrección: conserva el bloque 1 y propone el bloque 2 de `00:00:01,200` a `00:00:02,000`. Solo bajo las hipótesis de solape no deseado y duración declarada correcta, elimina ambos conflictos sin cambiar una palabra. No se ha aprobado ni sustituido el original. La ubicación de la voz, el corte y la pertinencia de recortar un segundo solo se pueden revisar con el medio real.

El ayudante sobre ese candidato devuelve estructura correcta (`helper_proposal.json`, salida 0), sin certificar audio o duración final. El bloque 2 quedaría en 0,8 s, con cinco caracteres y 6,25 caracteres/s. Los originales tienen aproximadamente 3,33 y 2,5 caracteres/s. No hay umbrales de legibilidad acordados: son métricas descriptivas y no un aprobado de lectura. Se mantiene el texto sin completarlo ni afirmar que sea fiel al audio.

Fuentes: `input.json#/input/srt`, `/video_duration_seconds` y `/audio_provided`. Skill versión 0.1.0, helper, plantilla y entrada identificados por hashes en `source_manifest.json`. `registro.csv` conserva originales, incidencias, candidato y verificación; `results.json` distingue duración declarada, ausencia de verificación y resultados del ayudante.

Verificados formato, secuencia, duraciones, solape y exceso contra el dato declarado; candidato comprobado solo a nivel estructural. No se han usado servicios externos, herramientas de transcripción, vídeo ni audio inexistentes.

Laguna observada: la habilidad exige duración comprobada para `--duration`, pero no describe cómo tratar una duración declarada sin medio. Se hizo la comparación condicional por separado. También pide copia corregida sin precisar cómo rotular una propuesta cuando falta audio: se entrega claramente como candidato no verificado. El helper no valida legibilidad ni sincronía y lo declara correctamente. La plantilla necesitó fuentes y separación de tiempos originales/propuestos.
