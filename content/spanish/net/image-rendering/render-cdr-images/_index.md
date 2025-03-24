---
title: Renderizar imágenes CDR
linktitle: Renderizar imágenes CDR
second_title: API GroupDocs.Viewer .NET
description: Aprenda a renderizar imágenes CDR en HTML, JPG, PNG y PDF utilizando GroupDocs.Viewer para .NET. Convierta fácilmente archivos CorelDRAW con este tutorial.
weight: 12
url: /es/net/image-rendering/render-cdr-images/
---

# Renderizar imágenes CDR

## Introducción
En este tutorial, lo guiaremos a través del proceso de renderizado de imágenes CDR (CorelDRAW) usando GroupDocs.Viewer para .NET. CDR es un formato de archivo asociado principalmente con CorelDRAW, un editor de gráficos vectoriales. Con GroupDocs.Viewer, puede convertir fácilmente archivos CDR a varios formatos como HTML, JPG, PNG y PDF.
## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1.  GroupDocs.Viewer para .NET: asegúrese de haber instalado GroupDocs.Viewer para .NET. Puedes descargarlo desde[aquí](https://releases.groupdocs.com/viewer/net/).
2. Directorio de documentos: prepare un directorio donde desee guardar las imágenes renderizadas.
3. Conocimientos básicos de C#: es necesario estar familiarizado con el lenguaje de programación C# para comprender los ejemplos de código.
## Importar espacios de nombres
Antes de profundizar en los ejemplos de código, importe los espacios de nombres necesarios en su archivo C#:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Ahora, dividamos cada ejemplo en varios pasos:
## Representación a HTML
1. Defina el directorio de salida donde desea guardar los archivos HTML renderizados:
```csharp
string outputDirectory = "Your Document Directory";
```
2. Especifique el formato de la ruta del archivo para archivos HTML:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. Utilice la clase Viewer para representar el archivo CDR en HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Renderizado a JPG
1. Defina el formato de ruta del archivo para archivos JPG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. Utilice la clase Viewer para renderizar el archivo CDR a JPG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Renderizado a PNG
1. Defina el formato de ruta de archivo para archivos PNG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. Utilice la clase Viewer para representar el archivo CDR en PNG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Renderizado a PDF
1. Defina el formato de ruta del archivo para PDF:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. Utilice la clase Viewer para representar el archivo CDR en PDF:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3.  Opcionalmente, puede especificar opciones de renderizado o renderizar páginas específicas pasando parámetros adicionales al`viewer.View()` método.
## Conclusión
Renderizar imágenes CDR en varios formatos como HTML, JPG, PNG y PDF utilizando GroupDocs.Viewer para .NET es un proceso sencillo. Si sigue los pasos descritos en este tutorial, puede convertir archivos CDR de manera eficiente a diferentes formatos según sus requisitos.
## Preguntas frecuentes
### ¿GroupDocs.Viewer para .NET es compatible con todas las versiones de archivos CDR?
GroupDocs.Viewer para .NET admite la representación de archivos CDR creados con diferentes versiones de CorelDRAW.
### ¿Puedo personalizar la salida de los archivos renderizados?
Sí, GroupDocs.Viewer para .NET proporciona varias opciones para personalizar la salida, como ajustar la calidad de la imagen, configurar una marca de agua, etc.
### ¿GroupDocs.Viewer para .NET requiere dependencias externas?
No, GroupDocs.Viewer para .NET es una biblioteca independiente y no requiere dependencias externas para representar documentos.
### ¿Existe una versión de prueba disponible para GroupDocs.Viewer para .NET?
 Sí, puede descargar una versión de prueba gratuita de GroupDocs.Viewer para .NET desde[aquí](https://releases.groupdocs.com/).
### ¿Dónde puedo obtener soporte para GroupDocs.Viewer para .NET?
 Puede obtener soporte en el foro de la comunidad GroupDocs.Viewer.[aquí](https://forum.groupdocs.com/c/viewer/9).