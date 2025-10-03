---
"description": "Domine la renderización de documentos de MS Project con GroupDocs.Viewer para .NET. Renderice notas, ajuste las unidades de tiempo y explore diversos formatos de salida sin esfuerzo."
"linktitle": "Notas de renderizado y ajuste de unidades de tiempo (MS Project)"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Notas de renderizado y ajuste de unidades de tiempo (MS Project)"
"url": "/es/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/"
"weight": 11
type: docs
---
# Notas de renderizado y ajuste de unidades de tiempo (MS Project)

## Introducción
GroupDocs.Viewer para .NET es una potente API de renderizado de documentos que permite a los desarrolladores visualizar y manipular diversos formatos de documentos en sus aplicaciones .NET. En este tutorial, nos centraremos en el renderizado de notas y el ajuste de unidades de tiempo específicamente para documentos de MS Project.
## Prerrequisitos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1. GroupDocs.Viewer para .NET: Asegúrese de haber descargado e instalado la biblioteca GroupDocs.Viewer para .NET. Puede descargarla desde [aquí](https://releases.groupdocs.com/viewer/net/).
2. Entorno de desarrollo: configure su entorno de desarrollo preferido con soporte .NET.
3. Documento de MS Project: tenga listo un documento de MS Project de muestra para probar.
## Importar espacios de nombres
Primero, importemos los espacios de nombres necesarios para comenzar a renderizar documentos de MS Project:
## Paso 1: Importar espacios de nombres
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Ahora que hemos importado los espacios de nombres necesarios, analicemos cada ejemplo en varios pasos para lograr una comprensión completa.
## Representación de un documento de MS Project en HTML
Para convertir un documento de MS Project en formato HTML con notas incluidas, siga estos pasos:
### Paso 2: Establecer el directorio de salida y el formato de archivo
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### Paso 3: Inicializar el objeto Visor y configurar las opciones
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### Paso 4: Renderizar el documento a HTML
```csharp
viewer.View(options);
```
## Representación de documentos de MS Project en formatos de imagen
También puedes renderizar documentos de MS Project a formatos de imagen como JPG y PNG. Aquí te explicamos cómo:
### Paso 5: Establecer el directorio de salida y el formato de archivo para JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### Paso 6: Inicializar el objeto Visor y configurar las opciones JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Paso 7: Renderizar el documento a JPG
```csharp
viewer.View(options);
```
Repita pasos similares para renderizar a PNG y otros formatos de imagen.
## Convertir un documento de MS Project en PDF
Para convertir un documento de MS Project en formato PDF, proceda de la siguiente manera:
### Paso 8: Establecer el directorio de salida y el formato de archivo para PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### Paso 9: Inicializar el objeto Visor y configurar las opciones de PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Paso 10: Convertir el documento a PDF
```csharp
viewer.View(options);
```

## Conclusión
¡Felicitaciones! Has aprendido a renderizar documentos de MS Project y a ajustar unidades de tiempo con GroupDocs.Viewer para .NET. Incorpora estos conocimientos a tus proyectos para mejorar la visualización de documentos.
## Preguntas frecuentes
### ¿Puedo renderizar documentos de MS Project en otros formatos además de HTML, imágenes y PDF?
Sí, GroupDocs.Viewer para .NET admite la representación en varios formatos, como DOCX, XLSX, PPTX y más.
### ¿Hay una versión de prueba disponible para GroupDocs.Viewer para .NET?
Sí, puedes obtener una prueba gratuita desde [aquí](https://releases.groupdocs.com/).
### ¿Cómo puedo obtener una licencia temporal para GroupDocs.Viewer para .NET?
Visita [este enlace](https://purchase.groupdocs.com/temporary-license/) para obtener una licencia temporal.
### ¿Dónde puedo encontrar documentación de GroupDocs.Viewer para .NET?
Consulte la documentación [aquí](https://tutorials.groupdocs.com/viewer/net/).
### ¿Dónde puedo buscar ayuda o hacer preguntas relacionadas con GroupDocs.Viewer para .NET?
Puedes visitar el foro de soporte [aquí](https://forum.groupdocs.com/c/viewer/9).