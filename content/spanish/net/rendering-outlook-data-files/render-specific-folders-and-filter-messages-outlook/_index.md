---
"description": "Aprenda a representar carpetas específicas y filtrar mensajes en Outlook con GroupDocs.Viewer para .NET. Simplifique la gestión de documentos en aplicaciones .NET."
"linktitle": "Representar carpetas específicas y filtrar mensajes (Outlook)"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Representar carpetas específicas y filtrar mensajes (Outlook)"
"url": "/es/net/rendering-outlook-data-files/render-specific-folders-and-filter-messages-outlook/"
"weight": 11
---

# Representar carpetas específicas y filtrar mensajes (Outlook)

## Introducción
En el mundo del desarrollo .NET, la gestión y visualización eficiente de documentos es crucial. GroupDocs.Viewer para .NET simplifica esta tarea al ofrecer potentes funciones para renderizar diversos formatos de documentos sin problemas. En este tutorial, profundizaremos en cómo renderizar carpetas específicas y filtrar mensajes en Outlook con GroupDocs.Viewer para .NET.
## Prerrequisitos
Antes de sumergirse en el tutorial, asegúrese de tener lo siguiente:
1. GroupDocs.Viewer para .NET: Asegúrese de tener instalado GroupDocs.Viewer para .NET. Puede descargarlo desde [sitio web](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: necesita tener el marco .NET instalado en su máquina.
3. Comprensión básica de C#: la familiaridad con el lenguaje de programación C# será beneficiosa para seguir el tutorial.

## Importar espacios de nombres
En primer lugar, importemos los espacios de nombres necesarios a nuestro código C#:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Paso 1: Definir el directorio de salida
```csharp
string outputDirectory = "Your Document Directory";
```
Reemplazar `"Your Document Directory"` con la ruta del directorio donde desea que se guarden los documentos renderizados.
## Paso 2: Definir el formato de la ruta del archivo de página
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Esta línea define el formato de las rutas de archivo de cada página renderizada. En este ejemplo, se generarán archivos HTML llamados `page_1.html`, `page_2.html`, etcétera.
## Paso 3: Inicializar el objeto Visor
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST_SUBFOLDERS))
```
Aquí, inicializamos un `Viewer` objeto con la ruta a la carpeta de muestra de Outlook.
## Paso 4: Definir las opciones de vista HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.OutlookOptions.Folder = "Входящие";
```
Creamos una instancia de `HtmlViewOptions` y especificamos el formato de los recursos incrustados. Además, configuramos la carpeta de Outlook para que se represente como `"Входящие"` (Entrante).
## Paso 5: Renderizar el documento
```csharp
viewer.View(options);
```
Esta línea activa el proceso de renderizado con las opciones especificadas.
## Paso 6: Mostrar mensaje de éxito
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Después de la renderización, se muestra este mensaje indicando la finalización exitosa del proceso de renderización y dirige al usuario al directorio de salida.

## Conclusión
En este tutorial, exploramos cómo renderizar carpetas específicas y filtrar mensajes en Outlook con GroupDocs.Viewer para .NET. Siguiendo los pasos descritos anteriormente, podrá administrar y mostrar documentos eficientemente en sus aplicaciones .NET.
## Preguntas frecuentes
### ¿Puedo representar documentos que no sean mensajes de Outlook con GroupDocs.Viewer para .NET?
Sí, GroupDocs.Viewer para .NET admite una amplia gama de formatos de documentos, incluidos PDF, DOCX, XLSX y más.
### ¿GroupDocs.Viewer para .NET es compatible con .NET Core?
Sí, GroupDocs.Viewer para .NET es compatible con .NET Framework y .NET Core.
### ¿Puedo personalizar el formato de salida de renderizado?
Por supuesto, GroupDocs.Viewer para .NET ofrece varias opciones para personalizar la salida de renderizado, incluidos formatos HTML, de imagen y PDF.
### ¿Hay una versión de prueba disponible para GroupDocs.Viewer para .NET?
Sí, puedes descargar una versión de prueba gratuita desde [sitio web](https://releases.groupdocs.com/).
### ¿Dónde puedo buscar ayuda o soporte para GroupDocs.Viewer para .NET?
Puedes visitar el [Foro de GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) Para cualquier ayuda o consulta.