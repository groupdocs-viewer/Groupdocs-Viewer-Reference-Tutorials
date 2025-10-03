---
"description": "Descubra cómo extraer información de visualización de archivos de datos de Outlook (PST, OST) con GroupDocs.Viewer para .NET. Mejore sus capacidades de gestión de documentos sin esfuerzo."
"linktitle": "Obtener información de visualización de archivos de datos de Outlook (PST, OST)"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Obtener información de visualización de archivos de datos de Outlook (PST, OST)"
"url": "/es/net/rendering-outlook-data-files/get-view-info-outlook-data-file/"
"weight": 10
type: docs
---
# Obtener información de visualización de archivos de datos de Outlook (PST, OST)

## Introducción
En el ámbito de la gestión y visualización de documentos, GroupDocs.Viewer para .NET es una herramienta potente, especialmente para gestionar archivos de datos de Outlook (PST, OST). En este tutorial, profundizaremos en el proceso de extracción de información de visualización de estos archivos paso a paso.
## Prerrequisitos
Antes de embarcarnos en este tutorial, asegúrese de tener los siguientes requisitos previos:
### 1. Instalación de GroupDocs.Viewer para .NET
Primero, necesita tener GroupDocs.Viewer para .NET instalado en su entorno de desarrollo. Puede descargar el paquete necesario desde [GroupDocs.Viewer para sitios web .NET](https://releases.groupdocs.com/viewer/net/).
### 2. Familiaridad con el lenguaje de programación C#
El conocimiento básico del lenguaje de programación C# es esencial para comprender e implementar los ejemplos de código proporcionados.
### 3. Archivos de datos de Outlook (PST, OST)
Asegúrese de tener archivos de datos de Outlook (PST, OST) disponibles para realizar pruebas. Puede obtener archivos de muestra de diversas fuentes o usar sus propios archivos de datos.

## Importar espacios de nombres
Antes de sumergirnos en el código, asegurémonos de importar los espacios de nombres necesarios:
```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Ahora, vamos a dividir el ejemplo proporcionado en varios pasos:
## Paso 1: Crear una instancia del objeto Visor
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST_SUBFOLDERS))
```
Aquí, inicializamos un objeto Visor con la ruta al archivo de datos de Outlook (OST) especificado como argumento.
## Paso 2: Configurar las opciones de información de visualización
```csharp
ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
```
Estamos configurando las opciones para recuperar la información de la vista. En este caso, optamos por la vista HTML.
## Paso 3: Recuperar información de visualización de Outlook
```csharp
OutlookViewInfo rootFolderInfo = viewer.GetViewInfo(options) as OutlookViewInfo;
```
Esta línea obtiene la información de visualización del archivo de datos de Outlook.
## Paso 4: Mostrar el tipo de archivo y el número de páginas
```csharp
Console.WriteLine("File type is: " + rootFolderInfo.FileType);
Console.WriteLine("Pages count: " + rootFolderInfo.Pages.Count);
```
Estamos imprimiendo el tipo de archivo y la cantidad de páginas en el archivo de datos de Outlook.
## Paso 5: Iterar a través de las carpetas
```csharp
foreach (string folder in rootFolderInfo.Folders)
    Console.WriteLine(folder);
```
Este bucle itera a través de las carpetas contenidas dentro del archivo de datos de Outlook e imprime sus nombres.
## Paso 6: Finalizar la recuperación
```csharp
Console.WriteLine("\nView info retrieved successfully.");
```
Se muestra un mensaje que indica la recuperación exitosa de la información de la vista.

## Conclusión
GroupDocs.Viewer para .NET ofrece una solución integral para extraer información de vista de archivos de datos de Outlook (PST, OST). Siguiendo los pasos de este tutorial, podrá obtener fácilmente información valiosa sobre estos archivos para una mejor gestión de documentos.
## Preguntas frecuentes
### ¿GroupDocs.Viewer para .NET es compatible con diferentes versiones de archivos de datos de Outlook?
Sí, GroupDocs.Viewer para .NET admite varias versiones de archivos de datos de Outlook, lo que garantiza la compatibilidad entre diferentes entornos.
### ¿Puedo personalizar las opciones de visualización de los archivos de datos de Outlook usando GroupDocs.Viewer para .NET?
¡Por supuesto! GroupDocs.Viewer para .NET ofrece amplias opciones de personalización, lo que le permite adaptar la experiencia de visualización a sus necesidades.
### ¿GroupDocs.Viewer para .NET admite otros formatos de archivos además de los archivos de datos de Outlook?
Sí, GroupDocs.Viewer para .NET admite una amplia gama de formatos de archivos, incluidos, entre otros, PDF, DOCX, XLSX y más.
### ¿Hay una prueba gratuita disponible para GroupDocs.Viewer para .NET?
Sí, puede acceder a una prueba gratuita de GroupDocs.Viewer para .NET desde el sitio web: [Prueba gratuita](https://releases.groupdocs.com/).
### ¿Dónde puedo encontrar soporte o asistencia adicional para GroupDocs.Viewer para .NET?
Para cualquier consulta o asistencia, puede visitar el foro de soporte de GroupDocs.Viewer para .NET: [Apoyo](https://forum.groupdocs.com/c/viewer/9).