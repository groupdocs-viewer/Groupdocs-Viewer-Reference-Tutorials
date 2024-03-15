---
title: Renderizar notas y ajustar unidades de tiempo (MS Project)
linktitle: Renderizar notas y ajustar unidades de tiempo (MS Project)
second_title: API GroupDocs.Viewer .NET
description: Domine la renderización de documentos de MS Project con GroupDocs.Viewer para .NET. Procese notas, ajuste unidades de tiempo y explore varios formatos de salida sin esfuerzo.
type: docs
weight: 11
url: /es/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/
---
## Introducción
GroupDocs.Viewer para .NET es una potente API de representación de documentos que permite a los desarrolladores ver y manipular varios formatos de documentos dentro de sus aplicaciones .NET. En este tutorial, nos centraremos en representar notas y ajustar unidades de tiempo específicamente para documentos de MS Project.
## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1. GroupDocs.Viewer para .NET: asegúrese de haber descargado e instalado la biblioteca GroupDocs.Viewer para .NET. Puedes descargarlo desde[aquí](https://releases.groupdocs.com/viewer/net/).
2. Entorno de desarrollo: configure su entorno de desarrollo preferido con soporte .NET.
3. Documento de MS Project: tenga un documento de muestra de MS Project listo para probar.
## Importar espacios de nombres
Primero, importemos los espacios de nombres necesarios para comenzar a renderizar documentos de MS Project:
## Paso 1: importar espacios de nombres
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Ahora que hemos importado los espacios de nombres necesarios, dividamos cada ejemplo en varios pasos para lograr una comprensión integral.
## Representar un documento de MS Project a HTML
Para representar un documento de MS Project en formato HTML con notas incluidas, siga estos pasos:
### Paso 2: configurar el directorio de salida y el formato de archivo
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### Paso 3: inicializar el objeto del visor y configurar las opciones
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### Paso 4: renderizar documento a HTML
```csharp
viewer.View(options);
```
## Representación de documentos de MS Project a formatos de imagen
También puede renderizar documentos de MS Project en formatos de imagen como JPG y PNG. Así es cómo:
### Paso 5: configurar el directorio de salida y el formato de archivo para JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### Paso 6: Inicialice el objeto del visor y establezca las opciones JPG
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Paso 7: renderizar el documento a JPG
```csharp
viewer.View(options);
```
Repita pasos similares para renderizar a PNG y otros formatos de imagen.
## Representar un documento de MS Project a PDF
Para renderizar un documento de MS Project a formato PDF, proceda de la siguiente manera:
### Paso 8: configurar el directorio de salida y el formato de archivo para PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### Paso 9: inicialice el objeto del visor y establezca las opciones de PDF
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Paso 10: renderizar documento a PDF
```csharp
viewer.View(options);
```

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo renderizar documentos de MS Project y ajustar unidades de tiempo usando GroupDocs.Viewer para .NET. Incorpore este conocimiento en sus proyectos para mejorar las capacidades de visualización de documentos.
## Preguntas frecuentes
### ¿Puedo renderizar documentos de MS Project en otros formatos además de HTML, imágenes y PDF?
Sí, GroupDocs.Viewer para .NET admite la renderización en varios formatos, como DOCX, XLSX, PPTX y más.
### ¿Existe una versión de prueba disponible para GroupDocs.Viewer para .NET?
 Sí, puedes obtener una prueba gratuita desde[aquí](https://releases.groupdocs.com/).
### ¿Cómo puedo obtener una licencia temporal para GroupDocs.Viewer para .NET?
 Visita[este enlace](https://purchase.groupdocs.com/temporary-license/) para obtener una licencia temporal.
### ¿Dónde puedo encontrar documentación para GroupDocs.Viewer para .NET?
 Consulte la documentación.[aquí](https://reference.groupdocs.com/viewer/net/).
### ¿Dónde puedo buscar soporte o hacer preguntas relacionadas con GroupDocs.Viewer para .NET?
 Puedes visitar el foro de soporte.[aquí](https://forum.groupdocs.com/c/viewer/9).