---
title: Recuperar y guardar documentos adjuntos
linktitle: Recuperar y guardar documentos adjuntos
second_title: API GroupDocs.Viewer .NET
description: Administre eficientemente los archivos adjuntos de documentos dentro de aplicaciones .NET utilizando GroupDocs.Viewer. Recupere y guarde archivos adjuntos sin problemas.
weight: 12
url: /es/net/processing-document-attachments/retrieve-and-save-attachments/
---
## Introducción
En la era digital, la gestión eficiente de documentos es crucial tanto para las empresas como para los particulares. Ya sea para administrar correos electrónicos, ver contratos o acceder a informes, tener una herramienta confiable para la visualización de documentos es esencial. GroupDocs.Viewer para .NET surge como una solución sólida que permite a los usuarios ver e interactuar sin esfuerzo con varios formatos de documentos directamente dentro de sus aplicaciones .NET.
## Requisitos previos
Antes de profundizar en el uso de GroupDocs.Viewer para .NET para recuperar y guardar documentos adjuntos, asegúrese de tener los siguientes requisitos previos:
1. Entorno operativo: un entorno de trabajo configurado con .NET framework.
2.  Instalación: Biblioteca GroupDocs.Viewer para .NET descargada e instalada. Puedes acceder a la biblioteca desde el[enlace de descarga](https://releases.groupdocs.com/viewer/net/).
3. Comprensión básica: familiaridad con el lenguaje de programación C#.
4. Fuente del documento: acceso a un documento de muestra con archivos adjuntos para fines de demostración.

## Importar espacios de nombres
Para comenzar a utilizar GroupDocs.Viewer para .NET para recuperar y guardar documentos adjuntos, importe los espacios de nombres necesarios:
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Results;
```

## Paso 1: definir el directorio de salida
```csharp
string outputDirectory = "Your Document Directory";
```
Defina el directorio donde desea guardar los archivos adjuntos recuperados del documento.
## Paso 2: Crear una instancia del objeto Visor
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
Cree una instancia del objeto Visor con la ruta al documento que contiene los archivos adjuntos.
## Paso 3: recuperar archivos adjuntos
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
Recuperar una lista de archivos adjuntos presentes en el documento.
## Paso 4: guardar archivos adjuntos
```csharp
foreach(Attachment attachment in attachments)
{
    string filePath = Path.Combine(outputDirectory, attachment.FileName);  
    viewer.SaveAttachment(attachment, File.OpenWrite(filePath)); 
}
```
Repita cada archivo adjunto, defina la ruta del archivo y guarde el archivo adjunto en el directorio especificado.
## Paso 5: Mostrar mensaje de éxito
```csharp
Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
```
Muestra un mensaje de éxito que indica que los archivos adjuntos se guardaron correctamente junto con la ruta del directorio.

## Conclusión
La incorporación de GroupDocs.Viewer para .NET en sus flujos de trabajo de manejo de documentos agiliza el proceso de administración de archivos adjuntos, ofreciendo eficiencia y conveniencia. Siguiendo la guía paso a paso descrita anteriormente, los usuarios pueden recuperar y guardar documentos adjuntos sin problemas dentro de sus aplicaciones .NET.
## Preguntas frecuentes
### ¿Puede GroupDocs.Viewer para .NET manejar varios formatos de documentos?
Sí, GroupDocs.Viewer admite una amplia gama de formatos de documentos, incluidos PDF, documentos de Microsoft Office, imágenes y más.
### ¿Hay una prueba gratuita disponible para GroupDocs.Viewer para .NET?
 Sí, puedes acceder a la prueba gratuita desde[aquí](https://releases.groupdocs.com/).
### ¿Cómo puedo obtener licencias temporales de GroupDocs.Viewer para .NET?
 Las licencias temporales se pueden adquirir en[este enlace](https://purchase.groupdocs.com/temporary-license/).
### ¿Dónde puedo encontrar documentación para GroupDocs.Viewer para .NET?
 Documentación completa disponible[aquí](https://tutorials.groupdocs.com/viewer/net/).
### ¿Qué opciones de soporte están disponibles para GroupDocs.Viewer para .NET?
 Puede buscar ayuda en el foro de la comunidad.[aquí](https://forum.groupdocs.com/c/viewer/9).