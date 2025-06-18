---
"description": "Explora la magia de GroupDocs.Viewer para .NET&#58; integra a la perfección la visualización de documentos en tus aplicaciones. ¡Prueba la versión de prueba gratuita ahora!"
"linktitle": "Obtener nombres de hojas de trabajo"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Obtener nombres de hojas de trabajo"
"url": "/es/net/spreadsheet-rendering-options/get-worksheets-names/"
"weight": 11
---

# Obtener nombres de hojas de trabajo

## Introducción
¡Bienvenido al fascinante mundo de GroupDocs.Viewer para .NET! Si eres desarrollador o entusiasta y te interesa explorar las potentes funciones de visualización de documentos en tus aplicaciones .NET, te espera una gran sorpresa. En esta guía completa, profundizaremos en los detalles de la recuperación de nombres de hojas de cálculo con GroupDocs.Viewer. ¡Abróchate el cinturón y emprendamos este emocionante viaje!
## Prerrequisitos
Antes de sumergirnos en la magia de la codificación, asegurémonos de tener todo configurado:
1. Instalar GroupDocs.Viewer para .NET: Dirígete a la [enlace de descarga](https://releases.groupdocs.com/viewer/net/) Para obtener la última versión de GroupDocs.Viewer para .NET, siga las instrucciones de instalación para integrarlo sin problemas en su entorno de desarrollo.
2. Prepare su documento: asegúrese de tener un documento de destino, digamos un archivo de Excel llamado "file.xlsx", en el directorio de documentos designado.
## Importar espacios de nombres
Ahora que ya tiene los requisitos previos, comencemos importando los espacios de nombres necesarios. Esto garantiza que su aplicación reconozca y utilice las funcionalidades de GroupDocs.Viewer para .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## 1. Configuración del directorio de documentos
```csharp
string outputDirectory = "Your Document Directory";
```
Reemplace "Su directorio de documentos" con la ruta al directorio donde se encuentra su documento de destino.
## 2. Inicialización del visor
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
En este paso, creamos una instancia de la clase Viewer, proporcionando la ruta a su archivo Excel.
## 3. Configuración de las opciones de información de visualización
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
Aquí, configuramos ViewInfoOptions para generar vistas HTML y establecer opciones adicionales para la representación de hojas de cálculo.
## 4. Recuperación de información de visualización
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
Utilice la instancia del Visor para recuperar información de visualización según las opciones configuradas.
## 5. Visualización de nombres de hojas de trabajo
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
Recorra las páginas recuperadas e imprima el nombre de cada hoja de trabajo en la consola.
## Conclusión
¡Felicitaciones! Ha completado correctamente el proceso de obtención de nombres de hojas de cálculo con GroupDocs.Viewer para .NET. Esto abre un sinfín de posibilidades para mejorar la visualización de documentos en sus aplicaciones.
## Preguntas frecuentes
### ¿Puedo utilizar GroupDocs.Viewer para .NET con otros formatos de documentos?
¡Por supuesto! GroupDocs.Viewer admite una amplia gama de formatos de documentos, como PDF, Microsoft Office y más.
### ¿Hay una prueba gratuita disponible?
Sí, puede explorar GroupDocs.Viewer para .NET con nuestro [prueba gratuita](https://releases.groupdocs.com/).
### ¿Dónde puedo encontrar ayuda adicional?
Dirigirse a la [Foro de GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) Para apoyo y debates de la comunidad.
### ¿Puedo obtener una licencia temporal?
¡Por supuesto! Visita [este enlace](https://purchase.groupdocs.com/temporary-license/) para obtener su licencia temporal.
### ¿Hay recursos de documentación detallada disponibles?
¡Por supuesto! Echa un vistazo a [documentación oficial](https://tutorials.groupdocs.com/viewer/net/) Para obtener información detallada y guías.