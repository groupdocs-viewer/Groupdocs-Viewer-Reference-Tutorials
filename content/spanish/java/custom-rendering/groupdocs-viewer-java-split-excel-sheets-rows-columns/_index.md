---
date: '2026-06-15'
description: Aprenda cómo convertir Excel a PDF Java y dividir hojas de Excel por
  filas y columnas usando GroupDocs Viewer. Incluye configuración, código y buenas
  prácticas.
keywords:
- convert excel to pdf java
- split excel sheet rows
- split excel sheet columns
schemas:
- author: GroupDocs
  dateModified: '2026-06-15'
  description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  headline: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  type: TechArticle
- description: Learn how to convert Excel to PDF Java and split Excel sheets by rows
    and columns using GroupDocs Viewer. Includes setup, code, and best practices.
  name: Convert Excel to PDF Java & Split Sheets by Rows & Columns
  steps:
  - name: Set Up Paths and Initialize the Viewer
    text: First, define where the split pages will be saved and create a `Viewer`
      instance for the source workbook.
  - name: Configure Rows Per Page
    text: Tell the viewer how many rows each page should contain.
  - name: Render the Document
    text: Finally, render the workbook using the options you defined.
  - name: Set Up Paths and Initialize the Viewer
    text: The setup mirrors the row‑only example, only the file name changes.
  - name: Configure Rows and Columns Per Page
    text: Specify both dimensions to create a grid‑style split.
  - name: Render the Document
    text: Render using the same `view` call.
  type: HowTo
- questions:
  - answer: Yes. Replace `HtmlViewOptions` with `PdfViewOptions` and keep the same
      `SpreadsheetOptions` configuration.
    question: Can I generate a PDF instead of HTML?
  - answer: Direct content‑based splitting isn’t built into GroupDocs Viewer, but
      you can preprocess the workbook with Apache POI to create separate sheets before
      rendering.
    question: Is it possible to split based on cell content rather than fixed rows/columns?
  - answer: Absolutely. The viewer handles XLS, XLSX, CSV, and other spreadsheet formats.
    question: Does GroupDocs Viewer support older Excel formats (XLS)?
  - answer: Serve the output folder as a static resource and reference the generated
      `page_0.html`, `page_1.html`, etc., from your Thymeleaf or JSP templates.
    question: How do I embed the generated HTML into a Spring MVC view?
  - answer: A full production license from GroupDocs is required; trial licenses are
      for evaluation only.
    question: What license do I need for commercial deployment?
  type: FAQPage
title: Convertir Excel a PDF Java y dividir hojas por filas y columnas
type: docs
url: /es/java/custom-rendering/groupdocs-viewer-java-split-excel-sheets-rows-columns/
weight: 1
---

# Convertir Excel a PDF Java y dividir hojas por filas y columnas (Java)

Los libros de trabajo de Excel grandes a menudo contienen más datos de los que se pueden mostrar cómodamente en una sola pantalla o página impresa. **convert excel to pdf java** es un requisito común cuando necesitas un formato estático y compartible, mientras que **splitting Excel sheets by rows and columns** facilita el consumo de los datos en diseños web o impresos. En esta guía recorreremos ambas tareas usando **GroupDocs Viewer for Java**, te mostraremos cómo configurar la paginación y explicaremos consejos de mejores prácticas para el rendimiento y la solución de problemas.

