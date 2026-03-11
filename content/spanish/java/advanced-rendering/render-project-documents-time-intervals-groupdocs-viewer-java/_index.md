---
date: '2026-01-15'
description: Aprenda a usar GroupDocs Viewer para generar HTML a partir de documentos
  de proyecto dentro de intervalos de tiempo específicos. Esta guía cubre la configuración,
  el código y casos de uso del mundo real.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: Cómo usar GroupDocs Viewer para renderizar documentos de proyecto por intervalos
  de tiempo en Java
type: docs
url: /es/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Cómo usar GroupDocs Viewer para renderizar documentos de proyecto por intervalos de tiempo en Java

Si buscas **cómo usar GroupDocs** para renderizar cronogramas de proyecto en una ventana de tiempo enfocada, has llegado al lugar correcto. En este tutorial recorreremos todo el proceso—desde la configuración de Maven hasta la generación de HTML a partir de documentos de proyecto—para que puedas incrustar vistas de línea de tiempo precisas directamente en tus aplicaciones.

![Renderizar documentos de proyecto por intervalos de tiempo con GroupDocs.Viewer para Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## Respuestas rápidas
- **¿Qué hace la función?** Renderiza solo la porción de un archivo Microsoft Project que se encuentra entre una fecha de inicio y una fecha de fin.  
- **¿Qué formato de salida se utiliza?** HTML con recursos incrustados, perfecto para la integración web.  
- **¿Necesito una licencia?** Una prueba gratuita sirve para evaluación; se requiere una licencia completa para producción.  
- **¿Puedo cambiar el rango de fechas en tiempo de ejecución?** Sí—ajusta los valores `setStartDate` y `setEndDate` en las opciones de renderizado.  
- **¿Esto es compatible con todas las versiones de Java?** Funciona con Java 8+ siempre que uses GroupDocs.Viewer 25.2 o una versión más reciente.

## ¿Qué significa “Cómo usar GroupDocs” en este contexto?
GroupDocs Viewer es una biblioteca Java que convierte más de 100 formatos de archivo a representaciones amigables para la web. Cuando **cómo usar GroupDocs** para archivos de proyecto, obtienes la capacidad de extraer, visualizar y compartir datos de cronograma sin requerir Microsoft Project en el lado del cliente.

## ¿Por qué renderizar documentos de proyecto con intervalos de tiempo?
- **Análisis enfocado:** Muestra solo la fase que te interesa (p. ej., Q3 2024).  
- **Rendimiento:** Una salida HTML más pequeña significa cargas de página más rápidas.  
- **Integración:** Incrusta vistas de línea de tiempo en paneles, portales de informes o herramientas PM personalizadas.

## Requisitos previos

- **GroupDocs.Viewer for Java** versión 25.2 o superior.  
- Java Development Kit (JDK) 8 o posterior.  
- Un IDE como IntelliJ IDEA o Eclipse.  
- Conocimientos básicos de Maven.  

## Configuración de GroupDocs.Viewer para Java

### Dependencia Maven

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

### Pasos para obtener la licencia

1. **Prueba gratuita** – Descarga una versión de prueba desde la [página de descargas de GroupDocs](https://releases.groupdocs.com/viewer/java/).  
2. **Licencia temporal** – Obtén una licencia temporal para pruebas extendidas a través de [este enlace](https://purchase.groupdocs.com/temporary-license/).  
3. **Compra** – Para uso de producción sin restricciones, compra una licencia en la [Página de compra de GroupDocs](https://purchase.groupdocs.com/buy).

### Inicialización básica del Viewer

El siguiente fragmento muestra cómo crear una instancia de `Viewer` que apunta a un archivo Microsoft Project (`.mpp`):

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.mpp")) {
            // Your rendering code goes here
        }
    }
}
```

## Guía de implementación paso a paso

### 1. Definir el directorio de salida

Crea una carpeta donde se guardarán las páginas HTML generadas:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*¿Por qué?* Mantener los archivos renderizados organizados facilita servirlos desde un servidor web o incrustarlos en una interfaz de usuario.

### 2. Inicializar el Viewer con tu archivo de proyecto

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*¿Por qué?* Cargar el documento prepara el analizador interno y hace accesibles los metadatos específicos del proyecto.

### 3. Obtener información de vista para archivos de proyecto

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*¿Por qué?* `ProjectManagementViewInfo` te proporciona las fechas de inicio y fin del cronograma, que luego usarás para limitar el alcance del renderizado.

### 4. Configurar opciones de renderizado HTML (Generar HTML a partir del proyecto)

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*¿Por qué?* Configurar `StartDate` y `EndDate` indica a GroupDocs que **genere HTML a partir del proyecto** solo dentro de esa ventana.

### 5. Ejecutar el proceso de renderizado

```java
viewer.view(viewOptions);
```

*¿Por qué?* Esta llamada produce una serie de páginas HTML autónomas que representan el segmento de tiempo seleccionado de tu cronograma de proyecto.

## Problemas comunes y solución de problemas

- **Rutas de archivo incorrectas** – Verifica que tanto el archivo fuente `.mpp` como el directorio de salida existan.  
- **Tipo de archivo no compatible** – Asegúrate de que el documento sea un formato de Project compatible (p. ej., `.mpp`, `.mpt`).  
- **Errores de licencia** – Una licencia de prueba puede imponer límites de renderizado; cambia a una licencia completa para uso sin restricciones.  

## Aplicaciones prácticas

1. **Análisis de línea de tiempo del proyecto** – Muestra a los interesados solo la fase actual.  
2. **Informes automatizados** – Genera informes HTML con límite de tiempo para actualizaciones semanales de estado.  
3. **Integración con paneles** – Incrusta las páginas renderizadas en herramientas de BI o portales personalizados.  
4. **Archivado** – Guarda una instantánea web‑amigable del cronograma del proyecto para referencia futura.  

## Consejos de rendimiento

- Usa la opción de *recursos incrustados* para mantener cada página HTML autónoma, reduciendo solicitudes HTTP.  
- Para proyectos muy grandes, considera renderizar en fragmentos de fechas más pequeños para mantener bajo el uso de memoria.  
- Elimina los archivos temporales después de servirlos para evitar el aumento de espacio en disco.  

## Conclusión

Ahora sabes **cómo usar GroupDocs** Viewer para renderizar documentos de proyecto dentro de un intervalo de tiempo específico y **generar HTML a partir del proyecto** en Java. Esta capacidad simplifica las visualizaciones de líneas de tiempo, mejora la eficiencia de los informes y se integra sin problemas con aplicaciones web modernas.

### Próximos pasos
- Explora características adicionales del Viewer como marcas de agua, protección con contraseña o estilos CSS personalizados.  
- Combina este flujo de renderizado con una API REST para servir vistas de línea de tiempo bajo demanda.  

## Preguntas frecuentes

**Q: ¿Qué formatos de archivo admite GroupDocs.Viewer?**  
A: GroupDocs.Viewer admite una amplia gama de formatos, incluidos Microsoft Project (MPP), PDF, Word, Excel, PowerPoint y muchos más.

**Q: ¿Cómo empiezo con una prueba gratuita de GroupDocs.Viewer?**  
A: Puedes descargar la versión de prueba desde [aquí](https://releases.groupdocs.com/viewer/java/).

**Q: ¿Puedo renderizar documentos sin incrustar recursos?**  
A: Sí, puedes elegir una opción de vista HTML diferente que haga referencia a recursos externos en lugar de incrustarlos.

**Q: ¿Qué pasa si mi documento es demasiado grande para renderizar?**  
A: Considera dividir el documento en secciones más pequeñas o renderizar solo el rango de fechas requerido, como se muestra arriba.

**Q: ¿Cómo manejo los errores de renderizado?**  
A: Verifica todas las configuraciones, asegúrate de tener una licencia válida y consulta la documentación de GroupDocs para códigos de error detallados.

## Recursos
- **Documentación**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Referencia API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Descarga**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)
- **Compra**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Prueba gratuita**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)
- **Licencia temporal**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Soporte**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Última actualización:** 2026-01-15  
**Probado con:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs