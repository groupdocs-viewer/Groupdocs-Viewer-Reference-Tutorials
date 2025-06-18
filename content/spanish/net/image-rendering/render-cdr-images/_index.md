---
"description": "Aprenda a renderizar imágenes CDR a HTML, JPG, PNG y PDF con GroupDocs.Viewer para .NET. Convierta fácilmente archivos de CorelDRAW con este tutorial."
"linktitle": "Renderizar imágenes CDR"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Renderizar imágenes CDR"
"url": "/es/net/image-rendering/render-cdr-images/"
"weight": 12
---

# Renderizar imágenes CDR

## Introducción
En este tutorial, le guiaremos a través del proceso de renderizado de imágenes CDR (CorelDRAW) con GroupDocs.Viewer para .NET. CDR es un formato de archivo asociado principalmente con CorelDRAW, un editor de gráficos vectoriales. Con GroupDocs.Viewer, puede convertir fácilmente archivos CDR a diversos formatos como HTML, JPG, PNG y PDF.

![Renderizar imágenes CDR con GroupDocs.Viewer para .NET](/viewer/image-rendering/render-cdr-images.png)

## Prerrequisitos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1. GroupDocs.Viewer para .NET: Asegúrese de tener instalado GroupDocs.Viewer para .NET. Puede descargarlo desde [aquí](https://releases.groupdocs.com/viewer/net/).
2. Directorio de documentos: prepare un directorio donde desee guardar las imágenes renderizadas.
3. Conocimientos básicos de C#: Es necesario estar familiarizado con el lenguaje de programación C# para comprender los ejemplos de código.
## Importar espacios de nombres
Antes de sumergirnos en los ejemplos de código, importe los espacios de nombres necesarios en su archivo C#:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Ahora, vamos a dividir cada ejemplo en varios pasos:
## Representación en HTML
1. Define el directorio de salida donde quieres guardar los archivos HTML renderizados:
```csharp
string outputDirectory = "Your Document Directory";
```
2. Especifique el formato de la ruta del archivo para los archivos HTML:
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
1. Define el formato de ruta de archivo para archivos JPG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. Utilice la clase Viewer para renderizar el archivo CDR en JPG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Renderizado a PNG
1. Define el formato de ruta de archivo para archivos PNG:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. Utilice la clase Viewer para renderizar el archivo CDR en PNG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Renderizado a PDF
1. Define el formato de ruta de archivo para PDF:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. Utilice la clase Viewer para convertir el archivo CDR a PDF:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3. Opcionalmente, puede especificar opciones de representación o representar páginas específicas pasando parámetros adicionales al `viewer.View()` método.
## Conclusión
Renderizar imágenes CDR a diversos formatos como HTML, JPG, PNG y PDF con GroupDocs.Viewer para .NET es un proceso sencillo. Siguiendo los pasos de este tutorial, podrá convertir archivos CDR a diferentes formatos según sus necesidades.
## Preguntas frecuentes
### ¿GroupDocs.Viewer para .NET es compatible con todas las versiones de archivos CDR?
GroupDocs.Viewer para .NET admite la representación de archivos CDR creados por diferentes versiones de CorelDRAW.
### ¿Puedo personalizar la salida de los archivos renderizados?
Sí, GroupDocs.Viewer para .NET ofrece varias opciones para personalizar la salida, como ajustar la calidad de la imagen, configurar una marca de agua, etc.
### ¿GroupDocs.Viewer para .NET requiere alguna dependencia externa?
No, GroupDocs.Viewer para .NET es una biblioteca independiente y no requiere ninguna dependencia externa para representar documentos.
### ¿Hay una versión de prueba disponible para GroupDocs.Viewer para .NET?
Sí, puede descargar una versión de prueba gratuita de GroupDocs.Viewer para .NET desde [aquí](https://releases.groupdocs.com/).
### ¿Dónde puedo obtener soporte para GroupDocs.Viewer para .NET?
Puede obtener ayuda del foro de la comunidad de GroupDocs.Viewer [aquí](https://forum.groupdocs.com/c/viewer/9).