# Resultado de preparación Linux — caso ficticio

Fecha de revisión: 2026-11-03. Resultado: **plan preparado; instalación y prueba funcional pendientes**.

El destino es el ordenador virtual de una organización cliente descrito en `input.json`, no el equipo que ejecuta esta revisión. No hay acceso al destino y no existe autorización de instalación en producción. No se ha inspeccionado la máquina, instalado software, accedido a servicios externos ni tratado datos de clientes. Tampoco se ha comprobado una integración de IAbot.

## Hechos y límites de la evidencia

Fuente S1: `input.json`, revisión SHA-256 `6455fdec328b5f1de94eec1a149bdf61d0e0a675d95a9225c171572d630b1d22`.

- `/environment/requested_machine`: ordenador virtual de una organización cliente. Su identidad concreta no se facilita.
- `/environment/access_to_requested_machine`: `false`.
- `/environment/production_installation_authorized`: `false`.
- `/environment/known_inventory/python3`: versión declarada `3.12`, sin comprobación en el destino.
- `/environment/known_inventory/ocrmypdf` y `/environment/known_inventory/tesseract`: `null`. No queda definido si significa ausencia comprobada o inventario desconocido; no se afirma que estén desinstalados.
- No constan distribución, versión del sistema, arquitectura, espacio libre, permisos efectivos, versiones completas de paquetes, modelos de idioma ni alternativas ya instaladas.
- No se facilita una muestra ni una versión fechada de documentación oficial. No se han consultado servicios externos por la restricción de esta prueba.

## Plan concreto, condicionado a acceso y autorización posteriores

1. Identificar el ordenador virtual concreto y el empleado técnico autorizado. Recoger allí distribución y versión, arquitectura, permisos y espacio libre antes de elegir paquetes. Inspeccionar solo el inventario pertinente: Python, OCRmyPDF, Tesseract, idiomas y herramientas ya disponibles. Una consulta local de versión o ayuda únicamente será una prueba de inventario, no una prueba de OCR.
2. Comprobar primero si la herramienta existente o una alternativa compatible satisface el caso. Si ya existe una solución funcional, reutilizarla sin modificar paquetes ajenos.
3. Consultar documentación oficial de OCRmyPDF, Tesseract y la distribución identificada. Registrar URL, fecha de consulta, revisión y versiones candidatas. La documentación oficial de OCRmyPDF enlazada por la habilidad es `https://ocrmypdf.readthedocs.io/en/latest/`; es una referencia pendiente de consulta, no una fuente revisada en este ejercicio. No asumir compatibilidad con Python 3.12 ni instalar la versión más reciente por defecto.
4. Si faltan componentes, proponer primero paquetes del repositorio oficial de esa distribución para OCRmyPDF, Tesseract y datos del idioma español. Confirmar los nombres exactos, versiones y dependencias mediante documentación y simulación del gestor, sin ejecutar todavía la instalación. Si la propuesta requiere cambios globales fuera del alcance, detener esa opción y preparar una alternativa aislada compatible; un entorno Python aislado por sí solo no acredita las dependencias del sistema ni el modelo de español.
5. Presentar el cambio exacto para autorización: destino, paquetes y versiones, dependencias nuevas, espacio estimado, ficheros afectados y reversión. La falta de autorización no se elude usando un directorio de usuario. Tras autorización explícita y acceso al destino, instalar únicamente el alcance aprobado. No actualizar el sistema completo ni ejecutar scripts remotos.
6. Registrar las versiones reales, origen de paquetes, lista de cambios y configuración del idioma. Mantener intactos los PDFs originales y los entornos existentes.

## Prueba mínima prevista — no ejecutada

Preparar, sin datos de clientes, un PDF de una página que contenga una imagen de texto español legible con acentos y ñ, sin capa de texto previa. El texto esperado, por ejemplo `Mañana habrá reunión. Número de pedido: 12345.`, debe constar junto a la muestra. Guardar la entrada y salida con nombres distintos.

Después de confirmar la sintaxis en la versión instalada y la disponibilidad del idioma `spa`, el comando propuesto para OCRmyPDF es:

```sh
ocrmypdf -l spa ./muestra-es.pdf ./muestra-es-ocr.pdf
```

No se ha ejecutado este comando. Debe correr en una carpeta de prueba autorizada del ordenador destino y no sobrescribir una salida existente.

La prueba pasa cuando el proceso termina correctamente, la salida abre y conserva la imagen legible, existe una capa de texto seleccionable o extraíble y se recuperan las palabras, acentos, ñ y número esperados. Usar el visor o extractor ya existente; si no hay extractor, su instalación requiere incluirlo expresamente en el cambio. Registrar comando, código de salida, versiones, muestra y resultado. Un error de idioma ausente o PDF inválido debe producir un fallo registrado, conservar la entrada y corregirse dentro del alcance autorizado antes de reintentar.

El resultado solo acreditaría esa muestra. No acredita precisión garantizada, OCR de todos los PDFs ni conexión funcional con herramientas de IAbot. Si se requiere integración, habrá que definir y probar después la conexión autorizada y la entrega del resultado al usuario.

## Reversión y registro

Cambios reales: ninguno; reversión actual: no necesaria. Para una ejecución futura, conservar antes el inventario y configuración. Retirar solo ficheros de prueba y componentes añadidos por esta intervención que no hayan pasado a ser dependencias compartidas; revisar el gestor antes de retirar paquetes y restaurar solo la configuración cambiada. No usar una limpieza global ni desinstalar componentes preexistentes.

La tabla `linux-registro.csv` conserva las columnas de `assets/registro.csv`. Las versiones y resultados no comprobados se marcan pendientes.
