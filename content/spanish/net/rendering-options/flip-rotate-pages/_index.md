---
title: Voltear y rotar páginas
linktitle: Voltear y rotar páginas
second_title: API GroupDocs.Viewer .NET
description: Aprenda cómo integrar Groupdocs.Viewer para .NET en sus aplicaciones para renderizar, voltear y rotar documentos sin problemas.
weight: 12
url: /es/net/rendering-options/flip-rotate-pages/
---

# Voltear y rotar páginas

## Introducción
En este tutorial, profundizaremos en las funcionalidades de Groupdocs.Viewer para .NET, centrándonos específicamente en voltear y rotar páginas. Groupdocs.Viewer para .NET es una poderosa herramienta diseñada para representar documentos en varios formatos dentro de aplicaciones .NET. Ya sea que esté desarrollando un sistema de gestión de documentos o necesite integrar capacidades de visualización de documentos en su software, Groupdocs.Viewer para .NET proporciona una solución eficiente.
## Requisitos previos
Antes de comenzar, asegúrese de tener configurados los siguientes requisitos previos:
### Instalación de Groupdocs.Viewer para .NET
 Para utilizar Groupdocs.Viewer para .NET, debe instalar el paquete a través del Administrador de paquetes NuGet. Puede encontrar instrucciones de instalación detalladas en el[documentación](https://tutorials.groupdocs.com/viewer/net/).

## Importar espacios de nombres
Asegúrese de haber importado los espacios de nombres necesarios en su proyecto para utilizar Groupdocs.Viewer para .NET de manera efectiva.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Dividamos el proceso de voltear y rotar páginas usando Groupdocs.Viewer para .NET en pasos simples:
## Paso 1: configurar el directorio de salida y la ruta del archivo
Defina el directorio donde desea guardar el archivo de salida y especifique la ruta del archivo de salida.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## Paso 2: inicializar el objeto visor
Cree una instancia de la clase Visor pasando la ruta al documento que desea ver.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## Paso 3: configurar las opciones de visualización
Configure las opciones de visualización, como especificar el formato del archivo de salida y cualquier configuración adicional como la rotación de páginas.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## Paso 4: renderizar documento
Invoque el método Ver del objeto Visor y pase las opciones de vista.
```csharp
viewer.View(viewOptions);
```
## Paso 5: Mostrar mensaje de éxito
Informe al usuario que el documento se ha procesado correctamente y especifique el directorio de salida para su verificación.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusión
En conclusión, Groupdocs.Viewer para .NET ofrece potentes capacidades para representar documentos, incluido voltear y rotar páginas. Si sigue los pasos descritos en este tutorial, podrá integrar perfectamente estas funciones en sus aplicaciones .NET, mejorando la experiencia de visualización de documentos para sus usuarios.
## Preguntas frecuentes
### ¿Groupdocs.Viewer para .NET es compatible con todos los formatos de documentos?
Sí, Groupdocs.Viewer para .NET admite una amplia gama de formatos de documentos, incluidos DOCX, PDF, PPTX y más.
### ¿Puedo personalizar las opciones de visualización más allá de voltear y rotar páginas?
Por supuesto, Groupdocs.Viewer para .NET proporciona varias opciones de personalización para ver documentos, lo que le permite adaptar la experiencia a sus necesidades.
### ¿Hay una prueba gratuita disponible para Groupdocs.Viewer para .NET?
 Sí, puede aprovechar una prueba gratuita de Groupdocs.Viewer para .NET visitando el[sitio web](https://releases.groupdocs.com/).
### ¿Cómo puedo obtener soporte para Groupdocs.Viewer para .NET?
 Puede buscar ayuda e interactuar con la comunidad a través de[Foro Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9).
### ¿Dónde puedo obtener una licencia temporal de Groupdocs.Viewer para .NET?
 Las licencias temporales para Groupdocs.Viewer para .NET se pueden obtener en[pagina de compra](https://purchase.groupdocs.com/temporary-license/).