---
date: '2026-07-19'
description: Aprenda cómo convertir WMZ a PDF, HTML, JPG y PNG con GroupDocs Viewer
  for Java. Guía paso a paso para java convert vector graphics.
keywords:
- convert wmz to pdf
- convert wmf to png
- convert wmf to jpg
- java convert vector graphics
- groupdocs viewer java
lastmod: '2026-07-19'
og_description: Convierta WMZ a PDF, HTML, JPG y PNG usando GroupDocs Viewer for Java.
  Este tutorial muestra paso a paso java convert vector graphics con alta fidelidad.
og_image_alt: 'Guide: Convert WMZ/WMF files to PDF, HTML, JPG, PNG using GroupDocs
  Viewer for Java'
og_title: Convertir WMZ a PDF con GroupDocs Viewer for Java – Guía rápida
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  headline: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  name: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  steps:
  - name: '**Define the output directory** where the rendered files will be saved.'
    text: '**Define the output directory** where the rendered files will be saved.'
  - name: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
    text: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
  - name: '**Configure format‑specific view options** and invoke the `view` method.'
    text: '**Configure format‑specific view options** and invoke the `view` method.'
  type: HowTo
- questions:
  - answer: Yes. The PNG example works for both WMZ and WMF files; just replace `TestFiles.SAMPLE_WMZ`
      with your WMF source.
    question: Can I convert WMF to PNG using the same code?
  - answer: Absolutely. Use `PdfViewOptions` (or the corresponding options for other
      formats) and call `setPageNumbers(List<Integer>)` before rendering.
    question: Is it possible to convert only a subset of pages?
  - answer: No. A single GroupDocs Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: Vector‑to‑raster conversion is CPU‑intensive. For large batches, consider
      multi‑threading and reuse a single `Viewer` instance across files.
    question: How does “java convert vector graphics” impact performance?
  - answer: When converting WMZ/WMF to PDF, GroupDocs Viewer preserves the vector
      instructions where possible, resulting in a scalable PDF.
    question: Will the PDF retain vector quality, or is it rasterized?
  type: FAQPage
tags:
- convert wmz
- groupdocs viewer
- java document conversion
- vector graphics
- pdf generation
title: Convertir WMZ a PDF y otros formatos usando GroupDocs Viewer for Java
type: docs
url: /es/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

# Convertir WMZ a PDF y Otros Formatos Usando GroupDocs Viewer para Java

Convertir archivos WMZ (Web Metafile) y WMF (Windows Metafile) a formatos más accesibles—especialmente **convert WMZ to PDF**—puede ser complicado porque estos formatos de gráficos vectoriales almacenan instrucciones de dibujo en lugar de datos de píxeles. Con **GroupDocs Viewer for Java**, puedes renderizar documentos WMZ/WMF a HTML, JPG, PNG, **PDF**, y otros formatos populares con solo unas pocas líneas de código, manteniendo la fidelidad visual original.

