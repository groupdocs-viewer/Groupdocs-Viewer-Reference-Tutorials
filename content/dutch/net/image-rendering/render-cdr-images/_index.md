---
"description": "Leer hoe u CDR-afbeeldingen kunt renderen naar HTML, JPG, PNG en PDF met GroupDocs.Viewer voor .NET. Converteer CorelDRAW-bestanden eenvoudig met deze tutorial."
"linktitle": "CDR-afbeeldingen renderen"
"second_title": "GroupDocs.Viewer .NET API"
"title": "CDR-afbeeldingen renderen"
"url": "/nl/net/image-rendering/render-cdr-images/"
"weight": 12
---

# CDR-afbeeldingen renderen

## Invoering
In deze tutorial begeleiden we je door het proces van het renderen van CDR (CorelDRAW)-afbeeldingen met GroupDocs.Viewer voor .NET. CDR is een bestandsformaat dat voornamelijk wordt geassocieerd met CorelDRAW, een vectorafbeeldingseditor. Met GroupDocs.Viewer kun je CDR-bestanden eenvoudig converteren naar verschillende formaten zoals HTML, JPG, PNG en PDF.

![CDR-afbeeldingen renderen met GroupDocs.Viewer voor .NET](/viewer/image-rendering/render-cdr-images.png)

## Vereisten
Voordat u begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. GroupDocs.Viewer voor .NET: Zorg ervoor dat je GroupDocs.Viewer voor .NET hebt geïnstalleerd. Je kunt het downloaden van [hier](https://releases.groupdocs.com/viewer/net/).
2. Documentmap: bereid een map voor waar u de gerenderde afbeeldingen wilt opslaan.
3. Basiskennis van C#: Kennis van de programmeertaal C# is noodzakelijk om de codevoorbeelden te begrijpen.
## Naamruimten importeren
Voordat u in de codevoorbeelden duikt, importeert u de benodigde naamruimten in uw C#-bestand:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Laten we elk voorbeeld nu opsplitsen in meerdere stappen:
## Renderen naar HTML
1. Definieer de uitvoermap waar u de gerenderde HTML-bestanden wilt opslaan:
```csharp
string outputDirectory = "Your Document Directory";
```
2. Geef het bestandspadformaat voor HTML-bestanden op:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. Gebruik de Viewer-klasse om het CDR-bestand naar HTML te renderen:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Renderen naar JPG
1. Definieer het bestandspadformaat voor JPG-bestanden:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. Gebruik de Viewer-klasse om het CDR-bestand naar JPG te renderen:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Renderen naar PNG
1. Definieer het bestandspadformaat voor PNG-bestanden:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. Gebruik de Viewer-klasse om het CDR-bestand naar PNG te renderen:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Renderen naar PDF
1. Definieer het bestandspadformaat voor PDF:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. Gebruik de Viewer-klasse om het CDR-bestand naar PDF te renderen:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3. Optioneel kunt u weergaveopties opgeven of specifieke pagina's weergeven door extra parameters aan de pagina door te geven. `viewer.View()` methode.
## Conclusie
Het renderen van CDR-afbeeldingen naar verschillende formaten zoals HTML, JPG, PNG en PDF met GroupDocs.Viewer voor .NET is een eenvoudig proces. Door de stappen in deze tutorial te volgen, kunt u CDR-bestanden efficiënt converteren naar verschillende formaten, afhankelijk van uw wensen.
## Veelgestelde vragen
### Is GroupDocs.Viewer voor .NET compatibel met alle versies van CDR-bestanden?
GroupDocs.Viewer voor .NET ondersteunt het renderen van CDR-bestanden die zijn gemaakt met verschillende versies van CorelDRAW.
### Kan ik de uitvoer van gerenderde bestanden aanpassen?
Ja, GroupDocs.Viewer voor .NET biedt verschillende opties om de uitvoer aan te passen, zoals het aanpassen van de beeldkwaliteit, het instellen van een watermerk, enzovoort.
### Heeft GroupDocs.Viewer voor .NET externe afhankelijkheden nodig?
Nee, GroupDocs.Viewer voor .NET is een zelfstandige bibliotheek en vereist geen externe afhankelijkheden voor het renderen van documenten.
### Is er een proefversie beschikbaar voor GroupDocs.Viewer voor .NET?
Ja, u kunt een gratis proefversie van GroupDocs.Viewer voor .NET downloaden van [hier](https://releases.groupdocs.com/).
### Waar kan ik ondersteuning krijgen voor GroupDocs.Viewer voor .NET?
U kunt ondersteuning krijgen via het GroupDocs.Viewer communityforum [hier](https://forum.groupdocs.com/c/viewer/9).