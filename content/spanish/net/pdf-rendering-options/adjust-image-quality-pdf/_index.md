---
"description": "Aprenda a ajustar la calidad de imagen en documentos PDF con GroupDocs.Viewer para .NET. Siga nuestro tutorial paso a paso para una integración perfecta."
"linktitle": "Ajustar la calidad de la imagen en PDF"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Ajustar la calidad de la imagen en PDF"
"url": "/es/net/pdf-rendering-options/adjust-image-quality-pdf/"
"weight": 10
type: docs
---
# Ajustar la calidad de la imagen en PDF

## Introducción
GroupDocs.Viewer para .NET es una potente biblioteca que permite a los desarrolladores integrar fácilmente funciones de renderizado de documentos en sus aplicaciones .NET. Una de sus características clave es la posibilidad de ajustar la calidad de la imagen al renderizar documentos PDF. En este tutorial, le guiaremos paso a paso en el proceso de ajuste de la calidad de la imagen con GroupDocs.Viewer para .NET.

![Ajuste la calidad de la imagen en PDF con GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/adjust-image-quality-in-pdf.png)

## Prerrequisitos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1. Conocimientos básicos de programación en C#.
2. Visual Studio instalado en su sistema.
3. Se descargó e instaló la biblioteca GroupDocs.Viewer para .NET. Puede descargarla desde [aquí](https://releases.groupdocs.com/viewer/net/).

## Importar espacios de nombres
Primero, debe importar los espacios de nombres necesarios para trabajar con GroupDocs.Viewer para .NET:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Paso 1: Definir el directorio de salida
```csharp
string outputDirectory = "Your Document Directory";
```
Reemplazar `"Your Document Directory"` con la ruta donde desea guardar las páginas HTML renderizadas.
## Paso 2: Definir el formato de la ruta del archivo de página
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Esta línea define el formato de la ruta del archivo de cada página HTML renderizada. `{0}` es un marcador de posición para el número de página.
## Paso 3: Ajustar la calidad de la imagen
```csharp
using (Viewer viewer = new Viewer("Your PDF File Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.ImageQuality = ImageQuality.Medium;
    viewer.View(options);
}
```
Reemplazar `"Your PDF File Path"` con la ruta a su documento PDF.
## Paso 4: Mostrar la ruta de salida
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Esta línea muestra la ruta donde se guardan las páginas HTML renderizadas.

## Conclusión
En este tutorial, aprendimos a ajustar la calidad de imagen al renderizar documentos PDF con GroupDocs.Viewer para .NET. Siguiendo los sencillos pasos descritos anteriormente, podrá personalizar fácilmente la calidad de imagen según sus necesidades.
## Preguntas frecuentes
### ¿Puedo ajustar la calidad de la imagen para otros formatos de documentos además de PDF?
Sí, GroupDocs.Viewer para .NET admite varios formatos de documentos y puede ajustar la calidad de la imagen para la mayoría de ellos.
### ¿Cuáles son las opciones de calidad de imagen disponibles?
GroupDocs.Viewer para .NET ofrece opciones de calidad de imagen baja, media y alta.
### ¿Hay alguna forma de obtener una vista previa del documento antes de renderizarlo con la calidad de imagen ajustada?
Sí, puede utilizar GroupDocs.Viewer para .NET para generar vistas previas de documentos con diferentes configuraciones de calidad de imagen.
### ¿GroupDocs.Viewer para .NET requiere una licencia para uso comercial?
Sí, necesita obtener una licencia para uso comercial. Puede comprar una licencia en [aquí](https://purchase.groupdocs.com/buy).
### ¿Dónde puedo obtener soporte para GroupDocs.Viewer para .NET?
Puede obtener ayuda en el foro de GroupDocs.Viewer [aquí](https://forum.groupdocs.com/c/viewer/9).