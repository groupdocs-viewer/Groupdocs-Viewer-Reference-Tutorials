---
title: Reemplazar fuente faltante
linktitle: Reemplazar fuente faltante
second_title: API GroupDocs.Viewer .NET
description: Aprenda cómo reemplazar fuentes faltantes en documentos .NET sin esfuerzo usando GroupDocs.Viewer. Garantice una representación precisa con pasos simples.
weight: 20
url: /es/net/rendering-options/replace-missing-font/
---
## Introducción
En el mundo del desarrollo .NET, el manejo eficiente de documentos es crucial. GroupDocs.Viewer para .NET proporciona una poderosa solución para ver varios formatos de documentos dentro de sus aplicaciones .NET. En este tutorial, exploraremos cómo usar GroupDocs.Viewer para .NET para reemplazar fuentes faltantes en documentos. Ya sea que trabaje con archivos PDF, presentaciones de PowerPoint o documentos de Word, GroupDocs.Viewer simplifica el proceso y garantiza que sus documentos se representen con precisión, incluso cuando faltan fuentes.
## Requisitos previos
Antes de sumergirse en este tutorial, asegúrese de tener lo siguiente:
1. GroupDocs.Viewer para .NET: descargue e instale la biblioteca GroupDocs.Viewer desde el sitio web](https://releases.groupdocs.com/viewer/net/).
2. Entorno de desarrollo: configure un entorno de desarrollo .NET, como Visual Studio.
3. Conocimientos básicos de C#: familiaridad con el lenguaje de programación C# y el marco .NET.

## Importar espacios de nombres
En su código C#, importe los espacios de nombres necesarios para acceder a las funcionalidades de GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ahora, veamos el proceso de reemplazo de fuentes faltantes en documentos usando GroupDocs.Viewer para .NET.
## Paso 1: definir el directorio de salida
```csharp
string outputDirectory = "Your Document Directory";
```
Establezca el directorio donde se guardarán las páginas del documento renderizado.
## Paso 2: Definir el formato de ruta del archivo de página
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Especifique el formato para nombrar los archivos HTML de salida. En este ejemplo, cada página se guardará como un archivo HTML con la convención de nomenclatura "página_{page_number}.html".
## Paso 3: inicializar el objeto visor
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_PPTX))
```
Inicialice una nueva instancia de la clase Visor, pasando la ruta al archivo del documento (en este caso, una presentación de PowerPoint a la que le faltan fuentes) como parámetro.
## Paso 4: configurar las opciones de vista HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.DefaultFontName = "Courier New";
```
Cree una instancia de HtmlViewOptions y configúrela para incrustar recursos en la salida HTML. Especifique un nombre de fuente predeterminado para utilizarlo como reemplazo de las fuentes faltantes.
## Paso 5: renderizar documento
```csharp
viewer.View(options);
```
Invoca el método View del objeto Viewer, pasando las opciones de vista HTML. Esto renderizará las páginas del documento usando las opciones especificadas.
## Paso 6: Mostrar ruta de salida
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Imprima un mensaje que indique la representación exitosa del documento y proporcione la ruta donde se guardan los archivos HTML de salida.

## Conclusión
En este tutorial, aprendimos cómo usar GroupDocs.Viewer para .NET para reemplazar fuentes faltantes en documentos. Si sigue estos pasos, puede asegurarse de que sus documentos se representen con precisión, incluso cuando ciertas fuentes no estén disponibles. GroupDocs.Viewer simplifica el proceso, permitiéndole concentrarse en crear aplicaciones .NET sólidas sin preocuparse por problemas de compatibilidad de fuentes.
## Preguntas frecuentes
### ¿GrupoDocs.Viewer puede manejar otros tipos de problemas relacionados con fuentes?
Sí, GroupDocs.Viewer proporciona varias funcionalidades relacionadas con las fuentes, incluida la sustitución y detección de fuentes.
### ¿GroupDocs.Viewer es compatible con todos los marcos .NET?
GroupDocs.Viewer admite una amplia gama de marcos .NET, incluidos .NET Core y .NET Standard.
### ¿Puedo personalizar el reemplazo de fuente predeterminado en GroupDocs.Viewer?
Por supuesto, puede especificar cualquier fuente de su elección como reemplazo predeterminado de las fuentes faltantes.
### ¿GroupDocs.Viewer admite el procesamiento por lotes de documentos?
Sí, GroupDocs.Viewer le permite procesar varios documentos simultáneamente, lo que lo hace ideal para escenarios de procesamiento por lotes.
### ¿Dónde puedo encontrar más ayuda o soporte para GroupDocs.Viewer?
 Puedes visitar el foro de GroupDocs.Viewer[aquí](https://forum.groupdocs.com/c/viewer/9) para cualquier consulta de asistencia o soporte.