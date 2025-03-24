---
title: Cijfers weergeven
linktitle: Cijfers weergeven
second_title: GroupDocs.Viewer .NET-API
description: Ontdek de kracht van Groupdocs.Viewer voor .NET bij het naadloos weergeven van Numbers-bestanden. Converteer moeiteloos naar HTML, JPG, PNG en PDF.
weight: 15
url: /nl/net/spreadsheet-rendering-options/rendering-numbers/
---

# Cijfers weergeven

## Invoering
Welkom bij deze stapsgewijze zelfstudie over het renderen van Numbers-bestanden met Groupdocs.Viewer voor .NET. Of u nu een doorgewinterde ontwikkelaar of een beginner bent, deze handleiding leidt u door het proces van het converteren van Numbers-documenten naar verschillende indelingen. Groupdocs.Viewer voor .NET is een krachtig hulpmiddel waarmee u de weergavemogelijkheden van documenten naadloos kunt integreren in uw .NET-toepassingen.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Een praktische kennis van C# en .NET-ontwikkeling.
-  Groupdocs.Viewer voor .NET-bibliotheek geïnstalleerd. Je kunt het downloaden[hier](https://releases.groupdocs.com/viewer/net/).
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
## Stap 1: Stel de uitvoerdirectory in
Voordat u begint met renderen, definieert u de uitvoermap waar de geconverteerde bestanden zullen worden opgeslagen. Vervang "Uw documentenmap" door het daadwerkelijke pad:
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
Converteer het Numbers-bestand naar JPG-indeling met de volgende code:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Stap 4: Renderen naar PNG
Transformeer het Numbers-bestand naar PNG-indeling met behulp van de volgende code:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Stap 5: Renderen naar PDF
Converteer ten slotte het Numbers-bestand naar PDF-indeling met behulp van de volgende code:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Gefeliciteerd! U hebt Numbers-bestanden met succes in verschillende indelingen omgezet met Groupdocs.Viewer voor .NET.
## Conclusie
In deze zelfstudie hebben we de basisbeginselen besproken van het weergeven van Numbers-bestanden met Groupdocs.Viewer voor .NET. Deze krachtige bibliotheek biedt naadloze integratie voor het bekijken en converteren van documenten in uw .NET-applicaties.
## Veelgestelde vragen
### Kan ik Groupdocs.Viewer voor .NET gebruiken met andere documenttypen?
Ja, Groupdocs.Viewer ondersteunt een breed scala aan documentformaten, waaronder Word, Excel, PDF en meer.
### Is er een tijdelijke licentie beschikbaar voor testdoeleinden?
 Ja, u kunt een tijdelijke licentie verkrijgen[hier](https://purchase.groupdocs.com/temporary-license/) om uit te proberen.
### Waar kan ik ondersteuning vinden voor Groupdocs.Viewer voor .NET?
 Bezoek de[Groupdocs.Viewer-forum](https://forum.groupdocs.com/c/viewer/9) voor hulp en discussies.
### Hoe koop ik de volledige versie van Groupdocs.Viewer voor .NET?
 U kunt de volledige versie kopen[hier](https://purchase.groupdocs.com/buy).
### Is er een gratis proefversie beschikbaar?
 Ja, u kunt de gratis proefversie verkennen[hier](https://releases.groupdocs.com/).