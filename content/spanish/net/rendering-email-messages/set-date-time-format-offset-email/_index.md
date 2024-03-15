---
title: Establecer formato de fecha y hora y compensación de zona horaria (correo electrónico)
linktitle: Establecer formato de fecha y hora y compensación de zona horaria (correo electrónico)
second_title: API GroupDocs.Viewer .NET
description: Integre GroupDocs.Viewer para .NET sin problemas en sus aplicaciones para obtener potentes capacidades de visualización de documentos. Mejore la experiencia del usuario con opciones personalizables.
type: docs
weight: 11
url: /es/net/rendering-email-messages/set-date-time-format-offset-email/
---

## Introducción
GroupDocs.Viewer para .NET es una poderosa herramienta que permite a los desarrolladores integrar perfectamente capacidades de visualización de documentos en sus aplicaciones .NET. Con GroupDocs.Viewer, puede mostrar una amplia gama de formatos de documentos, incluidos PDF, documentos de Microsoft Office, imágenes y más, directamente dentro de su aplicación, sin la necesidad de complementos o visores externos. En este completo tutorial, lo guiaremos a través del proceso de configuración de GroupDocs.Viewer para .NET, exploraremos sus características y demostraremos cómo utilizarlo de manera efectiva para mejorar las capacidades de visualización de documentos de su aplicación.
## Requisitos previos
Antes de sumergirse en este tutorial, asegúrese de tener configurados los siguientes requisitos previos:
1. Visual Studio: asegúrese de tener Visual Studio instalado en su sistema. GroupDocs.Viewer para .NET es totalmente compatible con Visual Studio, lo que permite una integración perfecta en sus proyectos .NET.
2.  GroupDocs.Viewer para .NET: descargue e instale GroupDocs.Viewer para .NET desde[enlace de descarga](https://releases.groupdocs.com/viewer/net/). Siga las instrucciones de instalación proporcionadas para configurar la biblioteca dentro de su entorno de desarrollo.
3. .NET Framework: asegúrese de tener instalada la versión adecuada de .NET Framework. GroupDocs.Viewer para .NET admite varias versiones de .NET Framework, incluidos .NET Core y .NET Standard.

## Importar espacios de nombres
Para utilizar GroupDocs.Viewer para .NET de forma eficaz, debe importar los espacios de nombres necesarios a su proyecto. Siga estos pasos para importar los espacios de nombres requeridos:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


Dividamos el ejemplo proporcionado en varios pasos para comprender cada componente y su funcionalidad.
## Paso 1: configurar el directorio de salida y la ruta del archivo
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
En este paso, definimos el directorio de salida donde se guardará el documento renderizado y especificamos la ruta del archivo HTML de salida.
## Paso 2: Crear una instancia del objeto Visor
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
 Aquí, creamos una nueva instancia del`Viewer` clase, pasando la ruta del documento que se va a ver (en este caso, un archivo EML de muestra) como parámetro.
## Paso 3: definir las opciones de vista HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
En este paso, configuramos las opciones de vista HTML para la representación del documento, especificando la ruta del archivo de salida para el documento HTML representado.
## Paso 4: Establecer el formato de fecha y hora y el desplazamiento de zona horaria
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Aquí, personalizamos el formato de fecha y hora para los mensajes de correo electrónico y configuramos el desplazamiento de la zona horaria según la zona horaria deseada.
## Paso 5: renderizar documento
```csharp
viewer.View(options);
```
 Finalmente llamamos al`View` método de la`Viewer` objeto, pasando las opciones de vista HTML configuradas para representar el documento en formato HTML.
## Paso 6: Mostrar directorio de salida
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Este paso simplemente muestra un mensaje que indica la renderización exitosa del documento y proporciona la ruta al directorio de salida donde se encuentra el documento HTML renderizado.

## Conclusión
GroupDocs.Viewer para .NET ofrece una solución sólida para integrar capacidades de visualización de documentos en sus aplicaciones .NET. Si sigue los pasos descritos en este tutorial, puede configurar fácilmente GroupDocs.Viewer, importar los espacios de nombres necesarios y utilizar sus funciones para representar documentos con opciones personalizables. Ya sea que esté trabajando con archivos PDF, documentos de Microsoft Office u otros formatos, GroupDocs.Viewer simplifica el proceso de visualización de documentos y mejora la experiencia del usuario de sus aplicaciones.
## Preguntas frecuentes
### ¿GroupDocs.Viewer es compatible con .NET Core?
Sí, GroupDocs.Viewer para .NET es compatible con .NET Core, lo que permite la compatibilidad multiplataforma para sus aplicaciones.
### ¿Puedo personalizar la apariencia de los documentos renderizados?
¡Absolutamente! GroupDocs.Viewer ofrece varias opciones de personalización, incluidos niveles de zoom, rotación de páginas y más, para adaptar la experiencia de visualización según sus preferencias.
### ¿Existe una versión de prueba disponible para fines de prueba?
 Sí, puede descargar una versión de prueba gratuita de GroupDocs.Viewer para .NET desde[enlace de página web](https://releases.groupdocs.com/viewer/net/) para evaluar sus características antes de realizar una compra.
### ¿GroupDocs.Viewer admite la representación de documentos protegidos con contraseña?
Sí, GroupDocs.Viewer tiene soporte integrado para representar documentos protegidos con contraseña, lo que garantiza una visualización segura de los documentos dentro de sus aplicaciones.
### ¿Dónde puedo encontrar soporte o asistencia adicional con GroupDocs.Viewer?
 Para cualquier consulta técnica o asistencia, puede visitar GroupDocs.Viewer[foro](https://forum.groupdocs.com/c/viewer/9) o comuníquese con su equipo de soporte para obtener ayuda y orientación inmediatas.