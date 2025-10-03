---
"description": "Aprenda a renderizar archivos CHM en .NET con GroupDocs.Viewer. Convierta fácilmente archivos CHM a HTML, JPG, PNG y PDF."
"linktitle": "Renderizar archivos CHM"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Renderizar archivos CHM"
"url": "/es/net/rendering-web-documents/render-chm/"
"weight": 10
type: docs
---
# Renderizar archivos CHM

## Introducción
En este tutorial, exploraremos cómo renderizar archivos CHM (Ayuda HTML compilada) con GroupDocs.Viewer para .NET. GroupDocs.Viewer para .NET es una potente API de renderizado de documentos que permite a los desarrolladores mostrar más de 170 tipos de documentos en sus aplicaciones .NET sin necesidad de instalar software externo.

## Prerrequisitos

Antes de comenzar a renderizar archivos CHM, asegúrese de tener los siguientes requisitos previos:

### Instalación de GroupDocs.Viewer para .NET

Para comenzar, necesita instalar GroupDocs.Viewer para .NET. Puede descargar la biblioteca desde [Sitio web de GroupDocs](https://releases.groupdocs.com/viewer/net/) o instálelo a través del Administrador de paquetes NuGet ejecutando el siguiente comando en la Consola del Administrador de paquetes:

```bash
Install-Package GroupDocs.Viewer
```

## Importación de espacios de nombres

Asegúrese de importar los espacios de nombres necesarios en su proyecto:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ahora vamos a dividir el proceso de renderizado en varios pasos:

## Paso 1: Definir el directorio de salida

Define el directorio donde quieres que se guarden los archivos renderizados:

```csharp
string outputDirectory = "Your Document Directory";
```

## Paso 2: Renderizar a HTML

Para convertir archivos CHM a HTML, utilice el siguiente fragmento de código:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // Establezca en verdadero para convertir todo el contenido CHM en una sola página

    viewer.View(options); // Convertir todas las páginas
}
```

## Paso 3: Renderizar a JPG

Para convertir archivos CHM en imágenes JPG, utilice el siguiente fragmento de código:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Convertir solo las páginas 1, 2, 3
}
```

## Paso 4: Renderizar a PNG

Para convertir archivos CHM en imágenes PNG, utilice el siguiente fragmento de código:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Convertir solo las páginas 1, 2, 3
}
```

## Paso 5: Renderizar a PDF

Para convertir archivos CHM en un documento PDF, utilice el siguiente fragmento de código:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); // Convertir todas las páginas
}
```

## Paso 6: Verificar la salida

Una vez completado el proceso de renderizado, verifique el directorio de salida especificado para los archivos renderizados:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusión

Renderizar archivos CHM con GroupDocs.Viewer para .NET es un proceso sencillo. Siguiendo los pasos de este tutorial, podrá convertir eficientemente documentos CHM a diversos formatos, como HTML, imágenes (JPG, PNG) y PDF, en sus aplicaciones .NET.

## Preguntas frecuentes

### P1: ¿Puede GroupDocs.Viewer reproducir otros formatos de documentos además de CHM?

A1: Sí, GroupDocs.Viewer admite la representación de más de 170 formatos de documentos, incluidos PDF, DOCX, XLSX, PPTX y más.

### P2: ¿GroupDocs.Viewer es compatible con .NET Core?

A2: Sí, GroupDocs.Viewer admite .NET Core además del tradicional .NET Framework.

### P3: ¿Puedo personalizar las opciones de renderizado para diferentes formatos de salida?

A3: Sí, GroupDocs.Viewer ofrece varias opciones para personalizar el proceso de renderizado, como especificar números de página, configurar la calidad de la imagen y configurar rutas de salida.

### P4: ¿GroupDocs.Viewer requiere alguna dependencia externa para renderizar documentos?

A4: No, GroupDocs.Viewer es una biblioteca independiente y no requiere dependencias externas ni instalaciones de software de terceros.

### P5: ¿Hay una prueba gratuita disponible para GroupDocs.Viewer?

A5: Sí, puede aprovechar una prueba gratuita de GroupDocs.Viewer visitando el sitio web [sitio web](https://releases.groupdocs.com/).