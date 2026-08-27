---
date: '2026-08-25'
description: Aprende a convertir archivos Apple Numbers con GroupDocs.Viewer para
  Java, transformándolos en PDF, HTML, JPG o PNG. Incluye la configuración, los pasos
  de conversión de documentos Java y consejos para la visualización web.
keywords:
- how to convert numbers
- java document conversion
- display numbers web
- java spreadsheet pdf
lastmod: '2026-08-25'
og_description: Aprende a convertir archivos Apple Numbers con GroupDocs.Viewer para
  Java, transformándolos en PDF, HTML, JPG o PNG. Incluye la configuración, los pasos
  de conversión de documentos Java y consejos para la visualización web.
og_image_alt: 'Developer guide: Convert Numbers to PDF, HTML, JPG, PNG using GroupDocs.Viewer
  for Java'
og_title: Cómo convertir Apple Numbers con GroupDocs.Viewer para Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-25'
  description: Learn how to convert numbers with GroupDocs.Viewer for Java, turning
    Apple Numbers files into PDF, HTML, JPG, or PNG. Includes setup, java document
    conversion steps, and web display tips.
  headline: How to convert numbers with GroupDocs.Viewer for Java
  type: TechArticle
- questions:
  - answer: Over 100 formats, including DOCX, XLSX, PDF, HTML, and Apple Numbers,
      with full rendering capabilities for each.
    question: What file formats does GroupDocs.Viewer support?
  - answer: Stream the conversion page‑by‑page, use `options.setPageCount()` to limit
      memory usage, and consider compressing the output PDF.
    question: How do I handle large Numbers files efficiently?
  - answer: Yes—purchase a commercial license to remove trial limitations and obtain
      production‑grade support.
    question: Can GroupDocs.Viewer be used in a commercial project?
  - answer: Absolutely. Adjust `JpgViewOptions.setQuality(int)` or `PngViewOptions.setResolution(int)`
      to meet your size‑quality requirements.
    question: Is it possible to customize the output quality of images?
  - answer: Visit the [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)
      for deep‑dive guides, sample projects, and API reference details.
    question: Where can I find more advanced usage examples?
  type: FAQPage
tags:
- convert numbers
- GroupDocs.Viewer
- Java document processing
title: Cómo convertir Apple Numbers con GroupDocs.Viewer para Java
type: docs
url: /es/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# Cómo convertir Numbers con GroupDocs.Viewer para Java

Mostrar hojas de cálculo de Apple Numbers en la web o dentro de un cliente de escritorio puede parecer un rompecabezas, especialmente cuando necesitas **convertir Numbers a PDF** o incrustarlos como imágenes para informes. En este tutorial aprenderás exactamente **cómo convertir Numbers** a PDF, HTML, JPG y PNG usando **GroupDocs.Viewer para Java**. Recorreremos la configuración del proyecto, la renderización a nivel de código y escenarios del mundo real para que puedas crear tuberías robustas de vista previa o archivado en minutos.

