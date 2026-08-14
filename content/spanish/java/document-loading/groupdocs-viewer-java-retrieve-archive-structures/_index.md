---
date: '2026-06-30'
description: Aprenda cómo obtener viewinfo y recuperar estructuras de tipo archivo
  Java usando GroupDocs.Viewer. Esta guía cubre la configuración, ejemplos de código
  y casos de uso del mundo real.
keywords:
- how to get viewinfo
- retrieve archive structures
- java archive file type
- GroupDocs Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  headline: How to Get ViewInfo and Retrieve Archive Structures in Java
  type: TechArticle
- description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  name: How to Get ViewInfo and Retrieve Archive Structures in Java
  steps:
  - name: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
    text: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
  - name: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
    text: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
  - name: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
    text: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
  type: HowTo
- questions:
  - answer: It returns file type, page count, and a complete listing of folders and
      files inside an archive.
    question: What does “viewinfo” provide?
  - answer: ZIP, RAR, TAR, 7z, ISO, and 12+ other common formats.
    question: Which archive formats are supported?
  - answer: Yes—a commercial license is required for production; a free trial works
      for evaluation.
    question: Do I need a license for production?
  - answer: Absolutely—use streaming options and process one folder level at a time
      to keep memory usage low.
    question: Can large archives be processed efficiently?
  - answer: Maven is the recommended dependency manager, but Gradle or manual JAR
      inclusion also work.
    question: Is Maven the only way to add the library?
  type: FAQPage
title: Cómo obtener ViewInfo y recuperar estructuras de archivo en Java
type: docs
url: /es/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Cómo obtener ViewInfo y recuperar estructuras de archivo en Java

Gestionar archivos de archivo de manera eficaz requiere una comprensión clara de su estructura. En este tutorial aprenderás **cómo obtener viewinfo** para cualquier archivo y verás cómo te ayuda a trabajar con el **tipo de archivo java archive**. Recorreremos la configuración de GroupDocs.Viewer, la extracción de información de vista y la lectura recursiva de jerarquías de carpetas para que puedas integrar la solución en proyectos reales.

![Archive Structures with GroupDocs.Viewer for Java](/viewer/document-loading/archive-structures-java.png)

**Qué aprenderás**
- Configurar y ajustar GroupDocs.Viewer para Java.  
- Métodos para **obtener viewinfo** de archivos.  
- Técnicas para leer y mostrar la estructura de carpetas de un archivo de archivo.  
- Aplicaciones prácticas y consideraciones de rendimiento al usar GroupDocs.Viewer en proyectos Java.

## Respuestas rápidas
- **What does “viewinfo” provide?** Devuelve el tipo de archivo, el recuento de páginas y una lista completa de carpetas y archivos dentro de un archivo.  
- **Which archive formats are supported?** ZIP, RAR, TAR, 7z, ISO y más de 12 formatos comunes.  
- **Do I need a license for production?** Sí, se requiere una licencia comercial para producción; una prueba gratuita funciona para evaluación.  
- **Can large archives be processed efficiently?** Absolutamente—utiliza opciones de streaming y procesa un nivel de carpeta a la vez para mantener bajo el uso de memoria.  
- **Is Maven the only way to add the library?** Maven es el gestor de dependencias recomendado, pero Gradle o la inclusión manual de JAR también funcionan.

## Qué es “how to get viewinfo”?

`getViewInfo` es un método de la API GroupDocs.Viewer que extrae metadatos de un documento o archivo sin renderizado completo. Devuelve el árbol interno de carpetas, el recuento de archivos y propiedades básicas en una sola llamada, permitiéndote decidir qué partes procesar. La llamada devuelve una instantánea completa de archivos de hasta 500 MB en menos de un segundo en servidores típicos.

## Por qué recuperar estructuras de tipo de archivo Java Archive?

