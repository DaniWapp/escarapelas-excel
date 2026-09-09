# Generador de Escarapelas

Herramienta 100% en el navegador para generar escarapelas (gafetes) de eventos a partir de un archivo Excel, y exportarlas todas juntas a un PDF listo para imprimir.

No requiere instalación, servidor ni conexión a internet: es un único archivo HTML que puedes abrir con doble clic en cualquier computador con Windows, Mac o Linux.

## Características

- **Sin instalación**: un solo archivo (`generador-escarapelas.html`) con todo incluido (librerías, tipografía, imágenes por defecto).
- **Carga masiva desde Excel**: sube un `.xlsx` con las columnas `nombre` y `cargo` y se genera una escarapela por cada fila.
- **Ajuste automático de texto**: si un nombre o cargo es muy largo, el tamaño de letra se reduce automáticamente para que no se desborde.
- **Exportación a PDF**: genera un PDF con varias escarapelas por hoja (tamaño carta), con líneas punteadas de corte.
- **Totalmente personalizable** sin tocar código:
  - Header, logos de patrocinadores y fondo: se reemplazan subiendo tu propia imagen desde la interfaz.
  - Textos editables: título/eslogan (esquina superior derecha), etiqueta del segundo campo (cargo, colegio, universidad, etc.) y nombre de la institución (pie de página).
- **Tus cambios se guardan solos**: las imágenes y textos personalizados quedan guardados en el navegador (`localStorage`), así que si cierras y vuelves a abrir el archivo, se mantienen.

## Uso rápido

1. Descarga `generador-escarapelas.html` (y opcionalmente `datos_ejemplo.xlsx` para probar).
2. Ábrelo con doble clic — se abre en tu navegador por defecto.
3. Ajusta los textos y, si quieres, sube tus propias imágenes de header, patrocinadores y fondo.
4. Carga tu archivo Excel con las columnas `nombre` y `cargo`.
5. Revisa la vista previa de todas las escarapelas generadas.
6. Haz clic en **Generar PDF** y listo para imprimir.

## Formato del Excel

El archivo debe tener al menos estas dos columnas (el nombre de la columna no distingue mayúsculas ni tildes):

| nombre | cargo |
|---|---|
| Ana Sofía Rojas | Directora General |
| Juan David Peralta | Coordinador de Proyectos |

En este repositorio se incluye `datos_ejemplo.xlsx` con 10 filas de ejemplo para hacer pruebas rápidas.

> Nota: por compatibilidad, una columna llamada `colegio` también funciona igual que `cargo`.

## Personalización

Desde la propia página, sin editar código:

- **Imagen del header**: logo + nombre del evento.
- **Imagen de patrocinadores (footer)**: fila de logos institucionales.
- **Imagen de fondo**: fondo completo de la escarapela.
- **Eslogan**, **etiqueta del segundo campo** y **nombre de la institución**: campos de texto editables.

Usa el botón **Restaurar imágenes originales** para volver a las imágenes que trae el proyecto por defecto.

## Notas técnicas

- Construido sobre [SheetJS](https://sheetjs.com/) (lectura de Excel), [jsPDF](https://github.com/parallax/jsPDF) y [html2canvas](https://html2canvas.hertzen.com/) (generación de PDF), y la tipografía [Montserrat](https://fonts.google.com/specimen/Montserrat) — todo embebido dentro del propio HTML.
- Las imágenes y textos personalizados se guardan con `localStorage`, que es local a cada navegador/computador — no se sincroniza entre dispositivos ni viaja con el archivo.
- Tamaño de escarapela: 10 x 12.5 cm (1181 x 1471 px a 300dpi).