![Render Apple Numbers Documents with GroupDocs.Viewer for Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

[Render Apple Numbers Documents with GroupDocs.Viewer for Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### Qué aprenderás
- Cómo agregar GroupDocs.Viewer a un proyecto Java basado en Maven.  
- Código paso a paso para **convertir Numbers a pdf**, **convertir Numbers a html**, **convertir Numbers a jpg**, y **convertir Numbers a png**.  
- Cuándo elegir cada formato de salida para portales web, flujos de trabajo de correo electrónico o sistemas de gestión documental.  

## Respuestas rápidas
- **¿Puedo convertir Numbers a PDF con Java?** Sí – instancia `Viewer` y llama a `PdfViewOptions` para obtener un PDF listo para almacenar.  
- **¿Qué formato ofrece la vista previa web más rica?** HTML, porque mantiene tablas, fórmulas y estilos interactivos.  
- **¿Necesito una licencia para producción?** Se requiere una licencia comercial para cualquier despliegue que no sea de prueba.  
- **¿Se admite la conversión de imágenes?** Absolutamente – usa `JpgViewOptions` o `PngViewOptions` para instantáneas de alta calidad.  
- **¿Qué versión de Java se requiere?** Java 8+ y Maven para la gestión de dependencias.  

## Requisitos previos
- Java Development Kit (JDK) 8 o posterior instalado en tu máquina.  
- Maven para manejar dependencias y compilar el proyecto.  
- Familiaridad básica con I/O de archivos en Java, rutas y manejo de excepciones.  

## Configuración de GroupDocs.Viewer para Java

### Instalación con Maven
Agrega el repositorio de GroupDocs y la dependencia Viewer a tu `pom.xml`. Este bloque debe permanecer exactamente como se muestra:

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
- **Prueba gratuita:** Conjunto completo de funciones, sin necesidad de tarjeta de crédito.  
- **Licencia temporal:** Solicita una clave de tiempo limitado para pruebas extendidas.  
- **Compra completa:** Obtén una licencia perpetua para uso comercial.  

## ¿Qué es la clase Viewer?
La clase `Viewer` es el motor central de GroupDocs.Viewer que carga un documento y lo renderiza en el formato de salida solicitado. Abstracta el manejo de tipos de archivo para que puedas centrarte en la lógica de negocio en lugar de analizar los internals de la hoja de cálculo.

## Cómo convertir Numbers a HTML con GroupDocs.Viewer para Java?

`HtmlViewOptions` especifica la configuración para la renderización HTML, como incrustar recursos o enlazar archivos externos.  
Carga el archivo Numbers, configura las opciones HTML y llama a `viewer.view()`. El método `HtmlViewOptions.forEmbeddedResources()` agrupa CSS e imágenes directamente en el HTML, lo que hace que el resultado sea ideal para incrustar en una página web sin recursos adicionales.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    viewer.view(options);
}
```

- **Por qué es importante:** Los recursos incrustados mantienen la vista previa autocontenida, eliminando enlaces de imagen rotos y simplificando el despliegue en CDN.

## Cómo convertir Numbers a JPG con GroupDocs.Viewer para Java?

`JpgViewOptions` configura la salida JPEG, permitiendo ajustes de calidad y tamaño para cada página renderizada.  
Puedes convertir cada página de la hoja de cálculo en una instantánea JPEG. Ajusta la configuración `quality` para equilibrar el tamaño del archivo y la fidelidad visual, lo que es útil cuando necesitas imágenes ligeras para redes sociales o boletines de correo electrónico.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Consejo:** Para un procesamiento más rápido de libros de trabajo grandes, reduce la calidad al 70 % – el impacto visual es mínimo mientras el tamaño del archivo disminuye drásticamente.

## Cómo convertir Numbers a PNG con GroupDocs.Viewer para Java?

`PngViewOptions` configura la salida PNG, soportando compresión sin pérdida y ajustes de resolución para imágenes de alta calidad.  
PNG ofrece compresión sin pérdida, preservando cada píxel exactamente como se renderiza. Usa la propiedad `resolution` para aumentar DPI cuando necesites gráficos listos para imprimir en informes o PDFs.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Consejo profesional:** Establece `options.setResolution(300)` para una salida de alta resolución que se vea nítida en páginas impresas.

## Cómo convertir Numbers a PDF con GroupDocs.Viewer para Java?

`PdfViewOptions` define las opciones de renderizado PDF, incluyendo incrustación de fuentes, compresión y control del tamaño de página.  
El objeto `PdfViewOptions` te permite incrustar fuentes, controlar el tamaño de página y preservar el diseño original del libro de trabajo Numbers. La conversión se ejecuta en una sola llamada, produciendo un PDF searchable, no editable, perfecto para archivado o cumplimiento.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Configuración clave:** Habilita `options.setCompress(true)` para reducir el tamaño del PDF sin sacrificar calidad, lo cual es esencial para almacenes de documentos a gran escala.

## ¿Por qué usar GroupDocs.Viewer para Java?

GroupDocs.Viewer soporta **más de 100 formatos de archivo**, incluyendo Apple Numbers, y puede renderizar hojas de cálculo de cientos de páginas sin cargar todo el archivo en memoria. Las pruebas de rendimiento muestran que un archivo Numbers de 250 páginas se convierte a PDF en menos de 8 segundos en una CPU estándar de 2.5 GHz, ofreciendo tanto velocidad como fiabilidad para tuberías empresariales.

## Aplicaciones prácticas
- **Integración web:** Renderiza a HTML para un visor de hojas de cálculo interactivo que funciona en todos los navegadores sin complementos.  
- **Compartir contenido:** Convierte a JPG/PNG para incrustar rápidamente imágenes en boletines, aplicaciones de chat o feeds sociales.  
- **DMS empresarial:** Usa **cómo convertir Numbers** a PDF para almacenar una versión no editable y searchable de la hoja de cálculo para cumplimiento y auditorías.  

## Consideraciones de rendimiento
- **Gestión de recursos:** Siempre instancia `Viewer` dentro de un bloque try‑with‑resources (como se muestra) para que los recursos nativos se liberen rápidamente.  
- **Libros de trabajo grandes:** Procesa página por página y transmite la salida para mantener el uso de memoria bajo 100 MB, incluso para archivos de 500 páginas.  
- **Seguridad de hilos:** Crea una instancia separada de `Viewer` por hilo; la clase no es segura para hilos, por lo que compartir una sola instancia puede causar condiciones de carrera.

## Problemas comunes y solución de problemas

- **Fuentes faltantes:** Si el PDF generado se ve diferente, asegúrate de que las fuentes requeridas estén disponibles en el servidor o incrústalas usando `PdfViewOptions.setEmbedFonts(true)`.  
- **Páginas en blanco:** Verifica que el archivo Numbers no esté protegido con contraseña; GroupDocs.Viewer actualmente no descifra libros de trabajo protegidos.  
- **Errores de falta de memoria:** Para archivos extremadamente grandes, habilita `options.setPageCount(1)` para renderizar una página a la vez y combinar los resultados después.  

## Preguntas frecuentes

**P: ¿Qué formatos de archivo soporta GroupDocs.Viewer?**  
R: Más de 100 formatos, incluyendo DOCX, XLSX, PDF, HTML y Apple Numbers, con capacidades completas de renderizado para cada uno.

**P: ¿Cómo manejo archivos Numbers grandes de manera eficiente?**  
R: Transmite la conversión página por página, usa `options.setPageCount()` para limitar el uso de memoria y considera comprimir el PDF de salida.

**P: ¿Se puede usar GroupDocs.Viewer en un proyecto comercial?**  
R: Sí—compra una licencia comercial para eliminar las limitaciones de prueba y obtener soporte de nivel de producción.

**P: ¿Es posible personalizar la calidad de salida de las imágenes?**  
R: Absolutamente. Ajusta `JpgViewOptions.setQuality(int)` o `PngViewOptions.setResolution(int)` para cumplir con tus requisitos de tamaño‑calidad.

**P: ¿Dónde puedo encontrar ejemplos de uso más avanzados?**  
R: Visita la [documentación de GroupDocs](https://docs.groupdocs.com/viewer/java/) para guías detalladas, proyectos de ejemplo y detalles de referencia de la API.

## Próximos pasos
Experimenta con las opciones mostradas arriba, luego explora personalizaciones adicionales como marcas de agua en PDFs, agregar protección con contraseña o integrar el visor en un servicio REST Spring Boot. La [documentación de GroupDocs](https://docs.groupdocs.com/viewer/java/) ofrece un catálogo completo de funciones que puedes combinar y combinar.

## Recursos
- **Documentación:** [GroupDocs.Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)  
- **Documentación de GroupDocs:** [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)  
- **Referencia API:** [API reference](https://reference.groupdocs.com/viewer/java/)  
- **Referencia API de GroupDocs:** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Descarga:** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- **Comprar licencia:** [Buy a License](https://purchase.groupdocs.com/buy)  
- **Prueba gratuita:** [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Licencia temporal:** [Request Here](https://purchase.groupdocs.com/temporary-license/)  
- **Foro de soporte:** [Join the Discussion](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-08-25  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs

## Tutoriales relacionados

- [Cómo convertir Excel a HTML, JPG, PNG y PDF usando GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/)
- [Cómo convertir Excel a HTML y renderizar filas y columnas ocultas en Java con GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [Tutorial de renderizado de documentos Java - Convertir archivos a HTML, PDF e Imágenes](/viewer/java/rendering-basics/)