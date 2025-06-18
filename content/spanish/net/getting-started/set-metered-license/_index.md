---
"description": "Mejore sus aplicaciones .NET con GroupDocs.Viewer para una visualización fluida de documentos. Integre fácilmente funciones de renderizado de documentos en sus proyectos."
"linktitle": "Establecer licencia medida"
"second_title": "API .NET de GroupDocs.Viewer"
"title": "Establecer licencia medida"
"url": "/es/net/getting-started/set-metered-license/"
"weight": 12
---

# Establecer licencia medida

## Introducción
En el mundo del desarrollo .NET, incorporar potentes funciones de visualización de documentos en sus aplicaciones es esencial para mejorar la experiencia del usuario y la funcionalidad. GroupDocs.Viewer para .NET ofrece una solución robusta para integrar a la perfección las funciones de visualización de documentos en sus proyectos .NET. Ya sea que trabaje con archivos PDF, documentos de Microsoft Office o diversos formatos de imagen, GroupDocs.Viewer simplifica el proceso de renderizado y visualización de estos documentos en sus aplicaciones.

![Establecer una licencia medida con GroupDocs.Viewer para .NET](/viewer/getting-started/set-metered-license.png)

## Prerrequisitos
Antes de sumergirse en la implementación de GroupDocs.Viewer para .NET, asegúrese de tener los siguientes requisitos previos:
### 1. Instalar GroupDocs.Viewer para .NET
Para comenzar, deberá descargar e instalar GroupDocs.Viewer para .NET. Puede encontrar el enlace de descarga. [aquí](https://releases.groupdocs.com/viewer/net/)Siga las instrucciones de instalación proporcionadas para configurar la biblioteca dentro de su entorno de desarrollo.
### 2. Obtener una licencia con medidor
Para utilizar GroupDocs.Viewer para .NET, necesita obtener una licencia con límite de uso. Esta licencia le permite controlar y supervisar el uso de su API según cuotas predefinidas. Siga los pasos a continuación para configurar su licencia con límite de uso:

## Importar espacios de nombres
Primero, asegúrese de importar los espacios de nombres necesarios para acceder a la funcionalidad proporcionada por GroupDocs.Viewer para .NET:
```csharp
using System;
```

Ahora, vamos a dividir el código de ejemplo proporcionado en varios pasos:
## Paso 1: Declarar claves públicas y privadas
Declare variables para almacenar sus claves públicas y privadas:
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
Asegúrese de reemplazar `"YOUR_PUBLIC_KEY"` y `"YOUR_PRIVATE_KEY"` con tus llaves reales.
## Paso 2: Establecer una licencia medida
Compruebe si se proporciona la clave pública. De lo contrario, solicite al usuario que configure las claves:
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://purchase.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## Paso 3: Inicializar el objeto medido y configurar la licencia
Inicialice el objeto medido y configure la licencia medida utilizando sus claves públicas y privadas:
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## Paso 4: Mensaje de confirmación
Mostrar un mensaje de confirmación indicando que la licencia se ha configurado correctamente:
```csharp
Console.WriteLine("License set successfully.");
```

## Conclusión
En conclusión, GroupDocs.Viewer para .NET ofrece una solución integral para incorporar funciones de visualización de documentos en sus aplicaciones .NET. Siguiendo los pasos descritos, puede configurar fácilmente una licencia medida y empezar a aprovechar las capacidades de GroupDocs.Viewer en sus proyectos.
## Preguntas frecuentes
### P: ¿Dónde puedo encontrar documentación de GroupDocs.Viewer para .NET?
Puede encontrar la documentación [aquí](https://tutorials.groupdocs.com/viewer/net/).
### P: ¿Hay una prueba gratuita disponible para GroupDocs.Viewer para .NET?
Sí, puedes acceder a la prueba gratuita. [aquí](https://releases.groupdocs.com/).
### P: ¿Cómo puedo obtener licencias temporales para fines de prueba?
Se pueden obtener licencias temporales [aquí](https://purchase.groupdocs.com/temporary-license/).
### P: ¿Dónde puedo buscar ayuda o hacer preguntas relacionadas con GroupDocs.Viewer para .NET?
Puede buscar ayuda y hacer preguntas en el foro de GroupDocs.Viewer [aquí](https://forum.groupdocs.com/c/viewer/9).
### P: ¿Dónde puedo comprar una licencia para GroupDocs.Viewer para .NET?
Puedes comprar una licencia [aquí](https://purchase.groupdocs.com/buy).