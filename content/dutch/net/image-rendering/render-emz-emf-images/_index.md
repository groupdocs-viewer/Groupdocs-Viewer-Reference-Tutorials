---
title: Geef EMZ- en EMF-afbeeldingen weer
linktitle: Geef EMZ- en EMF-afbeeldingen weer
second_title: GroupDocs.Viewer .NET-API
description: Leer hoe u EMZ- en EMF-afbeeldingen naar verschillende formaten kunt renderen met GroupDocs.Viewer voor .NET. Eenvoudig te volgen tutorial voor ontwikkelaars.
weight: 14
url: /nl/net/image-rendering/render-emz-emf-images/
---
## Invoering

GroupDocs.Viewer voor .NET is een krachtige API voor documentweergave waarmee ontwikkelaars verschillende documenttypen, waaronder EMZ- (Enhanced Windows Metafile) en EMF-afbeeldingen (Enhanced Metafile), kunnen weergeven in hun .NET-toepassingen. In deze zelfstudie onderzoeken we hoe u EMZ- en EMF-afbeeldingen kunt weergeven in verschillende formaten, zoals HTML, JPG, PNG en PDF met behulp van GroupDocs.Viewer voor .NET.

## Vereisten

Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:

1.  GroupDocs.Viewer voor .NET: U kunt de bibliotheek downloaden van[hier](https://releases.groupdocs.com/viewer/net/).
2. Ontwikkelomgeving: Zorg ervoor dat u een compatibele ontwikkelomgeving hebt ingesteld voor .NET-ontwikkeling.
3. Voorbeeld EMZ/EMF-afbeeldingen: zorg ervoor dat u voorbeeld-EMZ- en EMF-afbeeldingen beschikbaar hebt voor weergave.

## Naamruimten importeren

Laten we, voordat we in de code duiken, de benodigde naamruimten importeren:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Laten we nu elk voorbeeld opsplitsen in meerdere stappen in een stapsgewijze handleiding:

## EMZ/EMF-afbeeldingen renderen naar HTML

### Stap 1: Stel de uitvoerdirectory in:
```csharp
string outputDirectory = "Your Document Directory";
```
 Vervangen`"Your Document Directory"`met het pad waar u het gerenderde HTML-bestand wilt opslaan.

### Stap 2: Definieer het paginabestandspadformaat:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
Hiermee wordt het bestandspadformaat voor het weergegeven HTML-bestand gespecificeerd.

### Stap 3: Renderen naar HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
 Deze code initialiseert de`Viewer` object met de voorbeeld-EMZ-afbeelding en rendert deze naar HTML-indeling met behulp van de opgegeven opties.

## EMZ/EMF-afbeeldingen renderen naar JPG, PNG en PDF

Herhaal de volgende stappen voor weergave naar JPG-, PNG- en PDF-formaten:

### Stap 1: Definieer het paginabestandspadformaat:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
Pas de bestandsnaam en extensie aan volgens het gewenste uitvoerformaat (`jpg`, `png` , of`pdf`).

### Stap 2: Renderen naar respectievelijk formaat:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // Pas opties aan volgens het uitvoerformaat (Jpg, Png, Pdf)
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
 Vervangen`JpgViewOptions` met`PngViewOptions` of`PdfViewOptions` op basis van het gewenste uitvoerformaat.

## Conclusie

Concluderend biedt GroupDocs.Viewer voor .NET een naadloze oplossing voor het renderen van EMZ- en EMF-afbeeldingen naar verschillende formaten in .NET-toepassingen. Door de stappen in deze tutorial te volgen, kunnen ontwikkelaars moeiteloos documentweergavemogelijkheden in hun applicaties integreren.

## Veelgestelde vragen

### Vraag: Kan GroupDocs.Viewer andere documentformaten weergeven dan EMZ- en EMF-afbeeldingen?
A: Ja, GroupDocs.Viewer ondersteunt een breed scala aan documentformaten, waaronder PDF, DOCX, PPTX, XLSX en meer.

### Vraag: Is er een gratis proefversie beschikbaar voor GroupDocs.Viewer voor .NET?
 A: Ja, u heeft toegang tot de gratis proefperiode[hier](https://releases.groupdocs.com/).

### Vraag: Biedt GroupDocs.Viewer ondersteuning voor ontwikkelaars?
 A: Ja, GroupDocs biedt ondersteuning via zijn[forum](https://forum.groupdocs.com/c/viewer/9) waar ontwikkelaars vragen kunnen stellen en hulp kunnen zoeken.

### Vraag: Kan ik een tijdelijke licentie kopen voor GroupDocs.Viewer voor .NET?
 A: Ja, tijdelijke licenties zijn te koop[hier](https://purchase.groupdocs.com/temporary-license/).

### Vraag: Waar kan ik gedetailleerde documentatie vinden voor GroupDocs.Viewer voor .NET?
 A: U kunt de documentatie raadplegen[hier](https://tutorials.groupdocs.com/viewer/net/)voor uitgebreide richtlijnen voor het gebruik van de API.