---
title: Agregar marca de agua en el documento
linktitle: Agregar marca de agua en el documento
second_title: API GroupDocs.Viewer .NET
description: Aprenda cómo agregar fácilmente marcas de agua a documentos usando GroupDocs.Viewer para .NET. Mejore la seguridad de los documentos y la marca con este tutorial fácil de seguir.
weight: 10
url: /es/net/rendering-options/add-watermark/
---

# Agregar marca de agua en el documento

## Introducción
En la era digital actual, gestionar y visualizar varios formatos de documentos sin problemas es una necesidad tanto para muchas empresas como para particulares. Afortunadamente, con herramientas como GroupDocs.Viewer para .NET, manejar documentos se vuelve muy sencillo. Esta potente biblioteca .NET permite a los desarrolladores integrar sin esfuerzo la funcionalidad de visualización de documentos en sus aplicaciones, lo que permite a los usuarios ver documentos sin necesidad del software original que los creó.
## Requisitos previos
Antes de sumergirse en el uso de GroupDocs.Viewer para .NET para agregar marcas de agua a documentos, asegúrese de tener lo siguiente:
1. Configuración del entorno: tenga un entorno de desarrollo configurado con .NET Framework o .NET Core instalado.
2.  GroupDocs.Viewer para .NET: descargue e instale la biblioteca GroupDocs.Viewer para .NET desde[pagina de descarga](https://releases.groupdocs.com/viewer/net/).
3. Archivos de documentos: prepare los archivos de documentos con los que desea trabajar, como DOCX, PDF u otros.
4. Conocimientos básicos de C#: es necesaria familiaridad con el lenguaje de programación C# para implementar los ejemplos de código.

## Importar espacios de nombres
Antes de comenzar a agregar marcas de agua a documentos usando GroupDocs.Viewer para .NET, asegúrese de importar los espacios de nombres requeridos en su código C#. Este paso le permite acceder sin problemas a las clases y métodos proporcionados por la biblioteca.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ahora, veamos el proceso de agregar una marca de agua a un documento usando GroupDocs.Viewer para .NET. Siga estos pasos para integrar perfectamente la funcionalidad de marcas de agua en su aplicación.
## Paso 1: configurar el directorio de salida
```csharp
string outputDirectory = "Your Document Directory";
```
Especifique el directorio donde desea que se guarden los archivos de salida después de aplicar la marca de agua.
## Paso 2: Definir el formato de ruta del archivo de página
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Establezca el formato para las rutas de archivo de las páginas renderizadas. En este ejemplo, se generarán archivos HTML con números de página.
## Paso 3: Crear una instancia del objeto Visor
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // El código continúa en el siguiente paso...
}
```
Cree una instancia de la clase Viewer, pasando la ruta al archivo del documento como parámetro. En este ejemplo, utilizamos un archivo DOCX de muestra.
## Paso 4: configurar las opciones de vista HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
Configure las opciones de vista HTML, incluido el texto de la marca de agua que desea agregar al documento.
## Paso 5: Ver documento con marca de agua
```csharp
viewer.View(options);
```
Invoca el método View del objeto Viewer, pasando las opciones configuradas. Esto generará el documento con la marca de agua especificada.
## Paso 6: Mostrar la ruta del directorio de salida
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Informe al usuario sobre la representación exitosa del documento e indique el directorio donde se guardan los archivos de salida.

## Conclusión
GroupDocs.Viewer para .NET proporciona una manera conveniente de agregar marcas de agua a documentos mediante programación. Si sigue los pasos descritos en este tutorial, podrá integrar perfectamente la funcionalidad de marcas de agua en sus aplicaciones .NET, mejorando la seguridad de los documentos y la marca.
## Preguntas frecuentes
### ¿Puedo personalizar la apariencia de la marca de agua?
Sí, puedes personalizar varias propiedades de la marca de agua, como texto, fuente, color, tamaño y posición.
### ¿GroupDocs.Viewer admite la visualización de documentos desde fuentes remotas?
Sí, GroupDocs.Viewer admite la visualización de documentos desde el almacenamiento local, así como de URL remotas.
### ¿Existe una versión de prueba disponible para GroupDocs.Viewer para .NET?
Sí, puedes descargar una versión de prueba gratuita desde[aquí](https://releases.groupdocs.com/).
### ¿Puedo agregar marcas de agua a varias páginas de un documento?
Por supuesto, GroupDocs.Viewer permite agregar marcas de agua a páginas individuales o a todas las páginas de un documento.
### ¿Cómo puedo obtener soporte o asistencia si tengo algún problema?
 Puede buscar ayuda y soporte en los foros de la comunidad de GroupDocs.[aquí](https://forum.groupdocs.com/c/viewer/9).