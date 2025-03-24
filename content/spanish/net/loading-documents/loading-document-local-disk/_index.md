---
title: Cargar documentos desde el disco local
linktitle: Cargar documentos desde el disco local
second_title: API GroupDocs.Viewer .NET
description: Aprenda cómo renderizar documentos sin problemas desde su disco local usando Groupdocs.Viewer para .NET. Mejore sus aplicaciones .NET con documentos eficientes.
weight: 10
url: /es/net/loading-documents/loading-document-local-disk/
---
## Introducción
En la era digital actual, la representación eficiente de documentos es esencial para diversas aplicaciones. Groupdocs.Viewer para .NET ofrece una poderosa solución para renderizar documentos directamente desde su disco local. En este tutorial, lo guiaremos a través del proceso de cargar documentos desde su disco local usando Groupdocs.Viewer para .NET. Ya sea que sea un desarrollador experimentado o recién esté comenzando, esta guía paso a paso lo ayudará a integrar sin problemas la representación de documentos en sus aplicaciones .NET.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de tener los siguientes requisitos previos:
1.  Groupdocs.Viewer para .NET: descargue e instale la última versión desde[aquí](https://releases.groupdocs.com/viewer/net/).
2. Entorno de desarrollo .NET: asegúrese de tener un entorno de desarrollo .NET funcional configurado en su sistema.
3. Documentos locales: tenga los documentos que desea procesar almacenados localmente en su disco.

## Importar espacios de nombres
En primer lugar, importemos los espacios de nombres necesarios para acceder a las funcionalidades de Groupdocs.Viewer para .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Paso 1: cargar documentos desde el disco local
Comience configurando el directorio de salida donde se guardarán las páginas HTML renderizadas.
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Paso 2: inicializar el visor y renderizar documentos
Inicialice el objeto Visor con la ruta del documento y renderícelo usando las opciones de vista HTML.
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Paso 3: Mostrar salida
Una vez que se completa la renderización, muestra un mensaje que indica la renderización exitosa del documento fuente y la ubicación de los archivos de salida.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo cargar documentos desde su disco local usando Groupdocs.Viewer para .NET. Esta poderosa herramienta abre un mundo de posibilidades para la representación de documentos dentro de sus aplicaciones .NET.
## Preguntas frecuentes
### ¿Puedo renderizar documentos de diferentes formatos usando Groupdocs.Viewer para .NET?
Sí, Groupdocs.Viewer para .NET admite una amplia gama de formatos de documentos, incluidos DOCX, PDF, XLSX, PPTX y más.
### ¿Groupdocs.Viewer para .NET es compatible con todos los marcos .NET?
Groupdocs.Viewer para .NET es compatible con la mayoría de los marcos .NET, incluidos .NET Core, .NET Framework y .NET Standard.
### ¿Puedo personalizar las opciones de renderizado de mis documentos?
¡Absolutamente! Groupdocs.Viewer para .NET proporciona amplias opciones de personalización que le permiten adaptar el proceso de renderizado a sus requisitos específicos.
### ¿Existe una versión de prueba disponible para Groupdocs.Viewer para .NET?
Sí, puedes descargar una versión de prueba gratuita desde[aquí](https://releases.groupdocs.com/).
### ¿Dónde puedo encontrar soporte o recursos adicionales para Groupdocs.Viewer para .NET?
 Para obtener soporte y recursos adicionales, visite Groupdocs.Viewer para .NET[foro](https://forum.groupdocs.com/c/viewer/9).