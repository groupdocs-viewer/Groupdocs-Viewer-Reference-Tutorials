---
"description": "Aprenda a habilitar la representación por capas en documentos PDF con GroupDocs.Viewer para .NET. Mejore la experiencia de visualización de documentos sin esfuerzo."
"linktitle": "Habilitar la representación en capas en PDF"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Habilitar la representación en capas en PDF"
"url": "/es/net/pdf-rendering-options/enable-layered-rendering-pdf/"
"weight": 15
type: docs
---
# Habilitar la representación en capas en PDF

## Introducción
En este tutorial, profundizaremos en el proceso de habilitar la representación por capas en documentos PDF con GroupDocs.Viewer para .NET. La representación por capas permite una mejor visualización y manipulación de documentos, ofreciendo a los usuarios una experiencia de visualización más interactiva.

![Habilitar la representación en capas en PDF con GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/enable-layered-rendering-in-pdf.png)

## Prerrequisitos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1. GroupDocs.Viewer para .NET: asegúrese de haber instalado el paquete o la biblioteca necesarios para usar GroupDocs.Viewer para .NET en su proyecto.
2. Visual Studio: debe tener Visual Studio instalado en su sistema para codificar y ejecutar los ejemplos proporcionados.
3. Comprensión básica de C#: este tutorial supone familiaridad con la sintaxis y los conceptos del lenguaje de programación C#.

## Importar espacios de nombres
Comience importando los espacios de nombres necesarios en su proyecto:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Paso 1: Definir el directorio de salida
```csharp
string outputDirectory = "Your Document Directory";
```
Asegúrese de especificar la ruta del directorio donde desea que se guarde la salida renderizada.
## Paso 2: Definir el formato de la ruta del archivo de página
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Este paso establece el formato de las rutas de archivos de páginas individuales en la salida renderizada. `{0}` es un marcador de posición para el número de página.
## Paso 3: Habilitar la representación en capas
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
Aquí creamos un `Viewer` objeto y especificamos el documento PDF que se procesará. Luego configuramos `HtmlViewOptions` con el formato de ruta de archivo de página definido. Al configurar `EnableLayeredRendering` propiedad a `true` en `PdfOptions`Habilitamos la representación en capas para el documento PDF.
## Paso 4: Mostrar el directorio de salida
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Finalmente, imprimimos un mensaje indicando la representación exitosa del documento fuente y solicitamos al usuario que verifique la salida en el directorio especificado.

## Conclusión
Habilitar la representación por capas en documentos PDF con GroupDocs.Viewer para .NET mejora la visualización de documentos, ofreciendo a los usuarios una experiencia más completa e interactiva. Siguiendo los pasos de este tutorial, podrá integrar esta función sin problemas en sus aplicaciones .NET.
## Preguntas frecuentes
### ¿Qué es la renderización en capas en documentos PDF?
La renderización en capas permite la separación y manipulación de diferentes componentes dentro de un documento PDF, lo que permite una visualización interactiva y una mejor experiencia del usuario.
### ¿Puedo personalizar el directorio de salida para los documentos renderizados?
Sí, puede especificar cualquier ruta de directorio para la salida según sus requisitos.
### ¿GroupDocs.Viewer admite otros formatos de archivos además de PDF?
Sí, GroupDocs.Viewer admite una amplia gama de formatos de documentos, incluidos Word, Excel, PowerPoint y más.
### ¿GroupDocs.Viewer es compatible con .NET Core?
Sí, GroupDocs.Viewer es compatible con entornos .NET Framework y .NET Core.
### ¿Dónde puedo encontrar apoyo o asistencia adicional?
Puede visitar el foro de GroupDocs.Viewer para cualquier consulta o asistencia con respecto a la biblioteca de visores.