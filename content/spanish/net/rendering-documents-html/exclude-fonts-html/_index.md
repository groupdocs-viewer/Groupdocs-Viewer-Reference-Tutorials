---
"description": "Aprenda a excluir fuentes del HTML renderizado con GroupDocs.Viewer para .NET. Siga esta guía paso a paso para una visualización fluida de documentos."
"linktitle": "Excluir fuentes del HTML renderizado"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Excluir fuentes del HTML renderizado"
"url": "/es/net/rendering-documents-html/exclude-fonts-html/"
"weight": 10
type: docs
---
# Excluir fuentes del HTML renderizado

## Introducción
GroupDocs.Viewer para .NET es una potente biblioteca de renderizado de documentos que permite a los desarrolladores mostrar más de 50 formatos de documentos en sus aplicaciones .NET sin necesidad de dependencias externas. En este tutorial, nos centraremos en una función específica de GroupDocs.Viewer: la exclusión de fuentes de la salida HTML renderizada. 
## Prerrequisitos
Antes de comenzar, asegúrese de tener lo siguiente:
1. Comprensión básica del desarrollo en C# y .NET.
2. GroupDocs.Viewer para .NET está instalado. Puede descargarlo desde [aquí](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio o cualquier otro IDE para desarrollo en C#.

## Importar espacios de nombres
En su código C#, asegúrese de incluir los espacios de nombres necesarios:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Paso 1: Definir el directorio de salida
Configure el directorio donde desea que se guarden los archivos HTML renderizados.
```csharp
string outputDirectory = "Your Document Directory";
```
## Paso 2: Definir el formato de la ruta del archivo de página
Especifique el formato de las rutas de archivo de páginas individuales del documento renderizado.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Paso 3: Inicializar el objeto Visor
Cree una instancia del objeto Viewer con el documento que desea renderizar.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // Tu código va aquí
}
```
## Paso 4: Establecer las opciones de vista HTML
Define las opciones para la representación HTML, incluido el formato de los recursos integrados y las fuentes a excluir.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## Paso 5: Renderizar el documento
Pase las opciones de vista HTML al objeto Visor para renderizar el documento.
```csharp
viewer.View(options);
```
## Paso 6: Ubicación del documento renderizado de salida
Informar al usuario sobre la ubicación donde se guardan los archivos HTML renderizados.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusión
En este tutorial, aprendimos a usar GroupDocs.Viewer para .NET para excluir fuentes de la salida HTML renderizada. Siguiendo los pasos descritos anteriormente, puede personalizar el proceso de renderizado para satisfacer sus necesidades específicas, garantizando una visualización óptima de los documentos en sus aplicaciones.
## Preguntas frecuentes
### ¿Puedo excluir varias fuentes del HTML renderizado?
Sí, puedes agregar varios nombres de fuentes a la `FontsToExclude` lista en las opciones de vista HTML.
### ¿GroupDocs.Viewer es compatible con todos los marcos .NET?
Sí, GroupDocs.Viewer es compatible con .NET Framework 4.6.1 y versiones superiores.
### ¿Puedo renderizar documentos desde ubicaciones de almacenamiento remotas?
Sí, GroupDocs.Viewer admite la representación de documentos desde el almacenamiento local, así como desde ubicaciones de almacenamiento y transmisiones remotas.
### ¿GroupDocs.Viewer admite diseño responsivo para salida HTML?
Sí, puedes habilitar la representación responsiva ajustando las opciones de vista HTML en consecuencia.
### ¿Hay soporte técnico disponible para GroupDocs.Viewer?
Sí, usted puede buscar ayuda y participar en discusiones sobre el tema. [Foro de GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9).