---
"date": "2025-04-25"
"description": "Aprenda a extraer información de archivo de forma eficiente con GroupDocs.Viewer para .NET. Esta guía abarca la configuración, ejemplos de código y aplicaciones prácticas."
"title": "Cómo recuperar información de archivo con GroupDocs.Viewer para .NET&#58; una guía completa"
"url": "/es/net/metadata-properties/groupdocs-viewer-net-retrieve-archive-info/"
"weight": 1
type: docs
---
# Cómo recuperar información de archivo con GroupDocs.Viewer para .NET: una guía completa

## Introducción

¿Busca extraer información detallada de archivos comprimidos como ZIP de forma eficiente? Comprender la estructura es fundamental para la gestión documental. Esta guía le mostrará cómo usarla. **GroupDocs.Viewer para .NET** para recuperar y mostrar detalles completos sobre un archivo comprimido.

![Recuperar información de archivo con GroupDocs.Viewer para .NET](/viewer/metadata-properties/retrieve-archive-information.png)

En este tutorial, cubriremos:
- Configuración de GroupDocs.Viewer en su aplicación .NET
- Recuperar información de visualización de archivos de almacenamiento
- Visualización de estructuras de carpetas dentro de archivos

Al finalizar esta guía, comprenderá sólidamente la implementación de estas funcionalidades. Comencemos con lo necesario antes de profundizar en el código.

### Prerrequisitos

Asegúrese de tener lo siguiente listo:

- **Bibliotecas y versiones**:Instalar GroupDocs.Viewer para .NET (versión 25.3.0).
- **Configuración del entorno**:Utilice un entorno de desarrollo .NET adecuado como Visual Studio.
- **Requisitos previos de conocimiento**:Comprensión básica de C# y manejo de archivos en aplicaciones .NET.

## Configuración de GroupDocs.Viewer para .NET

Para utilizar GroupDocs.Viewer para .NET, instálelo a través del Administrador de paquetes NuGet:

### Instrucciones de instalación

**Consola del administrador de paquetes NuGet**
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**CLI de .NET**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Adquisición de una licencia

GroupDocs.Viewer ofrece varias opciones de licencia:
- **Prueba gratuita**:Explorar las funcionalidades básicas.
- **Licencia temporal**:Acceso a todas las funciones durante la evaluación.
- **Compra**Para uso a largo plazo, considere comprar una licencia.

Tras instalar y configurar su licencia, inicialice GroupDocs.Viewer en su aplicación. A continuación, se muestra un ejemplo de configuración:

```csharp
using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS"))
{
    // Utilice las funcionalidades del Visor aquí.
}
```

## Guía de implementación

Desglosaremos la implementación en características clave para un enfoque estructurado.

### Recuperar información de visualización de archivos de archivo

Comprender la estructura de su archivo es crucial. A continuación, le explicamos cómo lograrlo:

#### Inicializar el objeto Visor

Crear una instancia de la `Viewer` clase con la ruta de su archivo de almacenamiento:

```csharp
string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS";
using (Viewer viewer = new Viewer(documentPath))
{
    // Su código para procesamiento irá aquí.
}
```

#### Obtener información de visualización

Recuperar información de visualización, formateada como imágenes JPG:

```csharp
ViewInfo info = viewer.GetViewInfo(ViewInfoOptions.ForJpgView());
Console.WriteLine("File type: " + info.FileType);
Console.WriteLine("Pages count: " + info.Pages.Count);
```

#### Mostrar información de la carpeta raíz

Para obtener una descripción general completa, imprima los detalles de la carpeta raíz:

```csharp
Console.WriteLine("Folders:");
Console.WriteLine(" - /");
```

#### Leer e imprimir nombres de subcarpetas de forma recursiva

Para explorar subcarpetas dentro de su archivo, utilice este método recursivo:

```csharp
string rootFolder = string.Empty;
ReadArchiveFolders(viewer, rootFolder);

private static void ReadArchiveFolders(Viewer viewer, string folder)
{
    ViewInfoOptions options = ViewInfoOptions.ForJpgView();
    options.ArchiveOptions.Folder = folder;

    ArchiveViewInfo viewInfo = viewer.GetViewInfo(options) as ArchiveViewInfo;
    foreach (string subFolder in viewInfo.Folders)
    {
        Console.WriteLine($" - {subFolder}");
        ReadArchiveFolders(viewer, subFolder);
    }
}
```

### Aplicaciones prácticas

GroupDocs.Viewer para .NET se puede utilizar en varios escenarios:
- **Sistemas de gestión de documentos**: Extrae y muestra automáticamente estructuras de archivo.
- **Plataformas de distribución de contenido**:Proporcione vistas previas del contenido archivado a los usuarios.
- **Herramientas de análisis de datos**:Analizar las jerarquías de carpetas dentro de los archivos para obtener información empresarial.

La integración con otros marcos como ASP.NET o WPF es sencilla, lo que permite una incorporación perfecta a los sistemas existentes.

## Consideraciones de rendimiento

Para un rendimiento óptimo:
- **Optimizar el uso de recursos**:Administre eficientemente la memoria y gestione archivos grandes.
- **Mejores prácticas de gestión de memoria**:Desechar `Viewer` objetos adecuadamente para liberar recursos rápidamente.

## Conclusión

En este tutorial, aprendió a usar GroupDocs.Viewer para .NET para recuperar información detallada de archivos de almacenamiento. Implementar estas funciones puede mejorar significativamente su gestión documental.

### Próximos pasos

Considere explorar las funciones más avanzadas que ofrece GroupDocs.Viewer o integrarlo con otros componentes de su aplicación. Experimente con diferentes tipos de archivos y estructuras de carpetas complejas para profundizar su comprensión.

## Sección de preguntas frecuentes

1. **¿Cuál es el propósito de? `ViewInfoOptions`?**
   - Configura cómo desea ver un documento, como por ejemplo renderizar formatos específicos como JPG.

2. **¿Cómo puedo gestionar archivos grandes de manera eficiente?**
   - Utilice técnicas de gestión de memoria y gestione los recursos de forma adecuada.

3. **¿Puede GroupDocs.Viewer procesar archivos protegidos con contraseña?**
   - Sí, con la licencia y configuración correctas, puede manejar documentos encriptados.

4. **¿Existe un límite para el tamaño del archivo que se puede procesar?**
   - El límite depende de la capacidad de memoria de su sistema; los archivos más grandes requieren más recursos.

5. **¿Cómo integro GroupDocs.Viewer con aplicaciones ASP.NET?**
   - Utilice la clase Viewer dentro de las acciones o servicios de su controlador, de forma similar a como lo haría en una aplicación de consola.

## Recursos

- [Documentación](https://docs.groupdocs.com/viewer/net/)
- [Referencia de API](https://reference.groupdocs.com/viewer/net/)
- [Descargar GroupDocs.Viewer para .NET](https://releases.groupdocs.com/viewer/net/)
- [Comprar una licencia](https://purchase.groupdocs.com/buy)
- [Versión de prueba gratuita](https://releases.groupdocs.com/viewer/net/)
- [Solicitud de licencia temporal](https://purchase.groupdocs.com/temporary-license/)
- [Foro de soporte](https://forum.groupdocs.com/c/viewer/9)