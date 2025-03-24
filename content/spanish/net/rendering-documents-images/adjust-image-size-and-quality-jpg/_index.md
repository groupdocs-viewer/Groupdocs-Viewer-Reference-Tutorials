---
title: Ajustar el tamaño y la calidad de la imagen (JPG)
linktitle: Ajustar el tamaño y la calidad de la imagen (JPG)
second_title: API GroupDocs.Viewer .NET
description: Aprenda a optimizar el tamaño y la calidad de la imagen en formato JPEG utilizando Groupdocs.Viewer para .NET. Mejore su experiencia de visualización de documentos.
weight: 11
url: /es/net/rendering-documents-images/adjust-image-size-and-quality-jpg/
---
## Introducción
Groupdocs.Viewer para .NET es una potente biblioteca que permite a los desarrolladores integrar perfectamente la funcionalidad de visualización de documentos en sus aplicaciones .NET. Un requisito común en las aplicaciones de visualización de documentos es la capacidad de ajustar el tamaño y la calidad de las imágenes, particularmente cuando se trata de imágenes JPEG (JPG). En este tutorial, lo guiaremos a través del proceso de ajustar el tamaño y la calidad de la imagen usando Groupdocs.Viewer para .NET.
## Requisitos previos
Antes de comenzar, asegúrese de tener lo siguiente:
1. Conocimientos básicos del lenguaje de programación C#.
2. Visual Studio instalado en su sistema.
3.  Groupdocs.Viewer para la biblioteca .NET instalada. Puedes descargarlo desde[aquí](https://releases.groupdocs.com/viewer/net/).

## Importar espacios de nombres
Primero, necesita importar los espacios de nombres necesarios en su código C#. Estos espacios de nombres brindan acceso a las clases y métodos necesarios para trabajar con Groupdocs.Viewer.
## Paso 1: importar espacios de nombres
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ahora, dividamos el código de ejemplo proporcionado en varios pasos para una mejor comprensión.
## Paso 2: Establecer el directorio de salida y el formato de ruta del archivo de página
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
En este paso, especificamos el directorio de salida donde se guardarán las imágenes renderizadas y definimos el formato para la ruta del archivo de cada imagen de página.
## Paso 3: inicialice el visor y configure las opciones de visualización JPG
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
Aquí, inicializamos el objeto Visor con la ruta al documento que se va a ver. Luego, creamos una instancia de JpgViewOptions y configuramos el ancho y alto deseados para las imágenes JPEG.
## Paso 4: renderizar el documento fuente
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Finalmente, imprimimos un mensaje indicando la renderización exitosa del documento fuente y la ubicación donde se guardan las imágenes de salida.

## Conclusión
En este tutorial, aprendimos cómo ajustar el tamaño y la calidad de las imágenes JPEG usando Groupdocs.Viewer para .NET. Si sigue los pasos descritos anteriormente, puede incorporar fácilmente esta funcionalidad en sus aplicaciones .NET, brindando a los usuarios una experiencia de visualización de imágenes optimizada.
## Preguntas frecuentes
### ¿Puedo ajustar la calidad de la imagen también?
Sí, puede ajustar la calidad de la imagen configurando la propiedad Calidad en JpgViewOptions.
### ¿Qué formatos de documentos admite Groupdocs.Viewer para .NET?
Groupdocs.Viewer para .NET admite una amplia gama de formatos de documentos, incluidos DOCX, PDF, PPTX, XLSX y más.
### ¿Groupdocs.Viewer para .NET es compatible con .NET Core?
Sí, Groupdocs.Viewer para .NET es compatible con .NET Core junto con el .NET Framework tradicional.
### ¿Puedo personalizar el formato de nombre del archivo de salida?
Sí, puede personalizar el formato de denominación del archivo de salida modificando la variable pageFilePathFormat en el código.
### ¿Groupdocs.Viewer para .NET admite anotaciones de documentos?
Sí, Groupdocs.Viewer para .NET brinda soporte integral para anotaciones de documentos, incluido resaltado, subrayado y comentarios de texto.