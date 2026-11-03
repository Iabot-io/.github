# Herramientas Linux para empleados de IAbot.io

Una skill contiene un procedimiento. El programa que necesita, los archivos y
el permiso para usarlos se preparan aparte en el ordenador de la organización.
Comprueba el inventario antes de instalar: una imagen de ordenador puede incluir
herramientas que otra no tiene.

| Trabajo | Herramientas posibles | Comprobación antes de darlo por listo |
| --- | --- | --- |
| Documentos, hojas y presentaciones | [LibreOffice](https://www.libreoffice.org/) | Abrir y guardar una muestra, comprobar fuentes, fórmulas y exportación. |
| Modelado y render 3D | [Blender](https://www.blender.org/) | Abrir el modelo y revisar recursos; comprobar GPU por separado si el encargo la exige. |
| CAD paramétrico | [FreeCAD](https://www.freecad.org/) | Abrir y exportar el formato solicitado y medir una cota conocida. |
| Mapas y datos espaciales | [QGIS](https://qgis.org/) y [GDAL](https://gdal.org/) | Confirmar sistema de referencia, unidades y transformación. |
| Vídeo, audio y metadatos | [FFmpeg y ffprobe](https://ffmpeg.org/) | Verificar códecs disponibles, pistas y reproducción del archivo exportado. |
| Composición de vídeo por HTML | [HyperFrames](https://hyperframes.app/) | Comprobar versión de Node, recursos, previsualización y render de muestra. |
| Texto de imágenes | [Tesseract](https://tesseract-ocr.github.io/) | Confirmar idiomas y revisar una página con cifras y nombres. |
| PDF buscable | [OCRmyPDF](https://ocrmypdf.readthedocs.io/) | Conservar el original y comprobar número de páginas, texto y firmas pertinentes. |
| Conversión de documentos | [Pandoc](https://pandoc.org/) | Confirmar formatos y motor PDF si se necesita; revisar el resultado visual. |
| Análisis y automatización | [Python](https://www.python.org/) | Aislar dependencias y probar una entrada representativa sin tocar datos reales. |

## Preparación de una herramienta

1. Identifica el ordenador de destino: no confundas el servidor central con el
   ordenador virtual de una empresa.
2. Comprueba distribución, arquitectura, versión, espacio y permisos.
3. Consulta el método oficial de instalación y conserva la versión adecuada al
   proyecto. Instala solo lo que necesita el encargo.
4. Mantén las dependencias aisladas cuando corresponda; conserva la configuración
   y las aplicaciones que ya utilizan los empleados.
5. Prueba el formato de entrada y salida necesario y registra el resultado.

Consultar `--version` demuestra que se puede invocar un programa, no que funcione
todo el recorrido. Un vídeo terminado tampoco demuestra que se haya usado una
GPU: ese dato requiere evidencia específica del render.

Las herramientas mantienen sus propias licencias y marcas. La lista no indica
que estén todas preinstaladas, que IAbot.io sea su autor ni que su mantenimiento
corresponda a sus proyectos originales dentro de cada ordenador de cliente.

## Habilidades relacionadas

- [Inventario Linux](https://github.com/Iabot-io/data-software-skills/tree/main/skills/linux-tool-readiness).
- [Preparación de software](https://github.com/Iabot-io/data-software-skills/tree/main/skills/linux-software-setup).
- [Buscar skills compatibles](https://github.com/Iabot-io/data-software-skills/tree/main/skills/iabot-skill-discovery).
