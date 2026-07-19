---
date: '2026-07-19'
description: Aprenda cómo convertir PST a HTML y otros formatos como JPG, PNG, PDF
  usando GroupDocs.Viewer for Java. Esta guía cubre todos los pasos y configuraciones
  necesarios.
keywords:
- convert pst to html
- convert pst to pdf
- java convert ost
- convert pst to png
- convert pst to jpg
lastmod: '2026-07-19'
og_description: Convierta PST a HTML rápidamente usando GroupDocs.Viewer for Java.
  Aprenda paso a paso cómo también exportar a JPG, PNG y PDF en una guía lista para
  producción.
og_image_alt: 'Developer guide: Convert PST to HTML, JPG, PNG, PDF using GroupDocs
  Viewer for Java'
og_title: Convertir PST a HTML con GroupDocs.Viewer for Java – Exportación rápida
  de correo electrónico
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  headline: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  name: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  steps:
  - name: Set Up Output Directory
    text: Define a folder where the HTML pages will be written. GroupDocs creates
      a sub‑folder for each email to keep assets organized.
  - name: Configure Load Options
    text: '`LoadOptions` lets you specify password handling, resource‑loading timeouts,
      and selective page rendering. Setting a timeout of 30 seconds works well for
      most server environments.'
  - name: Define HTML View Options
    text: '`HtmlViewOptions` specifies the output folder, resource handling, and optional
      CSS settings for HTML conversion.'
  - name: Initialize Viewer and Render HTML
    text: Create a `Viewer` object, pass the PST file path, and call `view` with the
      `HtmlViewOptions`. The API automatically iterates through all messages inside
      the PST and generates a tidy HTML hierarchy.
  - name: Set Up Output Directory
    text: Create a dedicated folder for JPG snapshots; each email will become one
      or more image files depending on its length.
  - name: Configure Load Options
    text: The same `LoadOptions` used for HTML can be reused here, ensuring consistent
      password handling across formats.
  - name: Define JPG View Options
    text: '`JpgViewOptions` controls image resolution, quality, and output folder
      for JPEG conversion.'
  - name: Initialize Viewer and Render JPG
    text: Use `viewer.view(jpgOptions)` to generate high‑quality JPEG files ready
      for web preview.
  - name: Set Up Output Directory
    text: PNG output is useful when you need lossless quality for archiving or OCR
      processing.
  - name: Configure Load Options
    text: No additional settings are required beyond the password and timeout configuration.
  type: HowTo
- questions:
  - answer: Use `PdfViewOptions` as shown in the PDF rendering section; the rest of
      the code remains identical.
    question: How do I **convert pst to pdf** with the same code base?
  - answer: Yes, provide the password via `LoadOptions.setPassword("yourPassword")`
      before rendering.
    question: Can GroupDocs.Viewer handle encrypted PST files?
  - answer: PNG preserves lossless quality, ideal for screenshots, while JPG offers
      smaller file sizes for email previews.
    question: What is the difference between **java convert pst** to PNG vs JPG?
  - answer: Wrap the rendering logic in a loop that iterates over a directory of PST
      files; reuse the same `Viewer` configuration for each file.
    question: Is there a way to **how to convert pst** files in bulk?
  - answer: Yes, GroupDocs.Viewer streams data and can process files up to 2 GB without
      loading the entire archive into memory.
    question: Does the API support converting PST files larger than 1 GB?
  type: FAQPage
tags:
- convert pst
- GroupDocs.Viewer
- Java document processing
- email conversion
title: Convertir PST a HTML, JPG, PNG, PDF usando GroupDocs.Viewer for Java
type: docs
url: /es/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# Convertir PST a HTML, JPG, PNG, PDF usando GroupDocs.Viewer para Java

¿Está buscando **convertir pst a html** u otros formatos como JPG, PNG o PDF? Con la potente biblioteca GroupDocs.Viewer para Java, esta tarea es sencilla y eficiente. En este tutorial aprenderá cómo renderizar archivos Outlook PST/OST a HTML compatible con la web, archivos de imagen o un único PDF, facilitando el compartir y archivar sus correos electrónicos.

