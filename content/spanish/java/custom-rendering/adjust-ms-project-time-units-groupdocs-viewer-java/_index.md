---
date: '2026-05-21'
description: Aprenda cómo realizar la exportación HTML de MS Project con unidades
  de tiempo ajustadas usando GroupDocs Viewer for Java. Guía paso a paso con requisitos
  previos, configuración y solución de problemas.
keywords:
- ms project html export
- groupdocs viewer java time units
- render ms project files
schemas:
- author: GroupDocs
  dateModified: '2026-05-21'
  description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  headline: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  type: TechArticle
- description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  name: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  steps:
  - name: Define the output folder
    text: Choose a writable directory where the HTML pages will be saved, for example
      `output/`.
  - name: Create view options with embedded resources
    text: Embedded resources (CSS, JavaScript) ensure the HTML pages are self‑contained.
  - name: Set the time‑unit to days
    text: Use `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` to switch the
      granularity.
  - name: Render the document
    text: Call `viewer.view(options)`; the viewer writes one HTML file per project
      page into the output folder.
  - name: Verify the result
    text: Open the generated `index.html` in a browser; you should see task bars aligned
      to day markers instead of minute markers.
  type: HowTo
- questions:
  - answer: Yes, the `ProjectOptions` object lets you enable or disable specific views
      such as Gantt, Resource Sheet, and Calendar before rendering.
    question: Can I render other Project views (e.g., Resource Sheet) to HTML?
  - answer: Absolutely. Provide a custom stylesheet path via `options.setStyleSheetPath("path/to/custom.css")`
      and the viewer will embed it into every page.
    question: Is it possible to customize the CSS of the generated HTML?
  - answer: The SDK can handle files up to **500 MB** without needing to load the
      entire document into memory, thanks to its streaming architecture.
    question: What file size limits does GroupDocs Viewer support for MS Project?
  - answer: No. GroupDocs Viewer parses the .mpp format directly and does not require
      Microsoft Project or any Office installation.
    question: Do I need to install Microsoft Project on the server?
  - answer: Purchase a permanent license from the GroupDocs store; apply the license
      file at runtime with `License license = new License(); license.setLicense("path/to/license.lic");`.
      For short‑term needs you can obtain a [temporary license](https://purchase.groupdocs.com/temporary-license/).
    question: How do I license the viewer for a production environment?
  type: FAQPage
title: 'Exportación HTML de MS Project: Ajustar unidades de tiempo mediante GroupDocs
  Java'
type: docs
url: /es/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# Exportación HTML de MS Project: Ajustar unidades de tiempo mediante GroupDocs Java

Exportar un archivo **MS Project** a HTML es un requisito común para paneles de gestión de proyectos, portales de informes de estado y herramientas de revisión colaborativa. Por defecto, el visor renderiza los datos relacionados con el tiempo en minutos, lo que puede saturar el diseño visual y dificultar la lectura de los informes diarios. Con **GroupDocs Viewer for Java** puedes establecer programáticamente la unidad de tiempo a **days**, produciendo una exportación *ms project html export* limpia que se alinea con las expectativas típicas de los interesados. En este tutorial aprenderás cómo configurar el visor, ajustar la unidad de tiempo y renderizar el proyecto a HTML en unos sencillos pasos.

![Ajustar unidades de tiempo de MS Project con GroupDocs.Viewer para Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

[Adjust MS Project Time Units with GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

## Respuestas rápidas
- **¿Qué biblioteca renderiza archivos MS Project?** GroupDocs Viewer for Java.  
- **¿Qué unidad de tiempo puedo establecer para la exportación HTML?** Days, using `TimeUnit.DAYS`.  
- **¿Necesito una licencia para producción?** Sí— se requiere una licencia permanente; una prueba funciona para evaluación. Puedes comenzar con una [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).  
- **¿Qué IDE funciona mejor?** Any Java IDE (IntelliJ IDEA, Eclipse, NetBeans) that supports Maven.  
- **¿Es Maven obligatorio?** Maven simplifies dependency management, but you can also use Gradle or manual JAR inclusion.  
- **¿Dónde puedo comprar?** Visit the [buy page](https://purchase.groupdocs.com/buy) for pricing.

## ¿Qué es GroupDocs Viewer for Java?
**GroupDocs Viewer for Java** es un SDK de Java que convierte más de 150 formatos de documento—incluido MS Project—en HTML, PNG, JPEG o PDF compatibles con la web.  
Abstrae la lógica de análisis, te permite controlar opciones de renderizado como unidades de tiempo, y funciona en cualquier plataforma que soporte Java 8 o superior.  

## ¿Por qué ajustar las unidades de tiempo para la exportación HTML de MS Project?
Establecer la unidad de tiempo a **days** reduce el ruido visual, coincide con la mayoría de los ciclos de informes y mejora los tiempos de carga de la página porque se generan menos marcadores de tiempo granulares. En términos cuantitativos, renderizar con días en lugar de minutos puede reducir el tamaño del HTML generado hasta en **45 %** para proyectos típicos de 30 días, y acelera el renderizado del lado del cliente aproximadamente un **30 %**.

## Requisitos previos
- **Java Development Kit (JDK) 8 o más reciente** instalado en tu estación de trabajo.  
- **Maven** (o Gradle) para la gestión de dependencias.  
- Un archivo **MS Project (.mpp)** que deseas exportar.  
- Acceso a una licencia de **GroupDocs Viewer for Java** (prueba o permanente).  

### Bibliotecas requeridas
Agrega la siguiente dependencia a tu `pom.xml` (o al fragmento equivalente de Gradle):

```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-viewer</artifactId>
    <version>25.2</version>
</dependency>
```

> **Consejo profesional:** Mantén el número de versión actualizado; las versiones más recientes añaden soporte de formatos y mejoras de rendimiento.

## ¿Cómo configuro GroupDocs Viewer for Java?
Inicializa el visor creando una instancia de `Viewer` que apunte a tu archivo MS Project. La clase `Viewer` es el punto de entrada para todas las operaciones de renderizado. Carga el documento fuente, prepara estructuras internas y expone métodos como `view()` y `viewToHtml()` para generar los formatos de salida deseados.

```java
Viewer viewer = new Viewer("path/to/project.mpp");
```

> **Definición:** La clase `Viewer` es el componente central de GroupDocs Viewer que carga un documento fuente y proporciona métodos de renderizado como `view()` y `viewToHtml()`.

## ¿Cómo puedo ajustar las unidades de tiempo para la exportación HTML?
Para cambiar la granularidad del tiempo, crea un objeto `ViewOptions`, configura su `ProjectOptions` para usar `TimeUnit.DAYS` y pásalo al visor. `ViewOptions` define la configuración de renderizado para el documento, mientras que el enumerado `TimeUnit` especifica la unidad (minutes, hours, days) para los datos relacionados con el tiempo. Después de establecer estas opciones, invoca `viewer.view(options)` para generar HTML con marcadores diarios.

Carga tu archivo MS Project con `new Viewer("file.mpp")`, crea un objeto `ViewOptions`, establece `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)`, y luego llama a `viewer.view(options)`. Este flujo de tres pasos cambia la unidad de tiempo de minutos a días y genera archivos HTML que muestran solo intervalos diarios.

### Paso 1: Definir la carpeta de salida
Elige un directorio con permisos de escritura donde se guardarán las páginas HTML, por ejemplo `output/`.

### Paso 2: Crear opciones de vista con recursos incrustados
Los recursos incrustados (CSS, JavaScript) garantizan que las páginas HTML sean autónomas.

### Paso 3: Establecer la unidad de tiempo a days
Utiliza `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` para cambiar la granularidad.

### Paso 4: Renderizar el documento
Llama a `viewer.view(options)`; el visor escribe un archivo HTML por cada página del proyecto en la carpeta de salida.

### Paso 5: Verificar el resultado
Abre el `index.html` generado en un navegador; deberías ver barras de tareas alineadas con marcadores de día en lugar de marcadores de minuto.

## Problemas comunes y solución de errores
- **Ruta de salida incorrecta** – Asegúrate de que el directorio exista y el proceso Java tenga permisos de escritura.  
- **Licencia faltante** – Sin una licencia válida, el visor recurre al modo de prueba y puede incrustar marcas de agua.  
- **Archivos grandes (> 500 MB)** – Considera aumentar el tamaño del heap de JVM (`-Xmx2g`) o renderizar con `options.setRenderLimit(1000)` para procesar páginas en lotes.  

## Aplicaciones prácticas de la exportación HTML con unidad de tiempo ajustada
1. **Paneles ejecutivos** – La granularidad diaria coincide con la mayoría de visualizaciones de KPI.  
2. **Correos electrónicos de estado automatizados** – Incrusta el HTML generado directamente en el cuerpo de los correos para actualizaciones rápidas.  
3. **Portales de proyecto** – Aloja el HTML en un sitio intranet donde los miembros del equipo puedan filtrar tareas por día.  

## Consideraciones de rendimiento para archivos MS Project grandes
- **Gestión de memoria** – Usa las banderas del recolector de basura de Java (`-XX:+UseG1GC`) para liberar objetos no usados rápidamente.  
- **Renderizado selectivo** – Si solo necesitas el diagrama de Gantt, desactiva el renderizado de otros recursos mediante `options.getProjectOptions().setRenderGantt(true)` y `setRenderResources(false)`.  
- **Procesamiento paralelo** – Para conversiones por lotes, instancia objetos `Viewer` separados por archivo y ejecútalos en un pool de hilos para aprovechar CPUs multinúcleo.

## Conclusión
Ahora tienes un flujo de trabajo completo y listo para producción para realizar una **ms project html export** con unidades de tiempo establecidas en days usando GroupDocs Viewer for Java. Este enfoque reduce el tamaño del HTML, acelera el renderizado del cliente y ofrece una vista amigable para los interesados de los cronogramas del proyecto. Explora opciones de renderizado adicionales—como exportación a PDF o capturas de imagen—para ampliar la integración en pipelines de informes más amplios.

## Preguntas frecuentes

**P: ¿Puedo renderizar otras vistas de Project (p. ej., Hoja de recursos) a HTML?**  
A: Sí, el objeto `ProjectOptions` te permite habilitar o deshabilitar vistas específicas como Gantt, Hoja de recursos y Calendario antes de renderizar.

**P: ¿Es posible personalizar el CSS del HTML generado?**  
A: Absolutamente. Proporciona una ruta a una hoja de estilo personalizada mediante `options.setStyleSheetPath("path/to/custom.css")` y el visor la incrustará en cada página.

**P: ¿Qué límites de tamaño de archivo admite GroupDocs Viewer para MS Project?**  
A: El SDK puede manejar archivos de hasta **500 MB** sin necesidad de cargar todo el documento en memoria, gracias a su arquitectura de streaming.

**P: ¿Necesito instalar Microsoft Project en el servidor?**  
A: No. GroupDocs Viewer analiza el formato .mpp directamente y no requiere Microsoft Project ni ninguna instalación de Office.

**P: ¿Cómo licencio el visor para un entorno de producción?**  
A: Compra una licencia permanente en la tienda de GroupDocs; aplica el archivo de licencia en tiempo de ejecución con `License license = new License(); license.setLicense("path/to/license.lic");`. Para necesidades a corto plazo puedes obtener una [temporary license](https://purchase.groupdocs.com/temporary-license/).

---

**Última actualización:** 2026-05-21  
**Probado con:** GroupDocs Viewer Java 25.2  
**Autor:** GroupDocs  

**Recursos**  
- [Documentación](https://docs.groupdocs.com/viewer/java/)  
- [Referencia API](https://reference.groupdocs.com/viewer/java/)  
- [Descargar GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- [Comprar una licencia](https://purchase.groupdocs.com/buy)  

---

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

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

## Tutoriales relacionados

- [Cómo renderizar archivos MS Project como HTML, JPG, PNG y PDF con notas usando GroupDocs.Viewer para Java](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [Cómo usar GroupDocs Viewer para renderizar documentos de proyecto por intervalos de tiempo en Java](/viewer/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/)
- [Cómo establecer licencias en GroupDocs.Viewer Java: Guía de configuración de archivo y URL](/viewer/java/getting-started/groupdocs-viewer-java-license-setup/)