---
title: Excluir fuentes del HTML renderizado
linktitle: Excluir fuentes del HTML renderizado
second_title: API GroupDocs.Viewer .NET
description: Aprenda a excluir fuentes del HTML renderizado usando GroupDocs.Viewer para .NET. Siga esta guía paso a paso para una visualización perfecta de los documentos.
type: docs
weight: 10
url: /es/net/rendering-documents-html/exclude-fonts-html/
---
## Introducción
GroupDocs.Viewer para .NET es una potente biblioteca de representación de documentos que permite a los desarrolladores mostrar más de 50 formatos de documentos en sus aplicaciones .NET sin necesidad de dependencias externas. En este tutorial, nos centraremos en una característica específica de GroupDocs.Viewer: excluir fuentes de la salida HTML renderizada. 
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
1. Conocimientos básicos del desarrollo de C# y .NET.
2.  GroupDocs.Viewer para .NET instalado. Puedes descargarlo desde[aquí](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio o cualquier otro IDE para desarrollo en C#.

## Importar espacios de nombres
En su código C#, asegúrese de incluir los espacios de nombres necesarios:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Paso 1: definir el directorio de salida
Configure el directorio donde desea guardar los archivos HTML renderizados.
```csharp
string outputDirectory = "Your Document Directory";
```
## Paso 2: Definir el formato de ruta del archivo de página
Especifique el formato para las rutas de archivo de páginas individuales del documento renderizado.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Paso 3: inicializar el objeto visor
Cree una instancia del objeto Visor con el documento que desea representar.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // Tu código va aquí
}
```
## Paso 4: configurar las opciones de vista HTML
Defina las opciones para la representación HTML, incluido el formato de los recursos incrustados y las fuentes que se excluirán.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## Paso 5: renderizar documento
Pase las opciones de vista HTML al objeto Visor para representar el documento.
```csharp
viewer.View(options);
```
## Paso 6: Ubicación del documento renderizado de salida
Informe al usuario sobre la ubicación donde se guardan los archivos HTML renderizados.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusión
En este tutorial, aprendimos cómo usar GroupDocs.Viewer para .NET para excluir fuentes de la salida HTML renderizada. Si sigue los pasos descritos anteriormente, puede personalizar el proceso de renderizado para cumplir con sus requisitos específicos, garantizando una visualización óptima de los documentos en sus aplicaciones.
## Preguntas frecuentes
### ¿Puedo excluir varias fuentes del HTML renderizado?
 Sí, puede agregar varios nombres de fuentes al`FontsToExclude` lista en las opciones de vista HTML.
### ¿GroupDocs.Viewer es compatible con todos los marcos .NET?
Sí, GroupDocs.Viewer es compatible con .NET Framework 4.6.1 y superior.
### ¿Puedo renderizar documentos desde ubicaciones de almacenamiento remotas?
Sí, GroupDocs.Viewer admite la representación de documentos desde el almacenamiento local, así como desde ubicaciones y transmisiones de almacenamiento remoto.
### ¿GroupDocs.Viewer admite el diseño responsivo para salida HTML?
Sí, puede habilitar la representación responsiva ajustando las opciones de vista HTML en consecuencia.
### ¿Hay soporte técnico disponible para GroupDocs.Viewer?
 Sí, puede buscar ayuda y participar en debates sobre el[Foro GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9).