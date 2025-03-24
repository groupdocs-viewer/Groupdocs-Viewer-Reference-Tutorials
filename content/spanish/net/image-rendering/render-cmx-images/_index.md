---
title: Renderizar imágenes CMX
linktitle: Renderizar imágenes CMX
second_title: API GroupDocs.Viewer .NET
description: Aprenda a representar sin esfuerzo imágenes CMX en varios formatos utilizando GroupDocs.Viewer para .NET. Mejora tu gestión documental.
weight: 13
url: /es/net/image-rendering/render-cmx-images/
---
## Introducción
En el ámbito de la gestión y manipulación de documentos, renderizar imágenes en varios formatos es una tarea fundamental. GroupDocs.Viewer para .NET simplifica este proceso al proporcionar funcionalidades integrales para representar imágenes CMX en diferentes formatos, como HTML, JPG, PNG y PDF. Este tutorial lo guiará a través del proceso paso a paso de renderizar imágenes CMX usando GroupDocs.Viewer para .NET.
## Requisitos previos
Antes de sumergirse en el tutorial, asegúrese de cumplir con los siguientes requisitos previos:
1.  Biblioteca GroupDocs.Viewer para .NET: descargue e instale la biblioteca GroupDocs.Viewer para .NET desde[aquí](https://releases.groupdocs.com/viewer/net/).
2. Entorno de desarrollo: tenga un entorno de desarrollo de trabajo configurado con .NET framework.
3. Archivo de imagen CMX: obtenga un archivo de imagen CMX que desee renderizar.

## Importando espacios de nombres
Antes de continuar, asegúrese de importar los espacios de nombres necesarios para acceder a las funcionalidades de GroupDocs.Viewer en su aplicación .NET:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

## Representación a HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
- Definir directorio de salida: establezca el directorio donde desea almacenar los archivos HTML renderizados.
- Especificar formato de ruta de archivo: defina el formato para los archivos HTML de salida.
- Crear una instancia del objeto Visor: cree una instancia de la clase Visor con el archivo de imagen CMX.
- Opciones de representación HTML: configure las opciones de representación HTML, como la incorporación de recursos.
- Representar CMX en HTML: invoque el método Ver del objeto visor para representar la imagen CMX en HTML.
## Renderizado a JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- Definir directorio de salida: establezca el directorio para almacenar los archivos JPG renderizados.
- Especificar formato de ruta de archivo: defina el formato para los archivos JPG de salida.
- Crear una instancia del objeto Visor: cree una instancia de la clase Visor con el archivo de imagen CMX.
- Opciones de renderizado JPG: configure las opciones de renderizado JPG.
- Renderizar CMX a JPG: invoque el método Ver del objeto visor para renderizar la imagen CMX a JPG.
## Renderizado a PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Definir directorio de salida: establezca el directorio para almacenar los archivos PNG renderizados.
- Especificar formato de ruta de archivo: defina el formato para los archivos PNG de salida.
- Crear una instancia del objeto Visor: cree una instancia de la clase Visor con el archivo de imagen CMX.
- Opciones de renderizado PNG: configure las opciones de renderizado PNG.
- Renderizar CMX a PNG: invoque el método Ver del objeto visor para renderizar la imagen CMX a PNG.
## Renderizado a PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- Definir directorio de salida: establezca el directorio para almacenar el archivo PDF renderizado.
- Especificar formato de ruta de archivo: defina el formato del archivo PDF de salida.
- Crear una instancia del objeto Visor: cree una instancia de la clase Visor con el archivo de imagen CMX.
- Opciones de representación de PDF: configure las opciones de representación de PDF.
- Renderizar CMX a PDF: invoque el método Ver del objeto visor para renderizar la imagen CMX a PDF.

## Conclusión
En conclusión, GroupDocs.Viewer para .NET ofrece una solución sólida para representar imágenes CMX en varios formatos sin problemas. Si sigue los pasos descritos en este tutorial, podrá integrar sin esfuerzo las capacidades de representación de imágenes CMX en sus aplicaciones .NET, mejorando la eficiencia de la gestión de documentos.
## Preguntas frecuentes
### ¿Puedo renderizar páginas específicas de una imagen CMX?
Sí, puede renderizar páginas específicas especificando el número de página en las opciones de renderizado.
### ¿GroupDocs.Viewer para .NET es compatible con todos los marcos .NET?
Sí, GroupDocs.Viewer para .NET es compatible con múltiples marcos .NET, incluidos .NET Core y .NET Framework.
### ¿GroupDocs.Viewer admite la representación de imágenes CMX cifradas?
Sí, GroupDocs.Viewer admite la representación de imágenes CMX cifradas con las claves de descifrado adecuadas.
### ¿Puedo personalizar las opciones de renderizado para diferentes formatos de salida?
Por supuesto, GroupDocs.Viewer ofrece amplias opciones para personalizar los parámetros de renderizado según sus requisitos.
### ¿Existe un foro comunitario para soporte de GroupDocs.Viewer?
 Sí, puede buscar ayuda e interactuar con la comunidad GroupDocs.Viewer en el foro de soporte.[aquí](https://forum.groupdocs.com/c/viewer/9).