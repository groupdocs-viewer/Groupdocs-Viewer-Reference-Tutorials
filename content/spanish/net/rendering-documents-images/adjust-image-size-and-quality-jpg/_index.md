---
"description": "Aprenda a optimizar el tamaño y la calidad de las imágenes en formato JPEG con Groupdocs.Viewer para .NET. Mejore su experiencia de visualización de documentos."
"linktitle": "Ajustar el tamaño y la calidad de la imagen (JPG)"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Ajustar el tamaño y la calidad de la imagen (JPG)"
"url": "/es/net/rendering-documents-images/adjust-image-size-and-quality-jpg/"
"weight": 11
---

# Ajustar el tamaño y la calidad de la imagen (JPG)

## Introducción
Groupdocs.Viewer para .NET es una potente biblioteca que permite a los desarrolladores integrar fácilmente la visualización de documentos en sus aplicaciones .NET. Un requisito común en las aplicaciones de visualización de documentos es la posibilidad de ajustar el tamaño y la calidad de las imágenes, especialmente al trabajar con imágenes JPEG (JPG). En este tutorial, le guiaremos a través del proceso de ajuste del tamaño y la calidad de las imágenes con Groupdocs.Viewer para .NET.
## Prerrequisitos
Antes de comenzar, asegúrese de tener lo siguiente:
1. Comprensión básica del lenguaje de programación C#.
2. Visual Studio instalado en su sistema.
3. La biblioteca Groupdocs.Viewer para .NET está instalada. Puede descargarla desde [aquí](https://releases.groupdocs.com/viewer/net/).

## Importar espacios de nombres
Primero, debe importar los espacios de nombres necesarios a su código C#. Estos espacios de nombres proporcionan acceso a las clases y métodos necesarios para trabajar con Groupdocs.Viewer.
## Paso 1: Importar espacios de nombres
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ahora, vamos a dividir el código de ejemplo proporcionado en varios pasos para una mejor comprensión.
## Paso 2: Establecer el directorio de salida y el formato de la ruta del archivo de página
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
En este paso, especificamos el directorio de salida donde se guardarán las imágenes renderizadas y definimos el formato para la ruta del archivo de cada imagen de página.
## Paso 3: Inicializar el visor y configurar las opciones de visualización JPG
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
Aquí, inicializamos el objeto Visor con la ruta del documento que se va a visualizar. Luego, creamos una instancia de JpgViewOptions y configuramos el ancho y la altura deseados para las imágenes JPEG.
## Paso 4: Renderizar el documento fuente
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Finalmente, imprimimos un mensaje indicando la representación exitosa del documento fuente y la ubicación donde se guardan las imágenes de salida.

## Conclusión
En este tutorial, aprendimos a ajustar el tamaño y la calidad de las imágenes JPEG con Groupdocs.Viewer para .NET. Siguiendo los pasos descritos anteriormente, podrá incorporar fácilmente esta funcionalidad a sus aplicaciones .NET, ofreciendo a los usuarios una experiencia optimizada de visualización de imágenes.
## Preguntas frecuentes
### ¿Puedo ajustar también la calidad de la imagen?
Sí, puede ajustar la calidad de la imagen configurando la propiedad Calidad en JpgViewOptions.
### ¿Qué formatos de documentos admite Groupdocs.Viewer para .NET?
Groupdocs.Viewer para .NET admite una amplia gama de formatos de documentos, incluidos DOCX, PDF, PPTX, XLSX y más.
### ¿Groupdocs.Viewer para .NET es compatible con .NET Core?
Sí, Groupdocs.Viewer para .NET es compatible con .NET Core junto con el tradicional .NET Framework.
### ¿Puedo personalizar el formato de nombre del archivo de salida?
Sí, puede personalizar el formato de nombre del archivo de salida modificando la variable pageFilePathFormat en el código.
### ¿Groupdocs.Viewer para .NET admite anotaciones de documentos?
Sí, Groupdocs.Viewer para .NET proporciona soporte integral para anotaciones de documentos, incluido resaltado, subrayado y comentarios de texto.