---
date: '2026-08-03'
description: Aprenda cómo convertir zip a html usando GroupDocs.Viewer Java, establecer
  elementos por página, incrustar recursos html y convertir archivos por lotes de
  manera eficiente.
keywords:
- convert zip to html
- how to batch convert
- embed resources html
- batch convert archives
- how to convert archives
lastmod: '2026-08-03'
og_description: Aprenda cómo convertir zip a html usando GroupDocs.Viewer Java, establecer
  elementos por página, incrustar recursos html y convertir archivos por lotes de
  manera eficiente. Siga el código paso a paso y los consejos de rendimiento.
og_image_alt: 'Guide: convert zip to html with GroupDocs.Viewer Java, showing pagination
  and embedded resources'
og_title: Convertir zip a html y establecer elementos por página con GroupDocs.Viewer
  Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-03'
  description: Learn how to convert zip to html using GroupDocs.Viewer Java, set items
    per page, embed resources html, and batch convert archives efficiently.
  headline: Convert zip to html and set items per page with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: GroupDocs.Viewer Java is a server‑side library that renders over 50 document
      and archive formats—including ZIP and RAR—into HTML, PDF, or image files without
      requiring external applications.
    question: What is GroupDocs.Viewer Java?
  - answer: Visit the [free trial link](https://releases.groupdocs.com/viewer/java/)
      to download and test.
    question: How can I obtain a free trial of GroupDocs.Viewer?
  - answer: Yes, the viewer supports PDFs, Word, Excel, PowerPoint, and 35+ additional
      formats.
    question: Can I convert other document types besides archives?
  - answer: Reduce the number of items per page, enable streaming, or process archives
      in smaller batches to improve speed.
    question: What should I do if rendering is slow?
  - answer: Reach out via the [support forum](https://forum.groupdocs.com/c/viewer/9).
    question: Where can I get help or support?
  type: FAQPage
tags:
- convert zip
- GroupDocs.Viewer
- Java archive conversion
- html rendering
- batch conversion
title: Convertir zip a html y establecer elementos por página con GroupDocs.Viewer
  Java
type: docs
url: /es/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# Convertir zip a html y establecer elementos por página con GroupDocs.Viewer Java

En muchas aplicaciones web necesitas mostrar el contenido de un archivo ZIP o RAR directamente en el navegador. Con GroupDocs.Viewer for Java puedes **convert zip to html** en un solo paso, controlar cuántas entradas del archivo aparecen en cada página, incrustar todas las imágenes y CSS de soporte, e incluso procesar por lotes decenas de archivos. Este tutorial te guía a través del flujo de trabajo completo, desde la configuración de Maven hasta la renderización multipágina, y explica por qué cada configuración es importante para el rendimiento y la usabilidad.

![Convert Archives to HTML with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Respuestas rápidas
- **¿Qué controla “set items per page”?** Determina cuántos archivos o carpetas de un archivo aparecen en cada página HTML generada.  
- **¿Puedo incrustar imágenes y CSS directamente en el HTML?** Sí – usa la opción `forEmbeddedResources` para incrustar recursos HTML.  
- **¿Es posible la conversión por lotes?** Absolutamente; puedes iterar sobre una colección de archivos y renderizar cada uno con la misma configuración.  
- **¿Necesito Maven para usar GroupDocs.Viewer?** Sí, agrega la dependencia Maven `groupdocs-viewer` como se muestra a continuación.  
- **¿Qué formatos de salida son compatibles?** HTML de una sola página y HTML multipágina están disponibles, y la biblioteca soporta más de 50 tipos de archivos de entrada.

## Qué es “set items per page” en GroupDocs.Viewer?
La configuración **set items per page** pertenece a las opciones de renderizado de archivos. Indica al visor cuántas entradas del archivo (archivos o carpetas) deben mostrarse en cada página HTML cuando generas un documento HTML multipágina. Ajustar este valor te ayuda a equilibrar el tamaño de la página y la velocidad de navegación, especialmente para archivos grandes.

## ¿Por qué incrustar recursos html?
Incrustar recursos (imágenes, CSS, fuentes) directamente dentro del archivo HTML crea un documento único y portátil que puede abrirse sin archivos externos. Esto es ideal para adjuntos de correo electrónico, visualización sin conexión o incrustar la salida en otras páginas web. Este enfoque también simplifica el despliegue porque no es necesario gestionar rutas de recursos externas.

## Requisitos previos

- **Bibliotecas requeridas:** Incluye GroupDocs.Viewer versión 25.2 o posterior.  
- **Entorno:** Java Development Kit (JDK) instalado y configurado.  
- **Conocimientos:** Java básico y gestión de dependencias Maven.  

## Configuración de Maven GroupDocs Viewer

Agrega el repositorio de GroupDocs y la dependencia del visor a tu `pom.xml`:

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
GroupDocs.Viewer ofrece un **enlace de prueba gratuita**, una licencia temporal o una opción de compra completa. Elige la que se ajuste al cronograma de tu proyecto.

### Inicialización básica
Después de la configuración de Maven, incorpora el visor en tu código:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Cómo renderizar archivos a html de una sola página
Viewer es la clase principal que carga un documento o archivo para renderizar.

Para generar un único archivo HTML que contenga todo el archivo, crea una instancia de `Viewer` para el archivo ZIP y usa `HtmlViewOptions.forEmbeddedResources()` para incrustar todas las imágenes, CSS y fuentes. Renderizar el archivo con estas opciones produce una página autónoma adecuada para correo electrónico o uso sin conexión.

### Paso 1: Definir directorio de salida
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Paso 2: Establecer nombre de archivo para la salida de una sola página
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Paso 3: Inicializar el visor
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Paso 4: Configurar opciones de renderizado (incrustar recursos html)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Paso 5: Renderizar como una sola página
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Cómo renderizar archivos a html multipágina y establecer elementos por página
`HtmlViewOptions` configura cómo el visor genera la salida HTML, incluyendo paginación e incrustación de recursos.

Para dividir un archivo en varias páginas, crea `HtmlViewOptions.forEmbeddedResources()` y establece el tamaño de página deseado con `options.setItemsPerPage(20)`. El visor generará archivos HTML separados, cada uno mostrando hasta el número especificado de entradas, lo que mejora la navegación para archivos grandes y garantiza una carga más rápida.

### Paso 1: Reutilizar el directorio de salida
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Paso 2: Definir formato de nombre de archivo para múltiples páginas
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Paso 3: Inicializar el visor nuevamente
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Paso 4: Configurar opciones multipágina (incrustar recursos html)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Paso 5: Establecer elementos por página (palabra clave principal en acción)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Aplicaciones prácticas

- **Sistemas de gestión documental:** Añade funcionalidad de vista previa de archivos sin instalar visores adicionales.  
- **Portales web:** Ofrece a los usuarios una forma rápida y sin descarga de explorar documentos agrupados.  
- **Herramientas de colaboración:** Permite a los equipos inspeccionar archivos compartidos directamente en el navegador.

## Consideraciones de rendimiento

- **Gestión de recursos:** Mantén bajo el uso de memoria procesando archivos en streams; el visor puede manejar archivos de hasta 500 MB sin cargar todo el archivo en memoria.  
- **Conversión por lotes de archivos:** Recorre una lista de archivos y llama a la misma lógica de renderizado para maximizar el rendimiento.  
- **Estrategia de caché:** Almacena el HTML renderizado en caché si el mismo archivo se accede con frecuencia, reduciendo el tiempo de procesamiento repetido hasta en un 70 %.

## Preguntas frecuentes

**Q: ¿Qué es GroupDocs.Viewer Java?**  
A: GroupDocs.Viewer Java es una biblioteca del lado del servidor que renderiza más de 50 formatos de documentos y archivos —incluidos ZIP y RAR— a HTML, PDF o archivos de imagen sin requerir aplicaciones externas.

**Q: ¿Cómo puedo obtener una prueba gratuita de GroupDocs.Viewer?**  
A: Visita el [enlace de prueba gratuita](https://releases.groupdocs.com/viewer/java/) para descargar y probar.

**Q: ¿Puedo convertir otros tipos de documentos además de archivos?**  
A: Sí, el visor soporta PDFs, Word, Excel, PowerPoint y más de 35 formatos adicionales.

**Q: ¿Qué debo hacer si el renderizado es lento?**  
A: Reduce el número de elementos por página, habilita el streaming o procesa los archivos en lotes más pequeños para mejorar la velocidad.

**Q: ¿Dónde puedo obtener ayuda o soporte?**  
A: Contacta a través del [foro de soporte](https://forum.groupdocs.com/c/viewer/9).

**Q: ¿Es posible incrustar CSS e imágenes directamente en el HTML?**  
A: Absolutamente—usa `HtmlViewOptions.forEmbeddedResources` como se muestra en los ejemplos.

**Q: ¿Cómo convierto por lotes una carpeta de archivos?**  
A: Itera sobre cada archivo con un bucle `for`, aplicando la misma configuración de `Viewer` y `HtmlViewOptions` en cada iteración.

## Recursos

- **Documentación:** Profundiza en la funcionalidad con la [documentación de GroupDocs](https://docs.groupdocs.com/viewer/java/).  
- **Referencia de API:** Explora la API completa en el [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Descarga:** Obtén los últimos binarios en la [página de descargas](https://releases.groupdocs.com/viewer/java/).  
- **Compra y licencias:** Revisa las opciones en la [página de compra](https://purchase.groupdocs.com/buy).  
- **Soporte y comunidad:** Únete a las discusiones en el [foro de GroupDocs](https://forum.groupdocs.com/c/viewer/9).

---

**Última actualización:** 2026-08-03  
**Probado con:** GroupDocs.Viewer 25.2  
**Autor:** GroupDocs

## Tutoriales relacionados

- [Cómo convertir zip a HTML y renderizar carpetas zip en Java con GroupDocs.Viewer](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [convertir zip a pdf con GroupDocs.Viewer Java - Nombres de archivo personalizados](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [Cómo convertir DOCX a HTML usando GroupDocs.Viewer para Java: Guía paso a paso](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)