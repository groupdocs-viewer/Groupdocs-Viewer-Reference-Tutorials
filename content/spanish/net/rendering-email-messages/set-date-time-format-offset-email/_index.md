---
"description": "Integre GroupDocs.Viewer para .NET sin problemas en sus aplicaciones para disfrutar de potentes funciones de visualización de documentos. Mejore la experiencia del usuario con opciones personalizables."
"linktitle": "Establecer el formato de fecha y hora y la diferencia horaria (correo electrónico)"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Establecer el formato de fecha y hora y la diferencia horaria (correo electrónico)"
"url": "/es/net/rendering-email-messages/set-date-time-format-offset-email/"
"weight": 11
type: docs
---
# Establecer el formato de fecha y hora y la diferencia horaria (correo electrónico)


## Introducción
GroupDocs.Viewer para .NET es una potente herramienta que permite a los desarrolladores integrar fácilmente la visualización de documentos en sus aplicaciones .NET. Con GroupDocs.Viewer, puede visualizar una amplia gama de formatos de documentos, como PDF, documentos de Microsoft Office, imágenes y más, directamente en su aplicación, sin necesidad de complementos ni visores externos. En este completo tutorial, le guiaremos en el proceso de configuración de GroupDocs.Viewer para .NET, explorando sus funciones y demostrando cómo utilizarlo eficazmente para optimizar la visualización de documentos de su aplicación.
## Prerrequisitos
Antes de sumergirse en este tutorial, asegúrese de tener configurados los siguientes requisitos previos:
1. Visual Studio: Asegúrese de tener Visual Studio instalado en su sistema. GroupDocs.Viewer para .NET es totalmente compatible con Visual Studio, lo que permite una integración perfecta en sus proyectos .NET.
2. GroupDocs.Viewer para .NET: Descargue e instale GroupDocs.Viewer para .NET desde [enlace de descarga](https://releases.groupdocs.com/viewer/net/)Siga las instrucciones de instalación proporcionadas para configurar la biblioteca dentro de su entorno de desarrollo.
3. .NET Framework: Asegúrese de tener instalada la versión correcta de .NET Framework. GroupDocs.Viewer para .NET es compatible con varias versiones de .NET Framework, incluidas .NET Core y .NET Standard.

## Importar espacios de nombres
Para utilizar GroupDocs.Viewer para .NET eficazmente, debe importar los espacios de nombres necesarios a su proyecto. Siga estos pasos para importarlos:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


Dividamos el ejemplo proporcionado en varios pasos para comprender cada componente y su funcionalidad.
## Paso 1: Establecer el directorio de salida y la ruta del archivo
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
En este paso, definimos el directorio de salida donde se guardará el documento renderizado y especificamos la ruta del archivo HTML de salida.
## Paso 2: Crear una instancia del objeto Visor
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
Aquí, creamos una nueva instancia del `Viewer` clase, pasando la ruta del documento que se va a visualizar (en este caso, un archivo EML de muestra) como parámetro.
## Paso 3: Definir las opciones de vista HTML
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
En este paso, configuramos las opciones de vista HTML para la representación del documento, especificando la ruta del archivo de salida para el documento HTML representado.
## Paso 4: Establecer el formato de fecha y hora y la diferencia horaria
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Aquí, personalizamos el formato de fecha y hora para los mensajes de correo electrónico y establecemos la diferencia horaria de acuerdo con la zona horaria deseada.
## Paso 5: Renderizar el documento
```csharp
viewer.View(options);
```
Por último, llamamos a la `View` método de la `Viewer` objeto, pasando las opciones de vista HTML configuradas para representar el documento en formato HTML.
## Paso 6: Mostrar el directorio de salida
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Este paso simplemente muestra un mensaje que indica la representación exitosa del documento y proporciona la ruta al directorio de salida donde se encuentra el documento HTML representado.

## Conclusión
GroupDocs.Viewer para .NET ofrece una solución robusta para integrar la visualización de documentos en sus aplicaciones .NET. Siguiendo los pasos descritos en este tutorial, podrá configurar fácilmente GroupDocs.Viewer, importar los espacios de nombres necesarios y utilizar sus funciones para renderizar documentos con opciones personalizables. Tanto si trabaja con archivos PDF, documentos de Microsoft Office u otros formatos, GroupDocs.Viewer simplifica la visualización de documentos, mejorando la experiencia del usuario en sus aplicaciones.
## Preguntas frecuentes
### ¿GroupDocs.Viewer es compatible con .NET Core?
Sí, GroupDocs.Viewer para .NET es compatible con .NET Core, lo que permite compatibilidad entre plataformas para sus aplicaciones.
### ¿Puedo personalizar la apariencia de los documentos renderizados?
¡Por supuesto! GroupDocs.Viewer ofrece varias opciones de personalización, como niveles de zoom, rotación de página y más, para adaptar la experiencia de visualización a tus tutoriales.
### ¿Existe una versión de prueba disponible para fines de prueba?
Sí, puede descargar una versión de prueba gratuita de GroupDocs.Viewer para .NET desde [enlace del sitio web](https://releases.groupdocs.com/viewer/net/) para evaluar sus características antes de realizar la compra.
### ¿GroupDocs.Viewer admite la representación de documentos protegidos con contraseña?
Sí, GroupDocs.Viewer tiene soporte integrado para renderizar documentos protegidos con contraseña, lo que garantiza una visualización segura de documentos dentro de sus aplicaciones.
### ¿Dónde puedo encontrar soporte o asistencia adicional con GroupDocs.Viewer?
Para cualquier consulta técnica o asistencia, puede visitar GroupDocs.Viewer [foro](https://forum.groupdocs.com/c/viewer/9) comuníquese con su equipo de soporte para obtener ayuda y orientación inmediata.