![Dividir hojas de Excel por filas y columnas con GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

[Dividir hojas de Excel por filas y columnas con GroupDocs.Viewer for Java](/viewer/custom-rendering/split-excel-sheets-by-rows-and-columns.png)

## Respuestas rápidas
- **¿Qué biblioteca se usa?** GroupDocs Viewer for Java.  
- **¿Puedo dividir tanto por filas como por columnas?** Sí – puedes definir rows‑per‑page y columns‑per‑page juntos.  
- **¿Necesito una licencia?** Una licencia de prueba o temporal funciona para desarrollo; se requiere una licencia completa para producción.  
- **¿Qué formatos de salida son compatibles?** Se muestra HTML (recursos incrustados); PDF puede generarse con las mismas opciones.  
- **¿Se requiere Maven?** Maven es la forma recomendada de gestionar dependencias.  
- **¿Puedo también convertir Excel a PDF?** Absolutamente – solo cambia `HtmlViewOptions` a `PdfViewOptions` y reutiliza la misma configuración de paginación.

## Qué es “How to Split Excel”?
Dividir una hoja de Excel significa separar una sola hoja de cálculo en múltiples páginas o archivos basados en un número fijo de filas, columnas o ambos. Esta técnica es útil cuando necesitas crear informes paginados, incrustar datos en páginas web o generar secciones imprimibles sin cargar todo el libro de trabajo de una vez.

## ¿Por qué usar GroupDocs Viewer for Java?
GroupDocs Viewer procesa hojas de cálculo en una sola pasada y las pagina automáticamente, eliminando cálculos manuales. **Fast rendering processes a 250‑page XLSX workbook in under 2 seconds on a typical 2‑core server**, y **the library supports 50+ input and output formats**, incluyendo XLS, XLSX, CSV, PDF y HTML. Se ejecuta en cualquier plataforma compatible con JVM—Windows, Linux, macOS, contenedores Docker o entornos sin servidor basados en la nube—para que puedas integrarlo donde sea que viva tu aplicación Java.

## Requisitos previos
- Java 17 o posterior instalado.  
- Un IDE como IntelliJ IDEA o Eclipse.  
- Maven para la gestión de dependencias.  
- Conocimientos básicos de Java y familiaridad con el manejo de archivos Excel.

### Bibliotecas requeridas, versiones y dependencias
Add the GroupDocs repository and the viewer dependency to your `pom.xml`:

```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Obtención de licencia
Obtén una prueba gratuita, una licencia temporal o compra una licencia completa en [GroupDocs](https://purchase.groupdocs.com/buy).

## Cómo convertir Excel a PDF Java?
La clase `Viewer` es el componente central de GroupDocs Viewer que carga un documento y proporciona métodos de renderizado para varios formatos de salida. `SpreadsheetOptions` te permite controlar la configuración de paginación, como rows‑per‑page y columns‑per‑page para el renderizado de hojas de cálculo.

Carga tu archivo Excel con `new Viewer("source.xlsx")`, configura `SpreadsheetOptions` para la paginación y llama a `viewer.view(pdfOptions, stream)` – esa única llamada convierte el libro de trabajo a PDF respetando los límites de filas/columnas que estableciste. La conversión conserva fórmulas, imágenes y estilos de celda, entregando una réplica fiel en PDF lista para distribución.

## Cómo dividir hojas de Excel por filas
Dividir por filas crea una serie de páginas HTML, cada una con un número fijo de filas (p. ej., 15). Este enfoque es ideal para paneles que muestran un número limitado de registros por vista. El visor generará archivos HTML separados como `page_0.html`, `page_1.html`, etc., cada uno con el número especificado de filas. Esto simplifica cargar solo la porción necesaria en una interfaz web, reduciendo el ancho de banda y el tiempo de renderizado.

### Ancla de definición
`Viewer` es la clase central de GroupDocs Viewer que carga un documento y orquesta el renderizado al formato de salida elegido.

### Implementación paso a paso

#### Paso 1: Configurar rutas e inicializar el Viewer
First, define where the split pages will be saved and create a `Viewer` instance for the source workbook.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRows");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/TWO_PAGES_XLSX")) {
    // Proceed with further configuration...
}
```

#### Paso 2: Configurar filas por página
Tell the viewer how many rows each page should contain.

```java
int countRowsPerPage = 15;
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage));
```

#### Paso 3: Renderizar el documento
Finally, render the workbook using the options you defined.

```java
viewer.view(viewOptions);
```

## Cómo dividir hojas de Excel por filas y columnas
A veces una sola página necesita mostrar una matriz de filas **y** columnas (p. ej., 15 filas × 7 columnas). Esto te brinda control total sobre el diseño de cada página HTML. Las páginas resultantes muestran un bloque rectangular de celdas, por ejemplo filas 1‑15 y columnas A‑G en la primera página, filas 16‑30 y columnas H‑N en la siguiente. Esta paginación estilo cuadrícula es útil para crear informes imprimibles que se ajusten a tamaños de papel estándar.

### Ancla de definición
`SpreadsheetOptions` configura cuántas filas y columnas aparecen en cada página generada.

### Implementación paso a paso

#### Paso 1: Configurar rutas e inicializar el Viewer
The setup mirrors the row‑only example, only the file name changes.

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY/SplitByRowsAndColumns");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/FOUR_PAGES_XLSX")) {
    // Continue with configuration...
}
```

#### Paso 2: Configurar filas y columnas por página
Specify both dimensions to create a grid‑style split.

```java
int countRowsPerPage = 15;
int countColumnsPerPage = 7;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
options.setSpreadsheetOptions(SpreadsheetOptions.forSplitSheetIntoPages(countRowsPerPage, countColumnsPerPage));
```

#### Paso 3: Renderizar el documento
Render using the same `view` call.

```java
viewer.view(options);
```

## Aplicaciones prácticas
- **Generate Excel report Java**: Convierte grandes modelos financieros en una serie de informes HTML paginados.  
- **GroupDocs Viewer Excel**: Inserta páginas divididas directamente en un portal web para la exploración interactiva de datos.  
- **Render Excel HTML Java**: Sirve las páginas HTML generadas a través de un servlet o controlador Spring para un renderizado rápido del lado del cliente.  

## Consideraciones de rendimiento
- **Memory usage** – Los libros de trabajo grandes pueden consumir una cantidad significativa de heap; considera aumentar la configuración JVM `-Xmx`.  
- **Chunk size** – Elige recuentos de filas/columnas que equilibren el tamaño de la página y la velocidad de renderizado.  
- **Version updates** – Mantén GroupDocs Viewer actualizado para beneficiarte de mejoras de rendimiento; la última versión 25.2 mejora la velocidad de renderizado hasta en un 30 % comparado con la 24.x.

## Problemas comunes y solución de problemas
| Síntoma | Causa probable | Solución |
|---------|----------------|----------|
| `OutOfMemoryError` | Renderizar una hoja muy grande con demasiadas filas por página | Reducir `countRowsPerPage` o aumentar el heap de JVM |
| Archivos de salida en blanco | Ruta de archivo incorrecta o permisos de escritura faltantes | Verificar que `outputDirectory` exista y sea escribible |
| Recursos HTML no se cargan | Usar `forEmbeddedResources` pero servir archivos desde una URL base diferente | Servir toda la carpeta de salida o cambiar a `forExternalResources` |

## Preguntas frecuentes

**Q: ¿Puedo generar un PDF en lugar de HTML?**  
A: Sí. Reemplaza `HtmlViewOptions` con `PdfViewOptions` y mantén la misma configuración de `SpreadsheetOptions`.

**Q: ¿Es posible dividir basado en el contenido de la celda en lugar de filas/columnas fijas?**  
A: La división basada directamente en contenido no está incorporada en GroupDocs Viewer, pero puedes preprocesar el libro de trabajo con Apache POI para crear hojas separadas antes del renderizado.

**Q: ¿GroupDocs Viewer admite formatos antiguos de Excel (XLS)?**  
A: Absolutamente. El visor maneja XLS, XLSX, CSV y otros formatos de hoja de cálculo.

**Q: ¿Cómo incrusto el HTML generado en una vista Spring MVC?**  
A: Sirve la carpeta de salida como recurso estático y referencia los `page_0.html`, `page_1.html`, etc., generados desde tus plantillas Thymeleaf o JSP.

**Q: ¿Qué licencia necesito para despliegue comercial?**  
A: Se requiere una licencia de producción completa de GroupDocs; las licencias de prueba son solo para evaluación.

## Recursos
- **Documentation**: [Documentación de GroupDocs Viewer Java](https://docs.groupdocs.com/viewer/java/)
- **API Reference**: [Referencia de API de GroupDocs](https://reference.groupdocs.com/viewer/java/)
- **Download**: [Descargas de GroupDocs Viewer Java](https://releases.groupdocs.com/viewer/java/)
- **Purchase**: [Comprar licencia de GroupDocs](https://purchase.groupdocs.com/buy)
- **Free Trial**: [Prueba gratuita de GroupDocs](https://releases.groupdocs.com/viewer/java/)
- **Temporary License**: [Obtener licencia temporal](https://purchase.groupdocs.com/temporary-license/)
- **Support**: [Foro de soporte de GroupDocs](https://forum.groupdocs.com/c/viewer/9)

---

**Última actualización:** 2026-06-15  
**Probado con:** GroupDocs Viewer 25.2 for Java  
**Autor:** GroupDocs  

## Tutoriales relacionados

- [Renderizar filas y columnas ocultas en hojas de cálculo Java usando GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [Omitir el renderizado de filas vacías en Java usando GroupDocs.Viewer: Guía de rendimiento](/viewer/java/advanced-rendering/skip-rendering-empty-rows-java-groupdocs-viewer/)
- [Guía completa: Convertir Excel 2003 XML a HTML/JPG/PNG/PDF con GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-2003-xml-conversion/)