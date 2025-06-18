---
"description": "Aprenda a especificar el tipo de archivo al cargar documentos con GroupDocs.Viewer para .NET. Represente con precisión varios formatos en sus aplicaciones .NET."
"linktitle": "Especificar el tipo de archivo al cargar documentos"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Especificar el tipo de archivo al cargar documentos"
"url": "/es/net/advanced-loading/specify-file-type/"
"weight": 10
---

# Especificar el tipo de archivo al cargar documentos

## Introducción
GroupDocs.Viewer para .NET es una API versátil de renderizado de documentos compatible con una amplia gama de formatos de archivo, como DOCX, PDF, PPTX y más. Al especificar el tipo de archivo al cargar documentos, garantiza una renderización precisa y una experiencia de visualización fluida para sus usuarios.

![Especificar el tipo de archivo al cargar documentos en GroupDocs.Viewer para .NET](/viewer/advanced-loading/specify-file-type-when-loading-documents-img.png)

## Prerrequisitos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
- Conocimientos básicos de C# y .NET framework.
- Visual Studio instalado en su sistema.
- GroupDocs.Viewer para .NET está instalado en tu proyecto. Puedes descargarlo desde [aquí](https://releases.groupdocs.com/viewer/net/).
##
## Importar espacios de nombres
Primero, debe importar los espacios de nombres necesarios a su código C#. Estos espacios de nombres proporcionan acceso a las clases y métodos necesarios para la representación de documentos.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Paso 1: Configurar el directorio de salida
Define el directorio donde quieres guardar las páginas del documento renderizado.
```csharp
string outputDirectory = "Your Document Directory";
```
## Paso 2: Definir el formato de la ruta del archivo de página
Especifique el formato para nombrar los archivos HTML de salida para cada página del documento.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Paso 3: Especificar las opciones de carga
Crear una instancia de la `LoadOptions` clase y establezca el tipo de archivo deseado.
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## Paso 4: Cargar documento y renderizar
Utilice el `Viewer` Clase para cargar el documento y renderizarlo en formato HTML.
```csharp
using (Viewer viewer = new Viewer("YourDocument.docx", loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Paso 5: Mostrar mensaje de éxito
Informar al usuario que el documento se ha procesado correctamente y especificar la ubicación de los archivos de salida.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusión
En este tutorial, aprendimos a usar GroupDocs.Viewer para .NET para especificar el tipo de archivo al cargar documentos. Siguiendo estos sencillos pasos, podrá garantizar una representación precisa de diversos formatos de documentos en sus aplicaciones .NET.
## Preguntas frecuentes
### ¿Puedo renderizar documentos que no sean DOCX usando GroupDocs.Viewer para .NET?
Sí, GroupDocs.Viewer admite una amplia gama de formatos de archivos, incluidos PDF, PPTX, XLSX y más.
### ¿GroupDocs.Viewer para .NET es compatible con .NET Core?
Sí, GroupDocs.Viewer para .NET es compatible con .NET Framework y .NET Core.
### ¿Puedo personalizar los archivos HTML de salida generados por GroupDocs.Viewer?
Sí, puedes personalizar la salida HTML utilizando varias opciones proporcionadas por la API.
### ¿GroupDocs.Viewer para .NET requiere alguna dependencia externa?
No, GroupDocs.Viewer para .NET es una biblioteca independiente y no requiere ninguna dependencia externa.
### ¿Hay una versión de prueba disponible para GroupDocs.Viewer para .NET?
Sí, puedes descargar una versión de prueba gratuita desde [aquí](https://releases.groupdocs.com/viewer/net/).