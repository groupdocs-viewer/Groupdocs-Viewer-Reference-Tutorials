---
title: Ajustar el tamaño de la imagen de salida para dibujos CAD
linktitle: Ajustar el tamaño de la imagen de salida para dibujos CAD
second_title: API GroupDocs.Viewer .NET
description: Aprenda a ajustar el tamaño de la imagen de salida para dibujos CAD usando GroupDocs.Viewer para .NET. Mejore la visibilidad y la usabilidad sin esfuerzo.
weight: 15
url: /es/net/rendering-cad-drawings/adjust-output-image-size-cad/
---

# Ajustar el tamaño de la imagen de salida para dibujos CAD

## Introducción
Los dibujos CAD a menudo requieren ajustes específicos para una visualización y presentación óptimas. GroupDocs.Viewer para .NET proporciona un potente conjunto de herramientas para administrar y personalizar la salida de dibujos CAD. En este tutorial, lo guiaremos paso a paso a través del proceso de ajustar el tamaño de la imagen de salida para dibujos CAD.
## Requisitos previos
Antes de comenzar, asegúrese de tener los siguientes requisitos previos:
1.  GroupDocs.Viewer para .NET: descargue e instale GroupDocs.Viewer para .NET desde[aquí](https://releases.groupdocs.com/viewer/net/).
2. Directorio de documentos: prepare el directorio donde se encuentra su documento.
3. Comprensión básica: familiarícese con los conceptos básicos de la programación .NET.

## Importar espacios de nombres
Primero, asegúrese de importar los espacios de nombres necesarios para acceder a las funcionalidades de GroupDocs.Viewer:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Paso 1: configurar el directorio de salida
Defina el directorio donde desea almacenar las imágenes de salida de los dibujos CAD:
```csharp
string outputDirectory = "Your Document Directory";
```
## Paso 2: Definir el formato de ruta del archivo de página
Establezca el formato para las rutas de los archivos de página. Este formato se utilizará para nombrar y guardar páginas individuales como archivos HTML:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Paso 3: ajustar el tamaño de la imagen
Dentro de un bloque de uso para el objeto Visor, ajuste el tamaño de la imagen para los dibujos CAD configurando las opciones apropiadas:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## Paso 4: Mostrar el directorio de salida
Después de renderizar el documento, muestre un mensaje que indique la renderización exitosa y proporcione la ubicación del directorio de salida:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusión
Ajustar el tamaño de la imagen de salida para los dibujos CAD es crucial para mejorar su visibilidad y usabilidad. Con GroupDocs.Viewer para .NET, este proceso se simplifica y es eficiente, permitiéndole personalizar el resultado según sus requisitos específicos.
## Preguntas frecuentes
### ¿Puedo ajustar el tamaño de la imagen de salida para otros tipos de documentos además de los dibujos CAD?
Sí, GroupDocs.Viewer para .NET admite varios tipos de documentos y puede ajustar el tamaño de la imagen de salida para la mayoría de los formatos de documentos.
### ¿GroupDocs.Viewer para .NET es compatible con diferentes versiones de .NET framework?
Sí, GroupDocs.Viewer para .NET es compatible con múltiples versiones del marco .NET, lo que garantiza flexibilidad y usabilidad en diferentes entornos.
### ¿Hay opciones de licencia disponibles para GroupDocs.Viewer para .NET?
Sí, puede explorar diferentes opciones de licencia, incluidas licencias temporales y licencias comerciales, para satisfacer sus necesidades.
### ¿Puedo personalizar el formato de salida de los documentos renderizados?
Por supuesto, GroupDocs.Viewer para .NET ofrece varias opciones de personalización, lo que le permite adaptar el formato de salida según sus preferencias.
### ¿Dónde puedo encontrar soporte o asistencia adicional con GroupDocs.Viewer para .NET?
 Puedes visitar el foro de GroupDocs.Viewer[aquí](https://forum.groupdocs.com/c/viewer/9) para obtener apoyo, hacer preguntas e interactuar con la comunidad.