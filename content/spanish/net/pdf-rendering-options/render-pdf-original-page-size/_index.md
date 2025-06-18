---
"description": "Aprenda a renderizar archivos PDF con el tamaño de página original con GroupDocs.Viewer para .NET. Siga nuestra guía paso a paso e integre esta funcionalidad a la perfección."
"linktitle": "Renderizar PDF con el tamaño de página original"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Renderizar PDF con el tamaño de página original"
"url": "/es/net/pdf-rendering-options/render-pdf-original-page-size/"
"weight": 17
---

# Renderizar PDF con el tamaño de página original

## Introducción
En el ámbito del desarrollo .NET, GroupDocs.Viewer destaca como una potente herramienta para renderizar diversos formatos de documentos, incluyendo PDF. Un requisito común en la gestión de documentos es renderizar PDF conservando su tamaño de página original. Para lograr esta tarea sin problemas, se requiere un conocimiento profundo de GroupDocs.Viewer para .NET y sus funcionalidades.

![Renderizar PDF con el tamaño de página original con GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/render-pdf-with-original-page-size.png)

## Prerrequisitos
Antes de comenzar a renderizar archivos PDF con tamaños de página originales usando GroupDocs.Viewer para .NET, asegúrese de tener los siguientes requisitos previos:
### 1. Instalar GroupDocs.Viewer para .NET
Comience descargando la biblioteca GroupDocs.Viewer del sitio web. Puede obtenerla en el sitio web proporcionado. [enlace de descarga](https://releases.groupdocs.com/viewer/net/)Siga las instrucciones de instalación proporcionadas en la documentación para integrarlo en su proyecto .NET de manera efectiva.
### 2. Configurar el entorno de desarrollo
Asegúrese de tener un entorno de desarrollo configurado para el desarrollo .NET. Esto incluye tener instalado un IDE compatible, como Visual Studio, y conocimientos básicos de programación en C#.
### 3. Obtenga un documento PDF
Necesitará un documento PDF de muestra para renderizar con GroupDocs.Viewer. Puede usar cualquier documento PDF para realizar pruebas. Si no tiene uno, puede descargar un PDF de muestra de diversas fuentes en línea.

## Importar espacios de nombres
Antes de continuar con la renderización de archivos PDF, es fundamental importar los espacios de nombres necesarios a su proyecto de C#. Este paso le permite acceder a las clases y métodos necesarios desde la biblioteca GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ahora que tiene los requisitos previos establecidos y los espacios de nombres necesarios importados, desglosemos el proceso de renderización de archivos PDF con tamaños de página originales usando GroupDocs.Viewer para .NET en pasos simples:
## Paso 1: Definir el directorio de salida
```csharp
string outputDirectory = "Your Document Directory";
```
Asegúrese de especificar el directorio donde desea guardar las páginas renderizadas. Reemplazar `"Your Document Directory"` con la ruta del directorio deseado.
## Paso 2: Definir el formato de la ruta del archivo de página
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
Configure el formato para nombrar los archivos de página renderizados. En este ejemplo, las páginas se guardarán como imágenes PNG con nombres de archivo en el formato `"page_1.png"`, `"page_2.png"`, etcétera.
## Paso 3: Renderizar el PDF con el tamaño de página original
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
Instanciar una `Viewer` objeto con la ruta a su archivo PDF. Luego, cree `PngViewOptions` con el formato de ruta de archivo de página especificado. Establecer `RenderOriginalPageSize` propiedad a `true` para conservar los tamaños de página originales durante la renderización.
## Paso 4: Mostrar la ubicación del documento renderizado
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Imprima un mensaje indicando que la representación fue exitosa y proporcione el directorio donde se guardan las páginas representadas.

## Conclusión
Renderizar archivos PDF con el tamaño de página original con GroupDocs.Viewer para .NET es un proceso sencillo si sigue los pasos de este tutorial. Al importar los espacios de nombres necesarios y seguir la guía paso a paso, podrá integrar esta funcionalidad sin problemas en sus aplicaciones .NET.
## Preguntas frecuentes
### ¿Puede GroupDocs.Viewer reproducir otros formatos de documentos además de PDF?
Sí, GroupDocs.Viewer admite la representación de varios formatos de documentos, incluidos Word, Excel, PowerPoint y más.
### ¿GroupDocs.Viewer es compatible con .NET Core?
Sí, GroupDocs.Viewer es compatible con entornos .NET Framework y .NET Core.
### ¿Puedo personalizar el formato de salida de las páginas renderizadas?
Sí, puede personalizar el formato de salida ajustando las opciones proporcionadas por GroupDocs.Viewer, como configurar diferentes formatos de imagen o especificar opciones de renderizado personalizadas.
### ¿GroupDocs.Viewer ofrece soporte para la representación de documentos basada en la nube?
Sí, GroupDocs.Viewer proporciona API para la representación de documentos en la nube, lo que le permite representar documentos directamente desde proveedores de almacenamiento en la nube.
### ¿Hay una prueba gratuita disponible para GroupDocs.Viewer?
Sí, puede explorar GroupDocs.Viewer con una prueba gratuita visitando el sitio web proporcionado. [enlace](https://releases.groupdocs.com/).