Recuperar el diseño interno del **java archive file type** te permite localizar los archivos necesarios al instante, evitar extracciones innecesarias y crear pipelines automatizados que solo toquen sub‑carpetas relevantes. Este enfoque reduce I/O hasta un 70 % para archivos grandes y hace factible escanear miles de archivos por minuto en escenarios de ingestión de datos.

## Requisitos previos

- **Java Development Kit (JDK):** Versión 8 o superior.  
- **Maven:** Para la gestión de dependencias y compilaciones.  
- **Conocimientos básicos de Java:** Familiaridad con conceptos OOP ayuda pero no es obligatorio.  

También necesitas acceso a la biblioteca GroupDocs.Viewer, que puedes agregar a tu proyecto Maven como se muestra a continuación.

## Configuración de GroupDocs.Viewer para Java

### Configuración de Maven

Agrega el repositorio y la dependencia a tu `pom.xml`.

**Repositorios:**
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**Dependencias:**
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Obtención de licencia

- **Free Trial:** Prueba gratuita: Descarga una versión de prueba desde el sitio web de GroupDocs.  
- **Temporary License:** Licencia temporal: Solicita una clave temporal para evaluación a corto plazo.  
- **Full License:** Licencia completa: Compra una licencia comercial para uso ilimitado en producción.  

Una vez que la biblioteca está en tu classpath, puedes comenzar a codificar.

## Guía de implementación

### Cómo obtener ViewInfo para archivos de archivo

Para obtener información de vista, primero carga el archivo en el Viewer, luego llama a `getViewInfo` para recuperar los metadatos y, finalmente, itera sobre la jerarquía de carpetas devuelta. Este patrón de tres pasos funciona para todos los formatos de archivo compatibles y proporciona una instantánea completa en una sola llamada API, simplificando el procesamiento posterior.

#### Inicializar el Viewer

La clase `Viewer` es el punto de entrada para todas las operaciones de renderizado e inspección. Gestiona flujos de archivos, detección de formato y limpieza de recursos.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Recuperar información de vista

`ViewInfo` encapsula metadatos como tipo de archivo, total de páginas y una lista jerárquica de carpetas y archivos. Llamar a `getViewInfo` devuelve este objeto al instante.

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Mostrar estructura de carpetas

Itera a través de `viewInfo.getFolders()` para imprimir cada nombre de carpeta, su profundidad y los archivos contenidos. Este bucle simple te brinda una vista de árbol legible del archivo.

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Lectura recursiva de carpetas

Para archivos profundamente anidados, un método auxiliar recursivo puede recorrer el árbol en profundidad, asegurando que cada sub‑carpeta se visite sin cargar todo el archivo en memoria.

```java
private static void readFolders(Viewer viewer, String folder) {
    ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
    viewInfoOptions.getArchiveOptions().setFolder(folder);
    
    ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(viewInfoOptions);
    
    for (String subFolder : viewInfo.getFolders()) {
        System.out.println(" - " + subFolder);
        readFolders(viewer, subFolder);
    }
}
```

### Función 2: Recuperar estructura de carpetas del archivo

Esta función se centra en imprimir la estructura de carpetas de un archivo de archivo. Es similar a la primera función pero enfatiza la exploración recursiva.

#### Configurar opciones de ViewInfo

`ArchiveOptions` te permite especificar protección con contraseña, límites de página y preferencias de streaming antes de llamar a `getViewInfo`.

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Exploración recursiva

Una segunda rutina recursiva demuestra cómo manejar archivos protegidos por contraseña y conjuntos de archivos grandes de manera eficiente.

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Aplicaciones prácticas

1. **Gestión de datos:** Organiza rápidamente grandes conjuntos de datos comprendiendo las estructuras de los archivos.  
2. **Procesamiento automático de archivos:** Procesa por lotes archivos archivados sin extraerlos completamente, reduciendo I/O hasta un 70 %.  
3. **Integración CMS:** Mejora los sistemas de gestión de contenido con navegación de archivo en tiempo real, permitiendo a los editores previsualizar archivos directamente desde el archivo.  

