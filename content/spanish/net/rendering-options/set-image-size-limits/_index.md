---
title: Establecer límites de tamaño de imagen
linktitle: Establecer límites de tamaño de imagen
second_title: API GroupDocs.Viewer .NET
description: Aprenda a establecer límites de tamaño de imagen en aplicaciones .NET sin esfuerzo utilizando GroupDocs.Viewer para .NET, mejorando la experiencia de visualización de documentos.
weight: 21
url: /es/net/rendering-options/set-image-size-limits/
---

# Establecer límites de tamaño de imagen

## Introducción
GroupDocs.Viewer para .NET es una poderosa herramienta diseñada para facilitar la visualización perfecta de documentos dentro de aplicaciones .NET. Con sus sólidas funciones y su interfaz intuitiva, los desarrolladores pueden integrar sin esfuerzo capacidades de visualización de documentos en sus proyectos, mejorando la experiencia del usuario y la productividad. En este tutorial, exploraremos cómo establecer límites de tamaño de imagen usando GroupDocs.Viewer para .NET, garantizando una visualización óptima de los documentos manteniendo el rendimiento y la eficiencia.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
1.  GroupDocs.Viewer para .NET: asegúrese de tener instalada la biblioteca GroupDocs.Viewer para .NET necesaria en su entorno de desarrollo. Puedes descargarlo desde el[sitio web](https://releases.groupdocs.com/viewer/net/).
2. Entorno de desarrollo: configure su entorno de desarrollo .NET preferido, como Visual Studio, con las configuraciones requeridas.
3. Directorio de documentos: tenga un directorio designado donde se almacenen sus documentos y asegúrese de que la ruta del directorio sea accesible dentro de su aplicación.

## Importar espacios de nombres
Antes de continuar con la implementación, es esencial importar los espacios de nombres necesarios para acceder a las funcionalidades de GroupDocs.Viewer para .NET de manera efectiva.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Paso 1: definir el directorio de salida y la ruta del archivo
```csharp
string outputDirectory = "Your Document Directory";
string outputFile = Path.Combine(outputDirectory, "result_image_size_limit.jpg");
```
 Asegúrese de reemplazar`"Your Document Directory"` con la ruta real a su directorio de documentos.
## Paso 2: inicializar el objeto del visor y especificar la ruta del documento
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // TestFiles.SAMPLE_DOCX representa la ruta al documento de muestra.
    // Reemplácelo con la ruta al documento deseado.
```
 Reemplazar`TestFiles.SAMPLE_DOCX` con la ruta a su documento. Podría ser un DOCX, PDF o cualquier otro formato de archivo compatible.
## Paso 3: configurar las opciones de visualización JPEG
```csharp
JpgViewOptions options = new JpgViewOptions(outputFile);
options.MaxWidth = 400;
```
 Ajustar el`MaxWidth` propiedad para establecer el ancho máximo de la imagen renderizada según sus requisitos. Esto asegura que la imagen no exceda el ancho especificado, manteniendo una visualización óptima.
## Paso 4: renderizar el documento con las opciones especificadas
```csharp
viewer.View(options);
```
Esta línea de código desencadena el proceso de renderizado, generando la imagen de salida con los límites de tamaño definidos.
## Paso 5: Mostrar mensaje de éxito
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Tras la renderización exitosa, se muestra un mensaje que indica la finalización exitosa junto con la ruta del directorio de salida.

## Conclusión
En conclusión, dominar el arte de establecer límites de tamaño de imagen utilizando GroupDocs.Viewer para .NET puede mejorar significativamente la experiencia de visualización de documentos dentro de sus aplicaciones .NET. Si sigue la guía paso a paso descrita en este tutorial, puede optimizar sin esfuerzo la visualización de imágenes y al mismo tiempo garantizar el rendimiento y la eficiencia.
## Preguntas frecuentes
### ¿Puedo establecer tanto el ancho como el alto máximos para las imágenes renderizadas?
Sí, puede establecer tanto el ancho como el alto máximos utilizando las propiedades apropiadas en las opciones de vista.
### ¿Qué formatos de documentos son compatibles con GroupDocs.Viewer para .NET?
GroupDocs.Viewer para .NET admite una amplia gama de formatos de documentos, incluidos DOCX, PDF, PPT, XLS y más.
### ¿GroupDocs.Viewer para .NET es compatible con .NET Core?
Sí, GroupDocs.Viewer para .NET ofrece compatibilidad con .NET Core, lo que permite una integración perfecta en aplicaciones .NET modernas.
### ¿Puedo personalizar el formato de la imagen de salida que no sea JPEG?
Sí, GroupDocs.Viewer para .NET brinda soporte para varios formatos de salida, incluidos PNG, TIFF y PDF.
### ¿Existe una versión de prueba disponible para probar antes de comprar?
 Sí, puede aprovechar una versión de prueba gratuita desde[sitio web](https://releases.groupdocs.com/viewer/net/). para explorar las características y funcionalidades de GroupDocs.Viewer para .NET antes de realizar una compra.