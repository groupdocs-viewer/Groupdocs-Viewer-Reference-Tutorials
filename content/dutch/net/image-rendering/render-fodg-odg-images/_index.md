---
"description": "Leer hoe u FODG- en ODG-afbeeldingen kunt renderen naar HTML, JPG, PNG en PDF met GroupDocs.Viewer voor .NET. Verbeter uw documentverwerking."
"linktitle": "FODG- en ODG-afbeeldingen renderen"
"second_title": "GroupDocs.Viewer .NET API"
"title": "FODG- en ODG-afbeeldingen renderen"
"url": "/nl/net/image-rendering/render-fodg-odg-images/"
"weight": 15
type: docs
---
# FODG- en ODG-afbeeldingen renderen

## Invoering
In de wereld van softwareontwikkeling is efficiënte verwerking van documentformaten van het grootste belang. GroupDocs.Viewer voor .NET is een krachtige tool die is ontworpen om het renderen van FODG- en ODG-afbeeldingen in .NET-applicaties te vereenvoudigen. Deze tutorial leidt u door de stappen die nodig zijn om deze afbeeldingen te renderen in verschillende formaten, zoals HTML, JPG, PNG en PDF, met behulp van GroupDocs.Viewer voor .NET.

![FODG- en ODG-afbeeldingen renderen met GroupDocs.Viewer voor .NET](/viewer/image-rendering/render-fodg-and--odg-images.png)

## Vereisten
Voordat u met de tutorial begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. GroupDocs.Viewer voor .NET: Download en installeer GroupDocs.Viewer voor .NET van [hier](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Zorg ervoor dat .NET Framework op uw systeem is geïnstalleerd.
3. Basiskennis van C#: Kennis van de programmeertaal C# is nuttig.

## Naamruimten importeren
Importeer de benodigde naamruimten voordat u met de implementatie begint:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Stap 1: Uitvoermap instellen
```csharp
string outputDirectory = "Your Document Directory";
```
Vervangen `"Your Document Directory"` met het pad naar de map waarin u de gerenderde afbeeldingen wilt opslaan.
## Stap 2: Renderen naar HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
Met deze stap wordt de FODG-afbeelding omgezet naar HTML-formaat.
## Stap 3: Renderen naar JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Hier is de FODG-afbeelding weergegeven in JPG-formaat.
## Stap 4: Renderen naar PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Met deze stap wordt de FODG-afbeelding omgezet naar PNG-formaat.
## Stap 5: Renderen naar PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Ten slotte wordt de FODG-afbeelding omgezet naar PDF-formaat.

## Conclusie
In deze tutorial hebben we onderzocht hoe je FODG- en ODG-afbeeldingen in verschillende formaten kunt renderen met GroupDocs.Viewer voor .NET. Door deze stappen te volgen, kun je documentrendering naadloos integreren in je .NET-applicaties.
## Veelgestelde vragen
### Is GroupDocs.Viewer voor .NET compatibel met alle versies van .NET Framework?
GroupDocs.Viewer voor .NET is compatibel met een breed scala aan .NET Framework-versies, waaronder de nieuwste.
### Kan ik documenten asynchroon weergeven met GroupDocs.Viewer voor .NET?
Ja, GroupDocs.Viewer voor .NET biedt asynchrone renderingmogelijkheden voor betere prestaties.
### Ondersteunt GroupDocs.Viewer voor .NET het weergeven van versleutelde documenten?
Ja, GroupDocs.Viewer voor .NET ondersteunt het weergeven van versleutelde documenten met de juiste ontsleutelingssleutels.
### Is het mogelijk om de weergegeven uitvoer aan te passen met GroupDocs.Viewer voor .NET?
Jazeker, GroupDocs.Viewer voor .NET biedt diverse aanpassingsopties om de weergegeven uitvoer af te stemmen op uw vereisten.
### Kan ik documenten van externe opslaglocaties weergeven met GroupDocs.Viewer voor .NET?
Ja, GroupDocs.Viewer voor .NET ondersteunt het weergeven van documenten vanaf zowel lokale als externe opslaglocaties.