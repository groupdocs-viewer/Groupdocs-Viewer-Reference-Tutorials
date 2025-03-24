---
title: Cambiar el nombre de los campos de correo electrónico durante el renderizado
linktitle: Cambiar el nombre de los campos de correo electrónico durante el renderizado
second_title: API GroupDocs.Viewer .NET
description: Mejore la experiencia de visualización de documentos con GroupDocs.Viewer para .NET. Represente y personalice correos electrónicos sin problemas.
weight: 12
url: /es/net/rendering-email-messages/rename-email-fields/
---
## Introducción

En la era digital actual, administrar y visualizar documentos de manera eficiente es primordial tanto para empresas como para individuos. Ya sean contratos, informes o correos electrónicos, tener la capacidad de navegar por estos documentos sin problemas puede mejorar enormemente la productividad. Aquí es donde entra en juego GroupDocs.Viewer para .NET. Esta potente biblioteca permite a los desarrolladores integrar capacidades de visualización de documentos directamente en sus aplicaciones .NET, ofreciendo una amplia gama de funciones para representar varios formatos de documentos.

## Requisitos previos

Antes de profundizar en el tutorial sobre cómo cambiar el nombre de los campos de correo electrónico durante el procesamiento usando GroupDocs.Viewer para .NET, asegúrese de tener los siguientes requisitos previos:

1.  Biblioteca GroupDocs.Viewer para .NET: descargue e instale la biblioteca GroupDocs.Viewer para .NET desde[aquí](https://releases.groupdocs.com/viewer/net/).

2. Entorno de desarrollo: asegúrese de tener configurado un entorno de desarrollo adecuado para el desarrollo .NET, como Visual Studio.

3. Comprensión básica de C#: familiarícese con los conceptos básicos del lenguaje de programación C#, ya que el tutorial incluirá fragmentos de código C#.

4. Directorio de documentos: Prepare un directorio donde se almacenan los documentos a renderizar.

## Importar espacios de nombres

Para utilizar las funcionalidades de GroupDocs.Viewer en su aplicación .NET, debe importar los espacios de nombres necesarios.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ahora analicemos el proceso de cambiar el nombre de los campos de correo electrónico durante el procesamiento usando GroupDocs.Viewer para .NET en varios pasos:

## Paso 1: definir el directorio de salida

En primer lugar, especifique el directorio donde se guardarán las páginas HTML renderizadas.

```csharp
string outputDirectory = "Your Document Directory";
```

## Paso 2: Definir el formato de ruta del archivo de página

Defina el formato para las rutas de archivo de las páginas HTML renderizadas. Cada página se guardará como un archivo HTML independiente.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Paso 3: inicializar el objeto visor

Cree una instancia de la clase Viewer y pase la ruta del documento que se va a ver como parámetro.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
{
```

## Paso 4: configurar las opciones de vista HTML

Configure las opciones para la vista HTML, incluida la especificación del formato del archivo de salida y la configuración de asignaciones de campos de correo electrónico.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.EmailOptions.FieldTextMap[Field.From] = "Sender";
options.EmailOptions.FieldTextMap[Field.To] = "Receiver";
options.EmailOptions.FieldTextMap[Field.Sent] = "Date";
options.EmailOptions.FieldTextMap[Field.Subject] = "Topic";
```

## Paso 5: renderizar documento

Invoque el método View del objeto Viewer, pasando las opciones de vista HTML configuradas.

```csharp
viewer.View(options);
```

## Paso 6: Mostrar mensaje de éxito

Informar al usuario que el documento se ha renderizado correctamente.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusión

En conclusión, GroupDocs.Viewer para .NET proporciona una solución perfecta para representar documentos dentro de aplicaciones .NET. Si sigue los pasos descritos en este tutorial, puede cambiar fácilmente el nombre de los campos de correo electrónico durante la renderización, mejorando la legibilidad y usabilidad de los documentos de correo electrónico. Con su API intuitiva y funciones integrales, GroupDocs.Viewer permite a los desarrolladores optimizar los procesos de visualización de documentos de manera efectiva.

## Preguntas frecuentes

### P: ¿Puedo representar documentos que no sean correos electrónicos usando GroupDocs.Viewer para .NET?

R: Sí, GroupDocs.Viewer admite la representación de varios formatos de documentos, incluidos PDF, documentos de Microsoft Office, imágenes y más.

### P: ¿GroupDocs.Viewer es compatible con .NET Core?

R: Sí, GroupDocs.Viewer admite .NET Core junto con el tradicional .NET Framework.

### P: ¿Puedo personalizar la apariencia de los documentos renderizados?

R: Por supuesto, GroupDocs.Viewer ofrece amplias opciones de personalización para controlar la apariencia y el comportamiento de los documentos renderizados.

### P: ¿GroupDocs.Viewer admite la transmisión de documentos?

R: Sí, GroupDocs.Viewer permite transmitir documentos directamente al navegador del cliente sin necesidad de almacenarlos en el servidor.

### P: ¿GroupDocs.Viewer es adecuado para aplicaciones de nivel empresarial?

R: Ciertamente, GroupDocs.Viewer está diseñado para satisfacer las demandas de las aplicaciones de nivel empresarial con su escalabilidad, confiabilidad y su sólido conjunto de funciones.
