---
"description": "Aprenda a agregar marcas de agua a documentos sin problemas con GroupDocs.Viewer para .NET. Mejore la seguridad y la imagen de marca de sus documentos con este sencillo tutorial."
"linktitle": "Agregar marca de agua al documento"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Agregar marca de agua al documento"
"url": "/es/net/rendering-options/add-watermark/"
"weight": 10
type: docs
---
# Agregar marca de agua al documento

## Introducción
En la era digital actual, gestionar y visualizar diversos formatos de documentos sin problemas es una necesidad tanto para empresas como para particulares. Afortunadamente, con herramientas como GroupDocs.Viewer para .NET, gestionar documentos es pan comido. Esta potente biblioteca .NET permite a los desarrolladores integrar fácilmente la función de visualización de documentos en sus aplicaciones, permitiendo a los usuarios visualizarlos sin necesidad del software original que los creó.
## Prerrequisitos
Antes de comenzar a utilizar GroupDocs.Viewer para .NET para agregar marcas de agua a los documentos, asegúrese de tener lo siguiente:
1. Configuración del entorno: tenga un entorno de desarrollo configurado con .NET Framework o .NET Core instalado.
2. GroupDocs.Viewer para .NET: Descargue e instale la biblioteca GroupDocs.Viewer para .NET desde [página de descarga](https://releases.groupdocs.com/viewer/net/).
3. Archivos de documentos: prepare los archivos de documentos con los que desea trabajar, como DOCX, PDF u otros.
4. Conocimientos básicos de C#: Es necesario estar familiarizado con el lenguaje de programación C# para implementar los ejemplos de código.

## Importar espacios de nombres
Antes de empezar a añadir marcas de agua a los documentos con GroupDocs.Viewer para .NET, asegúrese de importar los espacios de nombres necesarios en su código C#. Este paso le permite acceder fácilmente a las clases y métodos de la biblioteca.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ahora, veamos el proceso de agregar una marca de agua a un documento con GroupDocs.Viewer para .NET. Siga estos pasos para integrar la función de marca de agua en su aplicación.
## Paso 1: Establecer el directorio de salida
```csharp
string outputDirectory = "Your Document Directory";
```
Especifique el directorio donde desea que se guarden los archivos de salida después de aplicar la marca de agua.
## Paso 2: Definir el formato de la ruta del archivo de página
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Establezca el formato de las rutas de archivo de las páginas renderizadas. En este ejemplo, se generarán archivos HTML con números de página.
## Paso 3: Crear una instancia del objeto Visor
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // El código continúa en el siguiente paso...
}
```
Crea una instancia de la clase Viewer y pasa la ruta del documento como parámetro. En este ejemplo, usamos un archivo DOCX de muestra.
## Paso 4: Configurar las opciones de vista HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
Configure las opciones de vista HTML, incluido el texto de marca de agua que desea agregar al documento.
## Paso 5: Ver documento con marca de agua
```csharp
viewer.View(options);
```
Invoque el método View del objeto Viewer y pase las opciones configuradas. Esto generará el documento con la marca de agua especificada.
## Paso 6: Mostrar la ruta del directorio de salida
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Informar al usuario sobre la representación exitosa del documento e indicar el directorio donde se guardan los archivos de salida.

## Conclusión
GroupDocs.Viewer para .NET ofrece una forma práctica de añadir marcas de agua a documentos mediante programación. Siguiendo los pasos de este tutorial, podrá integrar fácilmente la función de marcas de agua en sus aplicaciones .NET, mejorando así la seguridad y la imagen de marca de los documentos.
## Preguntas frecuentes
### ¿Puedo personalizar la apariencia de la marca de agua?
Sí, puedes personalizar varias propiedades de la marca de agua, como texto, fuente, color, tamaño y posición.
### ¿GroupDocs.Viewer admite la visualización de documentos de fuentes remotas?
Sí, GroupDocs.Viewer admite la visualización de documentos desde el almacenamiento local así como desde URL remotas.
### ¿Hay una versión de prueba disponible para GroupDocs.Viewer para .NET?
Sí, puedes descargar una versión de prueba gratuita desde [aquí](https://releases.groupdocs.com/).
### ¿Puedo agregar marcas de agua a varias páginas de un documento?
Por supuesto, GroupDocs.Viewer permite agregar marcas de agua a páginas individuales o a todas las páginas de un documento.
### ¿Cómo puedo obtener soporte o asistencia si encuentro algún problema?
Puede buscar ayuda y soporte en los foros de la comunidad de GroupDocs [aquí](https://forum.groupdocs.com/c/viewer/9).