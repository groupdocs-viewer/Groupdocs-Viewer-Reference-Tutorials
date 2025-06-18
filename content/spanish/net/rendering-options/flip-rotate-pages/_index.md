---
"description": "Aprenda a integrar Groupdocs.Viewer para .NET en sus aplicaciones para lograr una representación, rotación y volteo de documentos sin inconvenientes."
"linktitle": "Voltear y rotar páginas"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Voltear y rotar páginas"
"url": "/es/net/rendering-options/flip-rotate-pages/"
"weight": 12
---

# Voltear y rotar páginas

## Introducción
En este tutorial, profundizaremos en las funcionalidades de Groupdocs.Viewer para .NET, centrándonos específicamente en el cambio de página y la rotación de páginas. Groupdocs.Viewer para .NET es una potente herramienta diseñada para renderizar documentos en diversos formatos dentro de aplicaciones .NET. Tanto si desarrolla un sistema de gestión documental como si necesita integrar funciones de visualización de documentos en su software, Groupdocs.Viewer para .NET le ofrece una solución eficiente.
## Prerrequisitos
Antes de comenzar, asegúrese de tener establecidos los siguientes requisitos previos:
### Instalación de Groupdocs.Viewer para .NET
Para usar Groupdocs.Viewer para .NET, debe instalar el paquete mediante el Administrador de paquetes NuGet. Puede encontrar instrucciones de instalación detalladas en [documentación](https://tutorials.groupdocs.com/viewer/net/).

## Importar espacios de nombres
Asegúrese de tener los espacios de nombres necesarios importados en su proyecto para utilizar Groupdocs.Viewer para .NET de manera efectiva.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Analicemos el proceso de voltear y rotar páginas usando Groupdocs.Viewer para .NET en pasos simples:
## Paso 1: Establecer el directorio de salida y la ruta del archivo
Defina el directorio donde desea que se guarde el archivo de salida y especifique la ruta del archivo de salida.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## Paso 2: Inicializar el objeto Visor
Cree una instancia de la clase Viewer pasando la ruta al documento que desea ver.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## Paso 3: Configurar las opciones de visualización
Configure las opciones de visualización, como especificar el formato del archivo de salida y cualquier configuración adicional como la rotación de página.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## Paso 4: Renderizar el documento
Invoque el método View del objeto Viewer y pase las opciones de vista.
```csharp
viewer.View(viewOptions);
```
## Paso 5: Mostrar mensaje de éxito
Informar al usuario que el documento se ha procesado correctamente y especificar el directorio de salida para su verificación.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusión
En conclusión, Groupdocs.Viewer para .NET ofrece potentes funciones para renderizar documentos, como voltear y rotar páginas. Siguiendo los pasos de este tutorial, podrá integrar estas funciones sin problemas en sus aplicaciones .NET, mejorando así la experiencia de visualización de documentos para sus usuarios.
## Preguntas frecuentes
### ¿Groupdocs.Viewer para .NET es compatible con todos los formatos de documentos?
Sí, Groupdocs.Viewer para .NET admite una amplia gama de formatos de documentos, incluidos DOCX, PDF, PPTX y más.
### ¿Puedo personalizar las opciones de visualización más allá de girar y pasar páginas?
Por supuesto, Groupdocs.Viewer para .NET ofrece varias opciones de personalización para ver documentos, lo que le permite adaptar la experiencia según sus requisitos.
### ¿Hay una prueba gratuita disponible para Groupdocs.Viewer para .NET?
Sí, puede obtener una prueba gratuita de Groupdocs.Viewer para .NET visitando el sitio web [sitio web](https://releases.groupdocs.com/).
### ¿Cómo puedo obtener soporte para Groupdocs.Viewer para .NET?
Puede buscar ayuda e interactuar con la comunidad a través de [Foro de Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9).
### ¿Dónde puedo obtener una licencia temporal para Groupdocs.Viewer para .NET?
Las licencias temporales para Groupdocs.Viewer para .NET se pueden obtener en [página de compra](https://purchase.groupdocs.com/temporary-license/).