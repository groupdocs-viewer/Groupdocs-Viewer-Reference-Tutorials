---
title: Schakel gelaagde weergave in PDF in
linktitle: Schakel gelaagde weergave in PDF in
second_title: GroupDocs.Viewer .NET-API
description: Leer hoe u gelaagde weergave in PDF-documenten kunt inschakelen met GroupDocs.Viewer voor .NET. Verbeter moeiteloos de kijkervaring van documenten.
weight: 15
url: /nl/net/pdf-rendering-options/enable-layered-rendering-pdf/
---
## Invoering
In deze zelfstudie verdiepen we ons in het proces van het inschakelen van gelaagde weergave in PDF-documenten met behulp van GroupDocs.Viewer voor .NET. Gelaagde weergave maakt een verbeterde weergave en manipulatie van documenten mogelijk, waardoor gebruikers een meer interactieve kijkervaring krijgen.
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
1. GroupDocs.Viewer voor .NET: Zorg ervoor dat u het benodigde pakket of de benodigde bibliotheek voor het gebruik van GroupDocs.Viewer voor .NET in uw project hebt geïnstalleerd.
2. Visual Studio: Visual Studio moet op uw systeem zijn geïnstalleerd voor het coderen en uitvoeren van de gegeven voorbeelden.
3. Basiskennis van C#: Deze tutorial veronderstelt bekendheid met de syntaxis en concepten van de programmeertaal C#.

## Naamruimten importeren
Begin met het importeren van de vereiste naamruimten in uw project:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Stap 1: Definieer de uitvoerdirectory
```csharp
string outputDirectory = "Your Document Directory";
```
Zorg ervoor dat u het mappad opgeeft waar u de weergegeven uitvoer wilt opslaan.
## Stap 2: Definieer het paginabestandspadformaat
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Met deze stap stelt u het formaat in voor de bestandspaden van afzonderlijke pagina's in de weergegeven uitvoer.`{0}` is een tijdelijke aanduiding voor het paginanummer.
## Stap 3: Schakel gelaagde weergave in
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
 Hier creëren we een`Viewer` object en specificeer het PDF-document dat moet worden verwerkt. Wij configureren vervolgens`HtmlViewOptions` met het gedefinieerde paginabestandspadformaat. Door inte stellen`EnableLayeredRendering` eigendom aan`true` in `PdfOptions`, schakelen we gelaagde weergave in voor het PDF-document.
## Stap 4: Geef de uitvoerdirectory weer
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Ten slotte drukken we een bericht af dat de succesvolle weergave van het brondocument aangeeft en vragen we de gebruiker om de uitvoer in de opgegeven map te controleren.

## Conclusie
Door gelaagde weergave in PDF-documenten mogelijk te maken met GroupDocs.Viewer voor .NET worden de mogelijkheden voor het bekijken van documenten verbeterd, waardoor gebruikers een rijkere en interactievere ervaring krijgen. Door de stappen in deze zelfstudie te volgen, kunt u deze functie naadloos integreren in uw .NET-toepassingen.
## Veelgestelde vragen
### Wat is gelaagde weergave in PDF-documenten?
Gelaagde weergave maakt de scheiding en manipulatie van verschillende componenten binnen een PDF-document mogelijk, waardoor interactief bekijken en een verbeterde gebruikerservaring mogelijk wordt.
### Kan ik de uitvoermap voor weergegeven documenten aanpassen?
Ja, u kunt elk mappad voor de uitvoer opgeven volgens uw vereisten.
### Ondersteunt GroupDocs.Viewer naast PDF ook andere bestandsformaten?
Ja, GroupDocs.Viewer ondersteunt een breed scala aan documentformaten, waaronder Word, Excel, PowerPoint en meer.
### Is GroupDocs.Viewer compatibel met .NET Core?
Ja, GroupDocs.Viewer is compatibel met zowel .NET Framework- als .NET Core-omgevingen.
### Waar kan ik aanvullende ondersteuning of hulp vinden?
U kunt het GroupDocs.Viewer-forum bezoeken voor vragen of hulp met betrekking tot de viewerbibliotheek.