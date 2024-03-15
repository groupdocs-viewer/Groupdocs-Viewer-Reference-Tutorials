---
title: Ajustar la calidad de la imagen en PDF
linktitle: Ajustar la calidad de la imagen en PDF
second_title: API GroupDocs.Viewer .NET
description: Aprenda a ajustar la calidad de la imagen en documentos PDF usando GroupDocs.Viewer para .NET. Siga nuestro tutorial paso a paso para una integración perfecta.
type: docs
weight: 10
url: /es/net/pdf-rendering-options/adjust-image-quality-pdf/
---
## Introducción
GroupDocs.Viewer para .NET es una poderosa biblioteca que permite a los desarrolladores integrar capacidades de representación de documentos en sus aplicaciones .NET sin esfuerzo. Una de las características clave de esta biblioteca es la capacidad de ajustar la calidad de la imagen al renderizar documentos PDF. En este tutorial, lo guiaremos a través del proceso de ajuste de la calidad de la imagen paso a paso usando GroupDocs.Viewer para .NET.
## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1. Conocimientos básicos de programación en C#.
2. Visual Studio instalado en su sistema.
3. Biblioteca GroupDocs.Viewer para .NET descargada e instalada. Puedes descargarlo desde[aquí](https://releases.groupdocs.com/viewer/net/).

## Importar espacios de nombres
Primero, necesita importar los espacios de nombres necesarios para trabajar con GroupDocs.Viewer para .NET:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Paso 1: definir el directorio de salida
```csharp
string outputDirectory = "Your Document Directory";
```
 Reemplazar`"Your Document Directory"` con la ruta donde desea guardar las páginas HTML renderizadas.
## Paso 2: Definir el formato de ruta del archivo de página
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Esta línea define el formato de la ruta del archivo de cada página HTML representada.`{0}` es un marcador de posición para el número de página.
## Paso 3: ajustar la calidad de la imagen
```csharp
using (Viewer viewer = new Viewer("Your PDF File Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.ImageQuality = ImageQuality.Medium;
    viewer.View(options);
}
```
 Reemplazar`"Your PDF File Path"` con la ruta a su documento PDF.
## Paso 4: Mostrar ruta de salida
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Esta línea muestra la ruta donde se guardan las páginas HTML renderizadas.

## Conclusión
En este tutorial, aprendimos cómo ajustar la calidad de la imagen al renderizar documentos PDF usando GroupDocs.Viewer para .NET. Siguiendo los sencillos pasos descritos anteriormente, podrá personalizar fácilmente la calidad de la imagen según sus requisitos.
## Preguntas frecuentes
### ¿Puedo ajustar la calidad de la imagen para otros formatos de documentos además de PDF?
Sí, GroupDocs.Viewer para .NET admite varios formatos de documentos y puede ajustar la calidad de la imagen para la mayoría de ellos.
### ¿Cuáles son las opciones de calidad de imagen disponibles?
GroupDocs.Viewer para .NET ofrece opciones de calidad de imagen baja, media y alta.
### ¿Existe alguna forma de obtener una vista previa del documento antes de renderizarlo con una calidad de imagen ajustada?
Sí, puede utilizar GroupDocs.Viewer para .NET para generar vistas previas de documentos con diferentes configuraciones de calidad de imagen.
### ¿GroupDocs.Viewer para .NET requiere una licencia para uso comercial?
 Sí, necesita obtener una licencia para uso comercial. Puede adquirir una licencia en[aquí](https://purchase.groupdocs.com/buy).
### ¿Dónde puedo obtener soporte para GroupDocs.Viewer para .NET?
 Puede obtener soporte en el foro GroupDocs.Viewer[aquí](https://forum.groupdocs.com/c/viewer/9).