---
"description": "Ontdek de kracht van Groupdocs.Viewer voor .NET voor het naadloos renderen van Numbers-bestanden. Converteer moeiteloos naar HTML, JPG, PNG en PDF."
"linktitle": "Weergavecijfers"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Weergavecijfers"
"url": "/nl/net/spreadsheet-rendering-options/rendering-numbers/"
"weight": 15
---

# Weergavecijfers

## Invoering
Welkom bij deze stapsgewijze tutorial over het renderen van Numbers-bestanden met Groupdocs.Viewer voor .NET. Of u nu een ervaren ontwikkelaar of een beginner bent, deze gids begeleidt u door het proces van het converteren van Numbers-documenten naar verschillende formaten. Groupdocs.Viewer voor .NET is een krachtige tool waarmee u documentweergave naadloos kunt integreren in uw .NET-applicaties.
## Vereisten
Voordat u met de tutorial begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Werkkennis van C#- en .NET-ontwikkeling.
- Groupdocs.Viewer voor .NET-bibliotheek geïnstalleerd. U kunt het downloaden. [hier](https://releases.groupdocs.com/viewer/net/).
- Het pad naar uw documentmap waar de uitvoerbestanden worden opgeslagen.
## Naamruimten importeren
Zorg ervoor dat u in uw C#-project de benodigde naamruimten importeert om de Groupdocs.Viewer-bibliotheek te gebruiken:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Stap 1: Uitvoermap instellen
Voordat u begint met renderen, definieert u de uitvoermap waar de geconverteerde bestanden worden opgeslagen. Vervang "Uw documentmap" door het daadwerkelijke pad:
```csharp
string outputDirectory = "Your Document Directory";
```
## Stap 2: Renderen naar HTML met meerdere pagina's
Gebruik de volgende code om het Numbers-bestand te converteren naar HTML met meerdere pagina's:
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Stap 3: Renderen naar JPG
Converteer het Numbers-bestand naar JPG-formaat met de volgende code:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Stap 4: Renderen naar PNG
Transformeer het Numbers-bestand naar PNG-formaat met behulp van de volgende code:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Stap 5: Renderen naar PDF
Converteer ten slotte het Numbers-bestand naar PDF-formaat met behulp van de volgende code:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Gefeliciteerd! U hebt Numbers-bestanden succesvol in verschillende formaten weergegeven met Groupdocs.Viewer voor .NET.
## Conclusie
In deze tutorial hebben we de basisprincipes van het renderen van Numbers-bestanden met Groupdocs.Viewer voor .NET behandeld. Deze krachtige bibliotheek biedt naadloze integratie voor het bekijken en converteren van documenten in uw .NET-applicaties.
## Veelgestelde vragen
### Kan ik Groupdocs.Viewer voor .NET gebruiken met andere documenttypen?
Ja, Groupdocs.Viewer ondersteunt een breed scala aan documentformaten, waaronder Word, Excel, PDF en meer.
### Is er een tijdelijke licentie beschikbaar voor testdoeleinden?
Ja, u kunt een tijdelijke licentie verkrijgen [hier](https://purchase.groupdocs.com/temporary-license/) voor testen.
### Waar kan ik ondersteuning vinden voor Groupdocs.Viewer voor .NET?
Bezoek de [Groupdocs.Viewer Forum](https://forum.groupdocs.com/c/viewer/9) voor hulp en discussies.
### Hoe kan ik de volledige versie van Groupdocs.Viewer voor .NET kopen?
U kunt de volledige versie kopen [hier](https://purchase.groupdocs.com/buy).
### Is er een gratis proefversie beschikbaar?
Ja, u kunt de gratis proefversie uitproberen [hier](https://releases.groupdocs.com/).