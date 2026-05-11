---
date: '2026-02-15'
description: Aprende cómo convertir PST a HTML y a otros formatos como JPG, PNG y
  PDF usando GroupDocs.Viewer para Java. Esta guía cubre todos los pasos y configuraciones
  necesarios.
keywords:
- convert PST/OST
- GroupDocs.Viewer for Java
- render documents
title: Convertir PST a HTML, JPG, PNG, PDF usando GroupDocs.Viewer para Java
type: docs
url: /es/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

.png; keep unchanged.

All other URLs none.

Now output.# Convertir PST a HTML, JPG, PNG, PDF usando GroupDocs.Viewer para Java

¿Estás buscando **convertir pst a html** u otros formatos como JPG, PNG o PDF? Con la potente biblioteca GroupDocs.Viewer para Java, esta tarea es sencilla y eficiente. En este tutorial aprenderás a renderizar archivos Outlook PST/OST a HTML apto para la web, archivos de imagen o un único PDF, facilitando la compartición y el archivado de tus correos electrónicos.

![Convertir PST/OST a HTML, JPG, PNG, PDF con GroupDocs.Viewer para Java](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**Lo que aprenderás**
- Cómo configurar GroupDocs.Viewer para Java en un proyecto Maven.  
- Instrucciones paso a paso para **java convert pst** archivos a HTML, JPG, PNG y PDF.  
- Consejos de configuración para un rendimiento óptimo y errores comunes.

## Respuestas rápidas
- **¿Qué biblioteca maneja la conversión de PST?** GroupDocs.Viewer para Java.  
- **¿Puedo convertir PST a PDF directamente?** Sí, usando `PdfViewOptions`.  
- **¿Se requiere una licencia para producción?** Se necesita una licencia válida de GroupDocs.  
- **¿Qué versión de Java es compatible?** JDK 8 o superior.  
- **¿Necesito extraer los archivos adjuntos manualmente?** No, el visor los renderiza automáticamente.

## Cómo convertir pst a html usando GroupDocs.Viewer para Java
A continuación encontrarás una visión general concisa del proceso de conversión antes de profundizar en los ejemplos de código detallados.

### ¿Por qué elegir GroupDocs.Viewer?
- Renderizado de **alta fidelidad** de los cuerpos de correo, archivos adjuntos y formato.  
- **Múltiples formatos de salida** (HTML, JPG, PNG, PDF) desde una única API.  
- **Sin dependencias externas** – todo se ejecuta dentro de tu aplicación Java.

## Requisitos previos

- **GroupDocs.Viewer para Java** – versión 25.2 o posterior.  
- **Java Development Kit (JDK)** – 8 o superior.  
- Maven para la gestión de dependencias.  
- Conocimientos básicos de Java y familiaridad con Maven.

## Configuración de GroupDocs.Viewer para Java

Agrega el repositorio de GroupDocs y la dependencia a tu `pom.xml`:

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
- **Prueba gratuita** – explora todas las funciones sin costo.  
- **Licencia temporal** – extiende el tiempo de evaluación si es necesario.  
- **Licencia completa** – requerida para implementaciones en producción.

### Inicialización básica

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

Las siguientes secciones te guiarán a través del renderizado de archivos PST/OST en cada formato soportado.

### Renderizado de documentos PST/OST a HTML

#### Paso 1: Configurar el directorio de salida

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### Paso 2: Configurar opciones de carga

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Paso 3: Inicializar Viewer y renderizar HTML

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

### Renderizado de documentos PST/OST a JPG

#### Paso 1: Configurar el directorio de salida

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

#### Paso 2: Configurar opciones de carga

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Paso 3: Inicializar Viewer y renderizar JPG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Renderizado de documentos PST/OST a PNG

#### Paso 1: Configurar el directorio de salida

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### Paso 2: Configurar opciones de carga

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Paso 3: Inicializar Viewer y renderizar PNG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### Renderizado de documentos PST/OST a PDF

#### Paso 1: Configurar el directorio de salida

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### Paso 2: Configurar opciones de carga

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### Paso 3: Inicializar Viewer y renderizar PDF

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## Aplicaciones prácticas

- **Archivado de correos:** Convierte grandes archivos PST en HTML o PDF buscables para cumplimiento.  
- **Sistemas de gestión documental:** Almacena los archivos convertidos en sistemas que solo aceptan PDF, PNG o JPG.  
- **Plataformas de colaboración:** Comparte correos convertidos como imágenes en Slack o Teams.  
- **Revisión legal:** Proporciona a los tribunales versiones PDF de la evidencia de correos.  
- **Estrategias de respaldo:** Mantén instantáneas ligeras en PNG o JPG de mensajes críticos.

## Consideraciones de rendimiento

- **Gestión de recursos:** Reutiliza instancias de `Viewer` al procesar varios archivos para reducir la sobrecarga.  
- **Ajuste de memoria:** Ajusta `loadOptions.setResourceLoadingTimeout` según la capacidad del servidor.  
- **Procesamiento asíncrono:** Desplaza la conversión a hilos en segundo plano para interfaces responsivas.  

## Preguntas frecuentes

**Q: ¿Cómo **convertir pst a pdf** con la misma base de código?**  
A: Usa `PdfViewOptions` como se muestra en la sección de renderizado PDF; el resto del código permanece idéntico.

**Q: ¿Puede GroupDocs.Viewer manejar archivos PST cifrados?**  
A: Sí, proporciona la contraseña mediante `LoadOptions.setPassword("yourPassword")` antes de renderizar.

**Q: ¿Cuál es la diferencia entre **java convert pst** a PNG vs JPG?**  
A: PNG conserva calidad sin pérdida, ideal para capturas de pantalla, mientras que JPG ofrece tamaños de archivo más pequeños para vistas previas de correos.

**Q: ¿Existe una forma de **how to convert pst** archivos en lote?**  
A: Envuelve la lógica de renderizado en un bucle que itere sobre un directorio de archivos PST; reutiliza la misma configuración de `Viewer` para cada archivo.

## Conclusión

Ahora tienes una guía completa y lista para producción para **convertir pst a html**, JPG, PNG y PDF usando GroupDocs.Viewer para Java. Siguiendo los pasos anteriores puedes integrar la conversión de correos en cualquier flujo de trabajo basado en Java, mejorar la accesibilidad y cumplir con los requisitos de cumplimiento.

---

**Última actualización:** 2026-02-15  
**Probado con:** GroupDocs.Viewer para Java 25.2  
**Autor:** GroupDocs