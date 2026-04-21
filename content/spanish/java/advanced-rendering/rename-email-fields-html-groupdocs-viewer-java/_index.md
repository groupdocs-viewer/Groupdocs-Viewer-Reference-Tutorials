---
date: '2026-03-24'
description: Aprende cómo convertir correos electrónicos a HTML y renombrar los campos
  de correo electrónico usando GroupDocs Viewer para Java. Esta guía muestra cómo
  renderizar el correo electrónico como HTML con encabezados personalizados.
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: Convertir correo electrónico a HTML y renombrar campos – GroupDocs Viewer Java
type: docs
url: /es/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# Convertir correo electrónico a HTML y renombrar campos – GroupDocs Viewer Java

Si necesitas **convertir correo electrónico a HTML** mientras le das a los encabezados del correo un aspecto personalizado, estás en el lugar correcto. En este tutorial recorreremos los pasos exactos para renombrar los campos del correo, **convertir correo electrónico a HTML**, y personalizar los encabezados del correo usando GroupDocs.Viewer para Java. Al final tendrás una representación HTML limpia con los nombres de encabezado que prefieras, facilitando la lectura e integración del resultado en tus aplicaciones.

![Renombrar campos de correo al convertir correos a HTML con GroupDocs.Viewer para Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### Lo que aprenderás
- Cómo usar GroupDocs.Viewer para Java para **convertir correo electrónico a HTML**.  
- Técnicas para **renombrar campos de correo** como “From”, “To”, “Sent” y “Subject”.  
- Mejores prácticas para configurar Maven y licencias.  
- Escenarios del mundo real donde **personalizar los encabezados del correo** aporta valor.

## Quick Answers
- **¿Qué significa “convertir correo electrónico a HTML”?** Significa renderizar un archivo de correo (MSG/EML) como un documento HTML listo para la web.  
- **¿Qué biblioteca maneja la conversión?** GroupDocs.Viewer para Java (v25.2+).  
- **¿Necesito una licencia?** Una prueba funciona para evaluación; se requiere una licencia completa para producción.  
- **¿Puedo cambiar cualquier nombre de encabezado?** Sí, cualquier encabezado estándar de correo puede ser reasignado mediante `fieldTextMap`.  
- **¿La salida es HTML o recursos incrustados?** Puedes elegir recursos incrustados para un único archivo autocontenido.

## Qué es “convertir correo electrónico a HTML” en el contexto de GroupDocs.Viewer?
Convertir correo electrónico a HTML significa tomar un archivo de correo sin procesar y producir una página HTML que muestra el cuerpo del mensaje junto con sus metadatos. Cuando también **renombras campos de correo**, las etiquetas predeterminadas (p. ej., “From”) se reemplazan con texto personalizado (p. ej., “Sender”), lo que ayuda a coincidir con la terminología corporativa o mejorar la consistencia de la UI.

## ¿Por qué convertir correo electrónico a HTML y renombrar campos de correo?
- **Marca consistente:** Alinear la salida con el lenguaje de tu organización.  
- **Mejor capacidad de búsqueda:** Los encabezados personalizados pueden indexarse de forma más eficaz en sistemas de archivado.  
- **Mejor integración UI:** Adaptar el fragmento HTML para que encaje sin problemas en portales web o paneles de soporte.

## Prerequisites

### Bibliotecas requeridas, versiones y dependencias
- **GroupDocs.Viewer para Java** – versión 25.2 o posterior.  
- **Java Development Kit (JDK)** – versión 8+.

### Requisitos de configuración del entorno
- **Maven** para la gestión de dependencias.  
- Un IDE como IntelliJ IDEA, Eclipse o VS Code.

### Prerrequisitos de conocimiento
Un conocimiento básico de Java y Maven te ayudará a seguir rápidamente.

## Setting Up GroupDocs.Viewer for Java

### Configuración de Maven
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

### Pasos para obtener la licencia
- **Prueba gratuita:** Descarga una prueba gratuita desde [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/).  
- **Licencia temporal:** Obtén una licencia temporal para explorar todas las funciones sin limitaciones en [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/).  
- **Compra:** Para uso continuo, considera comprar una licencia a través de [GroupDocs Purchase](https://purchase.groupdocs.com/buy).

### Inicialización y configuración básica
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.msg")) {
            // Perform operations here
        }
    }
}
```
Ajusta la ruta del archivo para que apunte a tu archivo `.msg`.

## Cómo convertir correo electrónico a HTML y renombrar campos – Paso a paso

### 1. Configurar la ruta del directorio de salida
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*Reemplaza `"YOUR_OUTPUT_DIRECTORY"` con la carpeta donde deseas guardar los archivos HTML.*

### 2. Definir el formato de ruta de archivo de página
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*`{0}` será reemplazado por el número de página durante la renderización.*

### 3. Crear un mapeo de campos de correo a nuevos nombres
```java
import com.groupdocs.viewer.options.Field;
import java.util.HashMap;
import java.util.Map;

