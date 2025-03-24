---
title: Renderizar imágenes EMZ y EMF
linktitle: Renderizar imágenes EMZ y EMF
second_title: API GroupDocs.Viewer .NET
description: Aprenda a renderizar imágenes EMZ y EMF en varios formatos utilizando GroupDocs.Viewer para .NET. Tutorial fácil de seguir para desarrolladores.
weight: 14
url: /es/net/image-rendering/render-emz-emf-images/
---

# Renderizar imágenes EMZ y EMF

## Introducción

GroupDocs.Viewer para .NET es una potente API de representación de documentos que permite a los desarrolladores mostrar varios tipos de documentos, incluidas imágenes EMZ (Enhanced Windows Metafile) y EMF (Enhanced Metafile), en sus aplicaciones .NET. En este tutorial, exploraremos cómo renderizar imágenes EMZ y EMF en diferentes formatos, como HTML, JPG, PNG y PDF, utilizando GroupDocs.Viewer para .NET.

## Requisitos previos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

1.  GroupDocs.Viewer para .NET: puede descargar la biblioteca desde[aquí](https://releases.groupdocs.com/viewer/net/).
2. Entorno de desarrollo: asegúrese de tener un entorno de desarrollo compatible configurado para el desarrollo .NET.
3. Imágenes EMZ/EMF de muestra: tenga imágenes EMZ y EMF de muestra disponibles para renderizar.

## Importar espacios de nombres

Antes de profundizar en el código, importemos los espacios de nombres necesarios:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Ahora, dividamos cada ejemplo en varios pasos en un formato de guía paso a paso:

## Representación de imágenes EMZ/EMF a HTML

### Paso 1: configurar el directorio de salida:
```csharp
string outputDirectory = "Your Document Directory";
```
 Reemplazar`"Your Document Directory"`con la ruta donde desea guardar el archivo HTML renderizado.

### Paso 2: Definir el formato de ruta del archivo de página:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
Esto especificará el formato de ruta del archivo para el archivo HTML renderizado.

### Paso 3: renderizar en HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
 Este código inicializa el`Viewer` objeto con la imagen EMZ de muestra y lo representa en formato HTML utilizando las opciones especificadas.

## Renderizar imágenes EMZ/EMF a JPG, PNG y PDF

Repita los siguientes pasos para renderizar en formatos JPG, PNG y PDF:

### Paso 1: Definir el formato de ruta del archivo de página:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
Ajuste el nombre y la extensión del archivo según el formato de salida deseado (`jpg`, `png` , o`pdf`).

### Paso 2: renderizar al formato respectivo:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // Ajustar opciones según el formato de salida (Jpg, Png, Pdf)
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
 Reemplazar`JpgViewOptions` con`PngViewOptions` o`PdfViewOptions` según el formato de salida deseado.

## Conclusión

En conclusión, GroupDocs.Viewer para .NET proporciona una solución perfecta para representar imágenes EMZ y EMF en varios formatos en aplicaciones .NET. Siguiendo los pasos descritos en este tutorial, los desarrolladores pueden integrar fácilmente capacidades de representación de documentos en sus aplicaciones.

## Preguntas frecuentes

### P: ¿GrupoDocs.Viewer puede representar otros formatos de documentos además de las imágenes EMZ y EMF?
R: Sí, GroupDocs.Viewer admite una amplia gama de formatos de documentos, incluidos PDF, DOCX, PPTX, XLSX y más.

### P: ¿Hay una prueba gratuita disponible para GroupDocs.Viewer para .NET?
 R: Sí, puedes acceder a la prueba gratuita.[aquí](https://releases.groupdocs.com/).

### P: ¿GroupDocs.Viewer ofrece soporte para desarrolladores?
 R: Sí, GroupDocs brinda soporte a través de su[foro](https://forum.groupdocs.com/c/viewer/9) donde los desarrolladores pueden hacer preguntas y buscar ayuda.

### P: ¿Puedo comprar una licencia temporal de GroupDocs.Viewer para .NET?
 R: Sí, se pueden comprar licencias temporales[aquí](https://purchase.groupdocs.com/temporary-license/).

### P: ¿Dónde puedo encontrar documentación detallada de GroupDocs.Viewer para .NET?
 R: Puede consultar la documentación.[aquí](https://tutorials.groupdocs.com/viewer/net/)para obtener orientación completa sobre el uso de la API.