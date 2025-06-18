---
"description": "Aprenda a renderizar imágenes SVG y SVGZ con GroupDocs.Viewer para .NET. Convierta gráficos vectoriales a HTML, JPG, PNG y PDF fácilmente."
"linktitle": "Renderizar imágenes SVG y SVGZ"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Renderizar imágenes SVG y SVGZ"
"url": "/es/net/image-rendering/render-svg-svgz-images/"
"weight": 16
---

# Renderizar imágenes SVG y SVGZ

## Introducción
En este tutorial, le guiaremos a través del proceso de renderizado de imágenes SVG y SVGZ con GroupDocs.Viewer para .NET. GroupDocs.Viewer para .NET es una potente API de renderizado de documentos que permite a los desarrolladores renderizar diversos formatos de documentos en sus aplicaciones .NET. SVG y SVGZ son formatos de imagen populares para gráficos vectoriales, y con GroupDocs.Viewer para .NET, puede renderizarlos fácilmente en diferentes formatos de salida, como HTML, JPG, PNG y PDF.

![Renderizar imágenes SVG y SVGZ con GroupDocs.Viewer para .NET](/viewer/image-rendering/render-svg-and-svgz-images.png)

## Prerrequisitos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos instalados y configurados:
1. GroupDocs.Viewer para .NET: Descargue e instale GroupDocs.Viewer para .NET desde [aquí](https://releases.groupdocs.com/viewer/net/).
2. Entorno de desarrollo: asegúrese de tener un entorno de desarrollo funcional para el desarrollo .NET, como Visual Studio.
3. Archivo SVGZ de muestra: tenga un archivo SVGZ de muestra listo para probar.

## Importar espacios de nombres
Antes de sumergirnos en el código, importemos los espacios de nombres necesarios:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Paso 1: Renderizar SVGZ a HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## Paso 2: Convertir SVGZ a JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## Paso 3: Convertir SVGZ a PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Paso 4: Convertir SVGZ a PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Conclusión
En este tutorial, aprendimos a renderizar imágenes SVG y SVGZ con GroupDocs.Viewer para .NET. Con solo unos sencillos pasos, puedes convertir imágenes SVGZ a varios formatos de salida como HTML, JPG, PNG y PDF, haciéndolas accesibles y visibles en diferentes entornos.
## Preguntas frecuentes
### ¿Puede GroupDocs.Viewer renderizar otros formatos de imagen?
Sí, GroupDocs.Viewer admite la representación de varios formatos de imagen, incluidos PNG, JPEG, BMP, TIFF, GIF y más.
### ¿GroupDocs.Viewer es compatible con .NET Core?
Sí, GroupDocs.Viewer es compatible con .NET Framework y .NET Core.
### ¿Puedo personalizar las opciones de renderizado?
Sí, GroupDocs.Viewer ofrece amplias opciones de renderizado que le permiten personalizar la salida según sus requisitos.
### ¿GroupDocs.Viewer requiere alguna dependencia de terceros?
No, GroupDocs.Viewer es una API independiente y no requiere dependencias de terceros para representar documentos.
### ¿Hay una versión de prueba disponible para probar?
Sí, puedes descargar una versión de prueba gratuita de GroupDocs.Viewer desde [aquí](https://releases.groupdocs.com/) para evaluar sus características antes de realizar la compra.