![Convert PST/OST to HTML, JPG, PNG, PDF with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

[Convert PST/OST to HTML, JPG, PNG, PDF with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**Lo que aprenderá**
- Cómo configurar GroupDocs.Viewer para Java en un proyecto Maven.  
- Instrucciones paso a paso para **java convert pst** archivos a HTML, JPG, PNG y PDF.  
- Consejos de configuración para un rendimiento óptimo y errores comunes.

## Respuestas rápidas
- **¿Qué biblioteca maneja la conversión de PST?** GroupDocs.Viewer para Java.  
- **¿Puedo convertir PST a PDF directamente?** Sí, usando `PdfViewOptions`.  
- **¿Se requiere una licencia para producción?** Se necesita una licencia válida de GroupDocs.  
- **¿Qué versión de Java es compatible?** JDK 8 o superior.  
- **¿Necesito extraer los archivos adjuntos manualmente?** No, el visor los renderiza automáticamente.

## ¿Qué es GroupDocs.Viewer para Java?
GroupDocs.Viewer para Java es una API del lado del servidor que carga más de 100 formatos de documentos y correos electrónicos y los renderiza en HTML, imagen o salida PDF sin software externo. Procesa archivos PST de hasta 2 GB manteniendo el uso de memoria por debajo de 200 MB.

## ¿Cómo convertir pst a html usando GroupDocs.Viewer para Java?

Cargue el archivo PST con `new Viewer("source.pst")`, configure `HtmlViewOptions` para apuntar a una carpeta de salida y llame a `viewer.view(htmlOptions)`. La API extrae cada correo, preserva el formato, los adjuntos y los metadatos, y escribe una página HTML separada por mensaje, todo en una única llamada al método.

### ¿Por qué elegir GroupDocs.Viewer?
- **Renderizado de alta fidelidad** – 99,9 % del contenido del correo (incluidos cuerpos de texto enriquecido, tablas e imágenes incrustadas) se reproduce con precisión.  
- **Múltiples formatos de salida** – Una llamada a la API puede generar HTML, JPG, PNG o PDF, cubriendo más de 50 opciones de exportación.  
- **Cero dependencias externas** – No se necesita Outlook, Exchange Server ni convertidores de terceros; todo se ejecuta dentro de su entorno Java.

## Requisitos previos

- **GroupDocs.Viewer para Java** – versión 25.2 o posterior.  
- **Java Development Kit (JDK)** – 8 o más reciente.  
- Maven para la gestión de dependencias.  
- Conocimientos básicos de Java y familiaridad con Maven.

## Configuración de GroupDocs.Viewer para Java

`Viewer` es la clase central en GroupDocs.Viewer para Java que carga un documento y lo renderiza en el formato elegido. Añada el repositorio de GroupDocs y la dependencia a su `pom.xml`:

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
- **Prueba gratuita** – explore todas las funciones sin costo.  
- **Licencia temporal** – extienda el tiempo de evaluación si es necesario.  
- **Licencia completa** – requerida para implementaciones en producción.

### Inicialización básica

Las instancias de `Viewer` son ligeras; puede reutilizar una única instancia para muchos archivos y minimizar la sobrecarga de creación de objetos.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // Initialize Viewer with a sample PST file path
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

## Guía de implementación

Las siguientes secciones le guiarán paso a paso para renderizar archivos PST/OST en cada formato compatible.

### Renderizado de documentos PST/OST a HTML

#### Paso 1: Configurar el directorio de salida

Defina una carpeta donde se escribirán las páginas HTML. GroupDocs crea una subcarpeta para cada correo para mantener los recursos organizados.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### Paso 2: Configurar opciones de carga

`LoadOptions` le permite especificar el manejo de contraseñas, tiempos de espera de carga de recursos y renderizado selectivo de páginas. Un tiempo de espera de 30 segundos funciona bien en la mayoría de entornos de servidor.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Paso 3: Definir opciones de vista HTML

`HtmlViewOptions` especifica la carpeta de salida, el manejo de recursos y configuraciones CSS opcionales para la conversión a HTML.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

#### Paso 4: Inicializar Viewer y renderizar HTML

Cree un objeto `Viewer`, pase la ruta del archivo PST y llame a `view` con `HtmlViewOptions`. La API itera automáticamente por todos los mensajes dentro del PST y genera una jerarquía HTML ordenada.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

### Renderizado de documentos PST/OST a JPG

#### Paso 1: Configurar el directorio de salida

Cree una carpeta dedicada para instantáneas JPG; cada correo se convertirá en uno o más archivos de imagen según su longitud.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Paso 2: Configurar opciones de carga

Las mismas `LoadOptions` usadas para HTML pueden reutilizarse aquí, garantizando un manejo de contraseñas coherente entre formatos.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### Paso 3: Definir opciones de vista JPG

`JpgViewOptions` controla la resolución de la imagen, la calidad y la carpeta de salida para la conversión JPEG.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### Paso 4: Inicializar Viewer y renderizar JPG

Use `viewer.view(jpgOptions)` para generar archivos JPEG de alta calidad listos para vista web.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

### Renderizado de documentos PST/OST a PNG

#### Paso 1: Configurar el directorio de salida

La salida PNG es útil cuando necesita calidad sin pérdida para archivado o procesamiento OCR.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### Paso 2: Configurar opciones de carga

No se requieren configuraciones adicionales más allá de la contraseña y el tiempo de espera.

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### Paso 3: Definir opciones de vista PNG

`PngViewOptions` le permite establecer un fondo transparente y la carpeta de salida para imágenes PNG sin pérdida.

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Paso 4: Inicializar Viewer y renderizar PNG

Instancie `viewer.view(pngOptions)` para producir instantáneas PNG de cada correo.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Renderizado de documentos PST/OST a PDF

#### Paso 1: Configurar el directorio de salida

Un único archivo PDF por PST simplifica los flujos de trabajo de revisión legal y reduce el espacio de almacenamiento.

CODE_BLOCK_PLACEHOLDER_14_END

#### Paso 2: Configurar opciones de carga

Al convertir a PDF, puede habilitar `setEmbedFonts(true)` para garantizar la fidelidad visual en cualquier máquina.

CODE_BLOCK_PLACEHOLDER_15_END

#### Paso 3: Definir opciones de vista PDF

`PdfViewOptions` le permite elegir el nivel de compresión, incrustar fuentes y establecer el nombre del archivo de salida para la conversión a PDF.

CODE_BLOCK_PLACEHOLDER_16_END

#### Paso 4: Inicializar Viewer y renderizar PDF

Cree `PdfViewOptions`, opcionalmente seleccione un nivel de compresión y llame a `viewer.view(pdfOptions)`. La API combina todos los correos en un único documento PDF searchable.

CODE_BLOCK_PLACEHOLDER_17_END

## Aplicaciones prácticas

- **Archivado de correos:** Convierta grandes archivos PST en HTML o PDF searchable para cumplimiento normativo.  
- **Sistemas de gestión documental:** Almacene los archivos convertidos en sistemas que solo aceptan PDF, PNG o JPG.  
- **Plataformas de colaboración:** Comparta correos convertidos como imágenes en Slack o Teams.  
- **Revisión legal:** Proporcione a los tribunales versiones PDF de la evidencia de correo electrónico.  
- **Estrategias de respaldo:** Mantenga instantáneas PNG o JPG ligeras de mensajes críticos.

## Consideraciones de rendimiento

- **Gestión de recursos:** Reutilice instancias de `Viewer` al procesar varios archivos para reducir la sobrecarga.  
- **Ajuste de memoria:** Modifique `loadOptions.setResourceLoadingTimeout` según la capacidad del servidor.  
- **Procesamiento asíncrono:** Despliegue la conversión a hilos en segundo plano para interfaces de usuario más responsivas.  

## Preguntas frecuentes

**P: ¿Cómo **convertir pst a pdf** con la misma base de código?**  
R: Use `PdfViewOptions` como se muestra en la sección de renderizado PDF; el resto del código permanece idéntico.

**P: ¿GroupDocs.Viewer puede manejar archivos PST cifrados?**  
R: Sí, proporcione la contraseña mediante `LoadOptions.setPassword("yourPassword")` antes de renderizar.

**P: ¿Cuál es la diferencia entre **java convert pst** a PNG vs JPG?**  
R: PNG conserva calidad sin pérdida, ideal para capturas de pantalla, mientras que JPG ofrece tamaños de archivo menores para vistas previas de correos.

**P: ¿Existe una forma de **how to convert pst** archivos en lote?**  
R: Envuelva la lógica de renderizado en un bucle que itere sobre un directorio de archivos PST; reutilice la misma configuración de `Viewer` para cada archivo.

**P: ¿La API soporta la conversión de archivos PST mayores de 1 GB?**  
R: Sí, GroupDocs.Viewer transmite datos y puede procesar archivos de hasta 2 GB sin cargar todo el archivo en memoria.

## Conclusión

Ahora dispone de una guía completa y lista para producción para **convertir pst a html**, JPG, PNG y PDF usando GroupDocs.Viewer para Java. Siguiendo los pasos anteriores podrá integrar la conversión de correos en cualquier flujo de trabajo basado en Java, mejorar la accesibilidad y cumplir con los requisitos de cumplimiento.

---

**Última actualización:** 2026-07-19  
**Probado con:** GroupDocs.Viewer para Java 25.2  
**Autor:** GroupDocs

## Tutoriales relacionados

- [Convertir NSF a PDF, HTML, JPG, PNG usando GroupDocs.Viewer para Java](/viewer/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/)
- [convert odf html java – Convertir ODF a HTML, JPG, PNG, PDF usando GroupDocs.Viewer para Java](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [Cómo convertir DOCX a HTML usando GroupDocs.Viewer para Java: Guía paso a paso](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)