---
"description": "Aprenda a representar figuras de Visio con GroupDocs.Viewer para .NET con este completo tutorial. Mejore la visualización de documentos en sus aplicaciones .NET."
"linktitle": "Renderizar figuras de Visio"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Renderizar figuras de Visio"
"url": "/es/net/rendering-visio-documents/render-visio-figures/"
"weight": 10
type: docs
---
# Renderizar figuras de Visio

## Introducción
En la era digital actual, la renderización de documentos desempeña un papel crucial en diversas aplicaciones. Ya sea para mostrar documentos en un sitio web o convertirlos a diferentes formatos, una renderización eficiente es esencial. GroupDocs.Viewer para .NET ofrece una solución robusta para visualizar y manipular documentos en aplicaciones .NET. En este tutorial, profundizaremos en la renderización de figuras de Visio con GroupDocs.Viewer para .NET, desglosando el proceso en pasos sencillos.
## Prerrequisitos
Antes de sumergirse en el tutorial, asegúrese de tener los siguientes requisitos previos:
1. Configuración del entorno: asegúrese de tener un entorno de trabajo para el desarrollo .NET.
2. GroupDocs.Viewer para .NET: Descargue e instale GroupDocs.Viewer para .NET desde [enlace de descarga](https://releases.groupdocs.com/viewer/net/).
3. Comprensión básica de C#: familiarícese con los fundamentos del lenguaje de programación C#.
4. Documento de Visio de muestra: tenga un documento de Visio de muestra listo para renderizar.

## Importar espacios de nombres
En su proyecto de C#, comience importando los espacios de nombres necesarios:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. Renderizado a HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "result_page.html");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Directorio de salida: define el directorio donde se guardará el HTML renderizado.
- Formato de ruta de archivo de página: especifique el formato de ruta para la página HTML.
- Inicialización del visor: inicializa el objeto Visor con la ruta al documento de Visio.
- Opciones de visualización HTML: configure las opciones para representar HTML.
- Opciones de representación de Visio: establezca opciones específicas para la representación de Visio, como representar solo figuras y el ancho de las figuras.
## 2. Renderizado a JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.jpg");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- De manera similar a la renderización en HTML, configure las opciones para renderizar en formato JPG.
## 3. Renderizado a PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.png");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- La configuración para la renderización en formato PNG sigue un patrón similar a la renderización en JPG.
## 4. Renderizado a PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.pdf");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Para renderizar a PDF, configure opciones específicas del formato PDF.

## Conclusión
En este tutorial, exploramos cómo renderizar figuras de Visio con GroupDocs.Viewer para .NET. Siguiendo la guía paso a paso, podrá integrar fácilmente las funciones de renderizado de documentos en sus aplicaciones .NET, mejorando así la experiencia del usuario y la productividad.
## Preguntas frecuentes
### ¿Puedo personalizar las opciones de renderizado para las figuras de Visio?
Sí, GroupDocs.Viewer para .NET ofrece amplias opciones para personalizar la representación, incluido el ancho de las figuras, la representación solo de figuras y más.
### ¿GroupDocs.Viewer para .NET es adecuado para la representación de documentos a gran escala?
Por supuesto, GroupDocs.Viewer para .NET está optimizado para gestionar de manera eficiente la representación de documentos a gran escala.
### ¿GroupDocs.Viewer admite otros formatos de documentos además de Visio?
Sí, GroupDocs.Viewer admite una amplia gama de formatos de documentos, incluidos PDF, Microsoft Office, AutoCAD y más.
### ¿Puedo integrar GroupDocs.Viewer en aplicaciones web?
Sí, GroupDocs.Viewer se puede integrar perfectamente en aplicaciones web para visualizar y manipular documentos.
### ¿Hay una versión de prueba disponible para probar antes de comprar?
Sí, puedes aprovechar una prueba gratuita desde [sitio web](https://releases.groupdocs.com/) para probar las capacidades de GroupDocs.Viewer para .NET.