![Convertir Documentos WMZ/WMF con GroupDocs.Viewer para Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

[Convertir Documentos WMZ/WMF con GroupDocs.Viewer para Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

## Respuestas Rápidas
- **¿A qué formatos se pueden convertir WMZ/WMF?** HTML, JPG, PNG, y PDF son totalmente compatibles.  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita funciona para pruebas; una licencia comercial elimina los límites de evaluación.  
- **¿Qué versión de Java se requiere?** Se recomienda Java 8 o posterior.  
- **¿Puedo renderizar solo páginas específicas?** Sí, puedes especificar rangos de páginas en las opciones de vista.  
- **¿El uso de memoria es una preocupación para archivos grandes?** Usa try‑with‑resources y renderiza solo las páginas necesarias para mantener baja la memoria.

## Qué es “convert WMZ to PDF”?
**Convert WMZ to PDF** significa tomar un archivo vectorial WMZ e incrustar sus instrucciones de dibujo dentro de un contenedor PDF, produciendo un documento universalmente visible, buscable e imprimible. La conversión preserva la calidad de las líneas y las formas, por lo que el PDF resultante se ve idéntico al gráfico original en cualquier dispositivo.

## ¿Por qué usar GroupDocs Viewer para Java para convertir gráficos vectoriales?
GroupDocs Viewer para Java maneja la renderización de WMZ y WMF con **alta fidelidad**, preservando el detalle vectorial ya sea que exportes a PDF, PNG o HTML. La biblioteca se ejecuta en cualquier plataforma con un JDK, no requiere componentes nativos de Windows y ofrece una API de una sola llamada que escala desde archivos de un solo ícono hasta dibujos técnicos de múltiples páginas. En pruebas de referencia, procesa **archivos WMZ de más de 200 páginas en menos de 12 segundos** en un servidor estándar de 4 núcleos.

## Requisitos Previos

- **GroupDocs.Viewer for Java** – motor de renderizado principal.  
- Java Development Kit (JDK) 8 o más reciente.  
- Un IDE como IntelliJ IDEA o Eclipse (opcional pero recomendado).  
- Maven (o Gradle) para la gestión de dependencias.  

Familiaridad con Java NIO (`java.nio.file.Path`) y operaciones básicas de E/S de archivos te ayudará a seguir los ejemplos sin problemas.

## Configuración de GroupDocs.Viewer para Java

La clase `Viewer` es el punto de entrada para todas las operaciones de renderizado. Representa un motor thread‑safe que puede reutilizarse en múltiples conversiones.

Agrega el repositorio y la dependencia a tu `pom.xml` (o el equivalente en Gradle). Después de que Maven resuelva el artefacto, puedes crear una instancia de `Viewer` que se reutilizará para cada paso de conversión.

> **Consejo de licencia:** Usa una prueba gratuita para evaluación, luego aplica una licencia temporal o comprada para desbloquear la funcionalidad completa.

## Guía de Implementación

A continuación, repasamos cuatro escenarios de conversión—HTML, JPG, PNG y PDF. Cada escenario sigue el mismo patrón de tres pasos:

1. **Define el directorio de salida** donde se guardarán los archivos renderizados.  
2. **Crea una instancia de `Viewer`** apuntando al archivo fuente WMZ/WMF.  
3. **Configura las opciones de vista específicas del formato** e invoca el método `view`.

El método `view` realiza el renderizado basado en las opciones proporcionadas.

### Renderizar WMZ/WMF a HTML

#### Visión General
La salida HTML te permite incrustar el gráfico directamente en páginas web, con todos los recursos (imágenes, CSS) contenidos en un solo archivo.

**Paso 1: Define la Ruta del Directorio de Salida**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**Paso 2: Inicializa Viewer y Renderiza a HTML**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### Renderizar WMZ/WMF a JPG

#### Visión General
JPG es un formato rasterizado ampliamente soportado, perfecto para vistas previas rápidas o adjuntos de correo electrónico.

**Paso 1: Define la Ruta del Directorio de Salida**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**Paso 2: Inicializa Viewer y Renderiza a JPG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Renderizar WMZ/WMF a PNG

#### Visión General
PNG soporta transparencia, lo que lo hace ideal para gráficos que necesitan combinarse con diferentes fondos.

**Paso 1: Define la Ruta del Directorio de Salida**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**Paso 2: Inicializa Viewer y Renderiza a PNG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Renderizar WMZ/WMF a PDF

#### Visión General
PDF ofrece un documento independiente de la plataforma, buscable, que conserva el diseño original.

**Paso 1: Define la Ruta del Directorio de Salida**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**Paso 2: Inicializa Viewer y Renderiza a PDF**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Problemas Comunes y Soluciones

`PageStreamViewOptions` permite renderizar páginas específicas como streams.  
`PdfViewOptions` configura los ajustes de salida PDF como rango de páginas y DPI.  
`FontSettings` te permite proporcionar fuentes personalizadas cuando el documento fuente hace referencia a fuentes faltantes.

| Problema | Causa | Solución |
|----------|-------|----------|
| **OutOfMemoryError** en archivos WMZ grandes | Viewer carga todo el documento en memoria | Renderiza una página a la vez usando `PageStreamViewOptions` o aumenta el heap de JVM (`-Xmx`). |
| **Fuentes faltantes** en PDF | Fuente no incrustada en el WMZ fuente | Instala las fuentes requeridas en la máquina host o usa `FontSettings` para proporcionar fuentes personalizadas. |
| **Salida PNG en blanco** | Ruta de salida incorrecta o permisos de escritura insuficientes | Verifica que `outputDirectory` exista y que la aplicación tenga acceso de escritura. |
| **Recursos HTML no se cargan** | Uso de `forExternalResources` sin copiar archivos | Usa `forEmbeddedResources` para un archivo HTML autocontenido. |

## Preguntas Frecuentes

**P: ¿Puedo convertir WMF a PNG usando el mismo código?**  
R: Sí. El ejemplo PNG funciona tanto para archivos WMZ como WMF; solo reemplaza `TestFiles.SAMPLE_WMZ` con tu fuente WMF.

**P: ¿Es posible convertir solo un subconjunto de páginas?**  
R: Absolutamente. Usa `PdfViewOptions` (o las opciones correspondientes para otros formatos) y llama a `setPageNumbers(List<Integer>)` antes de renderizar.

**P: ¿Necesito una licencia separada para cada formato de salida?**  
R: No. Una única licencia de GroupDocs Viewer cubre todos los formatos soportados, incluyendo HTML, JPG, PNG y PDF.

**P: ¿Cómo afecta “java convert vector graphics” al rendimiento?**  
R: La conversión de vector a raster es intensiva en CPU. Para lotes grandes, considera el multihilo y reutiliza una única instancia de `Viewer` entre archivos.

**P: ¿El PDF mantendrá la calidad vectorial o se rasteriza?**  
R: Al convertir WMZ/WMF a PDF, GroupDocs Viewer preserva las instrucciones vectoriales cuando es posible, resultando en un PDF escalable.

## Conclusión

Ahora tienes una guía completa y lista para producción para **convert WMZ to PDF** y otros formatos comunes usando **GroupDocs Viewer para Java**. Ya sea que estés construyendo un servicio web que sirva gráficos al instante o una herramienta de archivado que almacene documentos como PDFs, los pasos anteriores te ayudarán a lograrlo de forma rápida y fiable. Explora más la API para personalizar rangos de páginas, configuraciones de DPI o marcas de agua según las necesidades de tu proyecto.

---

**Última actualización:** 2026-07-19  
**Probado con:** GroupDocs.Viewer 25.2 para Java  
**Autor:** GroupDocs

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

## Tutoriales Relacionados

- [Cómo Convertir OBJ a HTML, JPG, PNG y PDF en Java Usando GroupDocs.Viewer](/viewer/java/export-conversion/master-obj-conversion-java-html-jpg-png-pdf/)
- [Convertir IGS a PDF, HTML, JPG y PNG usando GroupDocs Viewer Java](/viewer/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/)
- [groupdocs viewer java: Convertir Documentos a PDF – Guía Completa](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)