Map<Field, String> fieldTextMap = new HashMap<>();
fieldTextMap.put(Field.FROM, "Sender");
fieldTextMap.put(Field.TO, "Receiver");
fieldTextMap.put(Field.SENT, "Date");
fieldTextMap.put(Field.SUBJECT, "Topic");
```
*Aquí cambiamos las etiquetas predeterminadas por personalizadas.*

### 4. Configurar opciones de vista HTML
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` agrupa CSS/JS dentro del HTML, mientras que `setFieldTextMap` aplica los nombres de encabezado personalizados.*

### 5. Renderizar el correo a HTML
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*Reemplaza `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` con la ruta real a tu archivo MSG.*

#### Consejos de solución de problemas
- Verifica que el directorio de salida sea escribible.  
- Asegúrate de que el archivo MSG de entrada exista y la ruta sea correcta.  
- Usa la misma versión de GroupDocs.Viewer (25.2) declarada en Maven.

## Aplicaciones prácticas
1. **Informes de correo personalizados:** Alinear los encabezados de correo con la terminología corporativa para informes más claros.  
2. **Sistemas de archivado de correo:** Mejorar la capacidad de búsqueda usando nombres de encabezado estandarizados.  
3. **Plataformas de soporte al cliente:** Presentar tickets con etiquetas de encabezado personalizadas para una mejor experiencia del agente.

## Consideraciones de rendimiento
- Descarta los objetos `Viewer` con try‑with‑resources para liberar memoria rápidamente.  
- Perfila lotes grandes y considera procesar correos en flujos paralelos si es necesario.

## Conclusión
Ahora sabes **cómo convertir correo electrónico a HTML** mientras **renombras campos de correo** y **personalizas los encabezados del correo** con GroupDocs.Viewer para Java. Esta técnica te brinda control total sobre la presentación de los metadatos del correo en salidas HTML.

### Próximos pasos
- Experimenta con mapeos de campos adicionales (p. ej., CC, BCC).  
- Explora otros formatos de renderizado como PDF o PNG.  
- Visita [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) para obtener información más profunda de la API.

## Preguntas frecuentes

**P: ¿Este enfoque funciona con otros formatos de correo como EML?**  
R: Sí, GroupDocs.Viewer soporta tanto archivos MSG como EML; la misma lógica de mapeo de campos se aplica.

**P: ¿Puedo generar el HTML sin recursos incrustados?**  
R: Puedes usar `HtmlViewOptions.forExternalResources(...)` si prefieres archivos CSS/JS separados.

**P: ¿Qué versión de GroupDocs.Viewer se probó?**  
R: El código se probó con GroupDocs.Viewer **25.2**.

**P: ¿Es posible cambiar la fuente o el estilo de los encabezados personalizados?**  
R: El estilo puede aplicarse mediante CSS después de la renderización, o puedes inyectar CSS personalizado usando `HtmlViewOptions.getResourcesPath()`.

**P: ¿Cómo puedo obtener programáticamente la ruta del archivo HTML generado?**  
R: La ruta del archivo sigue el patrón definido en `pageFilePathFormat`; puedes construirla usando `String.format` con el número de página.

## Recursos
- **Documentación:** Guías completas están disponibles en [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/).  
- **Referencia API:** Información detallada de la API se puede encontrar en [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/).  
- **Descargar GroupDocs.Viewer:** Accede a la última versión a través de la [Downloads Page](https://releases.groupdocs.com/viewer/java/).

---

**Última actualización:** 2026-03-24  
**Probado con:** GroupDocs.Viewer 25.2  
**Autor:** GroupDocs