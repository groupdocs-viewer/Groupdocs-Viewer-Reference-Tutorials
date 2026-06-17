---
date: '2026-04-01'
description: Aprende cómo dividir los dibujos CAD en mosaicos usando GroupDocs Viewer
  para Java, mejorando el rendimiento de renderizado y simplificando el manejo de
  archivos grandes.
keywords:
- how to split cad
- GroupDocs Viewer Java
- CAD tiling
title: Cómo dividir dibujos CAD en mosaicos con GroupDocs Viewer
type: docs
url: /es/java/advanced-rendering/split-cad-drawings-into-tiles-groupdocs-viewer-java/
weight: 1
---

# Cómo dividir dibujos CAD en mosaicos con GroupDocs Viewer

Si te preguntas **cómo dividir CAD** en archivos más pequeños y manejables, has llegado al lugar correcto. En este tutorial recorreremos los pasos exactos necesarios para dividir grandes dibujos CAD en mosaicos usando **GroupDocs Viewer for Java**. Al final tendrás una solución lista para usar que mejora la velocidad de renderizado, reduce el consumo de memoria y facilita la visualización de los dibujos en aplicaciones web o móviles.

![Dividir dibujos CAD con GroupDocs.Viewer for Java](/viewer/advanced-rendering/split-cad-drawings-java.png)

## Respuestas rápidas
- **¿Qué logra “dividir CAD”?** Divide un dibujo masivo en imágenes más pequeñas (mosaicos) que se cargan más rápido y consumen menos memoria.  
- **¿Qué formato se usa para los mosaicos?** Se generan archivos PNG por defecto, pero se admiten otros formatos mediante las opciones de Viewer.  
- **¿Necesito una licencia?** Una prueba gratuita funciona para desarrollo; se requiere una licencia de pago para producción.  
- **¿Puedo cambiar el tamaño del mosaico?** Sí – ajusta los cálculos de `tileWidth` y `tileHeight` según tus necesidades.  
- **¿Es este enfoque thread‑safe?** Renderizar cada mosaico en su propia instancia de `Viewer` con try‑with‑resources es seguro para la ejecución concurrente.

## Qué es “dividir CAD”?
Dividir CAD se refiere a separar un único dibujo CAD, a menudo enorme, en múltiples secciones rectangulares (mosaicos). Cada mosaico se renderiza de forma independiente, lo que permite cargar solo las partes que el usuario realmente necesita, perfecto para mapas web, portales de documentos y visores móviles.

## Por qué usar GroupDocs Viewer for Java?
GroupDocs Viewer ofrece soporte listo para usar de más de 100 formatos de archivo, incluidos DWG, DXF y DWF. Su API de mosaicos le permite especificar coordenadas exactas, de modo que pueda renderizar exactamente el área que le interesa sin procesar todo el archivo primero. Esto ahorra ciclos de CPU, reduce el ancho de banda y brinda una experiencia de usuario más fluida.

## Requisitos previos
- **Bibliotecas**: GroupDocs.Viewer for Java ≥ 25.2.  
- **JDK**: Cualquier Java Development Kit reciente (Java 8+).  
- **IDE**: IntelliJ IDEA, Eclipse u otro IDE compatible con Java.  
- **Herramienta de compilación**: Maven (otras herramientas de compilación funcionan siempre que se añada la dependencia).  

## Configuración de GroupDocs.Viewer para Java
Agrega el repositorio de GroupDocs y la dependencia a tu `pom.xml`:

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
GroupDocs Viewer ofrece una licencia de prueba gratuita para evaluación:

- **Prueba gratuita**: Visita [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) para descargar la biblioteca.  
- **Licencia temporal**: Solicítala en [Temporary License Page](https://purchase.groupdocs.com/temporary-license/).  
- **Licencia completa**: Compra una licencia de producción en la [Purchase Page](https://purchase.groupdocs.com/buy).

### Inicialización básica
Crea una instancia simple de `Viewer` para verificar que la biblioteca se cargue correctamente:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
            // Your rendering code goes here.
        }
    }
}
```

## Guía paso a paso para dividir dibujos CAD en mosaicos

### Paso 1: Definir el directorio de salida
Almacenaremos cada mosaico como un archivo PNG separado. Usar un método de utilidad mantiene la lógica de rutas limpia y reutilizable.

```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("SplitDrawingIntoTiles");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.png");
```

### Paso 2: Configurar opciones de vista
Establece el formato de renderizado a PNG y indica al visor que no precargue cada página (lo que ahorra memoria).

```java
import com.groupdocs.viewer.options.PngViewOptions;
import com.groupdocs.viewer.options.ViewInfoOptions;

PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forPngView(false);
```

### Paso 3: Calcular dimensiones del mosaico
Primero obtenemos el ancho y alto originales del dibujo, luego lo dividimos en cuatro cuadrantes iguales.

```java
import com.groupdocs.viewer.results.ViewInfo;
import com.groupdocs.viewer.options.Tile;

ViewInfo viewInfo = new Viewer("path/to/your/drawing.dwg").getViewer().getViewInfo(viewInfoOptions);
int width = viewInfo.getPages().get(0).getWidth();
int height = viewInfo.getPages().get(0).getHeight();

// Each tile is a quarter of the total size.
int tileWidth = width / 2;
int tileHeight = height / 2;

Tile[] tiles = {
    new Tile(0, 0, tileWidth, tileHeight),
    new Tile(tileWidth, 0, tileWidth, tileHeight),
    new Tile(0, tileHeight, tileWidth, tileHeight),
    new Tile(tileWidth, tileHeight, tileWidth, tileHeight)
};
```

### Paso 4: Renderizar y guardar los mosaicos
Añade los mosaicos calculados a las opciones de renderizado y permite que el `Viewer` genere los archivos PNG.

```java
viewOptions.getCadOptions().getTiles().addAll(java.util.Arrays.asList(tiles));

try (Viewer viewer = new Viewer("path/to/your/drawing.dwg")) {
    viewer.view(viewOptions);
}
```

### Consejos de solución de problemas
- **Ruta de compilación** – Asegúrate de que los archivos JAR de GroupDocs estén en el classpath.  
- **Permisos** – La carpeta de salida debe ser escribible por el proceso Java.  
- **Excepciones** – Si ves `ViewerException`, verifica que el archivo DWG no esté corrupto y que la licencia correcta esté aplicada.

## Casos de uso comunes para dividir mosaicos CAD
1. **Mapeo web** – Carga solo la porción visible de un plano de planta mientras el usuario hace pan/zoom.  
2. **Gestión de documentos** – Almacena cada mosaico por separado para generar vistas previas más rápidas.  
3. **Visualización móvil** – Reduce el ancho de banda descargando solo los mosaicos necesarios para la pantalla actual.

## Consideraciones de rendimiento
- **Tamaño del mosaico** – Mosaicos más grandes significan menos archivos pero renderizado más lento; encuentra un equilibrio según las necesidades de tu UI.  
- **Monitoreo de memoria** – Usa herramientas de perfilado de Java (p. ej., VisualVM) para observar el uso del heap al procesar dibujos muy grandes.  
- **Limpieza de recursos** – El patrón try‑with‑resources mostrado arriba libera automáticamente los recursos nativos.

## Preguntas frecuentes

**P: ¿Puedo dividir otros tipos de archivo (PDF, imágenes) en mosaicos usando el mismo enfoque?**  
R: Sí. GroupDocs Viewer admite muchos formatos; solo necesitas usar la clase de opciones correspondiente (p. ej., `PdfViewOptions`).

**P: ¿Cómo cambio la calidad de la imagen de salida?**  
R: Ajusta `viewOptions.setResolution(int dpi)` o configura los ajustes de compresión en el objeto `PngOptions`.

**P: Mi aplicación se queda sin memoria en archivos DWG muy grandes—¿qué puedo hacer?**  
R: Reduce las dimensiones del mosaico, aumenta el heap de la JVM (`-Xmx`), o renderiza los mosaicos secuencialmente en instancias separadas de `Viewer`.

**P: ¿Es posible renderizar mosaicos de forma asíncrona?**  
R: Absolutamente. Envuelve cada llamada de renderizado de mosaico en un `CompletableFuture` o usa un servicio de ejecución para paralelizar la carga de trabajo.

**P: ¿Necesito una licencia separada para cada mosaico?**  
R: No. Una única licencia válida de GroupDocs Viewer cubre todas las operaciones de renderizado dentro de tu aplicación.

## Recursos
- [Documentación](https://docs.groupdocs.com/viewer/java/)
- [Referencia de API](https://reference.groupdocs.com/viewer/java/)
- [Descargar GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)
- [Comprar una licencia](https://purchase.groupdocs.com/buy)
- [Prueba gratuita](https://releases.groupdocs.com/viewer/java/)
- [Licencia temporal](https://purchase.groupdocs.com/temporary-license/)
- [Foro de soporte](https://forum.groupdocs.com/c/viewer/9)

---

**Última actualización:** 2026-04-01  
**Probado con:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs