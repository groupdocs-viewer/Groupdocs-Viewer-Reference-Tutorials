---
"description": "Gestione eficientemente los adjuntos de documentos en aplicaciones .NET con GroupDocs.Viewer. Recupere y guarde adjuntos sin complicaciones."
"linktitle": "Recuperar y guardar archivos adjuntos de documentos"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Recuperar y guardar archivos adjuntos de documentos"
"url": "/es/net/processing-document-attachments/retrieve-and-save-attachments/"
"weight": 12
type: docs
---
# Recuperar y guardar archivos adjuntos de documentos

## Introducción
En la era digital, la gestión eficiente de documentos es crucial tanto para empresas como para particulares. Ya sea para gestionar correos electrónicos, consultar contratos o acceder a informes, contar con una herramienta fiable para la visualización de documentos es esencial. GroupDocs.Viewer para .NET se presenta como una solución robusta que permite a los usuarios visualizar e interactuar fácilmente con diversos formatos de documentos directamente en sus aplicaciones .NET.

![Recupere y guarde documentos adjuntos con GroupDocs.Viewer .NET](/viewer/processing-document-attachments/retrieve-and-save-document-attachments.png)

## Prerrequisitos
Antes de comenzar a utilizar GroupDocs.Viewer para .NET para recuperar y guardar archivos adjuntos de documentos, asegúrese de tener los siguientes requisitos previos:
1. Entorno operativo: Un entorno de trabajo configurado con el marco .NET.
2. Instalación: Se descargó e instaló la biblioteca GroupDocs.Viewer para .NET. Puede acceder a ella desde [enlace de descarga](https://releases.groupdocs.com/viewer/net/).
3. Comprensión básica: familiaridad con el lenguaje de programación C#.
4. Fuente del documento: Acceso a un documento de muestra con archivos adjuntos para fines demostrativos.

## Importar espacios de nombres
Para comenzar a utilizar GroupDocs.Viewer para .NET para recuperar y guardar archivos adjuntos de documentos, importe los espacios de nombres necesarios:
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Results;
```

## Paso 1: Definir el directorio de salida
```csharp
string outputDirectory = "Your Document Directory";
```
Define el directorio donde quieres guardar los archivos adjuntos recuperados del documento.
## Paso 2: Crear una instancia del objeto Visor
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
Cree una instancia del objeto Viewer con la ruta al documento que contiene los archivos adjuntos.
## Paso 3: Recuperar archivos adjuntos
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
Recupere una lista de archivos adjuntos presentes en el documento.
## Paso 4: Guardar archivos adjuntos
```csharp
foreach(Attachment attachment in attachments)
{
    string filePath = Path.Combine(outputDirectory, attachment.FileName);  
    viewer.SaveAttachment(attachment, File.OpenWrite(filePath)); 
}
```
Recorra cada archivo adjunto, defina la ruta del archivo y guarde el archivo adjunto en el directorio especificado.
## Paso 5: Mostrar mensaje de éxito
```csharp
Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
```
Muestra un mensaje de éxito indicando que los archivos adjuntos se guardaron correctamente junto con la ruta del directorio.

## Conclusión
Incorporar GroupDocs.Viewer para .NET en sus flujos de trabajo de gestión de documentos optimiza la gestión de adjuntos, ofreciendo eficiencia y comodidad. Siguiendo la guía paso a paso descrita anteriormente, los usuarios pueden recuperar y guardar fácilmente adjuntos de documentos en sus aplicaciones .NET.
## Preguntas frecuentes
### ¿Puede GroupDocs.Viewer para .NET manejar varios formatos de documentos?
Sí, GroupDocs.Viewer admite una amplia gama de formatos de documentos, incluidos PDF, documentos de Microsoft Office, imágenes y más.
### ¿Hay una prueba gratuita disponible para GroupDocs.Viewer para .NET?
Sí, puedes acceder a la prueba gratuita desde [aquí](https://releases.groupdocs.com/).
### ¿Cómo puedo obtener licencias temporales para GroupDocs.Viewer para .NET?
Las licencias temporales se pueden adquirir en [este enlace](https://purchase.groupdocs.com/temporary-license/).
### ¿Dónde puedo encontrar documentación de GroupDocs.Viewer para .NET?
Hay documentación completa disponible [aquí](https://tutorials.groupdocs.com/viewer/net/).
### ¿Qué opciones de soporte están disponibles para GroupDocs.Viewer para .NET?
Puede buscar ayuda en el foro de la comunidad. [aquí](https://forum.groupdocs.com/c/viewer/9).