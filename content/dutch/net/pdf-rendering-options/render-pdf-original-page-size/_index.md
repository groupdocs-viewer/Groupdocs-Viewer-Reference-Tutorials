---
"description": "Leer hoe u PDF's kunt renderen met de originele paginagrootte met GroupDocs.Viewer voor .NET. Volg onze stapsgewijze handleiding en integreer deze functionaliteit naadloos."
"linktitle": "PDF renderen met originele paginagrootte"
"second_title": "GroupDocs.Viewer .NET API"
"title": "PDF renderen met originele paginagrootte"
"url": "/nl/net/pdf-rendering-options/render-pdf-original-page-size/"
"weight": 17
---

# PDF renderen met originele paginagrootte

## Invoering
Binnen de .NET-ontwikkeling onderscheidt GroupDocs.Viewer zich als een krachtige tool voor het renderen van diverse documentformaten, waaronder pdf's. Een veelvoorkomende vereiste bij documentverwerking is het renderen van pdf's met behoud van de oorspronkelijke paginagrootte. Om deze taak naadloos uit te voeren, is een grondige kennis van GroupDocs.Viewer voor .NET en de functionaliteiten ervan vereist.

![PDF renderen met originele paginagrootte met GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/render-pdf-with-original-page-size.png)

## Vereisten
Voordat u met GroupDocs.Viewer voor .NET PDF's gaat renderen met de originele paginagrootte, moet u ervoor zorgen dat aan de volgende vereisten is voldaan:
### 1. GroupDocs.Viewer voor .NET installeren
Begin met het downloaden van de GroupDocs.Viewer-bibliotheek van de website. U kunt de bibliotheek verkrijgen via de meegeleverde [downloadlink](https://releases.groupdocs.com/viewer/net/)Volg de installatie-instructies in de documentatie om het effectief in uw .NET-project te integreren.
### 2. Ontwikkelomgeving instellen
Zorg ervoor dat je een ontwikkelomgeving hebt ingericht voor .NET-ontwikkeling. Dit omvat een compatibele IDE, zoals Visual Studio, en een basiskennis van C#-programmeren.
### 3. Een PDF-document verkrijgen
Je hebt een PDF-voorbeelddocument nodig om te renderen met GroupDocs.Viewer. Je kunt elk PDF-document gebruiken voor testdoeleinden. Als je geen PDF hebt, kun je een PDF-voorbeelddocument downloaden van verschillende online bronnen.

## Naamruimten importeren
Voordat u verdergaat met het renderen van PDF's, is het essentieel om de benodigde naamruimten in uw C#-project te importeren. Met deze stap krijgt u toegang tot de vereiste klassen en methoden uit de GroupDocs.Viewer-bibliotheek.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nu u aan de vereisten hebt voldaan en de benodigde naamruimten hebt geïmporteerd, gaan we het proces voor het renderen van PDF's met de oorspronkelijke paginaformaten met behulp van GroupDocs.Viewer voor .NET opsplitsen in eenvoudige stappen:
## Stap 1: Definieer de uitvoermap
```csharp
string outputDirectory = "Your Document Directory";
```
Zorg ervoor dat u de map opgeeft waar u de gerenderde pagina's wilt opslaan. Vervang `"Your Document Directory"` met het pad naar de gewenste directory.
## Stap 2: Definieer het padformaat van het paginabestand
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
Stel de notatie in voor de naamgeving van de gerenderde paginabestanden. In dit voorbeeld worden de pagina's opgeslagen als PNG-afbeeldingen met bestandsnamen in de notatie `"page_1.png"`, `"page_2.png"`, enzovoort.
## Stap 3: PDF renderen met originele paginagrootte
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
Instantieer een `Viewer` object met het pad naar uw PDF-bestand. Maak vervolgens `PngViewOptions` met de opgegeven paginabestandspadindeling. Instellen `RenderOriginalPageSize` eigendom van `true` om de originele paginaformaten te behouden tijdens het renderen.
## Stap 4: Locatie van het gerenderde document weergeven
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Geef een bericht weer dat aangeeft dat het renderen is gelukt en geef de map op waar de gerenderde pagina's zijn opgeslagen.

## Conclusie
Het renderen van PDF's met originele paginaformaten met GroupDocs.Viewer voor .NET is een eenvoudig proces wanneer u de stappen in deze tutorial volgt. Door de benodigde naamruimten te importeren en de stapsgewijze handleiding te volgen, kunt u deze functionaliteit naadloos integreren in uw .NET-applicaties.
## Veelgestelde vragen
### Kan GroupDocs.Viewer andere documentformaten dan PDF weergeven?
Ja, GroupDocs.Viewer ondersteunt het weergeven van verschillende documentformaten, waaronder Word, Excel, PowerPoint en meer.
### Is GroupDocs.Viewer compatibel met .NET Core?
Ja, GroupDocs.Viewer is compatibel met zowel .NET Framework- als .NET Core-omgevingen.
### Kan ik het uitvoerformaat van gerenderde pagina's aanpassen?
Ja, u kunt de uitvoeropmaak aanpassen door de opties van GroupDocs.Viewer aan te passen. U kunt bijvoorbeeld verschillende afbeeldingsindelingen instellen of aangepaste weergaveopties opgeven.
### Biedt GroupDocs.Viewer ondersteuning voor cloudgebaseerde documentweergave?
Ja, GroupDocs.Viewer biedt API's voor cloudgebaseerde documentweergave, zodat u documenten rechtstreeks vanuit cloudopslagproviders kunt weergeven.
### Is er een gratis proefversie beschikbaar voor GroupDocs.Viewer?
Ja, u kunt GroupDocs.Viewer gratis uitproberen met een proefperiode door de meegeleverde website te bezoeken. [link](https://releases.groupdocs.com/).