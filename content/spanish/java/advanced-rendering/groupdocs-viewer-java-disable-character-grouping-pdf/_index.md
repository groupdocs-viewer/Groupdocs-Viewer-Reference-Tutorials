---
date: '2025-12-21'
description: Aprende cómo desactivar la agrupación en PDFs con GroupDocs.Viewer para
  Java, usando java html de las opciones de renderizado de PDF para garantizar una
  representación precisa del texto.
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: Cómo desactivar la agrupación en PDFs con GroupDocs.Viewer para Java
type: docs
url: /es/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# Cómo desactivar la agrupación en PDFs con GroupDocs.Viewer para Java

Cuando necesitas **desactivar la agrupación** al renderizar PDFs, especialmente para scripts complejos o lenguas antiguas, la colocación precisa de los caracteres se vuelve esencial. La función predeterminada *Character Grouping* puede combinar caracteres incorrectamente, provocando una mala interpretación del contenido. En esta guía te mostraremos paso a paso cómo desactivar la agrupación usando GroupDocs.Viewer para Java, de modo que cada glifo permanezca exactamente donde corresponde.

![Técnicas de renderizado preciso con GroupDocs.Viewer para Java](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## Respuestas rápidas
- **¿Qué hace “desactivar la agrupación”?** Obliga al renderizador a tratar cada carácter como un elemento independiente, preservando el diseño exacto.  
- **¿Qué opción de API controla esto?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **¿Necesito una licencia?** Una prueba funciona para pruebas, pero se requiere una licencia completa para producción.  
- **¿Puedo generar HTML Java desde PDF al mismo tiempo?** Sí—usa `HtmlViewOptions` para crear salida HTML mientras desactivas la agrupación.  
- **¿Esta función está limitada a PDFs?** Principalmente es para PDFs, pero el visor soporta muchos otros formatos.

## Introducción

Al trabajar con documentos PDF, la precisión en el renderizado es crucial—especialmente al tratar con estructuras de texto complejas como jeroglíficos o lenguas que requieren una representación precisa de los caracteres. La función "Character Grouping" a menudo causa problemas al agrupar caracteres incorrectamente, lo que lleva a una mala interpretación del contenido del documento. Esto puede ser particularmente problemático para usuarios que necesitan una replicación exacta del diseño del texto de sus documentos.

### Requisitos previos

Antes de sumergirte en la implementación del código, asegúrate de cumplir con los siguientes requisitos:
- **Bibliotecas y dependencias**: Necesitarás GroupDocs.Viewer para Java versión 25.2 o posterior.
- **Configuración del entorno**: Asegúrate de tener instalado un Java Development Kit (JDK) y que tu IDE esté configurado para trabajar con proyectos Maven.
- **Conocimientos previos**: Comprensión básica de la programación en Java, especialmente el manejo de rutas de archivos y el uso de bibliotecas externas.

## Cómo desactivar la agrupación al renderizar PDF

### Configuración de GroupDocs.Viewer para Java

#### Instalación vía Maven

Primero, integra la biblioteca necesaria en tu proyecto. Añade la siguiente configuración en tu `pom.xml`:

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

#### Obtención de licencia

Para utilizar completamente GroupDocs.Viewer, considera adquirir una licencia:
- **Prueba gratuita**: Comienza con la prueba gratuita para probar las funciones.  
- **Licencia temporal**: Solicita una licencia temporal si necesitas más tiempo.  
- **Compra**: Para proyectos a largo plazo, se recomienda comprar una licencia.

#### Inicialización y configuración básica

Comienza configurando el entorno de tu proyecto:

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

// Initialize the GroupDocs Viewer
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getPdfOptions().setDisableCharsGrouping(true);

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

### Guía de implementación

#### Funcionalidad: Desactivar la agrupación de caracteres

##### Paso 1: Definir el directorio de salida

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**¿Por qué?** Esto asegura que tu salida esté organizada y sea fácilmente accesible.

##### Paso 2: Configurar el formato de la ruta de archivo

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**¿Por qué?** Ayuda a organizar sistemáticamente las páginas del documento PDF.

##### Paso 3: Inicializar opciones de vista HTML

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**¿Por qué?** Los recursos incrustados garantizan que todos los activos necesarios se incluyan dentro del archivo HTML de cada página.

##### Paso 4: Desactivar la agrupación de caracteres

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**¿Por qué?** Esto asegura que los caracteres se rendericen individualmente, preservando su diseño y significado previstos.

##### Paso 5: Renderizar el documento

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**¿Por qué?** Esto garantiza que todos los recursos se cierren adecuadamente, evitando fugas de memoria.

### Generar HTML Java desde PDF sin agrupación

La clase `HtmlViewOptions` te permite producir **java html from pdf** mientras mantienes cada carácter separado. Esto es especialmente útil cuando necesitas incrustar las páginas renderizadas en un portal web o una plataforma de e‑learning donde la colocación exacta de los glifos es importante.

### Consejos de solución de problemas

- Asegúrate de que la ruta de tu documento sea correcta para evitar `FileNotFoundException`.  
- Verifica que el directorio de salida tenga permisos de escritura.  
- Verifica doblemente que estés usando una versión compatible de GroupDocs.Viewer para Java.

## Aplicaciones prácticas

1. **Preservación de lenguas**: Ideal para renderizar documentos en lenguas como chino, japonés o escrituras antiguas donde la precisión de los caracteres es importante.  
2. **Documentos legales y financieros**: Garantiza la precisión en documentos que requieren una representación textual exacta para cumplimiento.  
3. **Recursos educativos**: Perfecto para libros de texto y trabajos académicos que incluyen diagramas complejos o anotaciones.

## Consideraciones de rendimiento

- **Optimizar el uso de recursos**: Asegúrate de que tu servidor tenga recursos adecuados para manejar archivos PDF grandes.  
- **Gestión de memoria en Java**: Usa estructuras de datos eficientes y prácticas de recolección de basura para gestionar la memoria de manera eficaz.  
- **Procesamiento por lotes**: Al renderizar varios documentos, procésalos en lotes para mejorar el rendimiento.

## Conclusión

Ahora has dominado **cómo desactivar la agrupación** durante el renderizado de PDFs con GroupDocs.Viewer para Java. Esta capacidad es crucial para aplicaciones que requieren una representación textual precisa. Para seguir explorando, intenta integrar esta función con otros sistemas de gestión de documentos o experimentar con opciones de renderizado adicionales.

Los siguientes pasos incluyen explorar funciones más avanzadas de GroupDocs.Viewer y afinar el rendimiento para implementaciones a gran escala.

## Preguntas frecuentes

**P:** *¿Por qué necesitaría desactivar la agrupación de caracteres?*  
**R:** Desactivar la agrupación evita que el renderizador combine caracteres que pertenecen a glifos distintos, lo cual es esencial para scripts donde el espaciado y el orden transmiten significado.

**P:** *¿La configuración `setDisableCharsGrouping` se aplica solo a la salida HTML?*  
**R:** No, afecta al motor de renderizado PDF subyacente, por lo que cualquier formato de salida (HTML, PNG, etc.) reflejará el cambio.

**P:** *¿Puedo combinar esta configuración con fuentes personalizadas?*  
**R:** Sí—simplemente carga tus fuentes personalizadas antes de inicializar `Viewer`, y la regla de agrupación seguirá aplicándose.

**P:** *¿Desactivar la agrupación afecta el rendimiento?*  
**R:** Un poco, porque el motor procesa cada carácter individualmente, pero el impacto es mínimo para la mayoría de los documentos.

**P:** *¿Hay una forma de alternar la agrupación por página?*  
**R:** Actualmente la opción es global por instancia de `PdfOptions`; necesitarías crear instancias separadas de `Viewer` para diferentes páginas.

## Recursos

- [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [Purchase License](https://purchase.groupdocs.com/buy)
- [Free Trial Version](https://releases.groupdocs.com/viewer/java/)
- [Temporary License Application](https://purchase.groupdocs.com/temporary-license/)
- [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

**Última actualización:** 2025-12-21  
**Probado con:** GroupDocs.Viewer 25.2 para Java  
**Autor:** GroupDocs