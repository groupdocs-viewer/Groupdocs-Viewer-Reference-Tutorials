---
title: Renderizar PDF con tamaño de página original
linktitle: Renderizar PDF con tamaño de página original
second_title: API GroupDocs.Viewer .NET
description: Aprenda a renderizar archivos PDF con tamaños de página originales usando GroupDocs.Viewer para .NET. Siga nuestra guía paso a paso e integre perfectamente esta funcionalidad.
weight: 17
url: /es/net/pdf-rendering-options/render-pdf-original-page-size/
---
## Introducción
En el ámbito del desarrollo de .NET, GroupDocs.Viewer se destaca como una poderosa herramienta para representar varios formatos de documentos, incluidos PDF. Un requisito común en el manejo de documentos es renderizar archivos PDF conservando sus tamaños de página originales. Lograr esta tarea sin problemas requiere una comprensión integral de GroupDocs.Viewer para .NET y sus funcionalidades.
## Requisitos previos
Antes de sumergirse en la renderización de archivos PDF con tamaños de página originales usando GroupDocs.Viewer para .NET, asegúrese de tener implementados los siguientes requisitos previos:
### 1. Instale GroupDocs.Viewer para .NET
 Comience descargando la biblioteca GroupDocs.Viewer del sitio web. Puede obtener la biblioteca desde el sitio proporcionado.[enlace de descarga](https://releases.groupdocs.com/viewer/net/). Siga las instrucciones de instalación proporcionadas en la documentación para integrarlo en su proyecto .NET de manera efectiva.
### 2. Configurar el entorno de desarrollo
Asegúrese de tener un entorno de desarrollo configurado para el desarrollo .NET. Esto incluye tener instalado un IDE compatible, como Visual Studio, y un conocimiento básico de la programación en C#.
### 3. Obtener un documento PDF
Necesitará un documento PDF de muestra para renderizar con GroupDocs.Viewer. Puede utilizar cualquier documento PDF con fines de prueba. Si no tiene uno, puede descargar un PDF de muestra de varias fuentes en línea.

## Importar espacios de nombres
Antes de continuar con la renderización de archivos PDF, es esencial importar los espacios de nombres necesarios a su proyecto C#. Este paso le permite acceder a las clases y métodos necesarios desde la biblioteca GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ahora que tiene los requisitos previos implementados y los espacios de nombres necesarios importados, dividamos el proceso de renderizado de archivos PDF con tamaños de página originales usando GroupDocs.Viewer para .NET en pasos simples:
## Paso 1: definir el directorio de salida
```csharp
string outputDirectory = "Your Document Directory";
```
 Asegúrese de especificar el directorio donde desea que se guarden las páginas renderizadas. Reemplazar`"Your Document Directory"` con la ruta del directorio deseado.
## Paso 2: Definir el formato de ruta del archivo de página
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
Configure el formato para nombrar los archivos de página renderizados. En este ejemplo, las páginas se guardarán como imágenes PNG con nombres de archivo en el formato`"page_1.png"`, `"page_2.png"`, etcétera.
## Paso 3: renderice PDF con el tamaño de página original
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
 Crear una instancia de`Viewer` objeto con la ruta a su archivo PDF. Luego, crea`PngViewOptions` con el formato de ruta de archivo de página especificado. Colocar`RenderOriginalPageSize` propiedad a`true` para conservar los tamaños de página originales durante la renderización.
## Paso 4: Mostrar la ubicación del documento renderizado
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Imprima un mensaje que indique la renderización exitosa y proporcione el directorio donde se guardan las páginas renderizadas.

## Conclusión
Renderizar archivos PDF con tamaños de página originales usando GroupDocs.Viewer para .NET es un proceso sencillo si sigue los pasos descritos en este tutorial. Al importar los espacios de nombres necesarios y seguir la guía paso a paso, puede integrar perfectamente esta funcionalidad en sus aplicaciones .NET.
## Preguntas frecuentes
### ¿GrupoDocs.Viewer puede representar otros formatos de documentos además de PDF?
Sí, GroupDocs.Viewer admite la representación de varios formatos de documentos, incluidos Word, Excel, PowerPoint y más.
### ¿GroupDocs.Viewer es compatible con .NET Core?
Sí, GroupDocs.Viewer es compatible con los entornos .NET Framework y .NET Core.
### ¿Puedo personalizar el formato de salida de las páginas renderizadas?
Sí, puede personalizar el formato de salida ajustando las opciones proporcionadas por GroupDocs.Viewer, como configurar diferentes formatos de imagen o especificar opciones de representación personalizadas.
### ¿GroupDocs.Viewer ofrece soporte para la representación de documentos basada en la nube?
Sí, GroupDocs.Viewer proporciona API para la representación de documentos basada en la nube, lo que le permite representar documentos directamente desde proveedores de almacenamiento en la nube.
### ¿Existe una prueba gratuita disponible para GroupDocs.Viewer?
 Sí, puede explorar GroupDocs.Viewer con una prueba gratuita visitando el sitio web proporcionado.[enlace](https://releases.groupdocs.com/).