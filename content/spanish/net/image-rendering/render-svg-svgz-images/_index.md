---
title: Renderizar imágenes SVG y SVGZ
linktitle: Renderizar imágenes SVG y SVGZ
second_title: API GroupDocs.Viewer .NET
description: Aprenda a renderizar imágenes SVG y SVGZ usando GroupDocs.Viewer para .NET. Convierta gráficos vectoriales a HTML, JPG, PNG y PDF sin esfuerzo.
weight: 16
url: /es/net/image-rendering/render-svg-svgz-images/
---
## Introducción
En este tutorial, lo guiaremos a través del proceso de renderizado de imágenes SVG y SVGZ usando GroupDocs.Viewer para .NET. GroupDocs.Viewer para .NET es una potente API de representación de documentos que permite a los desarrolladores representar varios formatos de documentos en sus aplicaciones .NET. SVG y SVGZ son formatos de imagen populares utilizados para gráficos vectoriales y con GroupDocs.Viewer para .NET, puede renderizarlos fácilmente en diferentes formatos de salida, como HTML, JPG, PNG y PDF.
## Requisitos previos
Antes de comenzar, asegúrese de tener instalados y configurados los siguientes requisitos previos:
1.  GroupDocs.Viewer para .NET: descargue e instale GroupDocs.Viewer para .NET desde[aquí](https://releases.groupdocs.com/viewer/net/).
2. Entorno de desarrollo: asegúrese de tener un entorno de desarrollo funcional para el desarrollo .NET, como Visual Studio.
3. Archivo SVGZ de muestra: tenga un archivo SVGZ de muestra listo para probar.

## Importar espacios de nombres
Antes de profundizar en el código, importemos los espacios de nombres necesarios:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Paso 1: renderice SVGZ a HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## Paso 2: renderice SVGZ a JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## Paso 3: renderizar SVGZ a PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Paso 4: renderice SVGZ a PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Conclusión
En este tutorial, hemos aprendido cómo renderizar imágenes SVG y SVGZ usando GroupDocs.Viewer para .NET. Con sólo unos sencillos pasos, puede convertir imágenes SVGZ a varios formatos de salida como HTML, JPG, PNG y PDF, haciéndolas accesibles y visibles en diferentes entornos.
## Preguntas frecuentes
### ¿GrupoDocs.Viewer puede representar otros formatos de imagen?
Sí, GroupDocs.Viewer admite la representación de varios formatos de imagen, incluidos PNG, JPEG, BMP, TIFF, GIF y más.
### ¿GroupDocs.Viewer es compatible con .NET Core?
Sí, GroupDocs.Viewer es compatible tanto con .NET Framework como con .NET Core.
### ¿Puedo personalizar las opciones de renderizado?
Sí, GroupDocs.Viewer proporciona amplias opciones de renderizado que le permiten personalizar la salida según sus requisitos.
### ¿GroupDocs.Viewer requiere dependencias de terceros?
No, GroupDocs.Viewer es una API independiente y no requiere dependencias de terceros para representar documentos.
### ¿Existe una versión de prueba disponible para probar?
Sí, puede descargar una versión de prueba gratuita de GroupDocs.Viewer desde[aquí](https://releases.groupdocs.com/) para evaluar sus características antes de realizar una compra.