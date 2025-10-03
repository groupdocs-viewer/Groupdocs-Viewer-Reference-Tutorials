---
"description": "Mejore sus aplicaciones .NET con GroupDocs.Viewer para una visualización fluida de documentos. Siga nuestra guía paso a paso e integre fácilmente potentes funciones de visualización de documentos."
"linktitle": "Establecer licencia desde Stream"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Establecer licencia desde Stream"
"url": "/es/net/getting-started/set-license-from-stream/"
"weight": 11
type: docs
---
# Establecer licencia desde Stream

## Introducción
¿Desea potenciar sus aplicaciones .NET con funciones avanzadas de visualización de documentos? GroupDocs.Viewer para .NET ofrece una solución integral para integrar a la perfección las funciones de visualización de documentos en sus proyectos. En este tutorial, profundizaremos en el proceso de aprovechar GroupDocs.Viewer para .NET para enriquecer sus aplicaciones con potentes funciones de visualización de documentos. 

![Establecer la licencia desde Stream con GroupDocs.Viewer para .NET](/viewer/getting-started/set-license-from-stream.png)

## Prerrequisitos
Antes de sumergirnos en el proceso de integración, asegúrese de tener los siguientes requisitos previos:
1. Conocimientos básicos de desarrollo .NET: Es fundamental estar familiarizado con C# y el marco .NET para seguir este tutorial.
   
2. Paquete GroupDocs.Viewer para .NET: Asegúrese de haber descargado e instalado el paquete GroupDocs.Viewer para .NET. Puede obtenerlo en [enlace de descarga](https://releases.groupdocs.com/viewer/net/).
3. Acceso a la documentación de GroupDocs: mantener la [documentación](https://tutorials.groupdocs.com/viewer/net/) Útil para tutoriales durante el proceso de integración.

## Importar espacios de nombres
Para empezar, importe los espacios de nombres necesarios a su aplicación .NET. Siga estos pasos:
### Paso 1: Abra su proyecto .NET.
Asegúrese de tener su proyecto .NET abierto en su entorno de desarrollo preferido.
### Paso 2: agregue el espacio de nombres GroupDocs.Viewer.
En su archivo de código, agregue el siguiente espacio de nombres para acceder a las funcionalidades de GroupDocs.Viewer:
```csharp
using System;
using System.IO;
```
## Establecer licencia desde Stream
El siguiente paso consiste en configurar la licencia desde una transmisión. Siga estos pasos detallados:
### Paso 1: Definir el directorio de salida.
Establezca el directorio donde se almacenarán sus documentos definiendo el directorio de salida:
```csharp
string outputDirectory = "Your Document Directory";
```
### Paso 2: Verifique la existencia del archivo de licencia.
Compruebe si el archivo de licencia existe en el directorio de su proyecto:
```csharp
if (File.Exists(Utils.LicensePath))
```
### Paso 3: Establecer licencia.
Si el archivo de licencia existe, configure la licencia utilizando el flujo proporcionado:
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### Paso 4: Gestionar la ausencia de licencia.
Si no se encuentra el archivo de licencia, proporcione instrucciones para obtener una licencia:
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://purchase.groupdocs.com/faqs/licensing. " +
                      "\nLearn how to request a temporary license at https://purchase.groupdocs.com/licencia-temporal.");
}
```

## Conclusión
¡Felicitaciones! Has aprendido a integrar GroupDocs.Viewer para .NET en tus aplicaciones. Con esta potente herramienta, ahora puedes visualizar fácilmente diversos formatos de documentos en tus proyectos .NET, mejorando así la experiencia del usuario y la productividad.
## Preguntas frecuentes
### ¿Necesito una licencia para utilizar GroupDocs.Viewer para .NET?
Sí, necesita una licencia para usar GroupDocs.Viewer para .NET. Puede obtener una licencia temporal o permanente en el sitio web de GroupDocs.
### ¿Puedo integrar GroupDocs.Viewer en mi aplicación ASP.NET?
¡Por supuesto! GroupDocs.Viewer para .NET se integra a la perfección con aplicaciones de escritorio y web, incluyendo ASP.NET.
### ¿Qué formatos de documentos admite GroupDocs.Viewer?
GroupDocs.Viewer admite una amplia gama de formatos de documentos, incluidos PDF, Microsoft Office (Word, Excel, PowerPoint), imágenes y más.
### ¿GroupDocs.Viewer es compatible con .NET Core?
Sí, GroupDocs.Viewer para .NET es compatible con .NET Framework y .NET Core.
### ¿Puedo personalizar la interfaz del visor según el tema de mi aplicación?
Sí, GroupDocs.Viewer ofrece amplias opciones de personalización, lo que le permite adaptar la interfaz del visor para que coincida perfectamente con el tema de su aplicación.