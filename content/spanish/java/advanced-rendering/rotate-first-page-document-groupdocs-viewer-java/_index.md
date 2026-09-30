---
date: '2026-09-30'
description: Aprende cómo rotar la página 90 grados en Java usando GroupDocs Viewer,
  incluyendo la configuración, el código y consejos de rendimiento.
keywords:
- rotate page 90 degrees
- how to rotate pdf
- GroupDocs Viewer Java rotation
- Java document rendering
- PDF page transformation
lastmod: '2026-09-30'
og_description: Rotar la página 90 grados en Java usando GroupDocs Viewer. Guía paso
  a paso, consejos de rendimiento y casos de uso reales para desarrolladores.
og_image_alt: Illustration of rotating the first page of a document using GroupDocs
  Viewer for Java
og_title: Rotar la página 90 grados con GroupDocs Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-30'
  description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  headline: Rotate page 90 degrees with GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  name: Rotate page 90 degrees with GroupDocs Viewer for Java
  steps:
  - name: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
    text: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
  - name: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
    text: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
  - name: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
    text: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
  type: HowTo
- questions:
  - answer: Yes—invoke `rotatePage()` for each page number you need to rotate, either
      in a loop or by chaining calls.
    question: Can I rotate multiple pages at once?
  - answer: Not directly. You would need to render the document again without the
      rotation options.
    question: Is there a way to undo the rotation after rendering?
  - answer: DOCX, PDF, PPTX, XLSX, and many other formats listed in the official documentation.
    question: Which file formats support page rotation in GroupDocs Viewer?
  - answer: Wrap the rotation logic in a loop that iterates over a collection of file
      paths, applying the same `rotatePage` configuration to each file.
    question: How can I rotate pages in a batch of documents automatically?
  - answer: Enclose the Viewer usage in a `try‑catch` block, log the exception details,
      and optionally continue processing the next file to avoid a single failure stopping
      the whole batch.
    question: What is the best practice for handling errors during rotation?
  type: FAQPage
tags:
- rotate page
- GroupDocs Viewer
- Java PDF processing
- document automation
title: Rotar la página 90 grados con GroupDocs Viewer for Java
type: docs
url: /es/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Rotar página 90 grados con GroupDocs Viewer for Java

Si necesitas **rotar página 90 grados** en un documento—ya sea un PDF, un archivo Word o una hoja de cálculo—hacerlo programáticamente en Java ahorra tiempo, elimina errores manuales y te permite incrustar la operación en pipelines automatizados. En esta guía avanzada aprenderás cómo rotar la primera página de cualquier documento compatible usando **GroupDocs Viewer for Java**, por qué esta capacidad es importante en proyectos del mundo real y cómo mantener el proceso liviano y eficiente en memoria.

