---
title: Obtener nombres de hojas de trabajo
linktitle: Obtener nombres de hojas de trabajo
second_title: API GroupDocs.Viewer .NET
description: Explore la magia de GroupDocs.Viewer para .NET integre perfectamente la visualización de documentos en sus aplicaciones. ¡Pruebe la prueba gratuita ahora!
weight: 11
url: /es/net/spreadsheet-rendering-options/get-worksheets-names/
---

# Obtener nombres de hojas de trabajo

## Introducción
¡Bienvenido al fascinante mundo de GroupDocs.Viewer para .NET! Si es un desarrollador o un entusiasta interesado en explorar potentes capacidades de visualización de documentos dentro de sus aplicaciones .NET, está de enhorabuena. En esta guía completa, profundizaremos en las complejidades de recuperar nombres de hojas de trabajo usando GroupDocs.Viewer. ¡Abróchate el cinturón y embárcate en este emocionante viaje!
## Requisitos previos
Antes de sumergirnos en la magia de la codificación, asegurémonos de tener todo configurado:
1.  Instale GroupDocs.Viewer para .NET: diríjase al[enlace de descarga](https://releases.groupdocs.com/viewer/net/)para obtener la última versión de GroupDocs.Viewer para .NET. Siga las instrucciones de instalación para integrarlo perfectamente en su entorno de desarrollo.
2. Prepare su documento: asegúrese de tener un documento de destino, digamos un archivo de Excel llamado "file.xlsx", en su directorio de documentos designado.
## Importar espacios de nombres
Ahora que tiene los requisitos previos implementados, comencemos importando los espacios de nombres necesarios. Esto garantiza que su aplicación reconozca y pueda utilizar las funcionalidades proporcionadas por GroupDocs.Viewer para .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## 1. Configurar el directorio de documentos
```csharp
string outputDirectory = "Your Document Directory";
```
Reemplace "Su directorio de documentos" con la ruta al directorio donde se encuentra su documento de destino.
## 2. Inicializando el Visor
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
En este paso, creamos una instancia de la clase Viewer, proporcionando la ruta a su archivo de Excel.
## 3. Configurar las opciones de visualización de información
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
Aquí, configuramos ViewInfoOptions para generar vistas HTML y establecer opciones adicionales para la representación de hojas de cálculo.
## 4. Recuperar información de visualización
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
Utilice la instancia del Visor para recuperar información de la vista según las opciones configuradas.
## 5. Mostrar nombres de hojas de trabajo
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
Recorra las páginas recuperadas e imprima el nombre de cada hoja de trabajo en la consola.
## Conclusión
¡Felicidades! Ha navegado con éxito por el proceso de obtención de nombres de hojas de trabajo utilizando GroupDocs.Viewer para .NET. Esto abre una infinidad de posibilidades para mejorar las funcionalidades de visualización de documentos dentro de sus aplicaciones.
## Preguntas frecuentes
### ¿Puedo utilizar GroupDocs.Viewer para .NET con otros formatos de documentos?
¡Absolutamente! GroupDocs.Viewer admite una amplia gama de formatos de documentos, incluidos PDF, Microsoft Office y más.
### ¿Hay una prueba gratuita disponible?
 Sí, puede explorar GroupDocs.Viewer para .NET con nuestro[prueba gratis](https://releases.groupdocs.com/).
### ¿Dónde puedo encontrar soporte adicional?
 Dirígete al[Foro GroupDocs.Viewer](https://forum.groupdocs.com/c/viewer/9) para apoyo y debates de la comunidad.
### ¿Puedo obtener una licencia temporal?
 ¡Ciertamente! Visita[este enlace](https://purchase.groupdocs.com/temporary-license/) para obtener su licencia temporal.
### ¿Hay recursos de documentación detallada disponibles?
 ¡Absolutamente! Revisar la[documentación oficial](https://tutorials.groupdocs.com/viewer/net/) para obtener información detallada y guías.