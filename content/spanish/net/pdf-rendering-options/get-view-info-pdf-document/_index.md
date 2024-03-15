---
title: Obtener información de visualización para un documento PDF
linktitle: Obtener información de visualización para un documento PDF
second_title: API GroupDocs.Viewer .NET
description: Aprenda a extraer información de visualización de documentos PDF utilizando GroupDocs.Viewer para .NET en este completo tutorial.
type: docs
weight: 16
url: /es/net/pdf-rendering-options/get-view-info-pdf-document/
---
## Introducción
GroupDocs.Viewer para .NET es una poderosa herramienta diseñada para optimizar la visualización de documentos dentro de aplicaciones .NET. Ya sea que trabaje con archivos PDF, documentos de Word, hojas de cálculo de Excel o presentaciones de PowerPoint, esta biblioteca simplifica el proceso de renderizado e interacción con varios formatos de archivos. En este tutorial, nos centraremos en aprovechar las capacidades de GroupDocs.Viewer específicamente para extraer información de visualización de documentos PDF.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de tener los siguientes requisitos previos:
1.  Instalación de GroupDocs.Viewer para .NET: asegúrese de haber descargado e instalado la biblioteca GroupDocs.Viewer. Puedes obtenerlo del[enlace de descarga](https://releases.groupdocs.com/viewer/net/).   
2. Conocimientos básicos de C#: la familiaridad con el lenguaje de programación C# es esencial para comprender e implementar los ejemplos de código proporcionados.
3. Acceso a un documento PDF: tenga listo un documento PDF que utilizará para extraer información de visualización.

## Importar espacios de nombres
En su proyecto C#, importe los espacios de nombres necesarios para utilizar las funcionalidades de GroupDocs.Viewer.

```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```


Ahora, analicemos el proceso de recuperación de información de visualización de un documento PDF usando GroupDocs.Viewer para .NET.
## Paso 1: inicializar el objeto visor
Cree un objeto Visor y proporcione la ruta al documento PDF como parámetro.
```csharp
using (Viewer viewer = new Viewer("path/to/your/sample.pdf"))
{
```
## Paso 2: definir ViewInfoOptions
Especifique las opciones de visualización, como la vista HTML, para recuperar información de la vista.
```csharp
	ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
```
## Paso 3: Obtener información de visualización
Invoque el método GetViewInfo para extraer información de visualización del documento PDF.
```csharp
	PdfViewInfo info = viewer.GetViewInfo(options) as PdfViewInfo;
```
## Paso 4: Información de vista de salida
Muestre la información de la vista extraída, como el tipo de documento, el recuento de páginas y los permisos de impresión.
```csharp
	Console.WriteLine("Document type is: " + info.FileType);
	Console.WriteLine("Pages count: " + info.Pages.Count);
	Console.WriteLine("Printing allowed: " + info.PrintingAllowed);
}
```

## Conclusión
En este tutorial, exploramos cómo utilizar GroupDocs.Viewer para .NET para extraer información de visualización de documentos PDF. Si sigue los pasos proporcionados, puede integrar perfectamente esta funcionalidad en sus aplicaciones .NET, mejorando la gestión de documentos y las capacidades de visualización.
## Preguntas frecuentes
### ¿GroupDocs.Viewer es compatible con otros formatos de archivo además de PDF?
Sí, GroupDocs.Viewer admite una amplia gama de formatos de documentos, incluidos Word, Excel, PowerPoint y más.
### ¿Puedo personalizar las opciones de visualización según los requisitos de mi aplicación?
Por supuesto, GroupDocs.Viewer ofrece varias opciones para adaptar la experiencia de visualización según sus necesidades específicas.
### ¿GroupDocs.Viewer es adecuado tanto para aplicaciones web como de escritorio?
Sí, GroupDocs.Viewer es versátil y se puede integrar perfectamente en aplicaciones .NET de escritorio y basadas en web.
### ¿GroupDocs.Viewer brinda soporte y asistencia si encuentro algún problema durante la implementación?
Ciertamente, puede buscar ayuda en el foro de la comunidad GroupDocs.Viewer o acceder a servicios de soporte profesional para una pronta resolución de cualquier problema.
### ¿Puedo probar GroupDocs.Viewer antes de realizar una compra?
 Sí, puede explorar las funciones de GroupDocs.Viewer accediendo a la versión de prueba gratuita disponible en[sitio web](https://purchase.groupdocs.com/buy).