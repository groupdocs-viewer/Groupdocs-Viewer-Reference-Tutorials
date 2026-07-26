---
date: '2026-03-29'
description: Aprende cómo rotar una página 90 grados en Java usando GroupDocs Viewer,
  incluyendo la configuración, el código y consejos de rendimiento.
keywords:
- rotate first page GroupDocs Viewer Java
- GroupDocs Viewer Java setup
- rotate pages in documents using Java
title: Rotar página 90 grados con GroupDocs Viewer para Java
type: docs
url: /es/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---

# Rotar página 90 grados con GroupDocs Viewer for Java

Cuando necesitas **rotar página 90 grados** en un documento—ya sea un PDF, un archivo Word o una hoja de cálculo—hacerlo programáticamente ahorra tiempo y elimina errores manuales. En esta guía avanzada recorreremos los pasos exactos para rotar la primera página de cualquier documento compatible usando **GroupDocs Viewer for Java**. Al final, tendrás un fragmento reutilizable que podrás incorporar en tus propios proyectos.  
También discutiremos por qué rotar páginas en Java es importante, escenarios comunes donde esta técnica destaca y cómo mantener la operación ligera.

![Rotar la primera página de un documento con GroupDocs.Viewer for Java](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## Respuestas rápidas
- **¿Qué significa “rotate page 90 degrees”?** Gira la página seleccionada en sentido horario un cuarto de vuelta.  
- **¿Qué biblioteca maneja la rotación?** GroupDocs Viewer for Java proporciona el método `rotatePage`.  
- **¿Puedo rotar páginas PDF con Java?** Sí—utiliza la misma llamada `rotatePage`; funciona para PDF, DOCX, XLSX y más.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia de pago para producción.  
- **¿La operación es intensiva en memoria?** No cuando cierras la instancia `Viewer` rápidamente; consulta los consejos de rendimiento a continuación.

## Qué es “rotate page 90 degrees”?
Rotar una página 90 grados reorienta la página de retrato a paisaje (o viceversa) sin alterar el contenido subyacente. Esto es especialmente útil para presentaciones, imprimir gráficos solo en paisaje, o corregir documentos escaneados que fueron capturados de lado.

## Por qué rotar páginas programáticamente con GroupDocs Viewer for Java?
GroupDocs Viewer abstrae las complejidades de manejar docenas de formatos de archivo. Te permite aplicar transformaciones a nivel de página—como la rotación—manteniendo el archivo original intacto. La API es fluida, segura para hilos y funciona en cualquier entorno Java 8+, lo que la convierte en una opción confiable para automatización de nivel empresarial.

## Requisitos previos

- **GroupDocs.Viewer for Java** (última versión)
- **JDK 8** o superior
- **Maven** (o Gradle) para la gestión de dependencias
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
- **Free trial** – descarga desde el sitio de GroupDocs.  
- **Temporary license** – solicita si necesitas un período de evaluación extendido.  
- **Full license** – compra para implementaciones en producción.

### Inicialización básica del Viewer
El siguiente código muestra la forma mínima de crear una instancia `Viewer`. Manténlo exactamente como se muestra:

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## Cómo rotar una página PDF con Java usando GroupDocs Viewer
Aunque la API funciona con muchos formatos, PDF es el caso de uso más común para la rotación de páginas. Se utiliza el mismo método `rotatePage`, por lo que solo necesitas apuntar el viewer a un archivo PDF y especificar el número de página.

## Implementación paso a paso: Rotar la primera página 90 grados

### 1. Importar los paquetes requeridos
Estas importaciones te dan acceso a las opciones de renderizado PDF y al enum de rotación.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. Definir ubicaciones de salida y crear el Viewer
Reemplaza las rutas de marcador de posición con tus directorios reales.

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
El método `rotatePage` recibe el número de página (basado en 1) y un valor del enum `Rotation`.

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. Renderizar el documento
Finalmente, llama a `view` para generar el PDF rotado.

```java
viewer.view(viewOptions);
```

#### Cómo funciona
- **PdfViewOptions** indica al Viewer que genere un archivo PDF.  
- **rotatePage(int, Rotation)** rota solo la página que especificas, dejando el resto sin cambios.  
- El método soporta `ON_90_DEGREE`, `ON_180_DEGREE` y `ON_270_DEGREE`.

## Problemas comunes y soluciones

| Síntoma | Causa probable | Solución |
|---------|----------------|----------|
| **FileNotFoundException** | Ruta incorrecta o carpeta faltante | Verifica que `YOUR_OUTPUT_DIRECTORY` y `YOUR_DOCUMENT_DIRECTORY` existan y sean legibles. |
| **Unsupported file format** | Intentar rotar un formato no soportado por Viewer | Revisa la página de [GroupDocs Viewer supported formats]. |
| **No rotation visible** | Usar el número de página incorrecto (basado en 0) | Recuerda que `rotatePage` usa indexación **basada en 1**. |
| **Out‑of‑memory errors on large docs** | Renderizar muchos archivos grandes en un solo hilo | Procesa los documentos secuencialmente o usa un pool de hilos con concurrencia limitada. |

## Aplicaciones prácticas

1. **Ajustes de presentación** – Convierte una diapositiva en retrato a paisaje al instante.  
2. **Corrección masiva de documentos** – Automatiza la corrección de PDFs escaneados que fueron capturados de lado.  
3. **Salida lista para imprimir** – Asegura que los gráficos en paisaje se impriman correctamente en papel orientado en retrato.

## Consejos de rendimiento

- **Cerrar recursos rápidamente** – El bloque `try‑with‑resources` elimina automáticamente el `Viewer`.  
- **Procesamiento por lotes** – Al manejar muchos archivos, reutiliza una única instancia `Viewer` por hilo para reducir la sobrecarga.  
- **Monitorear memoria** – Para documentos mayores de 100 MB, considera transmitir la salida a disco en lugar de mantenerla en memoria.

## Preguntas frecuentes

**Q: ¿Puedo rotar varias páginas a la vez?**  
A: Sí—llama a `rotatePage()` para cada número de página que necesites rotar.

**Q: ¿Hay una forma de deshacer la rotación después de renderizar?**  
A: No directamente. Necesitarías renderizar el documento nuevamente sin las opciones de rotación.

**Q: ¿Qué formatos de archivo soportan la rotación de página en GroupDocs Viewer?**  
A: DOCX, PDF, PPTX, XLSX y muchos otros formatos listados en la documentación oficial.

**Q: ¿Cómo puedo rotar páginas en un lote de documentos automáticamente?**  
A: Envuelve el código en un bucle que itere sobre una colección de rutas de archivo, aplicando la misma lógica `rotatePage` a cada una.

**Q: ¿Cuál es la mejor práctica para manejar errores durante la rotación?**  
A: Encierra el uso del Viewer en un bloque `try‑catch`, registra la excepción y, opcionalmente, continúa procesando el siguiente archivo.

## Recursos

- **Documentación**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **Referencia API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Descarga**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **Compra**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **Prueba gratuita**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **Licencia temporal**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **Soporte**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Última actualización:** 2026-03-29  
**Probado con:** GroupDocs Viewer 25.2 for Java  
**Autor:** GroupDocs