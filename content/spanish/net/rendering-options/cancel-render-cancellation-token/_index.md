---
"description": "Integre Groupdocs.Viewer para .NET sin problemas en sus proyectos .NET para una visualización eficiente de los documentos."
"linktitle": "Cancelar renderizado con token de cancelación"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Cancelar renderizado con token de cancelación"
"url": "/es/net/rendering-options/cancel-render-cancellation-token/"
"weight": 11
type: docs
---
# Cancelar renderizado con token de cancelación

## Introducción
Groupdocs.Viewer para .NET es una potente herramienta diseñada para simplificar la visualización y el procesamiento de documentos en aplicaciones .NET. Ya sea que trabaje con archivos PDF, documentos de Microsoft Office u otros formatos comunes, esta biblioteca ofrece una funcionalidad robusta para integrar a la perfección las funciones de visualización de documentos en sus proyectos .NET.
## Prerrequisitos
Antes de sumergirse en la integración de Groupdocs.Viewer para .NET, asegúrese de tener los siguientes requisitos previos:
1. Instalación: Descargue e instale la biblioteca Groupdocs.Viewer para .NET desde el directorio proporcionado. [enlace de descarga](https://releases.groupdocs.com/viewer/net/).
   
2. Licencia: Obtenga una licencia de [Documentos grupales](https://purchase.groupdocs.com/buy) para aprovechar al máximo el potencial de la biblioteca. Alternativamente, puede comenzar con una prueba gratuita usando [licencia temporal](https://purchase.groupdocs.com/temporary-license/).
   
3. Entorno de desarrollo: asegúrese de tener configurado un entorno de desarrollo compatible, incluido Visual Studio o cualquier otro IDE .NET de su elección.

## Importar espacios de nombres
Para utilizar Groupdocs.Viewer para .NET eficazmente, debe importar los espacios de nombres necesarios a su proyecto. Siga estos pasos:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Ahora, vamos a dividir el ejemplo proporcionado en varios pasos para una mejor comprensión e implementación:
## Paso 1: Definir el directorio de salida
```csharp
string outputDirectory = "Your Document Directory";
```
Este paso establece el directorio donde se almacenarán las páginas del documento renderizado.
## Paso 2: Definir el formato de la ruta del archivo de página
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Aquí definimos el formato de las rutas de archivo de las páginas individuales del documento.
## Paso 3: Inicializar CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource se utiliza para generar instancias de CancellationToken que se pueden usar para cancelar operaciones asincrónicas.
## Paso 4: Obtener el token de cancelación
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
Este paso recupera el token de CancellationTokenSource, que se utilizará para cancelar la operación de renderizado.
## Paso 5: Renderizar páginas del documento
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
Aquí, iniciamos la renderización de las páginas del documento de forma asíncrona mediante Task.Run(). Se crea la instancia Viewer con el archivo de documento especificado (SAMPLE_DOCX) y se configuran las opciones de renderización. El proceso de renderización se inicia mediante el método View de la clase Viewer.
## Paso 6: Establecer el tiempo de espera de renderizado
```csharp
cancellationTokenSource.CancelAfter(10);
```
Este paso establece un tiempo de espera de 10 milisegundos para la operación de renderizado. Si la operación excede este tiempo, se cancelará automáticamente.
## Paso 7: Mostrar mensaje de éxito
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Finalmente, se muestra un mensaje de éxito indicando que el documento se ha procesado correctamente.

## Conclusión
En este tutorial, hemos cubierto los fundamentos de la integración de Groupdocs.Viewer para .NET en sus proyectos. Siguiendo los pasos descritos anteriormente, podrá integrar fácilmente la visualización de documentos en sus aplicaciones .NET, mejorando así la experiencia del usuario y la productividad.
## Preguntas frecuentes
### ¿Groupdocs.Viewer para .NET es compatible con todos los formatos de documentos?
Groupdocs.Viewer para .NET admite una amplia gama de formatos de documentos, incluidos PDF, documentos de Microsoft Office, imágenes y más.
### ¿Puedo personalizar la apariencia de las páginas del documento renderizado?
Sí, puedes personalizar varios aspectos del proceso de renderizado, incluido el tamaño de la página, la calidad, la marca de agua y más.
### ¿Groupdocs.Viewer para .NET requiere conectividad a Internet?
No, Groupdocs.Viewer para .NET funciona localmente dentro de su entorno .NET y no requiere conectividad a Internet para visualizar documentos.
### ¿Hay soporte técnico disponible para Groupdocs.Viewer para .NET?
Sí, el soporte técnico está disponible a través de [Foro de Groupdocs](https://forum.groupdocs.com/c/viewer/9), donde puedes hacer preguntas, informar problemas e interactuar con la comunidad.
### ¿Puedo probar Groupdocs.Viewer para .NET antes de comprarlo?
Sí, puedes comenzar con una prueba gratuita utilizando el [versión de prueba](https://releases.groupdocs.com/).