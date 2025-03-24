---
title: Cancelar renderizado con token de cancelación
linktitle: Cancelar renderizado con token de cancelación
second_title: API GroupDocs.Viewer .NET
description: Integre Groupdocs.Viewer para .NET sin problemas en sus proyectos .NET para una visualización eficiente de documentos.
weight: 11
url: /es/net/rendering-options/cancel-render-cancellation-token/
---
## Introducción
Groupdocs.Viewer para .NET es una poderosa herramienta diseñada para simplificar la visualización y el procesamiento de documentos dentro de aplicaciones .NET. Ya sea que trabaje con archivos PDF, documentos de Microsoft Office u otros formatos comunes, esta biblioteca ofrece una funcionalidad sólida para integrar perfectamente las capacidades de visualización de documentos en sus proyectos .NET.
## Requisitos previos
Antes de profundizar en la integración de Groupdocs.Viewer para .NET, asegúrese de cumplir con los siguientes requisitos previos:
1.  Instalación: descargue e instale la biblioteca Groupdocs.Viewer para .NET desde el archivo proporcionado.[enlace de descarga](https://releases.groupdocs.com/viewer/net/).
   
2.  Licencia: Obtenga una licencia de[Documentos de grupo](https://purchase.groupdocs.com/buy) para desbloquear todo el potencial de la biblioteca. Alternativamente, puede comenzar con una prueba gratuita utilizando el[licencia temporal](https://purchase.groupdocs.com/temporary-license/).
   
3. Entorno de desarrollo: asegúrese de tener configurado un entorno de desarrollo compatible, incluido Visual Studio o cualquier otro IDE .NET de su elección.

## Importar espacios de nombres
Para utilizar Groupdocs.Viewer para .NET de forma eficaz, debe importar los espacios de nombres necesarios a su proyecto. Sigue estos pasos:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Ahora, dividamos el ejemplo proporcionado en varios pasos para una mejor comprensión e implementación:
## Paso 1: definir el directorio de salida
```csharp
string outputDirectory = "Your Document Directory";
```
Este paso establece el directorio donde se almacenarán las páginas del documento renderizado.
## Paso 2: Definir el formato de ruta del archivo de página
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Aquí definimos el formato para las rutas de archivo de las páginas de documentos individuales.
## Paso 3: inicializar CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource se utiliza para generar instancias de CancellationToken que se pueden utilizar para cancelar operaciones asincrónicas.
## Paso 4: obtener el token de cancelación
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
Este paso recupera el token de CancellationTokenSource, que se utilizará para cancelar la operación de representación.
## Paso 5: renderizar páginas de documentos
```csharp
Task.Run(() =>
{
    using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX, new ViewerSettings(new GroupDocs.Viewer.Logging.ConsoleLogger())))
    {
        HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
        options.RenderComments = true;
        viewer.View(options, cancellationToken);
    }
}, cancellationToken);
```
Aquí, iniciamos la representación de páginas de documentos de forma asincrónica usando Task.Run(). La instancia del Visor se crea con el archivo de documento especificado (SAMPLE_DOCX) y se configuran las opciones de representación. Luego, el proceso de renderizado se inicia utilizando el método View de la clase Viewer.
## Paso 6: Establecer el tiempo de espera de renderizado
```csharp
cancellationTokenSource.CancelAfter(10);
```
Este paso establece un tiempo de espera de 10 milisegundos para la operación de renderizado. Si la operación excede este tiempo de espera, se cancelará automáticamente.
## Paso 7: Mostrar mensaje de éxito
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Finalmente, se muestra un mensaje de éxito que indica que el documento se ha procesado correctamente.

## Conclusión
En este tutorial, cubrimos los conceptos básicos de la integración de Groupdocs.Viewer para .NET en sus proyectos. Si sigue los pasos descritos anteriormente, puede incorporar sin problemas capacidades de visualización de documentos en sus aplicaciones .NET, mejorando la experiencia del usuario y la productividad.
## Preguntas frecuentes
### ¿Groupdocs.Viewer para .NET es compatible con todos los formatos de documentos?
Groupdocs.Viewer para .NET admite una amplia gama de formatos de documentos, incluidos PDF, documentos de Microsoft Office, imágenes y más.
### ¿Puedo personalizar la apariencia de las páginas del documento renderizado?
Sí, puedes personalizar varios aspectos del proceso de renderizado, incluido el tamaño de la página, la calidad, las marcas de agua y más.
### ¿Groupdocs.Viewer para .NET requiere conectividad a Internet?
No, Groupdocs.Viewer para .NET funciona localmente dentro de su entorno .NET y no requiere conectividad a Internet para ver documentos.
### ¿Hay soporte técnico disponible para Groupdocs.Viewer para .NET?
 Sí, el soporte técnico está disponible a través del[Foro de documentos grupales](https://forum.groupdocs.com/c/viewer/9), donde puede hacer preguntas, informar problemas e interactuar con la comunidad.
### ¿Puedo probar Groupdocs.Viewer para .NET antes de comprarlo?
 Sí, puedes comenzar con una prueba gratuita utilizando el formulario proporcionado.[versión de prueba](https://releases.groupdocs.com/).