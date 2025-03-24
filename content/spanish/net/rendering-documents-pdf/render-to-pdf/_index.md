---
title: Renderizar documento a PDF
linktitle: Renderizar documento a PDF
second_title: API GroupDocs.Viewer .NET
description: Aprenda a renderizar documentos a PDF usando GroupDocs.Viewer para .NET. Guía paso a paso con requisitos previos y preguntas frecuentes incluidas.
weight: 10
url: /es/net/rendering-documents-pdf/render-to-pdf/
---

# Renderizar documento a PDF

## Introducción
GroupDocs.Viewer para .NET es una poderosa herramienta para representar varios formatos de documentos en PDF. En este tutorial, lo guiaremos a través del proceso paso a paso.
## Requisitos previos

Antes de comenzar, asegúrese de tener lo siguiente:
1.  GroupDocs.Viewer para la biblioteca .NET: puede descargar la biblioteca desde[aquí](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: asegúrese de tener instalada la versión adecuada de .NET Framework en su máquina.
3. Archivos de documentos: prepare los archivos de documentos que desea renderizar. Los formatos admitidos incluyen DOCX, PDF, PPTX, XLSX y más.

## Importación de espacios de nombres:
Antes de profundizar en el código, asegúrese de importar los espacios de nombres necesarios:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ahora, dividamos el proceso de renderizado en varios pasos:
## Paso 1: definir el directorio de salida y la ruta del archivo
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
 Asegúrese de reemplazar`"Your Document Directory"` con el directorio donde desea guardar el archivo PDF renderizado.
## Paso 2: Crear una instancia del objeto Visor
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Tu código aquí
}
```
 Reemplazar`TestFiles.SAMPLE_DOCX` con la ruta a su archivo de documento.
## Paso 3: configurar las opciones de visualización de PDF
```csharp
PdfViewOptions options = new PdfViewOptions(outputFilePath);
```
## Paso 4: renderizar documento a PDF
```csharp
viewer.View(options);
```
## Paso 5: Mostrar mensaje de éxito
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Después de seguir estos pasos, habrá renderizado exitosamente su documento a PDF usando GroupDocs.Viewer para .NET.

## Conclusión
La renderización de documentos a PDF es un requisito común en diversas aplicaciones. Con GroupDocs.Viewer para .NET, este proceso se vuelve fluido y eficiente, lo que le permite manejar una amplia gama de formatos de documentos con facilidad.
## Preguntas frecuentes
### ¿Puedo convertir documentos que no sean DOCX a PDF?
Sí, GroupDocs.Viewer para .NET admite varios formatos, como PDF, PPTX, XLSX y más.
### ¿Hay una versión de prueba disponible?
 Sí, puedes descargar una prueba gratuita desde[aquí](https://releases.groupdocs.com/).
### ¿Cómo puedo obtener soporte si tengo algún problema?
 Puedes visitar el foro de GroupDocs.Viewer[aquí](https://forum.groupdocs.com/c/viewer/9) para asistencia.
### ¿Necesito una licencia temporal para realizar pruebas?
 Sí, puede obtener una licencia temporal de[aquí](https://purchase.groupdocs.com/temporary-license/).
### ¿Dónde puedo comprar una licencia completa?
 Puede adquirir una licencia en[aquí](https://purchase.groupdocs.com/buy).