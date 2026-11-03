# Matriz descriptiva de ofertas inmobiliarias — prueba ficticia

Fecha general aportada: 2026-11-01; no acredita la fecha de actualización de cada anuncio. No se aporta inmueble objetivo ni criterios de selección. Se retienen las tres ofertas y no se presenta la muestra como conjunto de comparables validado.

| Inmueble / fuente | Precio de oferta | Superficie numérica | Tipo de superficie | Precio / superficie numérica |
|---|---:|---:|---|---:|
| A / listing-A | 100.000 EUR | 100 | Útil (`useful`) | 1.000 |
| B / listing-B | 120.000 EUR | 120 | Construida (`built`) | 1.000 |
| C / listing-C | 96.000 EUR | 80 | Útil (`useful`) | 1.200 |

La unidad de superficie no aparece en la entrada. Los cocientes son **EUR por unidad de superficie no especificada**, calculados a partir de los números aportados. No se etiquetan como €/m² ni se ofrece una conversión. Se necesita confirmar la misma unidad antes de interpretar un indicador unitario entre inmuebles.

## Qué puede compararse

Los tres precios comparten moneda EUR y naturaleza de oferta anunciada. Su rango observado es **96.000–120.000 EUR**; no representa cierres, valor de mercado, precio probable de venta ni tasación. La superficie, localización, estado y características distintas impiden usar el precio total por sí solo para ordenar valor relativo.

A y C comparten la etiqueta de superficie útil. Si se confirma una misma unidad y base de medición, sus cocientes numéricos 1.000 y 1.200 se podrán comparar sobre esa dimensión; su rango descriptivo sería 1.000–1.200 en la unidad confirmada. B emplea superficie construida y queda separado para ese indicador. La coincidencia numérica de A y B en 1.000 no los hace equivalentes. No se calcula una media o rango combinado de cocientes útiles y construidos.

No hay datos adicionales de comparabilidad: faltan ubicación, tipología, estado, antigüedad u otras características y condiciones de las ofertas. No se aplican coeficientes de ajuste, conversión útil/construida ni correcciones de precio sin evidencia. Tampoco se declara mejor oferta o selección por conveniencia.

## Pendientes y alcance

Confirmar inmueble objetivo y criterios, unidades y bases de superficie, datos de los inmuebles y fecha/revisión de cada anuncio. Las fuentes listing-A/B/C son identificadores aportados, sin documentos o enlaces verificables en esta prueba. Se entrega una comparación comercial descriptiva, sin tasación, comprobación registral ni recomendación de compra.

`registro.csv` conserva las tres fuentes y separa tipo de superficie, moneda y unidad desconocida. En `results.json`, los valores €/m², el indicador combinado y el valor de tasación son `null`.

## Trazabilidad

Fuente ficticia única: `input.json`, selección `#/input`. Revisión de la entrada: SHA-256 `e90a9cdb6bb2aa4cea8a825c58eff3637f19a4cff9751f1d554d18865d3b633f`. Habilidad: `https://github.com/Iabot-io/real-estate-skills/blob/main/skills/property-comparables-matrix/SKILL.md`, versión 0.1.0, SHA-256 `ed826df2d8ba14d96bc19e5a5dae46788639240be619faa00462b0fc1c41284d`. Se emplea su `assets/registro.csv` conservando todas las columnas y añadiendo los campos necesarios para referencias, revisión y estados. No se consultan servicios externos ni datos de producción.