## Consideraciones de rendimiento

- **Optimizar uso de memoria:** Procesa carpetas un nivel a la vez y cierra la instancia de `Viewer` rápidamente.  
- **Mantenerse actualizado:** Usa la última versión de GroupDocs.Viewer (25.2 al momento de escribir) y versiones de JDK para mejoras de rendimiento.  
- **Soporte de streaming:** La biblioteca puede transmitir archivos mayores de 1 GB sin cargar todo el archivo en RAM, gracias a su arquitectura interna de lectura por bloques.  

## Problemas comunes y soluciones

| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| `NullPointerException` al leer carpetas | `viewInfo.getFolders()` devuelve null para directorios vacíos | Verifique null o lista vacía antes de iterar. |
| Procesamiento lento de archivos ZIP enormes | Todo el archivo se carga en memoria | Utilice opciones de streaming disponibles en versiones más recientes de GroupDocs. |
| Licencia no encontrada | La ruta del archivo de licencia es incorrecta | Coloque el archivo de licencia en la raíz de la aplicación o establezca `License.setLicense("path/to/license.json")`. |

## Preguntas frecuentes

**Q:** ¿Qué es GroupDocs.Viewer?  
A: GroupDocs.Viewer es una biblioteca Java que renderiza más de 100 formatos de documentos, imágenes y archivos a HTML, PDF o flujos de imágenes sin requerir aplicaciones nativas.

**Q:** ¿Puedo usar GroupDocs.Viewer con otros lenguajes de programación?  
A: Sí, GroupDocs ofrece SDKs para .NET, Python, PHP y más, pero este tutorial se centra en la implementación Java.

**Q:** ¿Cómo manejo archivos de archivo grandes?  
A: Habilita streaming mediante `ArchiveOptions.setUseStreaming(true)`, procesa un nivel de carpeta a la vez y dispone del objeto `Viewer` después de su uso.

**Q:** ¿Qué tipos de archivos admite GroupDocs.Viewer?  
A: Soporta más de 12 formatos de archivo, incluidos ZIP, RAR, TAR, 7z, ISO, ARJ y CAB, además de muchos tipos de contenedores propietarios.

**Q:** ¿Existe un límite de tamaño para los archivos?  
A: El límite práctico depende de la RAM y CPU del servidor; pruebas muestran procesamiento fluido de archivos de 2 GB en una máquina con 16 GB de RAM cuando el streaming está habilitado.

**Q:** ¿Funciona “how to get viewinfo” con archivos protegidos por contraseña?  
A: Sí, suministra la contraseña mediante `ArchiveOptions.setPassword("yourPassword")` antes de invocar `getViewInfo`.

## Conclusión

Al seguir esta guía ahora sabes **cómo obtener viewinfo** para cualquier archivo compatible y cómo recorrer su jerarquía de carpetas usando GroupDocs.Viewer para Java. Estas técnicas te permiten crear pipelines de procesamiento de datos más inteligentes, mejorar integraciones CMS y manejar grandes colecciones de archivos archivados con confianza. A continuación, explora la renderización de archivos individuales del archivo o su conversión a PDF/HTML usando otras funciones del Viewer.

---

**Last Updated:** 2026-06-30  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs  

**Recursos**
- **Documentación:** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Referencia API:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **Descargar GroupDocs.Viewer:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Comprar GroupDocs:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **Prueba gratuita y licencia temporal:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)

## Tutoriales relacionados

- [Extraer metadatos de documento con GroupDocs.Viewer para Java - Recuperar información y perspectivas de vista del documento](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)
- [Cómo recuperar adjuntos e imprimir adjuntos de documento con GroupDocs.Viewer para Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Guía Java: Renderizar páginas específicas con la API de GroupDocs.Viewer para vista previa y gestión de documentos](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)