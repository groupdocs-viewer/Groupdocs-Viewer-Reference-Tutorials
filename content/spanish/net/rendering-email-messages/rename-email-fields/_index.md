---
"description": "Mejore la experiencia de visualización de documentos con GroupDocs.Viewer para .NET. Procese y personalice correos electrónicos sin problemas."
"linktitle": "Cambiar el nombre de los campos de correo electrónico durante la representación"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Cambiar el nombre de los campos de correo electrónico durante la representación"
"url": "/es/net/rendering-email-messages/rename-email-fields/"
"weight": 12
---

# Cambiar el nombre de los campos de correo electrónico durante la representación

## Introducción

En la era digital actual, gestionar y visualizar documentos de forma eficiente es fundamental tanto para empresas como para particulares. Ya sean contratos, informes o correos electrónicos, la capacidad de navegar por estos documentos sin problemas puede mejorar considerablemente la productividad. Aquí es donde GroupDocs.Viewer para .NET entra en juego. Esta potente biblioteca permite a los desarrolladores integrar funciones de visualización de documentos directamente en sus aplicaciones .NET, ofreciendo una amplia gama de funciones para renderizar diversos formatos de documentos.

## Prerrequisitos

Antes de sumergirse en el tutorial sobre cómo cambiar el nombre de los campos de correo electrónico durante la representación mediante GroupDocs.Viewer para .NET, asegúrese de tener los siguientes requisitos previos:

1. Biblioteca GroupDocs.Viewer para .NET: Descargue e instale la biblioteca GroupDocs.Viewer para .NET desde [aquí](https://releases.groupdocs.com/viewer/net/).

2. Entorno de desarrollo: asegúrese de tener un entorno de desarrollo adecuado configurado para el desarrollo .NET, como Visual Studio.

3. Comprensión básica de C#: familiarícese con los conceptos básicos del lenguaje de programación C#, ya que el tutorial involucrará fragmentos de código C#.

4. Directorio de documentos: prepara un directorio donde se almacenarán los documentos que se van a renderizar.

## Importar espacios de nombres

Para utilizar las funcionalidades de GroupDocs.Viewer en su aplicación .NET, debe importar los espacios de nombres necesarios.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Ahora, desglosemos el proceso de cambio de nombre de los campos de correo electrónico durante la representación mediante GroupDocs.Viewer para .NET en varios pasos:

## Paso 1: Definir el directorio de salida

En primer lugar, especifique el directorio donde se guardarán las páginas HTML renderizadas.

```csharp
string outputDirectory = "Your Document Directory";
```

## Paso 2: Definir el formato de la ruta del archivo de página

Define el formato de las rutas de archivo de las páginas HTML renderizadas. Cada página se guardará como un archivo HTML independiente.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Paso 3: Inicializar el objeto Visor

Crea una instancia de la clase Viewer y pasa la ruta del documento que se visualizará como parámetro.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
{
```

## Paso 4: Configurar las opciones de vista HTML

Configure las opciones para la vista HTML, incluida la especificación del formato del archivo de salida y la configuración de las asignaciones de campos de correo electrónico.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.EmailOptions.FieldTextMap[Field.From] = "Sender";
options.EmailOptions.FieldTextMap[Field.To] = "Receiver";
options.EmailOptions.FieldTextMap[Field.Sent] = "Date";
options.EmailOptions.FieldTextMap[Field.Subject] = "Topic";
```

## Paso 5: Renderizar el documento

Invoque el método View del objeto Viewer, pasando las opciones de vista HTML configuradas.

```csharp
viewer.View(options);
```

## Paso 6: Mostrar mensaje de éxito

Informar al usuario que el documento se ha procesado correctamente.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusión

En conclusión, GroupDocs.Viewer para .NET ofrece una solución integral para la representación de documentos en aplicaciones .NET. Siguiendo los pasos descritos en este tutorial, podrá renombrar fácilmente los campos de correo electrónico durante la representación, lo que mejora la legibilidad y la usabilidad de los documentos. Gracias a su API intuitiva y sus completas funciones, GroupDocs.Viewer permite a los desarrolladores optimizar la visualización de documentos de forma eficaz.

## Preguntas frecuentes

### P: ¿Puedo representar documentos que no sean correos electrónicos usando GroupDocs.Viewer para .NET?

R: Sí, GroupDocs.Viewer admite la representación de varios formatos de documentos, incluidos PDF, documentos de Microsoft Office, imágenes y más.

### P: ¿GroupDocs.Viewer es compatible con .NET Core?

R: Sí, GroupDocs.Viewer es compatible con .NET Core junto con el tradicional .NET Framework.

### P: ¿Puedo personalizar la apariencia de los documentos renderizados?

R: Por supuesto. GroupDocs.Viewer ofrece amplias opciones de personalización para controlar la apariencia y el comportamiento de los documentos renderizados.

### P: ¿GroupDocs.Viewer admite la transmisión de documentos?

R: Sí, GroupDocs.Viewer permite transmitir documentos directamente al navegador del cliente sin la necesidad de almacenarlos en el servidor.

### P: ¿GroupDocs.Viewer es adecuado para aplicaciones de nivel empresarial?

R: Ciertamente, GroupDocs.Viewer está diseñado para satisfacer las demandas de las aplicaciones de nivel empresarial con su escalabilidad, confiabilidad y sólido conjunto de características.