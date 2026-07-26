---
date: '2026-03-29'
description: Aprende cómo crear una vista HTML de archivos MPP usando GroupDocs Viewer
  en Java, renderizando documentos de proyecto por intervalos de tiempo con código
  paso a paso.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: Crear vista HTML de MPP con GroupDocs Viewer (Java)
type: docs
url: /es/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Cómo usar GroupDocs Viewer para renderizar documentos de proyecto por intervalos de tiempo en Java

En este tutorial aprenderá cómo **create html view mpp** con GroupDocs Viewer para Java, lo que le permite renderizar solo las partes de un archivo Microsoft Project que se encuentran dentro de un intervalo de tiempo específico. Recorreremos la configuración de Maven, la configuración del código y escenarios del mundo real para que pueda incrustar vistas de línea de tiempo precisas directamente en sus aplicaciones.

![Renderizar documentos de proyecto por intervalos de tiempo con GroupDocs.Viewer para Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## Respuestas rápidas
- **¿Qué hace la función?** Renderiza solo la porción de un archivo Microsoft Project que se encuentra entre una fecha de inicio y una fecha de fin.  
- **¿Qué formato de salida se utiliza?** HTML con recursos incrustados, perfecto para integración web.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para evaluación; se requiere una licencia completa para producción.  
- **¿Puedo cambiar el rango de fechas en tiempo de ejecución?** Sí—ajuste los valores `setStartDate` y `setEndDate` en las opciones de renderizado.  
- **¿Esto es compatible con todas las versiones de Java?** Funciona con Java 8+ siempre que use GroupDocs.Viewer 25.2 o posterior.  

## Cómo crear html view mpp para documentos de proyecto
GroupDocs Viewer puede convertir archivos Microsoft Project (`.mpp`, `.mpt`) en páginas HTML. Al configurar las fechas de inicio y fin en las opciones de renderizado, limita la salida al segmento de tiempo que le interesa, lo que reduce el tamaño del archivo y acelera la carga de las páginas.

## Qué significa “How to Use GroupDocs” en este contexto?
GroupDocs Viewer es una biblioteca Java que convierte más de 100 formatos de archivo a representaciones amigables para la web. Cuando **how to use GroupDocs** para archivos de proyecto, obtiene la capacidad de extraer, visualizar y compartir datos de programación sin requerir Microsoft Project en el lado del cliente.

## Por qué renderizar documentos de proyecto con intervalos de tiempo?
- **Análisis enfocado:** Muestra solo la fase que le interesa (p. ej., Q3 2024).  
- **Rendimiento:** Una salida HTML más pequeña significa cargas de página más rápidas.  
- **Integración:** Incruste vistas de línea de tiempo en paneles, portales de informes o herramientas PM personalizadas.  

## Requisitos previos
- **GroupDocs.Viewer for Java** versión 25.2 o superior.  
- Java Development Kit (JDK) 8 o superior.  
- Un IDE como IntelliJ IDEA o Eclipse.  
- Conocimientos básicos de Maven.  

## Configuración de GroupDocs.Viewer para Java

### Dependencia Maven
Agregue el repositorio y la dependencia a su `pom.xml`:

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
1. **Free Trial** – Descargue una versión de prueba desde [GroupDocs' download page](https://releases.groupdocs.com/viewer/java/).  
2. **Temporary License** – Obtenga una licencia temporal para pruebas extendidas a través de [this link](https://purchase.groupdocs.com/temporary-license/).  
3. **Purchase** – Para uso de producción sin restricciones, compre una licencia en [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

### Inicialización básica del Viewer
El siguiente fragmento muestra cómo crear una instancia `Viewer` que apunta a un archivo Microsoft Project (`.mpp`):

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
Cree una carpeta donde se guardarán las páginas HTML generadas:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*¿Por qué?* Mantener los archivos renderizados organizados facilita servirlos desde un servidor web o incrustarlos en una interfaz de usuario.

### 2. Inicializar el Viewer con su archivo de proyecto
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*¿Por qué?* Cargar el documento prepara el analizador interno y hace accesibles los metadatos específicos del proyecto.

### 3. Recuperar información de vista para archivos de proyecto
```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*¿Por qué?* `ProjectManagementViewInfo` le proporciona las fechas de inicio y fin del cronograma, que luego usará para limitar el alcance del renderizado.

### 4. Configurar opciones de renderizado HTML (Generar HTML desde Project)
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*¿Por qué?* Configurar `StartDate` y `EndDate` indica a GroupDocs que **generate html view mpp** datos solo dentro de esa ventana.

### 5. Ejecutar el proceso de renderizado
```java
viewer.view(viewOptions);
```

*¿Por qué?* Esta llamada produce una serie de páginas HTML autónomas que representan el segmento de tiempo seleccionado de su cronograma de proyecto.

## Errores comunes y solución de problemas
- **Rutas de archivo incorrectas** – Verifique que tanto el archivo fuente `.mpp` como el directorio de salida existan.  
- **Tipo de archivo no compatible** – Asegúrese de que el documento sea un formato de Project compatible (p. ej., `.mpp`, `.mpt`).  
- **Errores de licencia** – Una licencia de prueba puede imponer límites de renderizado; cambie a una licencia completa para uso sin restricciones.  

## Aplicaciones prácticas
1. **Análisis de línea de tiempo del proyecto** – Mostrar a los interesados solo la fase actual.  
2. **Informes automatizados** – Generar informes HTML con límites de tiempo para actualizaciones de estado semanales.  
3. **Integración con paneles** – Incrustar las páginas renderizadas en herramientas de BI o portales personalizados.  
4. **Archivado** – Guardar una captura web‑amigable del cronograma del proyecto para referencia futura.  

## Consejos de rendimiento
- Utilice la opción de *embedded resources* para mantener cada página HTML autónoma, reduciendo las solicitudes HTTP.  
- Para proyectos muy grandes, considere renderizar en fragmentos de fechas más pequeños para mantener bajo el uso de memoria.  
- Limpie los archivos temporales después de servirlos para evitar el exceso de espacio en disco.  

## Conclusión
Ahora sabe **how to use GroupDocs** Viewer para renderizar documentos de proyecto dentro de un intervalo de tiempo específico y **generate HTML from project** datos en Java. Esta capacidad simplifica las visualizaciones de líneas de tiempo, mejora la eficiencia de los informes e integra sin problemas con aplicaciones web modernas.

### Próximos pasos
- Explore características adicionales del Viewer como marcas de agua, protección con contraseña o estilos CSS personalizados.  
- Combine esta canalización de renderizado con una API REST para servir vistas de línea de tiempo bajo demanda.  

## Preguntas frecuentes

**Q: ¿Qué formatos de archivo admite GroupDocs.Viewer?**  
A: GroupDocs.Viewer admite una amplia gama de formatos, incluidos Microsoft Project (MPP), PDF, Word, Excel, PowerPoint y muchos más.

**Q: ¿Cómo comienzo con una prueba gratuita de GroupDocs.Viewer?**  
A: Puede descargar la versión de prueba desde [here](https://releases.groupdocs.com/viewer/java/).

**Q: ¿Puedo renderizar documentos sin incrustar recursos?**  
A: Sí, puede elegir una opción de vista HTML diferente que haga referencia a recursos externos en lugar de incrustarlos.

**Q: ¿Qué pasa si mi documento es demasiado grande para renderizar?**  
A: Considere dividir el documento en secciones más pequeñas o renderizar solo el rango de fechas requerido, como se muestra arriba.

**Q: ¿Cómo manejo los errores de renderizado?**  
A: Verifique todas las configuraciones, asegúrese de tener una licencia válida y consulte la documentación de GroupDocs para códigos de error detallados.

## Recursos
- **Documentación**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **Referencia API**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Descarga**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)
- **Compra**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Prueba gratuita**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)
- **Licencia temporal**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Soporte**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Última actualización:** 2026-03-29  
**Probado con:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs  

---