![Rotar la primera página de un documento con GroupDocs.Viewer for Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Respuestas rápidas
- **¿Qué significa “rotar página 90 grados”?** Gira la página seleccionada en sentido horario un cuarto de vuelta.  
- **¿Qué biblioteca maneja la rotación?** GroupDocs Viewer for Java proporciona el método `rotatePage`.  
- **¿Puedo rotar páginas PDF con Java?** Sí—utiliza la misma llamada `rotatePage`; funciona para PDF, DOCX, XLSX y más.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia de pago para producción.  
- **¿La operación consume mucha memoria?** No cuando cierras la instancia `Viewer` rápidamente; consulta los consejos de rendimiento a continuación.

## ¿Qué es “rotar página 90 grados”?
Rotar una página 90 grados reorienta la página de retrato a paisaje (o viceversa) sin cambiar el contenido subyacente. Esto es útil para presentaciones, imprimir gráficos solo en paisaje o corregir documentos escaneados que fueron capturados de lado. La rotación se aplica en tiempo de renderizado, dejando el archivo original sin cambios.

## ¿Por qué rotar páginas programáticamente con GroupDocs Viewer for Java?
GroupDocs Viewer soporta **más de 50 formatos de entrada y salida**—incluidos PDF, DOCX, PPTX, XLSX y muchos tipos de imagen—para que puedas renderizar cualquier documento sin convertidores externos. La API es fluida, segura para hilos y se ejecuta en cualquier entorno Java 8+, lo que la convierte en una opción confiable para automatización de nivel empresarial que debe manejar docenas de tipos de archivo de forma consistente.

## Requisitos previos
- GroupDocs Viewer for Java (última versión)
- JDK 8 o superior
- Maven (o Gradle) para la gestión de dependencias
- Un IDE como IntelliJ IDEA o Eclipse
- Familiaridad básica con Java I/O

## Configuración de GroupDocs.Viewer para Java
Agrega el repositorio de GroupDocs y la dependencia a tu `pom.xml`. Este fragmento es idéntico al tutorial original:

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
- **Prueba gratuita** – descarga desde el sitio de GroupDocs.  
- **Licencia temporal** – solicita si necesitas un período de evaluación extendido.  
- **Licencia completa** – compra para implementaciones en producción.

### Inicialización básica del Viewer
La clase `Viewer` es el punto de entrada que carga un documento y expone métodos de renderizado y transformación. Mantén el código exactamente como se muestra:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Cómo rotar una página PDF en Java con GroupDocs Viewer
Carga el archivo objetivo con `Viewer`, especifica el número de página y llama a `rotatePage`. El método funciona para PDF, DOCX, PPTX, XLSX y cualquier otro formato soportado por la biblioteca. Después de la rotación, puedes renderizar el documento a un nuevo PDF o transmitirlo directamente al cliente, asegurando que el archivo original permanezca intacto.

## Implementación paso a paso: rotar la primera página 90 grados

### 1. Importar los paquetes requeridos
`PdfViewOptions` indica al Viewer que genere un archivo PDF, mientras que el enum `Rotation` define el ángulo. Ambas clases pertenecen al paquete `com.groupdocs.viewer.options`.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Definir ubicaciones de salida y crear el Viewer
Reemplaza las rutas de marcador de posición con tus directorios reales. El constructor `Viewer` acepta un objeto `File` que apunta al documento fuente.

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. Configurar opciones de vista PDF y aplicar la rotación
El método `rotatePage(int, Rotation)` recibe un índice de página **basado en 1** y un valor del enum `Rotation`. En este ejemplo usamos `Rotation.ON_90_DEGREE` para girar la primera página en sentido horario.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Renderizar el documento
Llamar a `view` con las opciones configuradas escribe el PDF rotado en la carpeta de salida.

```java
viewer.view(viewOptions);
```

#### Cómo funciona
- **PdfViewOptions** dirige al Viewer a generar un archivo PDF de salida.  
- **rotatePage(int, Rotation)** rota solo la página especificada, dejando todas las demás páginas sin cambios.  
- El método soporta tres constantes de rotación: `ON_90_DEGREE`, `ON_180_DEGREE` y `ON_270_DEGREE`.

## Problemas comunes y soluciones

| Síntoma | Causa probable | Solución |
|---------|----------------|----------|
| **FileNotFoundException** | Ruta incorrecta o carpeta faltante | Verifica que `YOUR_OUTPUT_DIRECTORY` y `YOUR_DOCUMENT_DIRECTORY` existan y sean legibles. |
| **Unsupported file format** | Intentando rotar un formato no soportado por Viewer | Revisa la página [GroupDocs Viewer supported formats]. |
| **No rotation visible** | Usando el número de página incorrecto (basado en 0) | Recuerda que `rotatePage` usa indexación **basada en 1**. |
| **Out‑of‑memory errors on large docs** | Renderizando muchos archivos grandes en un solo hilo | Procesa los documentos secuencialmente o usa un pool de hilos con concurrencia limitada. |

## Aplicaciones prácticas
1. **Ajustes de presentación** – Convierte una diapositiva en retrato a paisaje al instante para un mejor impacto visual.  
2. **Corrección masiva de documentos** – Automatiza la corrección de PDFs escaneados que fueron capturados de lado, ahorrando horas de trabajo manual.  
3. **Salida lista para imprimir** – Asegura que los gráficos en paisaje se impriman correctamente en papel orientado en retrato sin rotación manual en el controlador de la impresora.

## Consejos de rendimiento
- **Cerrar recursos rápidamente** – El bloque `try‑with‑resources` elimina automáticamente el `Viewer`, liberando memoria.  
- **Procesamiento por lotes** – Reutiliza una única instancia `Viewer` por hilo para reducir la sobrecarga de inicialización.  
- **Monitorear memoria** – Para documentos mayores de 100 MB, transmite la salida a disco en lugar de mantener todo el archivo en memoria; GroupDocs Viewer puede procesar archivos de 200 MB usando menos de 250 MB de RAM.

## Preguntas frecuentes

**P: ¿Puedo rotar varias páginas a la vez?**  
R: Sí—invoca `rotatePage()` para cada número de página que necesites rotar, ya sea en un bucle o encadenando llamadas.

**P: ¿Hay una forma de deshacer la rotación después de renderizar?**  
R: No directamente. Necesitarías renderizar el documento nuevamente sin las opciones de rotación.

**P: ¿Qué formatos de archivo soportan la rotación de página en GroupDocs Viewer?**  
R: DOCX, PDF, PPTX, XLSX y muchos otros formatos listados en la documentación oficial.

**P: ¿Cómo puedo rotar páginas en un lote de documentos automáticamente?**  
R: Envuelve la lógica de rotación en un bucle que itere sobre una colección de rutas de archivo, aplicando la misma configuración `rotatePage` a cada archivo.

**P: ¿Cuál es la mejor práctica para manejar errores durante la rotación?**  
R: Encierra el uso de Viewer en un bloque `try‑catch`, registra los detalles de la excepción y, opcionalmente, continúa procesando el siguiente archivo para evitar que una única falla detenga todo el lote.

## Recursos
- **Documentación**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **Referencia API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Descarga**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Compra**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Prueba gratuita**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Licencia temporal**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Soporte**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Última actualización:** 2026-09-30  
**Probado con:** GroupDocs Viewer 25.2 for Java  
**Autor:** GroupDocs

## Tutoriales relacionados
- [Cómo rotar páginas PDF específicas con GroupDocs.Viewer para Java](/viewer/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/)
- [Cargar documento desde URL en Java – Tutorial de GroupDocs.Viewer](/viewer/java/document-loading/)
- [Vistas de documentos en GroupDocs Viewer Java](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}