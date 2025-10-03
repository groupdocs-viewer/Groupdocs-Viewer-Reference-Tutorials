---
"description": "Explore la representación fluida de archivos XML SpreadSheetML en varios formatos con GroupDocs.Viewer para .NET. Intégrelo fácilmente en sus aplicaciones."
"linktitle": "Representación de XML SpreadSheetML"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Representación de XML SpreadSheetML"
"url": "/es/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/"
"weight": 16
type: docs
---
# Representación de XML SpreadSheetML

## Introducción
¡Bienvenido al mundo de GroupDocs.Viewer para .NET! En este tutorial, le guiaremos en la renderización de archivos XML SpreadSheetML fácilmente con GroupDocs.Viewer, una potente biblioteca .NET. Tanto si es un desarrollador experimentado como si está empezando, esta guía paso a paso le ayudará a integrar fácilmente la renderización de XML SpreadSheetML en sus aplicaciones.
## Prerrequisitos
Antes de sumergirse en el tutorial, asegúrese de tener configurados los siguientes requisitos previos:
- Un entorno de desarrollo con soporte .NET.
- La biblioteca GroupDocs.Viewer para .NET está instalada. Puede descargarla. [aquí](https://releases.groupdocs.com/viewer/net/).
- Una comprensión básica de la programación en C#.
## Importar espacios de nombres
Comience importando los espacios de nombres necesarios a su proyecto de C#. Esto le garantiza el acceso a las funcionalidades de GroupDocs.Viewer.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Paso 1: Configure su directorio de documentos
Define la ruta al directorio de tus documentos donde se guardará la salida.
```csharp
string outputDirectory = "Your Document Directory";
```
## Paso 2: Especificar las rutas de los archivos de salida
Configure las rutas completas para los archivos de salida HTML, JPG, PNG y PDF.
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.html");
```
## Paso 3: Especificar las opciones de carga
Especifique explícitamente el tipo de archivo como Excel 2003 XML SpreadSheetML para representarlo con precisión.
```csharp
LoadOptions loadOptions = new LoadOptions(FileType.Excel2003XML);
```
## Paso 4: Renderizar a HTML multipágina
Utilice las opciones de visualización HTML para convertir el archivo XML SpreadSheetML en un documento HTML de varias páginas.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Paso 5: Renderizar a JPG
Convierta el archivo XML SpreadSheetML en una imagen JPG utilizando las opciones especificadas.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Paso 6: Renderizar a PNG
De manera similar, convierta el archivo en una imagen PNG con las opciones especificadas.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Paso 7: Renderizar a PDF
Por último, convierta el archivo XML SpreadSheetML en un documento PDF utilizando las opciones especificadas.
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Conclusión
¡Felicitaciones! Ha aprendido a renderizar archivos XML SpreadSheetML con GroupDocs.Viewer para .NET. Mejore sus capacidades de visualización de documentos explorando las funciones y opciones que ofrece esta versátil biblioteca.
## Preguntas frecuentes
### ¿GroupDocs.Viewer es compatible con otros formatos de archivos?
Sí, GroupDocs.Viewer admite una amplia gama de formatos de documentos, incluidos PDF, Word, Excel y más.
### ¿Puedo personalizar la apariencia de los documentos renderizados?
¡Por supuesto! GroupDocs.Viewer ofrece varias opciones de personalización que te permiten adaptar el resultado a tus necesidades específicas.
### ¿Dónde puedo encontrar apoyo y recursos adicionales?
Visita el [Foro de GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) Para obtener apoyo comunitario y explorar la [documentación](https://tutorials.groupdocs.com/viewer/net/) para obtener información detallada.
### ¿Hay una prueba gratuita disponible?
Sí, puedes acceder a la prueba gratuita. [aquí](https://releases.groupdocs.com/).
### ¿Cómo obtengo una licencia temporal?
Puedes obtener una licencia temporal [aquí](https://purchase.groupdocs.com/temporary-license/).