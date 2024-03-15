---
title: Establecer tiempo de espera de carga de recursos (avanzado)
linktitle: Establecer tiempo de espera de carga de recursos (avanzado)
second_title: API GroupDocs.Viewer .NET
description: Aprenda a configurar tiempos de espera de carga de recursos en GroupDocs.Viewer para .NET de manera eficiente. Representación maestra de documentos con precisión y estabilidad.
type: docs
weight: 13
url: /es/net/advanced-loading/set-resource-loading-timeout/
---
## Introducción
En el ámbito del desarrollo .NET, GroupDocs.Viewer proporciona un potente conjunto de herramientas para representar documentos e imágenes con precisión y eficiencia. Aprovechar sus capacidades requiere comprender sus complejidades, incluido el establecimiento de tiempos de espera de carga de recursos. En este tutorial, profundizaremos en el proceso de configuración de tiempos de espera de carga de recursos en GroupDocs.Viewer para .NET.
## Requisitos previos
Antes de embarcarse en este tutorial, asegúrese de tener los siguientes requisitos previos:
1. Conocimientos básicos de desarrollo .NET: la familiaridad con la programación C# y los fundamentos del marco .NET es esencial.
2.  Instalación de GroupDocs.Viewer para .NET: Descargue e instale la biblioteca GroupDocs.Viewer para .NET desde[pagina de descarga](https://releases.groupdocs.com/viewer/net/).
3. Entorno de desarrollo integrado (IDE): tenga un IDE como Visual Studio instalado en su sistema.

## Importar espacios de nombres
Antes de sumergirse en el proceso de codificación, importe los espacios de nombres necesarios:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Paso 1: definir el directorio de salida
En primer lugar, defina el directorio donde se guardarán los documentos renderizados:
```csharp
string outputDirectory = "Your Document Directory";
```
 Reemplazar`"Your Document Directory"`con la ruta donde desea guardar los documentos renderizados.
## Paso 2: Definir el formato de ruta del archivo de página
Defina el formato para las rutas de archivo de páginas individuales:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Este formato generará nombres de archivos como`page_1.html`, `page_2.html`, etc., dentro del directorio de salida especificado.
## Paso 3: configurar las opciones de carga
Configure las opciones de carga, incluido el tiempo de espera de carga de recursos:
```csharp
LoadOptions loadOptions = new LoadOptions
{
    ResourceLoadingTimeout = TimeSpan.FromSeconds(5)
};
```
En este ejemplo, se establece un tiempo de espera de 5 segundos para la carga de recursos.
## Paso 4: inicializar el objeto visor
 Inicializar el`Viewer` objeto con el documento a renderizar y las opciones de carga definidas:
```csharp
using (Viewer viewer = new Viewer(TestFiles.WITH_EXTERNAL_IMAGE_DOC, loadOptions))
```
 Reemplazar`TestFiles.WITH_EXTERNAL_IMAGE_DOC` con la ruta al documento que desea renderizar.
## Paso 5: configurar las opciones de vista HTML
Configure las opciones de vista HTML para recursos integrados:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Esta configuración garantiza que los recursos incrustados, como imágenes, se incluyan en el HTML renderizado.
## Paso 6: renderizar documento
Renderice el documento usando las opciones configuradas:
```csharp
viewer.View(options);
```
Este paso inicia el proceso de renderizado.
## Paso 7: Mostrar el directorio de salida
Muestra un mensaje que indica la representación exitosa y la ubicación del directorio de salida:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusión
Dominar los tiempos de espera de carga de recursos en GroupDocs.Viewer para .NET es crucial para garantizar procesos de representación de documentos sin problemas. Al seguir este tutorial, obtendrá información sobre cómo configurar tiempos de espera de manera efectiva, mejorando su competencia en el desarrollo de .NET.
## Preguntas frecuentes
### ¿Cuál es la importancia de establecer tiempos de espera de carga de recursos?
Establecer tiempos de espera de carga de recursos garantiza que los procesos de renderizado no se bloqueen indefinidamente, lo que mejora la estabilidad de la aplicación.
### ¿Se pueden personalizar los tiempos de espera de carga de recursos según los tipos de documentos?
Sí, los tiempos de espera de carga de recursos se pueden ajustar según la complejidad y el tamaño de los documentos que se procesan.
### ¿Existe alguna implicación para el rendimiento al establecer tiempos de espera más cortos?
Los tiempos de espera más cortos pueden provocar una representación incompleta de documentos complejos si los recursos no se pueden cargar dentro del período especificado.
### ¿GroupDocs.Viewer es adecuado para representar varios formatos de documentos?
Sí, GroupDocs.Viewer admite la representación de una amplia gama de formatos de documentos, incluidos PDF, DOCX, XLSX y más.
### ¿Se pueden desactivar los tiempos de espera de carga de recursos?
Si bien no se recomienda, los tiempos de espera de carga de recursos se pueden establecer en un valor alto o desactivarse por completo según los requisitos específicos.