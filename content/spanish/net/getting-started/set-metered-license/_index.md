---
title: Establecer licencia medida
linktitle: Establecer licencia medida
second_title: API GroupDocs.Viewer .NET
description: Mejore sus aplicaciones .NET con GroupDocs.Viewer para una visualización perfecta de documentos. Integre fácilmente funcionalidades de representación de documentos en sus proyectos.
weight: 12
url: /es/net/getting-started/set-metered-license/
---

# Establecer licencia medida

## Introducción
En el mundo del desarrollo .NET, incorporar potentes capacidades de visualización de documentos en sus aplicaciones es esencial para mejorar la experiencia y la funcionalidad del usuario. GroupDocs.Viewer para .NET ofrece una solución sólida para integrar perfectamente funcionalidades de visualización de documentos en sus proyectos .NET. Ya sea que esté trabajando con archivos PDF, documentos de Microsoft Office o varios formatos de imagen, GroupDocs.Viewer simplifica el proceso de renderización y visualización de estos documentos dentro de sus aplicaciones.
## Requisitos previos
Antes de profundizar en la implementación de GroupDocs.Viewer para .NET, asegúrese de tener implementados los siguientes requisitos previos:
### 1. Instale GroupDocs.Viewer para .NET
 Para comenzar, deberá descargar e instalar GroupDocs.Viewer para .NET. Puedes encontrar el enlace de descarga.[aquí](https://releases.groupdocs.com/viewer/net/). Siga las instrucciones de instalación proporcionadas para configurar la biblioteca dentro de su entorno de desarrollo.
### 2. Obtener una licencia medida
Para utilizar GroupDocs.Viewer para .NET, necesita obtener una licencia medida. Esta licencia le permite controlar y monitorear el uso de su API en función de cuotas predefinidas. Siga los pasos a continuación para configurar su licencia medida:

## Importar espacios de nombres
Primero, asegúrese de importar los espacios de nombres necesarios para acceder a la funcionalidad proporcionada por GroupDocs.Viewer para .NET:
```csharp
using System;
```

Ahora, dividamos el código de ejemplo proporcionado en varios pasos:
## Paso 1: declarar claves públicas y privadas
Declare variables para almacenar sus claves públicas y privadas:
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
 Asegúrese de reemplazar`"YOUR_PUBLIC_KEY"` y`"YOUR_PRIVATE_KEY"` con tus llaves reales.
## Paso 2: configurar la licencia medida
Compruebe si se proporciona la clave pública. De lo contrario, solicite al usuario que configure las claves:
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://compra.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## Paso 3: inicializar el objeto medido y configurar la licencia
Inicialice el objeto medido y configure la licencia medida usando sus claves públicas y privadas:
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## Paso 4: Mensaje de confirmación
Muestra un mensaje de confirmación indicando que la licencia se ha configurado correctamente:
```csharp
Console.WriteLine("License set successfully.");
```

## Conclusión
En conclusión, GroupDocs.Viewer para .NET proporciona una solución integral para incorporar funcionalidades de visualización de documentos en sus aplicaciones .NET. Si sigue los pasos descritos, puede configurar fácilmente una licencia medida y comenzar a aprovechar las capacidades de GroupDocs.Viewer dentro de sus proyectos.
## Preguntas frecuentes
### P: ¿Dónde puedo encontrar documentación para GroupDocs.Viewer para .NET?
 Puedes encontrar la documentación.[aquí](https://tutorials.groupdocs.com/viewer/net/).
### P: ¿Hay una prueba gratuita disponible para GroupDocs.Viewer para .NET?
 Sí, puedes acceder a la prueba gratuita.[aquí](https://releases.groupdocs.com/).
### P: ¿Cómo puedo obtener licencias temporales para realizar pruebas?
 Se pueden obtener licencias temporales.[aquí](https://purchase.groupdocs.com/temporary-license/).
### P: ¿Dónde puedo buscar soporte o hacer preguntas relacionadas con GroupDocs.Viewer para .NET?
 Puede buscar ayuda y hacer preguntas en el foro GroupDocs.Viewer[aquí](https://forum.groupdocs.com/c/viewer/9).
### P: ¿Dónde puedo comprar una licencia de GroupDocs.Viewer para .NET?
 Puedes comprar una licencia[aquí](https://purchase.groupdocs.com/buy).