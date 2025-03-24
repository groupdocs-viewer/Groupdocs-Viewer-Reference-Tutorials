---
title: Renderizar archivos CHM
linktitle: Renderizar archivos CHM
second_title: API GroupDocs.Viewer .NET
description: Aprenda a renderizar archivos CHM en .NET usando GroupDocs.Viewer. Convierta formatos CHM a HTML, JPG, PNG y PDF sin esfuerzo.
weight: 10
url: /es/net/rendering-web-documents/render-chm/
---
## Introducción
En este tutorial, exploraremos cómo representar archivos CHM (Ayuda HTML compilada) usando GroupDocs.Viewer para .NET. GroupDocs.Viewer para .NET es una poderosa API de representación de documentos que permite a los desarrolladores mostrar más de 170 tipos de documentos dentro de sus aplicaciones .NET sin requerir ninguna instalación de software externo.

## Requisitos previos

Antes de sumergirnos en la renderización de archivos CHM, asegúrese de tener los siguientes requisitos previos:

### Instalación de GroupDocs.Viewer para .NET

 Para comenzar, necesita instalar GroupDocs.Viewer para .NET. Puedes descargar la biblioteca desde[Sitio web de GroupDocs](https://releases.groupdocs.com/viewer/net/) o instálelo a través del Administrador de paquetes NuGet ejecutando el siguiente comando en la Consola del Administrador de paquetes:

```bash
Install-Package GroupDocs.Viewer
```

## Importando espacios de nombres

Asegúrese de importar los espacios de nombres necesarios a su proyecto:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ahora dividamos el proceso de renderizado en varios pasos:

## Paso 1: definir el directorio de salida

Defina el directorio donde desea que se guarden los archivos renderizados:

```csharp
string outputDirectory = "Your Document Directory";
```

## Paso 2: renderizar en HTML

Para representar archivos CHM en HTML, utilice el siguiente fragmento de código:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // Configúrelo en verdadero para convertir todo el contenido CHM en una sola página

    viewer.View(options); //Convertir todas las páginas
}
```

## Paso 3: renderizar a JPG

Para convertir archivos CHM en imágenes JPG, utilice el siguiente fragmento de código:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Convertir sólo las páginas 1, 2, 3
}
```

## Paso 4: renderizar a PNG

Para convertir archivos CHM en imágenes PNG, utilice el siguiente fragmento de código:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Convertir sólo las páginas 1, 2, 3
}
```

## Paso 5: renderizar a PDF

Para representar archivos CHM en un documento PDF, utilice el siguiente fragmento de código:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); //Convertir todas las páginas
}
```

## Paso 6: verificar la salida

Una vez que se completa el proceso de renderizado, verifique el directorio de salida especificado para los archivos renderizados:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusión

Representar archivos CHM utilizando GroupDocs.Viewer para .NET es un proceso sencillo. Si sigue los pasos descritos en este tutorial, puede convertir de manera eficiente documentos CHM a varios formatos, como HTML, imágenes (JPG, PNG) y PDF dentro de sus aplicaciones .NET.

## Preguntas frecuentes

### P1: ¿GrupoDocs.Viewer puede representar otros formatos de documentos además de CHM?

R1: Sí, GroupDocs.Viewer admite la representación de más de 170 formatos de documentos, incluidos PDF, DOCX, XLSX, PPTX y más.

### P2: ¿GroupDocs.Viewer es compatible con .NET Core?

R2: Sí, GroupDocs.Viewer admite .NET Core además del .NET Framework tradicional.

### P3: ¿Puedo personalizar las opciones de renderizado para diferentes formatos de salida?

R3: Sí, GroupDocs.Viewer proporciona varias opciones para personalizar el proceso de renderizado, como especificar números de página, configurar la calidad de la imagen y configurar rutas de salida.

### P4: ¿GroupDocs.Viewer requiere dependencias externas para representar documentos?

R4: No, GroupDocs.Viewer es una biblioteca independiente y no requiere dependencias externas ni instalaciones de software de terceros.

### P5: ¿Existe una prueba gratuita disponible para GroupDocs.Viewer?

 R5: Sí, puede aprovechar una prueba gratuita de GroupDocs.Viewer visitando el[sitio web](https://releases.groupdocs.com/).