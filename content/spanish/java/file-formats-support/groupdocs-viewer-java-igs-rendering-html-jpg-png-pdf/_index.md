---
date: '2026-02-23'
description: Aprende cómo convertir IGS a PDF, HTML, JPG y PNG con GroupDocs.Viewer
  para Java. Sigue esta guía paso a paso con ejemplos de código listos para ejecutar.
keywords:
- GroupDocs.Viewer Java
- Convert IGS Files
- Render IGS Documents
title: Convertir IGS a PDF, HTML, JPG y PNG usando GroupDocs.Viewer Java
type: docs
url: /es/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# Convertir IGS a PDF, HTML, JPG y PNG usando GroupDocs.Viewer Java

Si necesitas **convertir IGS a PDF** (o a HTML, JPG, PNG) directamente desde una aplicación Java, has llegado al lugar correcto. En este tutorial repasaremos todo lo que necesitas —desde la configuración de la biblioteca hasta la renderización del modelo 3‑D en el formato que se ajuste a tu proyecto. Verás por qué GroupDocs.Viewer es una opción sólida para conversiones rápidas y fiables y obtendrás código práctico que puedes incorporar a tu propia solución.

![Convertir archivos IGS a HTML, JPG, PNG y PDF con GroupDocs.Viewer para Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Respuestas rápidas
- **¿Puedo convertir IGS a PDF con Java?** Sí, usando `PdfViewOptions` de GroupDocs.Viewer.  
- **¿Qué formatos de salida son compatibles?** HTML, JPG, PNG y PDF.  
- **¿Necesito una licencia para producción?** Se requiere una licencia comercial; hay una prueba gratuita disponible para pruebas.  
- **¿Qué versión de Java se requiere?** JDK 8 o superior.  
- **¿Maven es la única forma de agregar la biblioteca?** No, también puedes usar Gradle o incluir el JAR manualmente.  

## ¿Qué es “convertir IGS a PDF”?
Convertir IGS (un formato de archivo neutral para datos CAD 3‑D) a PDF significa transformar un modelo 3‑D complejo en un documento estático y ampliamente visualizable. Esto es útil para compartir diseños con partes interesadas que no disponen de herramientas CAD.

## ¿Por qué usar GroupDocs.Viewer para conversiones de IGS?
- **Renderizado CAD sin código** – la biblioteca se encarga del trabajo pesado de analizar el formato IGS.  
- **Múltiples opciones de salida** – una llamada a la API puede generar HTML, JPG, PNG o PDF.  
- **Multiplataforma** – funciona en cualquier SO que soporte Java.  
- **Enfocado en el rendimiento** – renderizado rápido incluso para ensamblajes grandes.  

## Requisitos previos
- **GroupDocs.Viewer for Java** ≥ 25.2  
- **JDK 8+** instalado y configurado en tu IDE (IntelliJ IDEA, Eclipse, NetBeans, etc.)  
- Conocimientos básicos de Maven (opcional pero recomendado)  

## Configuración de GroupDocs.Viewer para Java

### Dependencia Maven
Agrega el repositorio de GroupDocs y la dependencia Viewer a tu `pom.xml`:

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
GroupDocs.Viewer ofrece:
- **Prueba gratuita** – uso limitado, ideal para pruebas rápidas.  
- **Licencia temporal** – conjunto completo de funciones por un corto período de evaluación.  
- **Licencia comercial** – uso de producción sin restricciones.  

### Inicialización básica del Viewer
El fragmento a continuación muestra cómo crear una instancia de `Viewer` que apunta a tu archivo IGS:

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
La salida HTML te brinda una vista interactiva y amigable para el navegador del modelo 3‑D.

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

**Punto clave:** `HtmlViewOptions.forEmbeddedResources()` incrusta todos los recursos necesarios (CSS, imágenes) directamente en el archivo HTML, haciéndolo portátil.

## Renderizado de IGS a JPG

### ¿Cómo convertir IGS a JPG?
Las imágenes JPG son perfectas para miniaturas o vistas previas rápidas.

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

Puedes ajustar `JpgViewOptions` para controlar la resolución y la calidad de compresión.

## Renderizado de IGS a PNG

### ¿Cómo convertir IGS a PNG?
PNG admite transparencia, lo cual es útil para superponer el modelo sobre diferentes fondos.

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

Experimenta con `PngViewOptions` para obtener el mejor equilibrio entre el tamaño del archivo y la fidelidad visual.

## Renderizado de IGS a PDF

### ¿Cómo convertir IGS a PDF?
PDF es el formato preferido para compartir documentación de diseño detallada. Esta sección aborda directamente la palabra clave principal **convertir IGS a PDF**.

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

`PdfViewOptions` te permite controlar el diseño de página, la calidad de imagen y si se incrustan fuentes.

## Aplicaciones prácticas

- **Portales web** – incrusta modelos renderizados en HTML directamente en configuradores de productos.  
- **Recursos de marketing** – genera imágenes JPG/PNG de alta resolución para folletos.  
- **Documentación técnica** – incluye renderizados PDF de modelos CAD en manuales de usuario.  
- **Control de calidad** – automatiza la generación de miniaturas para grandes lotes de archivos IGS.  

## Problemas comunes y soluciones

| Problema | Solución |
|----------|----------|
| **Carpeta de salida no encontrada** | Verifica la ruta pasada a `Path outputDirectory` y asegura que el proceso Java tenga permisos de escritura. |
| **Páginas en blanco en PDF** | Asegúrate de que el archivo IGS no esté corrupto; intenta abrirlo primero en un visor CAD. |
| **Renderizado lento para ensamblajes grandes** | Incrementa el heap de JVM (`-Xmx2g` o más) y considera renderizar página por página usando `viewer.getPageCount()` si es necesario. |
| **Fuentes faltantes en PDF** | Usa `PdfViewOptions` para incrustar las fuentes requeridas o instala las fuentes faltantes en el servidor. |

## Preguntas frecuentes

**P: ¿Puedo convertir varios archivos IGS en una sola ejecución?**  
R: Sí. Recorre una lista de rutas de archivo e invoca el método `view` apropiado para cada uno.

**P: ¿Es posible personalizar el tamaño de página del PDF?**  
R: Por supuesto. `PdfViewOptions` ofrece `setPageSize(PageSize.A4)` y métodos similares.

**P: ¿Necesito una licencia separada para cada formato de salida?**  
R: No. Una única licencia de GroupDocs.Viewer cubre todos los formatos compatibles.

**P: ¿Qué tan grande puede ser un archivo IGS antes de que el rendimiento se degrade?**  
R: La biblioteca maneja archivos de hasta varios cientos de megabytes, pero puede que necesites asignar más memoria JVM para modelos muy grandes.

**P: ¿Puedo renderizar solo una vista u orientación específica?**  
R: GroupDocs.Viewer renderiza la vista predeterminada. Para orientaciones personalizadas, preprocesa el archivo IGS con una herramienta CAD antes de la conversión.

**Última actualización:** 2026-02-23  
**Probado con:** GroupDocs.Viewer 25.2 para Java  
**Autor:** GroupDocs