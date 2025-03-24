---
title: Render PDF met origineel paginaformaat
linktitle: Render PDF met origineel paginaformaat
second_title: GroupDocs.Viewer .NET-API
description: Leer hoe u PDF's met originele paginaformaten kunt renderen met GroupDocs.Viewer voor .NET. Volg onze stapsgewijze handleiding en integreer deze functionaliteit naadloos.
weight: 17
url: /nl/net/pdf-rendering-options/render-pdf-original-page-size/
---
## Invoering
Op het gebied van .NET-ontwikkeling onderscheidt GroupDocs.Viewer zich als een krachtig hulpmiddel voor het weergeven van verschillende documentformaten, waaronder PDF's. Een veel voorkomende vereiste bij het verwerken van documenten is het renderen van PDF's met behoud van hun oorspronkelijke paginaformaten. Om deze taak naadloos te kunnen uitvoeren, is een uitgebreid begrip van GroupDocs.Viewer voor .NET en zijn functionaliteiten vereist.
## Vereisten
Voordat u zich gaat verdiepen in het renderen van PDF's met originele paginaformaten met GroupDocs.Viewer voor .NET, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
### 1. Installeer GroupDocs.Viewer voor .NET
 Begin met het downloaden van de GroupDocs.Viewer-bibliotheek van de website. U kunt de bibliotheek verkrijgen via de meegeleverde[download link](https://releases.groupdocs.com/viewer/net/). Volg de installatie-instructies in de documentatie om het effectief in uw .NET-project te integreren.
### 2. Ontwikkelomgeving instellen
Zorg ervoor dat u een ontwikkelomgeving hebt ingesteld voor .NET-ontwikkeling. Dit omvat het installeren van een compatibele IDE, zoals Visual Studio, en een basiskennis van C#-programmeren.
### 3. Verkrijg een PDF-document
U hebt een voorbeeld-PDF-document nodig om te renderen met GroupDocs.Viewer. U kunt elk PDF-document gebruiken voor testdoeleinden. Als u er geen heeft, kunt u een voorbeeld-pdf downloaden van verschillende online bronnen.

## Naamruimten importeren
Voordat u doorgaat met het renderen van PDF's, is het van essentieel belang dat u de benodigde naamruimten in uw C#-project importeert. Met deze stap krijgt u toegang tot de vereiste klassen en methoden uit de GroupDocs.Viewer-bibliotheek.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nu u aan de vereisten voldoet en de benodigde naamruimten zijn geïmporteerd, gaan we het proces van het renderen van PDF's met originele paginaformaten met GroupDocs.Viewer voor .NET in eenvoudige stappen opsplitsen:
## Stap 1: Definieer de uitvoerdirectory
```csharp
string outputDirectory = "Your Document Directory";
```
 Zorg ervoor dat u de map opgeeft waar u de weergegeven pagina's wilt opslaan. Vervangen`"Your Document Directory"` met het pad van de gewenste directory.
## Stap 2: Definieer het paginabestandspadformaat
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
Stel het formaat in voor de naamgeving van de gerenderde paginabestanden. In dit voorbeeld worden de pagina's opgeslagen als PNG-afbeeldingen met bestandsnamen in het formaat`"page_1.png"`, `"page_2.png"`, enzovoort.
## Stap 3: Geef PDF weer met origineel paginaformaat
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
 Instantieer een`Viewer` object met het pad naar uw PDF-bestand. Creëer vervolgens`PngViewOptions` met het opgegeven paginabestandspadformaat. Set`RenderOriginalPageSize` eigendom aan`true` om de originele paginaformaten te behouden tijdens het renderen.
## Stap 4: Geef de weergegeven documentlocatie weer
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Druk een bericht af waarin wordt aangegeven dat de weergave is geslaagd en geef de map op waar de weergegeven pagina's zijn opgeslagen.

## Conclusie
Het renderen van PDF's met originele paginaformaten met GroupDocs.Viewer voor .NET is een eenvoudig proces als u de stappen volgt die in deze zelfstudie worden beschreven. Door de benodigde naamruimten te importeren en het stappenplan te volgen, kunt u deze functionaliteit naadloos integreren in uw .NET-applicaties.
## Veelgestelde vragen
### Kan GroupDocs.Viewer naast PDF ook andere documentformaten weergeven?
Ja, GroupDocs.Viewer ondersteunt het renderen van verschillende documentformaten, waaronder Word, Excel, PowerPoint en meer.
### Is GroupDocs.Viewer compatibel met .NET Core?
Ja, GroupDocs.Viewer is compatibel met zowel .NET Framework- als .NET Core-omgevingen.
### Kan ik het uitvoerformaat van weergegeven pagina's aanpassen?
Ja, u kunt het uitvoerformaat aanpassen door de opties van GroupDocs.Viewer aan te passen, zoals het instellen van verschillende afbeeldingsformaten of het opgeven van aangepaste weergaveopties.
### Biedt GroupDocs.Viewer ondersteuning voor cloudgebaseerde documentweergave?
Ja, GroupDocs.Viewer biedt API's voor cloudgebaseerde documentweergave, zodat u documenten rechtstreeks vanuit cloudopslagproviders kunt weergeven.
### Is er een gratis proefversie beschikbaar voor GroupDocs.Viewer?
 Ja, u kunt GroupDocs.Viewer verkennen met een gratis proefperiode door naar het meegeleverde bestand te gaan[koppeling](https://releases.groupdocs.com/).