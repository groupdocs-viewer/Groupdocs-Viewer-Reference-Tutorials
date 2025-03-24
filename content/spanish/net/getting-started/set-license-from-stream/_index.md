---
title: Establecer licencia desde Stream
linktitle: Establecer licencia desde Stream
second_title: API GroupDocs.Viewer .NET
description: Mejore sus aplicaciones .NET con GroupDocs.Viewer para una visualización perfecta de documentos. Siga nuestra guía paso a paso e integre potentes capacidades de visualización de documentos sin esfuerzo.
weight: 11
url: /es/net/getting-started/set-license-from-stream/
---

# Establecer licencia desde Stream

## Introducción
¿Está buscando potenciar sus aplicaciones .NET con capacidades avanzadas de visualización de documentos? GroupDocs.Viewer para .NET ofrece una solución integral para integrar perfectamente las funcionalidades de visualización de documentos en sus proyectos. En este tutorial, profundizaremos en el proceso de aprovechar GroupDocs.Viewer para .NET para enriquecer sus aplicaciones con potentes capacidades de visualización de documentos. 
## Requisitos previos
Antes de sumergirnos en el proceso de integración, asegúrese de cumplir con los siguientes requisitos previos:
1. Conocimientos básicos de desarrollo .NET: la familiaridad con C# y .NET Framework es esencial para seguir este tutorial.
   
2.  Paquete GroupDocs.Viewer para .NET: asegúrese de haber descargado e instalado el paquete GroupDocs.Viewer para .NET. Puedes obtenerlo del[enlace de descarga](https://releases.groupdocs.com/viewer/net/).
3.  Acceso a la documentación de GroupDocs: mantenga el[documentación](https://tutorials.groupdocs.com/viewer/net/) útil como referencia durante el proceso de integración.

## Importar espacios de nombres
Para empezar, importe los espacios de nombres necesarios a su aplicación .NET. Sigue estos pasos:
### Paso 1: abra su proyecto .NET.
Asegúrese de tener su proyecto .NET abierto en su entorno de desarrollo preferido.
### Paso 2: agregue el espacio de nombres GroupDocs.Viewer.
En su archivo de código, agregue el siguiente espacio de nombres para acceder a las funcionalidades de GroupDocs.Viewer:
```csharp
using System;
using System.IO;
```
## Establecer licencia desde Stream
El siguiente paso consiste en configurar la licencia desde una secuencia. Siga estos pasos detallados:
### Paso 1: definir el directorio de salida.
Establezca el directorio donde se almacenarán sus documentos definiendo el directorio de salida:
```csharp
string outputDirectory = "Your Document Directory";
```
### Paso 2: Verifique la existencia del archivo de licencia.
Compruebe si el archivo de licencia existe en el directorio de su proyecto:
```csharp
if (File.Exists(Utils.LicensePath))
```
### Paso 3: configurar la licencia.
Si el archivo de licencia existe, configure la licencia usando la secuencia proporcionada:
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### Paso 4: Manejar la ausencia de licencia.
Si no se encuentra el archivo de licencia, proporcione instrucciones para obtener una licencia:
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://compra.groupdocs.com/faqs/licensing. " +
                      "\nLearn how to request a temporary license at https://compra.groupdocs.com/temporary-license.");
}
```

## Conclusión
¡Felicidades! Ha aprendido con éxito cómo integrar GroupDocs.Viewer para .NET en sus aplicaciones. Con esta poderosa herramienta, ahora puede ver sin esfuerzo varios formatos de documentos dentro de sus proyectos .NET, mejorando la experiencia del usuario y la productividad.
## Preguntas frecuentes
### ¿Necesito una licencia para utilizar GroupDocs.Viewer para .NET?
Sí, necesita una licencia para utilizar GroupDocs.Viewer para .NET. Puede obtener una licencia temporal o permanente en el sitio web de GroupDocs.
### ¿Puedo integrar GroupDocs.Viewer en mi aplicación ASP.NET?
¡Absolutamente! GroupDocs.Viewer para .NET se integra perfectamente en aplicaciones web y de escritorio, incluido ASP.NET.
### ¿Qué formatos de documentos son compatibles con GroupDocs.Viewer?
GroupDocs.Viewer admite una amplia gama de formatos de documentos, incluidos PDF, Microsoft Office (Word, Excel, PowerPoint), imágenes y más.
### ¿GroupDocs.Viewer es compatible con .NET Core?
Sí, GroupDocs.Viewer para .NET es compatible tanto con .NET Framework como con .NET Core.
### ¿Puedo personalizar la interfaz del visor según el tema de mi aplicación?
Sí, GroupDocs.Viewer ofrece amplias opciones de personalización, lo que le permite adaptar la interfaz del visor para que coincida perfectamente con el tema de su aplicación.