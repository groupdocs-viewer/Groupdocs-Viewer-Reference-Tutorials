---
"description": "Leer hoe u gelaagde rendering in PDF-documenten kunt inschakelen met GroupDocs.Viewer voor .NET. Verbeter moeiteloos de weergave van documenten."
"linktitle": "Gelaagde rendering in PDF inschakelen"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Gelaagde rendering in PDF inschakelen"
"url": "/nl/net/pdf-rendering-options/enable-layered-rendering-pdf/"
"weight": 15
type: docs
---
# Gelaagde rendering in PDF inschakelen

## Invoering
In deze tutorial verdiepen we ons in het proces van het inschakelen van gelaagde rendering in PDF-documenten met behulp van GroupDocs.Viewer voor .NET. Gelaagde rendering zorgt voor een verbeterde weergave en bewerking van documenten, waardoor gebruikers een interactievere kijkervaring krijgen.

![Gelaagde rendering in PDF inschakelen met GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/enable-layered-rendering-in-pdf.png)

## Vereisten
Voordat we beginnen, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. GroupDocs.Viewer voor .NET: Zorg ervoor dat u het benodigde pakket of de benodigde bibliotheek hebt geïnstalleerd voor het gebruik van GroupDocs.Viewer voor .NET in uw project.
2. Visual Studio: Visual Studio moet op uw systeem geïnstalleerd zijn om de gegeven voorbeelden te kunnen coderen en uitvoeren.
3. Basiskennis van C#: voor deze tutorial is kennis van de syntaxis en concepten van de programmeertaal C# vereist.

## Naamruimten importeren
Begin met het importeren van de vereiste naamruimten in uw project:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Stap 1: Definieer de uitvoermap
```csharp
string outputDirectory = "Your Document Directory";
```
Zorg ervoor dat u het pad opgeeft naar de map waarin u de gerenderde uitvoer wilt opslaan.
## Stap 2: Definieer het padformaat van het paginabestand
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Met deze stap stelt u de indeling in voor de bestandspaden van afzonderlijke pagina's in de gerenderde uitvoer. `{0}` is een tijdelijke aanduiding voor het paginanummer.
## Stap 3: Gelaagde rendering inschakelen
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
Hier creëren we een `Viewer` object en specificeer het te verwerken PDF-document. Vervolgens configureren we `HtmlViewOptions` met het gedefinieerde padformaat van het paginabestand. Door in te stellen `EnableLayeredRendering` eigendom van `true` in `PdfOptions`, maken we gelaagde rendering mogelijk voor het PDF-document.
## Stap 4: Uitvoermap weergeven
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Tot slot printen we een bericht dat het renderen van het brondocument succesvol is verlopen en vragen we de gebruiker om de uitvoer in de opgegeven directory te controleren.

## Conclusie
Door gelaagde rendering in PDF-documenten in te schakelen met GroupDocs.Viewer voor .NET, worden de mogelijkheden voor het bekijken van documenten verbeterd en krijgen gebruikers een rijkere en interactievere ervaring. Door de stappen in deze tutorial te volgen, kunt u deze functie naadloos integreren in uw .NET-applicaties.
## Veelgestelde vragen
### Wat is gelaagde rendering in PDF-documenten?
Met gelaagde rendering kunt u verschillende onderdelen binnen een PDF-document scheiden en bewerken, waardoor u het document interactief kunt bekijken en de gebruikerservaring kunt verbeteren.
### Kan ik de uitvoermap voor gerenderde documenten aanpassen?
Ja, u kunt elk gewenst pad voor de uitvoer opgeven.
### Ondersteunt GroupDocs.Viewer andere bestandsformaten dan PDF?
Ja, GroupDocs.Viewer ondersteunt een breed scala aan documentindelingen, waaronder Word, Excel, PowerPoint en meer.
### Is GroupDocs.Viewer compatibel met .NET Core?
Ja, GroupDocs.Viewer is compatibel met zowel .NET Framework- als .NET Core-omgevingen.
### Waar kan ik aanvullende ondersteuning of hulp vinden?
Voor vragen of hulp met betrekking tot de viewerbibliotheek kunt u terecht op het GroupDocs.Viewer-forum.