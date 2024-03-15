---
title: Renderizar imágenes FODG y ODG
linktitle: Renderizar imágenes FODG y ODG
second_title: API GroupDocs.Viewer .NET
description: Aprenda a renderizar imágenes FODG y ODG en HTML, JPG, PNG y PDF utilizando GroupDocs.Viewer para .NET. Mejore su manejo de documentos.
type: docs
weight: 15
url: /es/net/image-rendering/render-fodg-odg-images/
---
## Introducción
En el mundo del desarrollo de software, el manejo eficiente de los formatos de documentos es primordial. GroupDocs.Viewer para .NET es una poderosa herramienta diseñada para simplificar el proceso de renderizado de imágenes FODG y ODG dentro de aplicaciones .NET. Este tutorial lo guiará a través de los pasos necesarios para representar estas imágenes en varios formatos, como HTML, JPG, PNG y PDF, utilizando GroupDocs.Viewer para .NET.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de tener los siguientes requisitos previos:
1.  GroupDocs.Viewer para .NET: descargue e instale GroupDocs.Viewer para .NET desde[aquí](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: asegúrese de tener .NET Framework instalado en su sistema.
3. Conocimientos básicos de C#: será útil estar familiarizado con el lenguaje de programación C#.

## Importar espacios de nombres
Antes de comenzar con la implementación, importe los espacios de nombres necesarios:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Paso 1: configurar el directorio de salida
```csharp
string outputDirectory = "Your Document Directory";
```
 Reemplazar`"Your Document Directory"`con la ruta del directorio donde desea guardar las imágenes renderizadas.
## Paso 2: renderizar en HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
Este paso procesa la imagen FODG en formato HTML.
## Paso 3: renderizar a JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Aquí, la imagen FODG se renderiza en formato JPG.
## Paso 4: renderizar a PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Este paso convierte la imagen FODG al formato PNG.
## Paso 5: renderizar a PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Finalmente, la imagen FODG se procesa en formato PDF.

## Conclusión
En este tutorial, exploramos cómo renderizar imágenes FODG y ODG en varios formatos usando GroupDocs.Viewer para .NET. Si sigue estos pasos, podrá integrar perfectamente las capacidades de representación de documentos en sus aplicaciones .NET.
## Preguntas frecuentes
### ¿GroupDocs.Viewer para .NET es compatible con todas las versiones de .NET Framework?
GroupDocs.Viewer para .NET es compatible con una amplia gama de versiones de .NET Framework, incluidas las más recientes.
### ¿Puedo representar documentos de forma asincrónica con GroupDocs.Viewer para .NET?
Sí, GroupDocs.Viewer para .NET proporciona capacidades de representación asincrónica para mejorar el rendimiento.
### ¿GroupDocs.Viewer para .NET admite la representación de documentos cifrados?
Sí, GroupDocs.Viewer para .NET admite la representación de documentos cifrados con las claves de descifrado adecuadas.
### ¿Es posible personalizar la salida de renderizado con GroupDocs.Viewer para .NET?
Por supuesto, GroupDocs.Viewer para .NET ofrece varias opciones de personalización para adaptar la salida de renderizado a sus requisitos.
### ¿Puedo renderizar documentos desde ubicaciones de almacenamiento remotas usando GroupDocs.Viewer para .NET?
Sí, GroupDocs.Viewer para .NET admite la representación de documentos desde ubicaciones de almacenamiento locales y remotas.