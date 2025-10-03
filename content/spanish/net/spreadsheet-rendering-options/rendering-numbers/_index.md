---
"description": "Explora el poder de Groupdocs.Viewer para .NET al renderizar archivos Numbers sin problemas. Convierte a HTML, JPG, PNG y PDF sin esfuerzo."
"linktitle": "Representación de números"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Representación de números"
"url": "/es/net/spreadsheet-rendering-options/rendering-numbers/"
"weight": 15
type: docs
---
# Representación de números

## Introducción
Bienvenido a este tutorial paso a paso sobre cómo renderizar archivos de Numbers con Groupdocs.Viewer para .NET. Tanto si eres un desarrollador experimentado como si eres principiante, esta guía te guiará en el proceso de convertir documentos de Numbers a varios formatos. Groupdocs.Viewer para .NET es una potente herramienta que te permite integrar fácilmente las funciones de visualización de documentos en tus aplicaciones .NET.
## Prerrequisitos
Antes de sumergirse en el tutorial, asegúrese de tener los siguientes requisitos previos:
- Un conocimiento práctico del desarrollo en C# y .NET.
- La biblioteca Groupdocs.Viewer para .NET está instalada. Puedes descargarla. [aquí](https://releases.groupdocs.com/viewer/net/).
- Ruta del directorio de documentos donde se guardarán los archivos de salida.
## Importar espacios de nombres
En su proyecto de C#, asegúrese de importar los espacios de nombres necesarios para usar la biblioteca Groupdocs.Viewer:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Paso 1: Configurar el directorio de salida
Antes de empezar a renderizar, defina el directorio de salida donde se guardarán los archivos convertidos. Reemplace "Directorio de su documento" con la ruta real:
```csharp
string outputDirectory = "Your Document Directory";
```
## Paso 2: Renderizar a HTML de varias páginas
Utilice el siguiente código para convertir el archivo Numbers a HTML de varias páginas:
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Paso 3: Renderizar a JPG
Convierta el archivo Numbers al formato JPG con el siguiente código:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Paso 4: Renderizar a PNG
Transforme el archivo Numbers al formato PNG usando el siguiente código:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Paso 5: Renderizar a PDF
Por último, convierta el archivo Numbers al formato PDF utilizando el siguiente código:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
¡Felicitaciones! Ha renderizado correctamente archivos de Numbers en varios formatos con Groupdocs.Viewer para .NET.
## Conclusión
En este tutorial, cubrimos los conceptos básicos de la representación de archivos Numbers con Groupdocs.Viewer para .NET. Esta potente biblioteca proporciona una integración perfecta para visualizar y convertir documentos en sus aplicaciones .NET.
## Preguntas frecuentes
### ¿Puedo utilizar Groupdocs.Viewer para .NET con otros tipos de documentos?
Sí, Groupdocs.Viewer admite una amplia gama de formatos de documentos, incluidos Word, Excel, PDF y más.
### ¿Existe una licencia temporal disponible para fines de prueba?
Sí, puedes obtener una licencia temporal [aquí](https://purchase.groupdocs.com/temporary-license/) para probar.
### ¿Dónde puedo encontrar soporte para Groupdocs.Viewer para .NET?
Visita el [Foro de Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) Para asistencia y discusiones.
### ¿Cómo puedo comprar la versión completa de Groupdocs.Viewer para .NET?
Puedes comprar la versión completa [aquí](https://purchase.groupdocs.com/buy).
### ¿Hay una versión de prueba gratuita disponible?
Sí, puedes explorar la versión de prueba gratuita. [aquí](https://releases.groupdocs.com/).