---
"description": "Aprenda a convertir documentos a PDF con GroupDocs.Viewer para .NET. Incluye una guía paso a paso con requisitos previos y preguntas frecuentes."
"linktitle": "Convertir documento a PDF"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Convertir documento a PDF"
"url": "/es/net/rendering-documents-pdf/render-to-pdf/"
"weight": 10
---

# Convertir documento a PDF

## Introducción
GroupDocs.Viewer para .NET es una potente herramienta para convertir varios formatos de documentos a PDF. En este tutorial, le guiaremos paso a paso por el proceso.
## Prerrequisitos

Antes de comenzar, asegúrese de tener lo siguiente:
1. Biblioteca GroupDocs.Viewer para .NET: puede descargar la biblioteca desde [aquí](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: asegúrese de tener la versión adecuada de .NET Framework instalada en su máquina.
3. Archivos de documento: Prepare los archivos de documento que desea renderizar. Los formatos compatibles incluyen DOCX, PDF, PPTX, XLSX y más.

## Importación de espacios de nombres:
Antes de sumergirse en el código, asegúrese de importar los espacios de nombres necesarios:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ahora, dividamos el proceso de renderizado en varios pasos:
## Paso 1: Definir el directorio de salida y la ruta del archivo
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
Asegúrese de reemplazar `"Your Document Directory"` con el directorio donde desea guardar el archivo PDF renderizado.
## Paso 2: Crear una instancia del objeto Visor
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Tu código aquí
}
```
Reemplazar `TestFiles.SAMPLE_DOCX` con la ruta a su archivo de documento.
## Paso 3: Establecer las opciones de visualización del PDF
```csharp
PdfViewOptions options = new PdfViewOptions(outputFilePath);
```
## Paso 4: Convertir el documento a PDF
```csharp
viewer.View(options);
```
## Paso 5: Mostrar mensaje de éxito
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Después de seguir estos pasos, habrá convertido exitosamente su documento en PDF usando GroupDocs.Viewer para .NET.

## Conclusión
Convertir documentos a PDF es un requisito común en diversas aplicaciones. Con GroupDocs.Viewer para .NET, este proceso se vuelve fluido y eficiente, permitiéndole gestionar una amplia gama de formatos de documentos con facilidad.
## Preguntas frecuentes
### ¿Puedo convertir documentos que no sean DOCX a PDF?
Sí, GroupDocs.Viewer para .NET admite varios formatos como PDF, PPTX, XLSX y más.
### ¿Hay una versión de prueba disponible?
Sí, puedes descargar una versión de prueba gratuita desde [aquí](https://releases.groupdocs.com/).
### ¿Cómo puedo obtener ayuda si encuentro algún problema?
Puedes visitar el foro de GroupDocs.Viewer [aquí](https://forum.groupdocs.com/c/viewer/9) para obtener ayuda.
### ¿Necesito una licencia temporal para realizar pruebas?
Sí, puede obtener una licencia temporal de [aquí](https://purchase.groupdocs.com/temporary-license/).
### ¿Dónde puedo comprar una licencia completa?
Puede adquirir una licencia en [aquí](https://purchase.groupdocs.com/buy).