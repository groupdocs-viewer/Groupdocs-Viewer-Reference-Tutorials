---
title: Render specifieke CAD-formaten (CF2)
linktitle: Render specifieke CAD-formaten (CF2)
second_title: GroupDocs.Viewer .NET-API
description: Leer hoe u specifieke CAD-formaten zoals CF2 naar HTML, JPG, PNG en PDF kunt renderen met Groupdocs.Viewer voor .NET.
weight: 12
url: /nl/net/rendering-cad-drawings/render-specific-cad-formats/
---

# Render specifieke CAD-formaten (CF2)

## Invoering
In deze zelfstudie onderzoeken we hoe u specifieke CAD-indelingen kunt weergeven met Groupdocs.Viewer voor .NET. Groupdocs.Viewer is een krachtige documentviewer-API waarmee ontwikkelaars meer dan 170 documenttypen in hun applicaties kunnen weergeven zonder dat hiervoor externe software-installaties nodig zijn. We zullen ons specifiek concentreren op het renderen van CAD-formaten zoals CF2 naar verschillende uitvoerformaten zoals HTML, JPG, PNG en PDF.
## Vereisten
Voordat we in de tutorial duiken, moet je ervoor zorgen dat je aan de volgende vereisten voldoet:
- Visual Studio is op uw systeem geïnstalleerd.
-  Groupdocs.Viewer voor .NET SDK. Je kunt het downloaden van[hier](https://releases.groupdocs.com/viewer/net/).
- Basiskennis van de programmeertaal C#.
## Naamruimten importeren
Laten we eerst de benodigde naamruimten importeren die nodig zijn voor het renderen van CAD-formaten.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Laten we nu elk voorbeeld in meerdere stappen opsplitsen:
## Render CF2 naar HTML
### Stap 1: Definieer de uitvoermap waar de weergegeven HTML wordt opgeslagen.
```csharp
string outputDirectory = "Your Document Directory";
```
### Stap 2: Definieer het bestandspadformaat voor de HTML-uitvoer.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### Stap 3: Initialiseer het Viewer-object en specificeer het invoer-CF2-bestand.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // Stel indien nodig aanvullende weergaveopties in
    // opties.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Render CF2 naar JPG
### Stap 1: Definieer het bestandspadformaat voor de JPG-uitvoer.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### Stap 2: Initialiseer het Viewer-object en specificeer het invoer-CF2-bestand.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // Stel indien nodig aanvullende weergaveopties in
    // opties.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Render CF2 naar PNG

### Stap 1: Definieer het bestandspadformaat voor de PNG-uitvoer.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### Stap 2: Initialiseer het Viewer-object en specificeer het invoer-CF2-bestand.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // Stel indien nodig aanvullende weergaveopties in
    // opties.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Render CF2 naar PDF
### Stap 1: Definieer het bestandspadformaat voor de PDF-uitvoer.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### Stap 2: Initialiseer het Viewer-object en specificeer het invoer-CF2-bestand.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // Stel indien nodig aanvullende weergaveopties in
    // opties.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u specifieke CAD-indelingen, zoals CF2, kunt weergeven met Groupdocs.Viewer voor .NET. Door de stapsgewijze handleiding te volgen, kunt u eenvoudig documentweergavemogelijkheden integreren in uw .NET-toepassingen.
## Veelgestelde vragen
### Kan Groupdocs.Viewer andere CAD-formaten weergeven dan CF2?
Ja, Groupdocs.Viewer ondersteunt een breed scala aan CAD-formaten, waaronder DWG, DXF, DGN en meer.
### Is Groupdocs.Viewer geschikt voor het weergeven van documenten in webapplicaties?
Absoluut, Groupdocs.Viewer kan naadloos worden geïntegreerd in webapplicaties om documenten rechtstreeks in de browser weer te geven.
### Heeft Groupdocs.Viewer externe afhankelijkheden nodig voor weergave?
Nee, Groupdocs.Viewer is een zelfstandige API en vereist geen externe afhankelijkheden of software-installaties.
### Kan ik de weergaveopties aanpassen aan mijn vereisten?
Ja, Groupdocs.Viewer biedt verschillende weergaveopties die kunnen worden aangepast aan uw specifieke behoeften.
### Is er een proefversie beschikbaar voor Groupdocs.Viewer?
 Ja, u kunt een gratis proefversie van Groupdocs.Viewer downloaden van[hier](https://releases.groupdocs.com/).