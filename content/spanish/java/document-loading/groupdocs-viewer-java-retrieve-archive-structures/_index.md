---
date: '2026-02-05'
description: Aprende cómo obtener viewinfo y recuperar estructuras de tipos de archivos
  Java Archive usando GroupDocs.Viewer. Esta guía cubre la configuración, ejemplos
  de código y casos de uso del mundo real.
keywords:
- GroupDocs.Viewer for Java
- retrieve archive structures
- Java document viewer
title: Cómo obtener ViewInfo y recuperar estructuras de archivo en Java
type: docs
url: /es/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Cómo obtener ViewInfo y recuperar estructuras de archivo en Java

Gestionar archivos de archivo de manera eficaz requiere una comprensión clara de su estructura. En este tutorial aprenderás **cómo obtener viewinfo** para cualquier archivo de archivo y verás cómo te ayuda a trabajar con el **tipo de archivo java archive**. Recorreremos la configuración de GroupDocs.Viewer, la extracción de información de vista y la lectura recursiva de jerarquías de carpetas para que puedas integrar la solución en proyectos reales.

![Estructuras de archivo con GroupDocs.Viewer para Java](/viewer/document-loading/archive-structures-java.png)

**Lo que aprenderás**
- Configurar y ajustar GroupDocs.Viewer para Java.  
- Métodos para **obtener viewinfo** de archivos de archivo.  
- Técnicas para leer y mostrar la estructura de carpetas de un archivo de archivo.  
- Aplicaciones prácticas y consideraciones de rendimiento al usar GroupDocs.Viewer en proyectos Java.

## Respuestas rápidas
- **¿Qué proporciona “viewinfo”?** Devuelve el tipo de archivo, el recuento de páginas y la lista de carpetas del archivo de archivo.  
- **¿Qué archivos de archivo son compatibles?** ZIP, RAR, TAR y otros formatos comunes.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para evaluación; se requiere una licencia comercial para producción.  
- **¿Puedo procesar archivos de archivo grandes?** Sí – usa streaming y un manejo adecuado de memoria como se muestra más adelante.  
- **¿Se requiere Maven?** Maven es la forma recomendada de gestionar la dependencia de GroupDocs.Viewer.

## ¿Qué es “cómo obtener viewinfo”?
`getViewInfo` es un método en la API de GroupDocs.Viewer que extrae metadatos sobre un documento o archivo de archivo sin renderizar todo el contenido. Para los archivos de archivo, revela el árbol interno de carpetas, permitiéndote decidir qué partes renderizar o procesar más adelante.

## ¿Por qué recuperar estructuras del tipo de archivo java archive?
Comprender el diseño interno de un **tipo de archivo java archive** (p. ej., ZIP, RAR) te permite:
- Ubicar rápidamente los archivos necesarios sin extraer todo.  
- Construir pipelines automatizados que procesen solo subcarpetas relevantes.  
- Integrar la navegación de archivos de archivo en sistemas de gestión de contenido o de ingestión de datos.

## Requisitos previos

- **Java Development Kit (JDK):** Versión 8 o superior.  
- **Maven:** Para la gestión de dependencias y compilaciones.  
- **Conocimientos básicos de Java:** Familiaridad con conceptos OOP ayuda, pero no es obligatorio.

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

- **Prueba gratuita:** Descarga una versión de prueba desde el sitio web de GroupDocs.  
- **Licencia temporal:** Solicita una clave temporal para evaluación a corto plazo.  
- **Licencia completa:** Compra una licencia comercial para uso ilimitado en producción.

Una vez que la biblioteca esté en tu classpath, puedes comenzar a codificar.

## Guía de implementación

### Cómo obtener ViewInfo para archivos de archivo

Esta sección muestra los pasos exactos para llamar a `getViewInfo` y leer la jerarquía de carpetas.

#### Inicializar el Viewer

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### Recuperar información de vista

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Mostrar la estructura de carpetas

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Lectura recursiva de carpetas

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

### Función 2: Recuperar la estructura de carpetas del archivo de archivo

Esta función se centra en imprimir la estructura de carpetas de un archivo de archivo. Es similar a la primera función pero enfatiza la exploración recursiva.

