---
date: '2026-08-08'
description: Aprende cómo convertir IGS a PDF, HTML, JPG y PNG usando GroupDocs.Viewer
  para Java. Guía paso a paso, requisitos previos y solución de problemas para desarrolladores
  Java.
keywords:
- convert igs to pdf
- convert cad to image
- convert igs to jpg
- java cad to pdf
lastmod: '2026-08-08'
og_description: Convierte IGS a PDF, HTML, JPG y PNG usando GroupDocs.Viewer para
  Java. Configuración detallada, fragmentos de código y solución de problemas para
  desarrolladores Java.
og_image_alt: 'Developer guide: convert IGS files to PDF, HTML, JPG, PNG with GroupDocs.Viewer
  Java'
og_title: Convertir IGS a PDF, HTML, JPG y PNG con GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-08'
  description: Learn how to convert IGS to PDF, HTML, JPG, and PNG using GroupDocs.Viewer
    for Java. Step‑by‑step guide, prerequisites, and troubleshooting for Java developers.
  headline: Convert IGS to PDF, HTML, JPG & PNG with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: Yes. Iterate over a collection of file paths and invoke the appropriate
      `view` method for each file within the same `Viewer` instance.
    question: Can I convert multiple IGS files in a single run?
  - answer: Absolutely. `PdfViewOptions` offers `setPageSize(PageSize.A4)`, `PageSize.Letter`,
      and custom dimensions via `setCustomSize(width, height)`.
    question: Is it possible to customize the PDF page size?
  - answer: No. A single GroupDocs.Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: The library reliably processes files up to **500 MB**; for models larger
      than 200 MB, allocate additional JVM memory and consider rendering in batches.
    question: How large can an IGS file be before performance degrades?
  - answer: GroupDocs.Viewer renders the default orientation defined in the IGS file.
      For custom views, preprocess the file with a CAD tool or adjust the model before
      conversion.
    question: Can I render only a specific view or orientation?
  type: FAQPage
tags:
- convert igs
- groupdocs.viewer
- java cad conversion
- pdf generation java
title: Convertir IGS a PDF, HTML, JPG y PNG con GroupDocs.Viewer Java
type: docs
url: /es/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# Convertir IGS a PDF, HTML, JPG y PNG con GroupDocs.Viewer Java

Si necesita **convertir IGS a PDF** (o a HTML, JPG, PNG) directamente desde una aplicación Java, ha llegado al lugar correcto. En este tutorial repasaremos todo lo que necesita—desde la instalación de la biblioteca hasta la renderización del modelo 3‑D en el formato que se ajuste a su proyecto. Entenderá por qué GroupDocs.Viewer es una opción sólida para conversiones rápidas y fiables y obtendrá fragmentos de código listos para ejecutar que podrá incorporar en su propia solución.

