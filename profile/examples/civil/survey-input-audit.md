# Auditoría de entrada topográfica — prueba ficticia

Revisión: 2026-11-03. Se conservan las cuatro filas y sus coordenadas originales; no se corrige, elimina, renombra, interpola ni transforma ningún punto.

| Comprobación | Resultado |
|---|---|
| Referencia horizontal declarada | EPSG:25830; unidad horizontal m |
| Referencia y unidad vertical | No aportadas; no se asume que Z esté en metros |
| Identificadores | 4 filas, 3 identificadores distintos; P2 repetido en filas 2 y 3 |
| Valores numéricos | X e Y numéricos en 4 filas; Z numérico en 3 y `unknown` en P3 |
| Coordenadas X/Y idénticas | Ningún par idéntico en la muestra; el problema de P2 es de identificador |
| Extensión X/Y | X: 500000–500030; Y: 4470000–4470030; amplitud 30 × 30 m |
| Rango numérico Z conocido | 12,4–12,8 en 3 filas, con unidad y referencia vertical desconocidas |

## Incidencias y control pendiente

1. Las dos filas P2 tienen coordenadas distintas: (500010, 4470010, 12,6) y (500020, 4470020, 12,8). Se necesitan el registro original y una decisión del responsable sobre su identidad. Se referencian por posición de fila además del identificador, sin inventar cuál es el punto correcto.
2. La cota de P3 es el texto `unknown`. Se mantiene como valor original no numérico; no se sustituye por cero ni por una interpolación.
3. No consta referencia vertical ni unidad Z. No puede determinarse si las alturas son elipsoidales, ortométricas o locales ni comparar semánticamente su rango con cotas de control.
4. Faltan fecha y origen del levantamiento, memoria, control independiente y tolerancias. No puede acreditarse exactitud, coherencia con un proyecto o ausencia de puntos anómalos mediante el pequeño rango observado.

EPSG:25830 se conserva como declaración de la fuente. No se ha verificado su correspondencia real con el levantamiento ni se ha inferido por apariencia. No se ha hecho una validación SIG, comparación visual o transformación: falta el levantamiento de control y esa comprobación queda pendiente. No se entrega un conjunto depurado como validado.

El registro `registro.csv` conserva una fila por registro de origen y las incidencias. `results.json` mantiene como desconocidos los metadatos ausentes.

## Trazabilidad

Fuente ficticia única: `input.json`, selección `#/input`. Revisión de la entrada: SHA-256 `0bd5bb55d913d27fe1950f4938b3b6ed237a9a2b6963348fc1d361283b0eda0c`. Habilidad: `https://github.com/Iabot-io/civil-engineering-skills/blob/main/skills/civil-survey-input-audit/SKILL.md`, versión 0.1.0, SHA-256 `8db9170b083337d7bd3fe51577444b72f1857cb72a44b872cd9eda53eceee7ae`. Se emplea su `assets/registro.csv` conservando todas las columnas y añadiendo los campos necesarios para referencias, revisión y estados. No se consultan servicios externos ni datos de producción.
