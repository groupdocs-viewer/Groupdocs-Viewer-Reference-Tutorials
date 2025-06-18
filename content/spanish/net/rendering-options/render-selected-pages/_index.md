---
"description": "Aprenda a renderizar páginas seleccionadas de documentos con Groupdocs.Viewer para .NET. Tutorial paso a paso con ejemplos de código."
"linktitle": "Renderizar páginas seleccionadas"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Renderizar páginas seleccionadas"
"url": "/es/net/rendering-options/render-selected-pages/"
"weight": 17
---

# Renderizar páginas seleccionadas

## Introducción

En este tutorial, profundizaremos en cómo usar Groupdocs.Viewer para .NET para renderizar páginas seleccionadas de un documento. Tanto si eres un desarrollador experimentado como si estás empezando, esta guía paso a paso te guiará por el proceso fácilmente.

## Prerrequisitos

Antes de comenzar, asegúrese de tener los siguientes requisitos previos:

### 1. Instalación

Asegúrese de tener instalado Groupdocs.Viewer para .NET en su entorno de desarrollo. De lo contrario, puede descargarlo desde [Enlace de descarga](https://releases.groupdocs.com/viewer/net/).

## Importación de espacios de nombres

En su archivo de código C#, importe los espacios de nombres necesarios para acceder a las clases y métodos requeridos. Puede hacerlo usando `using` directiva:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ahora vamos a dividir el código de ejemplo proporcionado en varios pasos:

## Paso 1: Establecer el directorio de salida

Define el directorio donde quieres guardar las páginas renderizadas. Reemplazar `"Your Document Directory"` con la ruta de directorio deseada.

```csharp
string outputDirectory = "Your Document Directory";
```

## Paso 2: Definir el formato de la ruta del archivo de página

Especifique el formato de las rutas de archivo de las páginas renderizadas. Esto se usará para guardar cada página como archivo HTML en el directorio de salida.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Paso 3: Crear una instancia del objeto Visor

Crea una instancia de la clase Viewer, pasando la ruta del documento que quieres renderizar como argumento.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## Paso 4: Configurar las opciones de vista HTML

Configura las opciones de visualización HTML para la renderización. En este ejemplo, configuramos opciones para incrustar recursos en la salida HTML.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## Paso 5: Renderizar las páginas seleccionadas

Especifique los números de página que desea renderizar. En este caso, renderizamos las páginas 1 a 3. A continuación, llame al método View en el objeto Viewer, pasando las opciones y los números de página como argumentos.

```csharp
viewer.View(options, 1, 3);
```

## Paso 6: Resultado de salida

Por último, muestra un mensaje indicando la representación exitosa del documento y la ubicación donde se guardan los archivos de salida.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusión

¡Felicitaciones! Aprendió a renderizar páginas seleccionadas de un documento con Groupdocs.Viewer para .NET. Con este conocimiento, ahora puede integrar fácilmente las funciones de renderizado de documentos en sus aplicaciones .NET.

## Preguntas frecuentes

### P: ¿Puedo renderizar páginas de diferentes tipos de documentos, como PDF o imágenes?

R: Sí, Groupdocs.Viewer para .NET admite la representación de páginas de varios formatos de documentos, incluidos PDF, documentos de Microsoft Office y archivos de imagen.

### P: ¿Hay una versión de prueba disponible para probar antes de comprar?

R: Sí, puede acceder a una versión de prueba gratuita de Groupdocs.Viewer para .NET desde [sitio web](https://releases.groupdocs.com/).

### P: ¿Puedo personalizar el formato de salida además de HTML?

R: Por supuesto. Groupdocs.Viewer para .NET ofrece opciones para representar páginas como imágenes, archivos PDF y más, además de HTML.

### P: ¿Cómo puedo obtener licencias temporales para fines de prueba?

A: Las licencias temporales se pueden adquirir en la [página de licencia temporal](https://purchase.groupdocs.com/temporary-license/) en el sitio web de Groupdocs.

### P: ¿Dónde puedo buscar asistencia u obtener ayuda con cualquier problema que encuentre?

A: Puedes visitar el [Foro de Groupdocs.Viewer](https://forum.groupdocs.com/c/viewer/9) para recibir apoyo y orientación de la comunidad y los desarrolladores.