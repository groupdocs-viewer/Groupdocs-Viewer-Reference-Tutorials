---
"description": "Aprenda a extraer información de visualización de documentos PDF utilizando GroupDocs.Viewer para .NET en este completo tutorial."
"linktitle": "Obtener información de visualización para el documento PDF"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Obtener información de visualización para el documento PDF"
"url": "/es/net/pdf-rendering-options/get-view-info-pdf-document/"
"weight": 16
type: docs
---
# Obtener información de visualización para el documento PDF

## Introducción
GroupDocs.Viewer para .NET es una potente herramienta diseñada para optimizar la visualización de documentos en aplicaciones .NET. Ya sea que trabaje con archivos PDF, documentos de Word, hojas de cálculo de Excel o presentaciones de PowerPoint, esta biblioteca simplifica el proceso de renderizado e interacción con diversos formatos de archivo. En este tutorial, nos centraremos en aprovechar las capacidades de GroupDocs.Viewer específicamente para extraer información de visualización de documentos PDF.

![Obtenga información de visualización de un documento PDF con GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/get-view-iInfo-for-pdf-document.png)

## Prerrequisitos
Antes de sumergirse en el tutorial, asegúrese de tener los siguientes requisitos previos:
1. Instalación de GroupDocs.Viewer para .NET: Asegúrese de haber descargado e instalado la biblioteca GroupDocs.Viewer. Puede obtenerla desde [enlace de descarga](https://releases.groupdocs.com/viewer/net/).   
2. Conocimientos básicos de C#: La familiaridad con el lenguaje de programación C# es esencial para comprender e implementar los ejemplos de código proporcionados.
3. Acceso a un documento PDF: Tenga listo un documento PDF que utilizará para extraer información de visualización.

## Importar espacios de nombres
En su proyecto C#, importe los espacios de nombres necesarios para utilizar las funcionalidades de GroupDocs.Viewer.

```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```


Ahora, analicemos el proceso de recuperación de información de visualización de un documento PDF usando GroupDocs.Viewer para .NET.
## Paso 1: Inicializar el objeto Visor
Cree un objeto Visor y proporcione la ruta al documento PDF como parámetro.
```csharp
using (Viewer viewer = new Viewer("path/to/your/sample.pdf"))
{
```
## Paso 2: Definir ViewInfoOptions
Especifique las opciones de visualización, como la vista HTML, para recuperar información de visualización.
```csharp
	ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
```
## Paso 3: Obtener información de visualización
Invoque el método GetViewInfo para extraer información de visualización del documento PDF.
```csharp
	PdfViewInfo info = viewer.GetViewInfo(options) as PdfViewInfo;
```
## Paso 4: Información de la vista de salida
Muestra la información de vista extraída, como el tipo de documento, el número de páginas y los permisos de impresión.
```csharp
	Console.WriteLine("Document type is: " + info.FileType);
	Console.WriteLine("Pages count: " + info.Pages.Count);
	Console.WriteLine("Printing allowed: " + info.PrintingAllowed);
}
```

## Conclusión
En este tutorial, exploramos cómo usar GroupDocs.Viewer para .NET para extraer información de visualización de documentos PDF. Siguiendo los pasos indicados, podrá integrar esta funcionalidad sin problemas en sus aplicaciones .NET, optimizando así la gestión y visualización de documentos.
## Preguntas frecuentes
### ¿GroupDocs.Viewer es compatible con otros formatos de archivos además de PDF?
Sí, GroupDocs.Viewer admite una amplia gama de formatos de documentos, incluidos Word, Excel, PowerPoint y más.
### ¿Puedo personalizar las opciones de visualización según los requisitos de mi aplicación?
Por supuesto, GroupDocs.Viewer ofrece varias opciones para adaptar la experiencia de visualización según sus necesidades específicas.
### ¿GroupDocs.Viewer es adecuado tanto para aplicaciones de escritorio como para aplicaciones web?
Sí, GroupDocs.Viewer es versátil y se puede integrar sin problemas en aplicaciones .NET tanto de escritorio como basadas en web.
### ¿GroupDocs.Viewer proporciona soporte y asistencia si encuentro algún problema durante la implementación?
Por supuesto, puede buscar ayuda en el foro de la comunidad de GroupDocs.Viewer o acceder a servicios de soporte profesional para resolver rápidamente cualquier problema.
### ¿Puedo probar GroupDocs.Viewer antes de realizar una compra?
Sí, puede explorar las funciones de GroupDocs.Viewer accediendo a la versión de prueba gratuita disponible en el sitio web. [sitio web](https://purchase.groupdocs.com/buy).