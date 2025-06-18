---
"description": "Aprenda a ajustar el tamaño de la imagen de salida para dibujos CAD con GroupDocs.Viewer para .NET. Mejore la visibilidad y la usabilidad fácilmente."
"linktitle": "Ajustar el tamaño de la imagen de salida para dibujos CAD"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Ajustar el tamaño de la imagen de salida para dibujos CAD"
"url": "/es/net/rendering-cad-drawings/adjust-output-image-size-cad/"
"weight": 15
---

# Ajustar el tamaño de la imagen de salida para dibujos CAD

## Introducción
Los dibujos CAD suelen requerir ajustes específicos para una visualización y presentación óptimas. GroupDocs.Viewer para .NET ofrece un potente conjunto de herramientas para gestionar y personalizar la salida de dibujos CAD. En este tutorial, le guiaremos paso a paso en el proceso de ajuste del tamaño de la imagen de salida para dibujos CAD.
## Prerrequisitos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1. GroupDocs.Viewer para .NET: Descargue e instale GroupDocs.Viewer para .NET desde [aquí](https://releases.groupdocs.com/viewer/net/).
2. Directorio de documentos: prepara el directorio donde se encuentra tu documento.
3. Comprensión básica: familiarícese con los conceptos básicos de la programación .NET.

## Importar espacios de nombres
Primero, asegúrese de importar los espacios de nombres necesarios para acceder a las funcionalidades de GroupDocs.Viewer:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Paso 1: Establecer el directorio de salida
Define el directorio donde quieres almacenar las imágenes de salida de los dibujos CAD:
```csharp
string outputDirectory = "Your Document Directory";
```
## Paso 2: Definir el formato de la ruta del archivo de página
Establezca el formato de las rutas de los archivos de página. Este formato se usará para nombrar y guardar páginas individuales como archivos HTML:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Paso 3: Ajustar el tamaño de la imagen
Dentro de un bloque de uso para el objeto Visor, ajuste el tamaño de la imagen para dibujos CAD configurando las opciones adecuadas:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## Paso 4: Mostrar el directorio de salida
Después de renderizar el documento, muestra un mensaje indicando que la renderización fue exitosa y proporciona la ubicación del directorio de salida:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusión
Ajustar el tamaño de la imagen de salida para dibujos CAD es crucial para mejorar su visibilidad y usabilidad. Con GroupDocs.Viewer para .NET, este proceso se simplifica y optimiza, permitiéndole personalizar la salida según sus necesidades específicas.
## Preguntas frecuentes
### ¿Puedo ajustar el tamaño de la imagen de salida para otros tipos de documentos además de los dibujos CAD?
Sí, GroupDocs.Viewer para .NET admite varios tipos de documentos y puede ajustar el tamaño de la imagen de salida para la mayoría de los formatos de documentos.
### ¿GroupDocs.Viewer para .NET es compatible con diferentes versiones de .NET Framework?
Sí, GroupDocs.Viewer para .NET es compatible con múltiples versiones del marco .NET, lo que garantiza flexibilidad y facilidad de uso en diferentes entornos.
### ¿Hay opciones de licencia disponibles para GroupDocs.Viewer para .NET?
Sí, puede explorar diferentes opciones de licencia, incluidas licencias temporales y licencias comerciales, para satisfacer sus necesidades.
### ¿Puedo personalizar el formato de salida de los documentos renderizados?
Por supuesto, GroupDocs.Viewer para .NET ofrece varias opciones de personalización, lo que le permite adaptar el formato de salida según sus tutoriales.
### ¿Dónde puedo encontrar soporte o asistencia adicional con GroupDocs.Viewer para .NET?
Puedes visitar el foro de GroupDocs.Viewer [aquí](https://forum.groupdocs.com/c/viewer/9) para obtener apoyo, hacer preguntas e interactuar con la comunidad.