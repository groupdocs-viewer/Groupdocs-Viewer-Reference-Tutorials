---
date: '2026-02-18'
description: Aprende cómo convertir archivos WMZ y WMF a PDF, HTML, JPG y PNG usando
  GroupDocs Viewer para Java. Esta guía cubre GroupDocs Viewer Java y la conversión
  de gráficos vectoriales en Java.
keywords:
- convert WMZ/WMF documents
- GroupDocs Viewer for Java
- rendering formats
title: Cómo convertir WMZ a PDF y otros formatos usando GroupDocs Viewer para Java
type: docs
url: /es/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

 ayudarán a lograrlo rápidamente."

Then horizontal rule.

"**Last Updated:** 2026-02-18" -> "**Última actualización:** 2026-02-18"

"**Tested With:** GroupDocs.Viewer 25.2 for Java" -> "**Probado con:** GroupDocs.Viewer 25.2 para Java"

"**Author:** GroupDocs" -> "**Autor:** GroupDocs"

Make sure to keep markdown formatting.

Check for any other shortcodes: none.

Make sure to keep code block placeholders unchanged.

Now produce final content.# Cómo Convertir WMZ a PDF y Otros Formatos Usando GroupDocs Viewer para Java

Convertir archivos WMZ (Web Metafile) y WMF (Windows Metafile) a formatos más accesibles—especialmente **convert WMZ to PDF**—puede ser complicado porque estos formatos de gráficos vectoriales almacenan instrucciones de dibujo en lugar de datos de píxeles. Con **GroupDocs Viewer for Java**, puedes renderizar documentos WMZ/WMF a HTML, JPG, PNG, **PDF**, y otros formatos populares con solo unas pocas líneas de código.

![Convert WMZ/WMF Documents with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-wmz-wmf-documents.png)

En este tutorial aprenderás cómo configurar la biblioteca, renderizar archivos WMZ/WMF al resultado deseado y manejar problemas comunes. Al final, podrás integrar **groupdocs viewer java** en tus aplicaciones Java para **java convert vector graphics** de forma rápida y fiable.

## Respuestas Rápidas
- **¿A qué formatos se pueden convertir WMZ/WMF?** HTML, JPG, PNG y PDF son totalmente compatibles.  
- **¿Necesito una licencia para desarrollo?** Una prueba gratuita funciona para pruebas; una licencia comercial elimina los límites de evaluación.  
- **¿Qué versión de Java se requiere?** Se recomienda Java 8 o posterior.  
- **¿Puedo renderizar solo páginas específicas?** Sí, puedes especificar rangos de páginas en las opciones de vista.  
- **¿El uso de memoria es un problema para archivos grandes?** Usa try‑with‑resources y renderiza solo las páginas necesarias para mantener baja la memoria.

## ¿Qué es “convert WMZ to PDF”?
Convertir WMZ a PDF significa tomar el archivo WMZ basado en vectores y rasterizarlo (o preservar sus datos vectoriales) dentro de un contenedor PDF. PDF es universalmente visible, buscable e imprimible, lo que lo hace ideal para archivar y compartir gráficos WMZ.

## ¿Por qué usar GroupDocs Viewer para Java para convertir gráficos vectoriales?
- **Alta fidelidad**: La biblioteca preserva la calidad original del dibujo, ya sea que exportes a PDF o PNG.  
- **Cero dependencias externas**: No se necesitan bibliotecas nativas de Windows; todo funciona en cualquier plataforma con un JDK.  
- **API simple**: Una instancia de `Viewer` y una única llamada a `view` manejan toda la conversión.  
- **Escalable**: Funciona igual de bien para íconos de una sola página y dibujos técnicos de varias páginas.

## Requisitos Previos

### Bibliotecas Requeridas
- **GroupDocs.Viewer for Java** – el motor central de renderizado.  
- Java Development Kit (JDK) 8+.

### Configuración del Entorno
- IDE como IntelliJ IDEA o Eclipse.  
- Maven para la gestión de dependencias (o Gradle si lo prefieres).

### Conocimientos Previos
- Familiaridad con Java file I/O (`java.nio.file.Path`).  
- Comprensión básica de cómo los visores de documentos renderizan contenido.

## Configuración de GroupDocs.Viewer para Java

Agrega el repositorio y la dependencia a tu `pom.xml`:

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

