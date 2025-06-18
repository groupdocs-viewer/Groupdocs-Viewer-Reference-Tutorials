---
"description": "Leer hoe u EMZ- en EMF-afbeeldingen naar verschillende formaten kunt renderen met GroupDocs.Viewer voor .NET. Eenvoudig te volgen tutorial voor ontwikkelaars."
"linktitle": "EMZ- en EMF-afbeeldingen renderen"
"second_title": "GroupDocs.Viewer .NET API"
"title": "EMZ- en EMF-afbeeldingen renderen"
"url": "/nl/net/image-rendering/render-emz-emf-images/"
"weight": 14
---

# EMZ- en EMF-afbeeldingen renderen

## Invoering

GroupDocs.Viewer voor .NET is een krachtige API voor documentweergave waarmee ontwikkelaars verschillende documenttypen, waaronder EMZ- (Enhanced Windows Metafile) en EMF- (Enhanced Metafile) afbeeldingen, in hun .NET-applicaties kunnen weergeven. In deze tutorial laten we zien hoe u EMZ- en EMF-afbeeldingen kunt weergeven naar verschillende formaten, zoals HTML, JPG, PNG en PDF, met behulp van GroupDocs.Viewer voor .NET.

![EMZ- en EMF-afbeeldingen renderen met GroupDocs.Viewer voor .NET](/viewer/image-rendering/render-emz-and-emf-images.png)

## Vereisten

Voordat we beginnen, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1. GroupDocs.Viewer voor .NET: U kunt de bibliotheek downloaden van [hier](https://releases.groupdocs.com/viewer/net/).
2. Ontwikkelomgeving: Zorg ervoor dat u een compatibele ontwikkelomgeving hebt ingesteld voor .NET-ontwikkeling.
3. Voorbeelden van EMZ/EMF-afbeeldingen: Zorg dat u EMZ- en EMF-voorbeeldafbeeldingen bij de hand hebt voor rendering.

## Naamruimten importeren

Voordat we in de code duiken, importeren we de benodigde naamruimten:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Laten we elk voorbeeld nu opsplitsen in meerdere stappen in een stapsgewijze handleiding:

## EMZ/EMF-afbeeldingen renderen naar HTML

### Stap 1: Uitvoermap instellen:
```csharp
string outputDirectory = "Your Document Directory";
```
Vervangen `"Your Document Directory"` met het pad waar u het gerenderde HTML-bestand wilt opslaan.

### Stap 2: Definieer het pad van het paginabestand:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
Hiermee wordt het bestandspad voor het gerenderde HTML-bestand gespecificeerd.

### Stap 3: Renderen naar HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
Deze code initialiseert de `Viewer` object met het EMZ-voorbeeldafbeelding en rendert het naar HTML-formaat met behulp van de opgegeven opties.

## EMZ/EMF-afbeeldingen renderen naar JPG, PNG en PDF

Herhaal de volgende stappen voor het renderen naar JPG-, PNG- en PDF-indelingen:

### Stap 1: Definieer het pad van het paginabestand:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
Pas de bestandsnaam en extensie aan volgens het gewenste uitvoerformaat (`jpg`, `png`, of `pdf`).

### Stap 2: Renderen naar het betreffende formaat:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // Pas de opties aan volgens het uitvoerformaat (Jpg, Png, Pdf)
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
Vervangen `JpgViewOptions` met `PngViewOptions` of `PdfViewOptions` gebaseerd op het gewenste uitvoerformaat.

## Conclusie

Kortom, GroupDocs.Viewer voor .NET biedt een naadloze oplossing voor het renderen van EMZ- en EMF-afbeeldingen naar diverse formaten in .NET-applicaties. Door de stappen in deze tutorial te volgen, kunnen ontwikkelaars moeiteloos mogelijkheden voor documentrendering integreren in hun applicaties.

## Veelgestelde vragen

### V: Kan GroupDocs.Viewer andere documentformaten weergeven dan EMZ- en EMF-afbeeldingen?
A: Ja, GroupDocs.Viewer ondersteunt een breed scala aan documentformaten, waaronder PDF, DOCX, PPTX, XLSX en meer.

### V: Is er een gratis proefversie beschikbaar voor GroupDocs.Viewer voor .NET?
A: Ja, u kunt deelnemen aan de gratis proefperiode [hier](https://releases.groupdocs.com/).

### V: Biedt GroupDocs.Viewer ondersteuning voor ontwikkelaars?
A: Ja, GroupDocs biedt ondersteuning via zijn [forum](https://forum.groupdocs.com/c/viewer/9) waar ontwikkelaars vragen kunnen stellen en hulp kunnen krijgen.

### V: Kan ik een tijdelijke licentie voor GroupDocs.Viewer voor .NET kopen?
A: Ja, tijdelijke licenties zijn te koop [hier](https://purchase.groupdocs.com/temporary-license/).

### V: Waar kan ik gedetailleerde documentatie vinden voor GroupDocs.Viewer voor .NET?
A: U kunt de documentatie raadplegen [hier](https://tutorials.groupdocs.com/viewer/net/) voor uitgebreide begeleiding bij het gebruik van de API.