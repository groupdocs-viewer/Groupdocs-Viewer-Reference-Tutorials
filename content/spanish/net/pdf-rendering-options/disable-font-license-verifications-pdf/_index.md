---
"description": "Disfrute de una visualización fluida de documentos en su .NET con GroupDocs.Viewer para .NET. Integre y personalice fácilmente la representación de documentos con mínimas dependencias."
"linktitle": "Desactivar las verificaciones de licencia de fuentes en PDF"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Desactivar las verificaciones de licencia de fuentes en PDF"
"url": "/es/net/pdf-rendering-options/disable-font-license-verifications-pdf/"
"weight": 12
---

# Desactivar las verificaciones de licencia de fuentes en PDF

## Introducción
En el ámbito del desarrollo .NET, la gestión y manipulación de documentos suele ser un aspecto crucial de muchas aplicaciones. Ya sea para visualizar archivos PDF, documentos de Word u otros tipos de archivos, es fundamental contar con herramientas robustas para gestionar estas tareas de forma eficiente. Aquí es donde GroupDocs.Viewer para .NET entra en juego. Esta potente biblioteca permite a los desarrolladores integrar a la perfección la función de visualización de documentos en sus aplicaciones .NET.

![Deshabilitar las verificaciones de licencia de fuentes en PDF con GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/disable-font-license-verifications-in-pdf.png)

## Prerrequisitos
Antes de comenzar a utilizar GroupDocs.Viewer para .NET, hay algunos requisitos previos que deberá tener en cuenta:
### 1. Instalar Visual Studio
Primero y principal, asegúrese de tener Visual Studio instalado en su sistema. Puede descargarlo del sitio web de Microsoft si aún no lo tiene.
### 2. Descargue GroupDocs.Viewer para .NET
Dirígete a la [enlace de descarga](https://releases.groupdocs.com/viewer/net/) Para adquirir la última versión de GroupDocs.Viewer para .NET, siga las instrucciones de instalación para configurarlo en su entorno de desarrollo.
### 3. Obtenga una licencia temporal
Para aprovechar al máximo el potencial de GroupDocs.Viewer para .NET durante el desarrollo y las pruebas, se recomienda obtener una licencia temporal. Puede solicitarla en [aquí](https://purchase.groupdocs.com/temporary-license/).

## Importar espacios de nombres
Una vez completados los prerrequisitos, estará listo para empezar a utilizar GroupDocs.Viewer para .NET en sus proyectos. Comience importando los espacios de nombres necesarios a su código base.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Dividiremos el ejemplo proporcionado en varios pasos para una comprensión más clara:
## Paso 1: Definir el directorio de salida
Comience por definir el directorio donde desea que se almacenen las páginas del documento renderizado.
```csharp
string outputDirectory = "Your Document Directory";
```
## Paso 2: Definir el formato de la ruta del archivo de página
Establezca el formato para las rutas de archivo de páginas individuales del documento.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
## Paso 3: Inicializar el objeto Visor
Crea una instancia de la clase Viewer, pasando la ruta al documento que deseas ver.
```csharp
using (Viewer viewer = new Viewer(TestFiles.OXPS_EMBEDDED_FONT))
```
## Paso 4: Configurar las opciones de vista HTML
Define las opciones para ver el documento como HTML, especificando el formato para los recursos incrustados (por ejemplo, imágenes).
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Paso 5: Desactivar las verificaciones de licencia de fuentes
Habilite la opción para deshabilitar las verificaciones de licencia de fuente para garantizar una representación fluida.
```csharp
options.PdfOptions.DisableFontLicenseVerifications = true;
```
## Paso 6: Ver documento
Invoca el método View del objeto Viewer, pasando las opciones configuradas.
```csharp
viewer.View(options);
```
## Paso 7: Mostrar el directorio de salida
Informar al usuario sobre la ubicación donde se almacenan las páginas del documento renderizado.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusión
GroupDocs.Viewer para .NET ofrece a los desarrolladores una solución integral para integrar fácilmente la visualización de documentos en sus aplicaciones .NET. Siguiendo los pasos de este tutorial, podrá utilizar eficazmente esta potente biblioteca para optimizar sus flujos de trabajo de gestión documental.
## Preguntas frecuentes
### ¿Puede GroupDocs.Viewer para .NET manejar múltiples formatos de documentos?
Sí, GroupDocs.Viewer admite una amplia gama de formatos de documentos, incluidos PDF, Microsoft Word, Excel, PowerPoint y más.
### ¿GroupDocs.Viewer para .NET es adecuado para aplicaciones web?
Por supuesto, GroupDocs.Viewer se puede integrar perfectamente en aplicaciones de escritorio y web desarrolladas con tecnologías .NET.
### ¿GroupDocs.Viewer requiere alguna dependencia adicional?
No, GroupDocs.Viewer para .NET tiene dependencias mínimas y se puede integrar fácilmente en sus proyectos existentes.
### ¿Puedo personalizar la apariencia de los documentos renderizados?
Sí, GroupDocs.Viewer ofrece varias opciones para personalizar la apariencia y el comportamiento de los documentos renderizados para satisfacer sus requisitos específicos.
### ¿Hay soporte técnico disponible para GroupDocs.Viewer para .NET?
Sí, puede buscar ayuda y orientación del equipo de soporte dedicado a través del [foro](https://forum.groupdocs.com/c/viewer/9).