> **Consejo de licencia:** Usa una prueba gratuita para evaluación, luego aplica una licencia temporal o comprada para desbloquear la funcionalidad completa.

Una vez que la dependencia se resuelva, puedes crear una instancia de `Viewer` que se reutilizará para cada paso de conversión.

## Guía de Implementación

Recorreremos cuatro escenarios de conversión: HTML, JPG, PNG y PDF. Cada ejemplo sigue el mismo patrón: definir una ruta de salida, instanciar `Viewer` con el archivo WMZ de origen, configurar las opciones de vista apropiadas y llamar a `view`.

### Renderizando WMZ/WMF a HTML

#### Visión General
La salida HTML te permite incrustar el gráfico directamente en páginas web, con todos los recursos (imágenes, CSS) contenidos en un solo archivo.

**Paso 1: Definir la Ruta del Directorio de Salida**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**Paso 2: Inicializar Viewer y Renderizar a HTML**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### Renderizando WMZ/WMF a JPG

#### Visión General
JPG es un formato raster muy soportado, perfecto para vistas previas rápidas o adjuntos de correo electrónico.

**Paso 1: Definir la Ruta del Directorio de Salida**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**Paso 2: Inicializar Viewer y Renderizar a JPG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Renderizando WMZ/WMF a PNG

#### Visión General
PNG soporta transparencia, lo que lo hace ideal para gráficos que necesitan combinarse con diferentes fondos.

**Paso 1: Definir la Ruta del Directorio de Salida**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**Paso 2: Inicializar Viewer y Renderizar a PNG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Renderizando WMZ/WMF a PDF

#### Visión General
PDF proporciona un documento independiente de la plataforma, buscable, que conserva el diseño original.

**Paso 1: Definir la Ruta del Directorio de Salida**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**Paso 2: Inicializar Viewer y Renderizar a PDF**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Problemas Comunes y Soluciones

| Problema | Causa | Solución |
|----------|-------|----------|
| **OutOfMemoryError** en archivos WMZ grandes | Viewer carga todo el documento en memoria | Renderiza una página a la vez usando `PageStreamViewOptions` o aumenta el heap de JVM (`-Xmx`). |
| **Fuentes faltantes** en PDF | Fuente no incrustada en el WMZ de origen | Instala las fuentes requeridas en la máquina host o usa `FontSettings` para proporcionar fuentes personalizadas. |
| **Salida PNG en blanco** | Ruta de salida incorrecta o permisos de escritura insuficientes | Verifica que `outputDirectory` exista y que la aplicación tenga acceso de escritura. |
| **Recursos HTML no se cargan** | Uso de `forExternalResources` sin copiar los archivos | Usa `forEmbeddedResources` para un archivo HTML autocontenido. |

## Preguntas Frecuentes

**P: ¿Puedo convertir WMF a PNG usando el mismo código?**  
R: Sí. El ejemplo de PNG funciona tanto para archivos WMZ como WMF; solo reemplaza `TestFiles.SAMPLE_WMZ` con tu fuente WMF.

**P: ¿Es posible convertir solo un subconjunto de páginas?**  
R: Absolutamente. Usa `PdfViewOptions` (o las opciones correspondientes para otros formatos) y llama a `setPageNumbers(List<Integer>)` antes de renderizar.

**P: ¿Necesito una licencia separada para cada formato de salida?**  
R: No. Una única licencia de GroupDocs Viewer cubre todos los formatos soportados, incluidos HTML, JPG, PNG y PDF.

**P: ¿Cómo afecta “java convert vector graphics” al rendimiento?**  
R: La conversión de vector a raster es intensiva en CPU. Para lotes grandes, considera multihilo y reutilizar una única instancia de `Viewer` entre archivos.

**P: ¿El PDF mantendrá la calidad vectorial o se rasteriza?**  
R: Al convertir WMZ/WMF a PDF, GroupDocs Viewer preserva las instrucciones vectoriales cuando es posible, resultando en un PDF escalable.

## Conclusión

Ahora tienes una guía completa y lista para producción para **convert WMZ to PDF** y otros formatos comunes usando **GroupDocs Viewer for Java**. Ya sea que estés construyendo un servicio web que sirva gráficos al instante o una herramienta de archivado que almacene documentos como PDFs, los pasos anteriores te ayudarán a lograrlo rápidamente.

---

**Última actualización:** 2026-02-18  
**Probado con:** GroupDocs.Viewer 25.2 para Java  
**Autor:** GroupDocs