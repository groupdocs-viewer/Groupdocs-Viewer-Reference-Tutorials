---
date: '2026-03-22'
description: Aprende cómo generar HTML a partir de PDF y desactivar la agrupación
  de caracteres usando GroupDocs Viewer for Java para una representación precisa del
  texto.
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: Generar HTML a partir de PDF y desactivar la agrupación – GroupDocs Java
type: docs
url: /es/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# Generar HTML a partir de PDF y Desactivar la Agrupación con GroupDocs Viewer para Java

En muchos proyectos necesitas **generar HTML a partir de PDF** manteniendo cada glifo exactamente en su lugar. Esto es especialmente cierto para scripts complejos, lenguas antiguas o documentos legales donde un solo carácter fuera de lugar puede cambiar el significado. En este tutorial te guiaremos a través del proceso completo de renderizar PDFs a HTML con GroupDocs Viewer para Java y te mostraremos **cómo desactivar la agrupación** para que cada carácter se trate como un elemento independiente.

![Precise Rendering Techniques with GroupDocs.Viewer for Java](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## Respuestas Rápidas
- **¿Qué hace “disable grouping”?** Obliga al renderizador a tratar cada carácter como un elemento independiente, preservando el diseño exacto.  
- **¿Qué opción de la API controla esto?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **¿Necesito una licencia?** Una prueba funciona para pruebas, pero se requiere una licencia completa para producción.  
- **¿Puedo generar HTML a partir de PDF al mismo tiempo?** Sí—usa `HtmlViewOptions` para crear salida HTML mientras desactivas la agrupación.  
- **¿Esta función está limitada a PDFs?** Es principalmente para PDFs, pero el visor soporta muchos otros formatos.

## Introducción

Al trabajar con documentos PDF, la precisión en el renderizado es crucial—especialmente al tratar con estructuras de texto complejas como jeroglíficos o lenguas que requieren una representación precisa de los caracteres. La función "Character Grouping" a menudo causa problemas al agrupar caracteres incorrectamente, lo que lleva a una interpretación errónea del contenido del documento. Esto puede ser particularmente problemático para usuarios que necesitan una replicación exacta del diseño del texto de sus documentos.

### Requisitos Previos

Antes de sumergirte en la implementación del código, asegúrate de cumplir con los siguientes requisitos:
- **Bibliotecas y Dependencias**: Necesitarás GroupDocs.Viewer para Java versión 25.2 o posterior.  
- **Configuración del Entorno**: Asegúrate de tener instalado un Java Development Kit (JDK) y tu IDE configurado para trabajar con proyectos Maven.  
- **Conocimientos Previos**: Comprensión básica de programación Java, especialmente el manejo de rutas de archivo y el uso de bibliotecas externas.

## Cómo generar HTML a partir de PDF con GroupDocs Viewer

Generar HTML a partir de PDF es un proceso de dos pasos: configurar el visor y luego renderizar el documento. La clave es desactivar la agrupación de caracteres antes de renderizar para que la salida HTML refleje el diseño original del PDF carácter por carácter.

### Configuración de GroupDocs.Viewer para Java

#### Instalación mediante Maven

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

#### Obtención de Licencia

Para utilizar completamente GroupDocs.Viewer, considera adquirir una licencia:
- **Prueba Gratuita**: Comienza con la prueba gratuita para probar las funciones.  
- **Licencia Temporal**: Solicita una licencia temporal si necesitas más tiempo.  
- **Compra**: Para proyectos a largo plazo, se recomienda comprar una licencia.

#### Inicialización y Configuración Básicas

A continuación tienes un fragmento listo para ejecutar que muestra el flujo de trabajo completo—desde establecer la carpeta de salida hasta renderizar el PDF como HTML mientras desactivas la agrupación de caracteres:

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

### Guía de Implementación

#### Función: Desactivar la Agrupación de Caracteres

A continuación desglosamos cada línea del ejemplo para que puedas entender **por qué** lo hacemos y **cómo** contribuye a generar HTML a partir de PDF sin la fusión no deseada de caracteres.

##### Paso 1: Definir el Directorio de Salida  

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**¿Por qué?** Esto garantiza que tus archivos HTML renderizados se almacenen en una carpeta dedicada, facilitando su localización y gestión posteriormente.

##### Paso 2: Configurar el Formato de Ruta de Archivo  

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**¿Por qué?** Usar un marcador de posición (`{0}`) permite al visor crear un archivo HTML separado para cada página del PDF, manteniendo la salida organizada.

##### Paso 3: Inicializar HTML View Options  

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**¿Por qué?** Los recursos incrustados agrupan imágenes, fuentes y CSS directamente con cada página HTML, lo cual es ideal para visores basados en la web o plataformas de e‑learning.

##### Paso 4: Desactivar la Agrupación de Caracteres  

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**¿Por qué?** Esta es la línea crucial que indica al motor de renderizado **no** combinar caracteres adyacentes, garantizando que el HTML generado refleje la ubicación exacta de los glifos del PDF original.

##### Paso 5: Renderizar el Documento  

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**¿Por qué?** Encerrar el `Viewer` en un bloque try‑with‑resources garantiza que todos los recursos nativos se liberen automáticamente, evitando fugas de memoria en aplicaciones de larga duración.

### Generar HTML Java a partir de PDF sin Agrupación

La clase `HtmlViewOptions` te permite producir **generate html from pdf** mientras mantienes cada carácter separado. Esto es especialmente útil cuando necesitas incrustar las páginas renderizadas en un portal web o una plataforma de e‑learning donde la ubicación exacta de los glifos es importante.

### Problemas Comunes y Soluciones

- **FileNotFoundException** – Verifica nuevamente la ruta que pasas a `new Viewer(...)`. Usa rutas absolutas o `Path.of(...)` para mayor claridad.  
- **Permisos de Escritura** – Asegúrate de que el directorio de salida sea escribible por el proceso Java; en Linux puede que necesites ajustar los permisos de la carpeta (`chmod 775`).  
- **Incompatibilidad de Versión** – La opción `setDisableCharsGrouping` está disponible a partir de la versión 25.2. Verifica que tu `pom.xml` refleje la versión correcta.  

### Aplicaciones Prácticas

1. **Preservación de Idiomas** – Ideal para renderizar documentos en chino, japonés, árabe o scripts antiguos donde el espaciado de los caracteres tiene significado.  
2. **Documentos Legales y Financieros** – Garantiza una replicación exacta del texto para documentación con altos requisitos de cumplimiento.  
3. **Recursos Educativos** – Perfecto para libros de texto que incluyen diagramas complejos, anotaciones o contenido multilingüe.

### Consideraciones de Rendimiento

- **Optimizar el Uso de Recursos** – Los PDFs grandes pueden consumir mucha memoria. Considera procesar páginas en lotes y disponer de las instancias de `Viewer` rápidamente.  
- **Gestión de Memoria en Java** – Ajusta el heap de la JVM (`-Xmx2g` o superior) si anticipas procesar PDFs de cientos de páginas.  
- **Renderizado Paralelo** – Para conversiones masivas, crea hilos separados, cada uno con su propia instancia de `Viewer`, para aprovechar CPUs multinúcleo.

## Preguntas Frecuentes

**P:** *¿Por qué necesitaría desactivar la agrupación de caracteres?*  
**R:** Desactivar la agrupación evita que el renderizador combine caracteres que pertenecen a glifos distintos, lo cual es esencial para scripts donde el espaciado y el orden transmiten significado.

**P:** *¿La configuración `setDisableCharsGrouping` se aplica solo a la salida HTML?*  
**R:** No, afecta al motor de renderizado PDF subyacente, por lo que cualquier formato de salida (HTML, PNG, JPEG, etc.) reflejará el cambio.

**P:** *¿Puedo combinar esta configuración con fuentes personalizadas?*  
**R:** Sí—carga tus fuentes personalizadas antes de inicializar `Viewer`, y la regla de agrupación seguirá aplicándose.

**P:** *¿Desactivar la agrupación afecta el rendimiento?*  
**R:** Ligeramente, porque el motor procesa cada carácter individualmente, pero el impacto es mínimo para la mayoría de los documentos.

**P:** *¿Existe una forma de alternar la agrupación por página?*  
**R:** Actualmente la opción es global por instancia de `PdfOptions`; necesitarías instancias separadas de `Viewer` para diferentes páginas si requieres un comportamiento mixto.

## Recursos

- [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [Purchase License](https://purchase.groupdocs.com/buy)
- [Free Trial Version](https://releases.groupdocs.com/viewer/java/)
- [Temporary License Application](https://purchase.groupdocs.com/temporary-license/)
- [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Última actualización:** 2026-03-22  
**Probado con:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs