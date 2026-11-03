# Revisión de ejecución presupuestaria — prueba ficticia

Revisión: 2026-11-03. Corte declarado: 2026-10-31. Moneda: EUR. Entidad, ejercicio presupuestario, partidas y definiciones formales de las fases: no aportados. El año de la fecha de corte no se sustituye por un ejercicio declarado.

Se analiza únicamente el bloque `budget` de la fuente. Se aplica su fecha de corte común a P1 y P2; no hay estados separados que permitan comprobar su sincronización de forma independiente. El total es la suma de estos dos programas, sin afirmar que abarque el organismo completo.

## Crédito y fases

El crédito vigente es un cálculo: crédito inicial + suma algebraica de modificaciones. Cada elemento del array de modificaciones se cuenta una sola vez; el neto no se vuelve a sumar como movimiento. No se aportan identificadores de modificación ni un crédito vigente oficial con el que conciliar o comprobar duplicados.

| Programa | Inicial (€) | Modificaciones (€) | Vigente calculado (€) | Compromisos (€) | Obligaciones (€) | Pagos (€) |
|---|---:|---:|---:|---:|---:|---:|
| P1 | 100.000 | (15.000) + (-5.000) = 10.000 | 110.000 | 70.000 | 50.000 | 40.000 |
| P2 | 20.000 | 0 (sin movimientos aportados) = 0 | 20.000 | 0 | 5.000 | 0 |
| Total del extracto | 120.000 | 10.000 | 130.000 | 70.000 | 55.000 | 40.000 |

Las etiquetas traducen los campos `committed`, `obligations` y `payments`. Se conservan como magnitudes distintas; no se presume que representen fases legales concretas, importes acumulados homogéneos o obligaciones reconocidas conforme a un marco contable no aportado.

## Ratios

Cada porcentaje se calcula como 100 × numerador / denominador. Los tres primeros usan como denominador el crédito vigente calculado del mismo programa o del total; el último usa obligaciones del mismo ámbito.

| Programa | Compromisos / vigente | Obligaciones / vigente | Pagos / vigente | Pagos / obligaciones |
|---|---:|---:|---:|---:|
| P1 | 63,64 % | 45,45 % | 36,36 % | 80,00 % |
| P2 | 0,00 % | 25,00 % | 0,00 % | 0,00 % |
| Total del extracto | 53,85 % | 42,31 % | 30,77 % | 72,73 % |

Los ratios del total se calculan con los totales de importes, sin promediar porcentajes de programas.

## Diferencias y salvedades

| Programa | Vigente − compromisos (€) | Compromisos − obligaciones (€) | Obligaciones − pagos (€) |
|---|---:|---:|---:|
| P1 | 40.000 | 20.000 | 10.000 |
| P2 | 20.000 | -5.000 | 5.000 |
| Total del extracto | 60.000 | 15.000 | 15.000 |

Estas diferencias son aritméticas; no se certifican como crédito disponible ni como deuda pendiente sin las definiciones y estados correspondientes.

- P1: las modificaciones aumentan el crédito en 10.000 €. No se aporta la causa de +15.000 € ni de −5.000 €. Si las fases son acumuladas y comparables, los importes muestran 20.000 € entre compromiso y obligación y 10.000 € entre obligación y pago.
- P2: obligaciones de 5.000 € frente a compromisos de 0 € producen una diferencia de −5.000 €. Requiere aclarar definiciones, cobertura temporal y completitud de las fases o corregir la fuente si procede. Se conserva el dato; no se rellena el compromiso ni se atribuye una irregularidad.
- El total mantiene esa diferencia de P2; agregar programas no resuelve la falta de conciliación de cada programa. No hay serie anterior ni calendario de ejecución para evaluar retrasos o variaciones temporales.

Pendiente de revisión del organismo: entidad y ejercicio; estructura y partidas; definiciones, naturaleza acumulada o de periodo y alcance de cada fase; identificación de modificaciones y crédito vigente oficial; explicación documentada de P2 y de las modificaciones de P1. No se emite fiscalización, aprobación ni resolución institucional.

## Trazabilidad

Fuente ficticia única: `input.json`, selección `#/budget` y `#/budget/programs/0..1`. Sin número de revisión aportado; se identifica exactamente por SHA-256 `81d2ea9ba1489cc978815372b505c0d304ba9bc5f6bda4bd0bd422b20c48e498`.

Habilidad aplicada: `https://github.com/Iabot-io/public-sector-skills/blob/main/skills/public-budget-execution-review/SKILL.md`, versión 0.1.0, SHA-256 `c3e8115e0e6b164351a7286c8872ed9feab37c0716bf0175e611c04f82cc9741`. Se utilizó su plantilla `assets/registro.csv`, ampliada con denominadores, corte, moneda y revisión de fuente; los campos repetidos de crédito por fase no son filas adicionales de movimientos.

Registro adjunto: `budget-execution-register.csv`. No se consultaron servicios externos ni datos reales.
