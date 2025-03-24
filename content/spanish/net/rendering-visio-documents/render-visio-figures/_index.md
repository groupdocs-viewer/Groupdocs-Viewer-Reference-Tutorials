---
title: Renderizar figuras de Visio
linktitle: Renderizar figuras de Visio
second_title: API GroupDocs.Viewer .NET
description: Aprenda a representar figuras de Visio usando GroupDocs.Viewer para .NET con este completo. Mejore las capacidades de visualización de documentos en sus aplicaciones .NET.
weight: 10
url: /es/net/rendering-visio-documents/render-visio-figures/
---

# Renderizar figuras de Visio

## Introducción
En la era digital actual, la representación de documentos desempeña un papel crucial en diversas aplicaciones. Ya sea para mostrar documentos en un sitio web o convertirlos a diferentes formatos, la renderización eficiente es esencial. GroupDocs.Viewer para .NET proporciona una solución sólida para ver y manipular documentos dentro de aplicaciones .NET. En este tutorial, profundizaremos en la representación de figuras de Visio usando GroupDocs.Viewer para .NET, dividiendo el proceso en pasos simples.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de tener los siguientes requisitos previos:
1. Configuración del entorno: asegúrese de tener un entorno de trabajo para el desarrollo .NET.
2.  GroupDocs.Viewer para .NET: descargue e instale GroupDocs.Viewer para .NET desde[enlace de descarga](https://releases.groupdocs.com/viewer/net/).
3. Comprensión básica de C#: familiarícese con los fundamentos del lenguaje de programación C#.
4. Documento de Visio de muestra: tenga un documento de Visio de muestra listo para renderizar.

## Importar espacios de nombres
En su proyecto C#, comience importando los espacios de nombres necesarios:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. Representación a HTML
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
- Directorio de salida: defina el directorio donde se guardará el HTML renderizado.
- Formato de ruta del archivo de página: especifique el formato de ruta de la página HTML.
- Inicialización del visor: inicializa el objeto Visor con la ruta al documento de Visio.
- Opciones de vista HTML: configure opciones para representar HTML.
- Opciones de renderizado de Visio: establezca opciones específicas para el renderizado de Visio, como renderizar solo figuras y ancho de figura.
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
- De manera similar a renderizar en HTML, configure las opciones para renderizar en formato JPG.
## 3. Representación a PNG
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
- La configuración para renderizar en formato PNG sigue un patrón similar al de renderizado JPG.
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
En este tutorial, exploramos cómo representar figuras de Visio usando GroupDocs.Viewer para .NET. Si sigue la guía paso a paso, podrá integrar perfectamente las capacidades de representación de documentos en sus aplicaciones .NET, mejorando la experiencia del usuario y la productividad.
## Preguntas frecuentes
### ¿Puedo personalizar las opciones de renderizado de las figuras de Visio?
Sí, GroupDocs.Viewer para .NET ofrece amplias opciones para personalizar la representación, incluido el ancho de las figuras, representar solo figuras y más.
### ¿GroupDocs.Viewer para .NET es adecuado para la representación de documentos a gran escala?
Por supuesto, GroupDocs.Viewer para .NET está optimizado para manejar la representación de documentos a gran escala de manera eficiente.
### ¿GroupDocs.Viewer admite otros formatos de documentos además de Visio?
Sí, GroupDocs.Viewer admite una amplia gama de formatos de documentos, incluidos PDF, Microsoft Office, AutoCAD y más.
### ¿Puedo integrar GroupDocs.Viewer en aplicaciones web?
Sí, GroupDocs.Viewer se puede integrar perfectamente en aplicaciones web para visualización y manipulación de documentos.
### ¿Existe una versión de prueba disponible para probar antes de comprar?
Sí, puedes aprovechar una prueba gratuita desde el[sitio web](https://releases.groupdocs.com/) para probar las capacidades de GroupDocs.Viewer para .NET.