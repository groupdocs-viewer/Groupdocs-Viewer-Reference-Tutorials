---
title: Representar páginas seleccionadas
linktitle: Representar páginas seleccionadas
second_title: API GroupDocs.Viewer .NET
description: Aprenda a representar páginas seleccionadas de documentos usando Groupdocs.Viewer para .NET. Tutorial paso a paso con ejemplos de código incluidos.
weight: 17
url: /es/net/rendering-options/render-selected-pages/
---
## Introducción

En este tutorial, profundizaremos en cómo utilizar Groupdocs.Viewer para .NET para representar páginas seleccionadas de un documento. Ya sea que sea un desarrollador experimentado o esté comenzando, esta guía paso a paso lo guiará a través del proceso con facilidad.

## Requisitos previos

Antes de comenzar, asegúrese de cumplir con los siguientes requisitos previos:

### 1. Instalación

 Asegúrese de tener Groupdocs.Viewer para .NET instalado en su entorno de desarrollo. Si no, puedes descargarlo desde[Enlace de descarga](https://releases.groupdocs.com/viewer/net/).

## Importando espacios de nombres

En su archivo de código C#, importe los espacios de nombres necesarios para acceder a las clases y métodos requeridos. Puedes hacer esto usando el`using` directiva:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ahora dividamos el código de ejemplo proporcionado en varios pasos:

## Paso 1: configurar el directorio de salida

 Defina el directorio donde desea que se guarden las páginas renderizadas. Reemplazar`"Your Document Directory"` con la ruta del directorio deseada.

```csharp
string outputDirectory = "Your Document Directory";
```

## Paso 2: Definir el formato de ruta del archivo de página

Especifique el formato de las rutas de archivo de las páginas renderizadas. Esto se utilizará para guardar cada página como un archivo HTML en el directorio de salida.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Paso 3: Crear una instancia del objeto Visor

Cree una instancia de la clase Viewer y pase la ruta del documento que desea representar como argumento.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## Paso 4: configurar las opciones de vista HTML

Configure las opciones de vista HTML para renderizar. En este ejemplo, estamos configurando opciones para incrustar recursos en la salida HTML.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## Paso 5: renderizar las páginas seleccionadas

Especifique los números de página que desea representar. En este caso, estamos representando las páginas 1 a 3. Luego, llamamos al método View en el objeto Viewer, pasando las opciones y los números de página como argumentos.

```csharp
viewer.View(options, 1, 3);
```

## Paso 6: resultado de salida

Finalmente, muestre un mensaje que indique la renderización exitosa del documento y la ubicación donde se guardan los archivos de salida.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusión

¡Felicidades! Ha aprendido con éxito cómo representar páginas seleccionadas de un documento usando Groupdocs.Viewer para .NET. Con este conocimiento, ahora puede integrar capacidades de representación de documentos en sus aplicaciones .NET con facilidad.

## Preguntas frecuentes

### P: ¿Puedo renderizar páginas de diferentes tipos de documentos, como archivos PDF o imágenes?

R: Sí, Groupdocs.Viewer para .NET admite la representación de páginas de varios formatos de documentos, incluidos PDF, documentos de Microsoft Office y archivos de imagen.

### P: ¿Existe una versión de prueba disponible para probar antes de comprar?

 R: Sí, puede acceder a una versión de prueba gratuita de Groupdocs.Viewer para .NET desde[sitio web](https://releases.groupdocs.com/).

### P: ¿Puedo personalizar el formato de salida que no sea HTML?

R: Por supuesto, Groupdocs.Viewer para .NET ofrece opciones para representar páginas como imágenes, archivos PDF y más, además de HTML.

### P: ¿Cómo puedo obtener licencias temporales para realizar pruebas?

R: Las licencias temporales se pueden adquirir en el[página de licencia temporal](https://purchase.groupdocs.com/temporary-license/) en el sitio web de Groupdocs.

### P: ¿Dónde puedo buscar asistencia u obtener ayuda con cualquier problema que tenga?

 R: Puedes visitar el[Foro Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) para obtener apoyo y orientación de la comunidad y los desarrolladores.