#### Configurar opciones de ViewInfo

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Exploración recursiva

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Aplicaciones prácticas

1. **Gestión de datos:** Organiza rápidamente grandes conjuntos de datos comprendiendo las estructuras de los archivos de archivo.  
2. **Procesamiento automatizado de archivos:** Procesa por lotes archivos archivados sin extraerlos completamente.  
3. **Integración CMS:** Mejora los sistemas de gestión de contenido con navegación de archivos de archivo en tiempo real.

## Consideraciones de rendimiento

- **Optimizar el uso de memoria:** Procesa carpetas un nivel a la vez y cierra la instancia de `Viewer` rápidamente.  
- **Mantente actualizado:** Usa la última versión de GroupDocs.Viewer y las versiones más recientes del JDK para obtener mejoras de rendimiento.

## Problemas comunes y soluciones

| Problema | Por qué ocurre | Solución |
|----------|----------------|----------|
| `NullPointerException` al leer carpetas | `viewInfo.getFolders()` devuelve null para directorios vacíos | Verifica null o lista vacía antes de iterar. |
| Procesamiento lento de archivos ZIP enormes | Todo el archivo de archivo se carga en memoria | Usa opciones de streaming disponibles en versiones más recientes de GroupDocs. |
| Licencia no encontrada | La ruta del archivo de licencia es incorrecta | Coloca el archivo de licencia en la raíz de la aplicación o establece `License.setLicense("path/to/license.json")`. |

## Preguntas frecuentes

**P: ¿Qué es GroupDocs.Viewer?**  
R: Es una potente biblioteca Java para renderizar documentos, incluidos archivos de archivo, a formatos como HTML, imagen y PDF.

**P: ¿Puedo usar GroupDocs.Viewer con otros lenguajes de programación?**  
R: Sí, GroupDocs ofrece SDKs para múltiples plataformas, pero este tutorial se centra en la implementación Java.

**P: ¿Cómo manejo archivos de archivo grandes?**  
R: Utiliza prácticas eficientes de gestión de memoria y considera dividir los archivos de archivo si es necesario.

**P: ¿Qué tipos de archivos de archivo admite GroupDocs.Viewer?**  
R: Admite una variedad de formatos, incluidos ZIP, RAR, TAR, entre otros.

**P: ¿Existe un límite de tamaño para los archivos de archivo que puedo procesar?**  
R: Los límites dependen de los recursos de tu sistema. Prueba en tu entorno objetivo para determinar límites prácticos.

**P: ¿“cómo obtener viewinfo” funciona con archivos de archivo protegidos con contraseña?**  
R: Sí, puedes proporcionar la contraseña mediante `ArchiveOptions.setPassword("yourPassword")` antes de llamar a `getViewInfo`.

## Conclusión

Al seguir esta guía ahora sabes **cómo obtener viewinfo** para cualquier archivo de archivo compatible y cómo recorrer su jerarquía de carpetas usando GroupDocs.Viewer para Java. Estas técnicas te permiten crear pipelines de procesamiento de datos más inteligentes, mejorar integraciones CMS y manejar grandes colecciones de archivos archivados con confianza. A continuación, explora la renderización de archivos individuales del archivo o su conversión a PDF/HTML usando otras funciones de Viewer.

---

**Última actualización:** 2026-02-05  
**Probado con:** GroupDocs.Viewer 25.2 para Java  
**Autor:** GroupDocs  

**Recursos**
- **Documentación:** [Documentación de GroupDocs Viewer Java](https://docs.groupdocs.com/viewer/java/)
- **Referencia de API:** [Referencia de API de GroupDocs para Java](https://reference.groupdocs.com/viewer/java/)
- **Descargar GroupDocs.Viewer:** [Página de descarga de GroupDocs](https://releases.groupdocs.com/viewer/java/)
- **Comprar licencia:** [Comprar GroupDocs](https://purchase.groupdocs.com/buy)
- **Prueba gratuita y licencia temporal:** [Prueba gratuita de GroupDocs](https://releases.groupdocs.com/viewer/java/) | [Licencia temporal](https://purchase.groupdocs.com/temporary-license/)