![Convertir archivos IGS a HTML, JPG, PNG y PDF con GroupDocs.Viewer para Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Respuestas rápidas
- **¿Puedo convertir IGS a PDF con Java?** Sí, use `PdfViewOptions` junto con la API `Viewer`.  
- **¿Qué formatos de salida son compatibles?** HTML, JPG, PNG y PDF se manejan de forma nativa.  
- **¿Necesito una licencia para producción?** Se requiere una licencia comercial; una prueba gratuita le permite probar las funciones principales.  
- **¿Qué versión de Java se requiere?** JDK 8 o superior; la biblioteca también funciona en Java 11, 17 y posteriores.  
- **¿Es Maven la única forma de agregar la biblioteca?** No, también puede usar Gradle o agregar manualmente los archivos JAR a su classpath.

## Qué es convertir IGS a PDF?
Convertir IGS a PDF significa transformar un archivo CAD 3‑D neutral en un documento estático y universalmente visible. Esto le permite compartir visualizaciones de diseño con partes interesadas que no disponen de herramientas CAD, incrustar la renderización en informes o archivar el modelo para fines de cumplimiento.

## Por qué usar GroupDocs.Viewer para conversiones de IGS?
GroupDocs.Viewer procesa archivos IGS sin requerir ningún software CAD externo. Soporta **más de 50 formatos de entrada y salida**, puede renderizar ensamblajes que contienen **cientos de piezas** manteniendo el uso de memoria por debajo de **200 MB**, y entrega resultados en menos de **2 segundos** para modelos típicos en un servidor estándar. Estos beneficios cuantificados lo convierten en una opción de alto rendimiento y rentable para pipelines empresariales.

## Requisitos previos
- **GroupDocs.Viewer para Java** ≥ 25.2 (la última versión estable).  
- **JDK 8+** instalado y configurado en su IDE (IntelliJ IDEA, Eclipse, NetBeans, etc.).  
- Conocimientos básicos de Maven (opcional pero recomendado para la gestión de dependencias).  

## Configuración de GroupDocs.Viewer para Java

### Dependencia Maven
Agregue el repositorio de GroupDocs y la dependencia Viewer a su `pom.xml`:

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
GroupDocs.Viewer ofrece tres opciones de licencia:
- **Prueba gratuita** – uso limitado, perfecta para pruebas rápidas de prueba de concepto.  
- **Licencia temporal** – conjunto completo de funciones por un corto período de evaluación, ideal para proyectos piloto.  
- **Licencia comercial** – uso de producción sin restricciones, incluye soporte prioritario y actualizaciones.

### Inicialización básica del visor
La clase `Viewer` es el punto de entrada para todas las operaciones de renderizado. Carga el archivo fuente, analiza el formato y expone métodos para producir la salida deseada.

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## Renderizado de IGS a HTML

### ¿Cómo convertir IGS a HTML?
Cargue el archivo IGS con una instancia de `Viewer` y pase un objeto `HtmlViewOptions` que incruste todos los recursos necesarios. La llamada devuelve un único archivo HTML que contiene la vista 3‑D completa, facilitando su inserción en páginas web. También puede personalizar el renderizado configurando opciones como el tamaño de página, el color de fondo y si incluir controles interactivos.  
HtmlViewOptions configura cómo se genera la salida HTML, incluyendo la incrustación de recursos y el diseño de página.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToHtml {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Renderizado de IGS a JPG

### ¿Cómo convertir IGS a JPG?
Cree un objeto `JpgViewOptions`, configure la resolución y la calidad de compresión deseadas, y permita que el `Viewer` genere imágenes rasterizadas para cada página del modelo. Los archivos JPG generados pueden guardarse en un directorio especificado, y puede ajustar el parámetro de calidad para equilibrar el tamaño del archivo con la fidelidad visual, lo cual es útil para miniaturas o impresiones de alta resolución.  
JpgViewOptions especifica la configuración para la generación de imágenes JPG, como resolución, calidad y directorio de salida.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToJpg {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Renderizado de IGS a PNG

### ¿Cómo convertir IGS a PNG?
La clase `PngViewOptions` le permite producir imágenes sin pérdida con transparencia opcional. Este formato es ideal para superponer el modelo sobre fondos de color en material de marketing. También puede definir la resolución y el color de fondo para que coincidan con las directrices de su marca, asegurando una apariencia consistente en todos los recursos generados.  
PngViewOptions define los parámetros para el renderizado PNG, incluyendo resolución, transparencia y color de fondo.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPng {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Renderizado de IGS a PDF

### ¿Cómo convertir IGS a PDF?
Utilice `PdfViewOptions` para producir un PDF paginado que preserve el diseño visual del modelo 3‑D. También puede incrustar fuentes y controlar el tamaño de página para cumplir con las directrices de marca corporativa. Configuraciones adicionales le permiten especificar la calidad de imagen, el nivel de compresión y si incluir una tabla de contenido para ensamblajes de varias páginas.  
PdfViewOptions controla la creación del PDF, permitiendo la configuración del tamaño de página, la calidad de imagen y la incrustación de fuentes.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPdf {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Aplicaciones prácticas
- **Portales web** – incruste modelos renderizados en HTML directamente en configuradores de productos, permitiendo a los clientes rotar y hacer zoom sin instalar complementos.  
- **Recursos de marketing** – genere imágenes JPG/PNG de alta resolución para folletos, presentaciones y publicaciones en redes sociales.  
- **Documentación técnica** – incluya renderizados PDF de modelos CAD en manuales de usuario, asegurando que los ingenieros puedan ver los diseños sin conexión.  
- **Control de calidad** – automatice la creación de miniaturas para miles de archivos IGS, acelerando los flujos de trabajo de inspección visual.

## Problemas comunes y soluciones

| Problema | Solución |
|----------|----------|
| **Carpeta de salida no encontrada** | Verifique la ruta pasada a `Path outputDirectory` y asegúrese de que el proceso Java tenga permisos de escritura en el directorio de destino. |
| **Páginas en blanco en PDF** | Confirme que el archivo IGS fuente no esté corrupto; ábralo primero en un visor CAD nativo. |
| **Renderizado lento para ensamblajes grandes** | Aumente el heap de la JVM (`-Xmx2g` o más) y considere renderizar página por página usando `viewer.getPageCount()` para procesar en bloques. |
| **Fuentes faltantes en PDF** | Utilice `PdfViewOptions` para incrustar las fuentes requeridas o instale las fuentes faltantes en el servidor que aloja el servicio de conversión. |

## Preguntas frecuentes

**Q: ¿Puedo convertir varios archivos IGS en una sola ejecución?**  
A: Sí. Itere sobre una colección de rutas de archivo e invoque el método `view` apropiado para cada archivo dentro de la misma instancia `Viewer`.

**Q: ¿Es posible personalizar el tamaño de página del PDF?**  
A: Absolutamente. `PdfViewOptions` ofrece `setPageSize(PageSize.A4)`, `PageSize.Letter` y dimensiones personalizadas mediante `setCustomSize(width, height)`.

**Q: ¿Necesito una licencia separada para cada formato de salida?**  
A: No. Una única licencia de GroupDocs.Viewer cubre todos los formatos compatibles, incluidos HTML, JPG, PNG y PDF.

**Q: ¿Qué tamaño puede tener un archivo IGS antes de que el rendimiento se degrade?**  
A: La biblioteca procesa de manera fiable archivos de hasta **500 MB**; para modelos mayores de 200 MB, asigne memoria JVM adicional y considere renderizar en lotes.

**Q: ¿Puedo renderizar solo una vista u orientación específica?**  
A: GroupDocs.Viewer renderiza la orientación predeterminada definida en el archivo IGS. Para vistas personalizadas, preprocese el archivo con una herramienta CAD o ajuste el modelo antes de la conversión.

---

**Última actualización:** 2026-08-08  
**Probado con:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs

## Tutoriales relacionados

- [convertir cdr a html, jpg, png, pdf con GroupDocs.Viewer Java](/viewer/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/)
- [Cómo convertir pdf a html y optimizar la calidad de imagen en Java con GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)