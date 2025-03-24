---
title: Representar carpetas específicas y filtrar mensajes (Outlook)
linktitle: Representar carpetas específicas y filtrar mensajes (Outlook)
second_title: API GroupDocs.Viewer .NET
description: Aprenda a representar carpetas específicas y filtrar mensajes en Outlook usando GroupDocs.Viewer para .NET. Simplifique la gestión de documentos en aplicaciones .NET.
weight: 11
url: /es/net/rendering-outlook-data-files/render-specific-folders-and-filter-messages-outlook/
---
## Introducción
En el mundo del desarrollo .NET, administrar y mostrar documentos de manera eficiente es crucial. GroupDocs.Viewer para .NET simplifica esta tarea al proporcionar potentes funcionalidades para representar varios formatos de documentos sin problemas. En este tutorial, profundizaremos en cómo representar carpetas específicas y filtrar mensajes en Outlook usando GroupDocs.Viewer para .NET.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de tener lo siguiente:
1.  GroupDocs.Viewer para .NET: asegúrese de haber instalado GroupDocs.Viewer para .NET. Puedes descargarlo desde el[sitio web](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Debe tener .NET Framework instalado en su máquina.
3. Comprensión básica de C#: será beneficioso seguir la familiaridad con el lenguaje de programación C# junto con el tutorial.

## Importar espacios de nombres
En primer lugar, importemos los espacios de nombres necesarios a nuestro código C#:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Paso 1: definir el directorio de salida
```csharp
string outputDirectory = "Your Document Directory";
```
 Reemplazar`"Your Document Directory"` con la ruta del directorio donde desea que se guarden los documentos renderizados.
## Paso 2: Definir el formato de ruta del archivo de página
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Esta línea define el formato de las rutas de archivo de cada página renderizada. En este ejemplo, generará archivos HTML llamados`page_1.html`, `page_2.html`, etcétera.
## Paso 3: inicializar el objeto visor
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST_SUBFOLDERS))
```
 Aquí inicializamos un`Viewer` objeto con la ruta a la carpeta de Outlook de muestra.
## Paso 4: definir las opciones de vista HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.OutlookOptions.Folder = "Входящие";
```
 Creamos una instancia de`HtmlViewOptions` y especifique el formato de los recursos integrados. Además, configuramos la carpeta de Outlook para que se represente como`"Входящие"` (Entrante).
## Paso 5: renderizar el documento
```csharp
viewer.View(options);
```
Esta línea desencadena el proceso de renderizado con las opciones especificadas.
## Paso 6: Mostrar mensaje de éxito
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Después de la renderización, se muestra este mensaje que indica la finalización exitosa del proceso de renderización y dirige al usuario al directorio de salida.

## Conclusión
En este tutorial, exploramos cómo representar carpetas específicas y filtrar mensajes en Outlook usando GroupDocs.Viewer para .NET. Si sigue los pasos descritos anteriormente, puede administrar y mostrar documentos de manera eficiente dentro de sus aplicaciones .NET.
## Preguntas frecuentes
### ¿Puedo representar documentos que no sean mensajes de Outlook con GroupDocs.Viewer para .NET?
Sí, GroupDocs.Viewer para .NET admite una amplia gama de formatos de documentos, incluidos PDF, DOCX, XLSX y más.
### ¿GroupDocs.Viewer para .NET es compatible con .NET Core?
Sí, GroupDocs.Viewer para .NET es compatible tanto con .NET Framework como con .NET Core.
### ¿Puedo personalizar el formato de salida del renderizado?
Por supuesto, GroupDocs.Viewer para .NET proporciona varias opciones para personalizar la salida de renderizado, incluidos los formatos HTML, imagen y PDF.
### ¿Existe una versión de prueba disponible para GroupDocs.Viewer para .NET?
 Sí, puedes descargar una prueba gratuita desde[sitio web](https://releases.groupdocs.com/).
### ¿Dónde puedo buscar ayuda o soporte para GroupDocs.Viewer para .NET?
 Puedes visitar el[Foro GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) para cualquier ayuda o consulta.