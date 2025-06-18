---
"description": "Aprenda a renderizar documentos sin problemas desde su disco local con Groupdocs.Viewer para .NET. Mejore sus aplicaciones .NET con una gestión eficiente de documentos."
"linktitle": "Cargar documentos desde el disco local"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Cargar documentos desde el disco local"
"url": "/es/net/loading-documents/loading-document-local-disk/"
"weight": 10
---

# Cargar documentos desde el disco local

## Introducción
En la era digital actual, la renderización eficiente de documentos es esencial para diversas aplicaciones. Groupdocs.Viewer para .NET ofrece una potente solución para renderizar documentos directamente desde su disco local. En este tutorial, le guiaremos en el proceso de carga de documentos desde su disco local con Groupdocs.Viewer para .NET. Tanto si es un desarrollador experimentado como si está empezando, esta guía paso a paso le ayudará a integrar a la perfección la renderización de documentos en sus aplicaciones .NET.

![Cargar documentos desde el disco local con GroupDocs.Viewer .NET](/viewer/loading-documents/load-documents-from-local-disk.png)

## Prerrequisitos
Antes de sumergirse en el tutorial, asegúrese de tener los siguientes requisitos previos:
1. Groupdocs.Viewer para .NET: Descargue e instale la última versión desde [aquí](https://releases.groupdocs.com/viewer/net/).
2. Entorno de desarrollo .NET: asegúrese de tener un entorno de desarrollo .NET en funcionamiento configurado en su sistema.
3. Documentos locales: tenga los documentos que desea renderizar almacenados localmente en su disco.

## Importar espacios de nombres
En primer lugar, importemos los espacios de nombres necesarios para acceder a las funcionalidades de Groupdocs.Viewer para .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Paso 1: Cargar documentos desde el disco local
Comience configurando el directorio de salida donde se guardarán las páginas HTML renderizadas.
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Paso 2: Inicializar el visor y renderizar documentos
Inicialice el objeto Viewer con la ruta del documento y representelo usando las opciones de visualización HTML.
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Paso 3: Mostrar salida
Una vez finalizada la renderización, muestra un mensaje indicando la renderización exitosa del documento de origen y la ubicación de los archivos de salida.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusión
¡Felicitaciones! Aprendió a cargar documentos desde su disco local con Groupdocs.Viewer para .NET. Esta potente herramienta abre un mundo de posibilidades para la representación de documentos en sus aplicaciones .NET.
## Preguntas frecuentes
### ¿Puedo renderizar documentos de diferentes formatos usando Groupdocs.Viewer para .NET?
Sí, Groupdocs.Viewer para .NET admite una amplia gama de formatos de documentos, incluidos DOCX, PDF, XLSX, PPTX y más.
### ¿Groupdocs.Viewer para .NET es compatible con todos los marcos .NET?
Groupdocs.Viewer para .NET es compatible con la mayoría de los marcos .NET, incluidos .NET Core, .NET Framework y .NET Standard.
### ¿Puedo personalizar las opciones de renderizado de mis documentos?
¡Por supuesto! Groupdocs.Viewer para .NET ofrece amplias opciones de personalización que le permiten adaptar el proceso de renderizado a sus necesidades específicas.
### ¿Hay una versión de prueba disponible para Groupdocs.Viewer para .NET?
Sí, puedes descargar una versión de prueba gratuita desde [aquí](https://releases.groupdocs.com/).
### ¿Dónde puedo encontrar soporte o recursos adicionales para Groupdocs.Viewer para .NET?
Para obtener ayuda y recursos adicionales, visite Groupdocs.Viewer para .NET [foro](https://forum.groupdocs.com/c/viewer/9).