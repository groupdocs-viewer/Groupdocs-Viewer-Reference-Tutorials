---
title: Obtener información de visualización para archivos de datos de Outlook (PST, OST)
linktitle: Obtener información de visualización para archivos de datos de Outlook (PST, OST)
second_title: API GroupDocs.Viewer .NET
description: Explore cómo extraer información de visualización de archivos de datos de Outlook (PST, OST) usando GroupDocs.Viewer para .NET. Mejore sus capacidades de gestión de documentos sin esfuerzo.
weight: 10
url: /es/net/rendering-outlook-data-files/get-view-info-outlook-data-file/
---

# Obtener información de visualización para archivos de datos de Outlook (PST, OST)

## Introducción
En el ámbito de la gestión y visualización de documentos, GroupDocs.Viewer para .NET se destaca como una herramienta poderosa, particularmente cuando se trata de manejar archivos de datos de Outlook (PST, OST). En este tutorial, profundizaremos en el proceso de extracción de información de visualización para estos archivos paso a paso.
## Requisitos previos
Antes de embarcarnos en este tutorial, asegúrese de tener implementados los siguientes requisitos previos:
### 1. Instalación de GroupDocs.Viewer para .NET
 En primer lugar, debe tener GroupDocs.Viewer para .NET instalado en su entorno de desarrollo. Puede descargar el paquete necesario desde el[GroupDocs.Viewer para el sitio web .NET](https://releases.groupdocs.com/viewer/net/).
### 2. Familiaridad con el lenguaje de programación C#
El conocimiento básico del lenguaje de programación C# es esencial para comprender e implementar los ejemplos de código proporcionados.
### 3. Archivos de datos de Outlook (PST, OST)
Asegúrese de tener archivos de datos de Outlook (PST, OST) disponibles para realizar pruebas. Puede obtener archivos de muestra de varias fuentes o utilizar sus propios archivos de datos.

## Importar espacios de nombres
Antes de profundizar en el código, asegurémonos de importar los espacios de nombres necesarios:
```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Ahora, dividamos el ejemplo proporcionado en varios pasos:
## Paso 1: crear una instancia del objeto visor
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST_SUBFOLDERS))
```
Aquí, estamos inicializando un objeto Visor con la ruta al archivo de datos de Outlook (OST) especificada como argumento.
## Paso 2: configurar las opciones de visualización de información
```csharp
ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
```
Estamos configurando las opciones para recuperar información de visualización. En este caso, optamos por la vista HTML.
## Paso 3: recuperar la información de vista de Outlook
```csharp
OutlookViewInfo rootFolderInfo = viewer.GetViewInfo(options) as OutlookViewInfo;
```
Esta línea recupera la información de visualización del archivo de datos de Outlook.
## Paso 4: Mostrar el tipo de archivo y el recuento de páginas
```csharp
Console.WriteLine("File type is: " + rootFolderInfo.FileType);
Console.WriteLine("Pages count: " + rootFolderInfo.Pages.Count);
```
Estamos imprimiendo el tipo de archivo y el recuento de páginas en el archivo de datos de Outlook.
## Paso 5: iterar a través de carpetas
```csharp
foreach (string folder in rootFolderInfo.Folders)
    Console.WriteLine(folder);
```
Este bucle recorre en iteración las carpetas contenidas en el archivo de datos de Outlook e imprime sus nombres.
## Paso 6: finalizar la recuperación
```csharp
Console.WriteLine("\nView info retrieved successfully.");
```
Se muestra un mensaje que indica la recuperación exitosa de la información de la vista.

## Conclusión
GroupDocs.Viewer para .NET proporciona una solución perfecta para extraer información de visualización de archivos de datos de Outlook (PST, OST). Si sigue los pasos descritos en este tutorial, podrá obtener fácilmente información valiosa sobre estos archivos para mejorar la gestión de documentos.
## Preguntas frecuentes
### ¿GroupDocs.Viewer para .NET es compatible con diferentes versiones de archivos de datos de Outlook?
Sí, GroupDocs.Viewer para .NET admite varias versiones de archivos de datos de Outlook, lo que garantiza la compatibilidad en diferentes entornos.
### ¿Puedo personalizar las opciones de visualización de archivos de datos de Outlook usando GroupDocs.Viewer para .NET?
¡Absolutamente! GroupDocs.Viewer para .NET ofrece amplias opciones de personalización, lo que le permite adaptar la experiencia de visualización según sus requisitos.
### ¿GroupDocs.Viewer para .NET admite otros formatos de archivo además de los archivos de datos de Outlook?
Sí, GroupDocs.Viewer para .NET admite una amplia gama de formatos de archivo, incluidos, entre otros, PDF, DOCX, XLSX y más.
### ¿Hay una prueba gratuita disponible para GroupDocs.Viewer para .NET?
 Sí, puede acceder a una prueba gratuita de GroupDocs.Viewer para .NET desde el sitio web:[Prueba gratis](https://releases.groupdocs.com/).
### ¿Dónde puedo encontrar soporte o asistencia adicional para GroupDocs.Viewer para .NET?
 Para cualquier consulta o asistencia, puede visitar el foro de soporte de GroupDocs.Viewer para .NET:[Apoyo](https://forum.groupdocs.com/c/viewer/9).