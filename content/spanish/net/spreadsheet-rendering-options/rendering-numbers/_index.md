---
title: Representar números
linktitle: Representar números
second_title: API GroupDocs.Viewer .NET
description: Explore el poder de Groupdocs.Viewer para .NET para renderizar archivos de Numbers sin problemas. Convierta a HTML, JPG, PNG y PDF sin esfuerzo.
weight: 15
url: /es/net/spreadsheet-rendering-options/rendering-numbers/
---
## Introducción
Bienvenido a este tutorial paso a paso sobre cómo renderizar archivos de Numbers usando Groupdocs.Viewer para .NET. Ya seas un desarrollador experimentado o un principiante, esta guía te guiará a través del proceso de conversión de documentos de Numbers a varios formatos. Groupdocs.Viewer para .NET es una poderosa herramienta que le permite integrar perfectamente capacidades de visualización de documentos en sus aplicaciones .NET.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
- Un conocimiento práctico del desarrollo de C# y .NET.
-  Groupdocs.Viewer para la biblioteca .NET instalada. Puedes descargarlo[aquí](https://releases.groupdocs.com/viewer/net/).
- La ruta del directorio de documentos donde se guardarán los archivos de salida.
## Importar espacios de nombres
En su proyecto C#, asegúrese de importar los espacios de nombres necesarios para usar la biblioteca Groupdocs.Viewer:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Paso 1: configurar el directorio de salida
Antes de comenzar a renderizar, defina el directorio de salida donde se guardarán los archivos convertidos. Reemplace "Su directorio de documentos" con la ruta real:
```csharp
string outputDirectory = "Your Document Directory";
```
## Paso 2: renderizar en HTML de varias páginas
Utilice el siguiente código para convertir el archivo de Numbers a HTML de varias páginas:
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Paso 3: renderizar a JPG
Convierta el archivo de Numbers al formato JPG con el siguiente código:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Paso 4: renderizar a PNG
Transforme el archivo de Numbers al formato PNG usando el siguiente código:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Paso 5: renderizar a PDF
Por último, convierta el archivo de Numbers a formato PDF usando el siguiente código:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
¡Felicidades! Ha procesado correctamente archivos de Numbers en varios formatos utilizando Groupdocs.Viewer para .NET.
## Conclusión
En este tutorial, cubrimos los conceptos básicos de la representación de archivos de Numbers usando Groupdocs.Viewer para .NET. Esta poderosa biblioteca proporciona una integración perfecta para ver y convertir documentos en sus aplicaciones .NET.
## Preguntas frecuentes
### ¿Puedo utilizar Groupdocs.Viewer para .NET con otros tipos de documentos?
Sí, Groupdocs.Viewer admite una amplia gama de formatos de documentos, incluidos Word, Excel, PDF y más.
### ¿Hay una licencia temporal disponible para fines de prueba?
 Sí, puedes obtener una licencia temporal.[aquí](https://purchase.groupdocs.com/temporary-license/) para las pruebas.
### ¿Dónde puedo encontrar soporte para Groupdocs.Viewer para .NET?
 Visita el[Foro Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) para ayuda y discusiones.
### ¿Cómo compro la versión completa de Groupdocs.Viewer para .NET?
 Puedes adquirir la versión completa.[aquí](https://purchase.groupdocs.com/buy).
### ¿Existe una versión de prueba gratuita disponible?
 Sí, puedes explorar la versión de prueba gratuita.[aquí](https://releases.groupdocs.com/).