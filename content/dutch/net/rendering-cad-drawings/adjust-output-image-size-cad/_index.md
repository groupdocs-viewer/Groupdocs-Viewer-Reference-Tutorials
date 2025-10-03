---
"description": "Leer hoe u de grootte van de uitvoerafbeeldingen voor CAD-tekeningen kunt aanpassen met GroupDocs.Viewer voor .NET. Verbeter moeiteloos de zichtbaarheid en bruikbaarheid."
"linktitle": "Pas de grootte van de uitvoerafbeelding aan voor CAD-tekeningen"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Pas de grootte van de uitvoerafbeelding aan voor CAD-tekeningen"
"url": "/nl/net/rendering-cad-drawings/adjust-output-image-size-cad/"
"weight": 15
type: docs
---
# Pas de grootte van de uitvoerafbeelding aan voor CAD-tekeningen

## Invoering
CAD-tekeningen vereisen vaak specifieke aanpassingen voor optimale weergave en presentatie. GroupDocs.Viewer voor .NET biedt een krachtige toolset om de uitvoer van CAD-tekeningen te beheren en aan te passen. In deze tutorial begeleiden we u stap voor stap door het proces van het aanpassen van de uitvoergrootte van CAD-tekeningen.
## Vereisten
Voordat u begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. GroupDocs.Viewer voor .NET: Download en installeer GroupDocs.Viewer voor .NET van [hier](https://releases.groupdocs.com/viewer/net/).
2. Documentmap: bereid de map voor waarin uw document zich bevindt.
3. Basiskennis: Maak uzelf vertrouwd met de basisconcepten van .NET-programmering.

## Naamruimten importeren
Zorg er eerst voor dat u de benodigde naamruimten importeert om toegang te krijgen tot de GroupDocs.Viewer-functionaliteiten:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Stap 1: Uitvoermap instellen
Definieer de map waarin u de uitvoerafbeeldingen van CAD-tekeningen wilt opslaan:
```csharp
string outputDirectory = "Your Document Directory";
```
## Stap 2: Definieer het padformaat van het paginabestand
Stel de indeling voor paginabestandspaden in. Deze indeling wordt gebruikt om individuele pagina's een naam te geven en op te slaan als HTML-bestanden:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Stap 3: Pas de afbeeldinggrootte aan
Pas binnen een blok voor het Viewer-object de afbeeldingsgrootte voor CAD-tekeningen aan door de juiste opties in te stellen:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## Stap 4: Uitvoermap weergeven
Nadat het document is weergegeven, wordt er een bericht weergegeven waarin staat dat het weergeven is gelukt. Ook wordt de locatie van de uitvoermap vermeld:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusie
Het aanpassen van de uitvoergrootte van CAD-tekeningen is cruciaal om de zichtbaarheid en bruikbaarheid ervan te verbeteren. Met GroupDocs.Viewer voor .NET wordt dit proces gestroomlijnd en efficiënt, zodat u de uitvoer kunt aanpassen aan uw specifieke vereisten.
## Veelgestelde vragen
### Kan ik de uitvoerformaat van de afbeeldingen aanpassen voor andere typen documenten dan CAD-tekeningen?
Ja, GroupDocs.Viewer voor .NET ondersteunt verschillende documenttypen en u kunt de uitvoergrootte van de afbeeldingen voor de meeste documentindelingen aanpassen.
### Is GroupDocs.Viewer voor .NET compatibel met verschillende versies van het .NET Framework?
Ja, GroupDocs.Viewer voor .NET is compatibel met meerdere versies van het .NET Framework, wat flexibiliteit en bruikbaarheid in verschillende omgevingen garandeert.
### Zijn er licentieopties beschikbaar voor GroupDocs.Viewer voor .NET?
Ja, u kunt verschillende licentieopties bekijken, waaronder tijdelijke licenties en commerciële licenties, die aansluiten bij uw behoeften.
### Kan ik het uitvoerformaat van gerenderde documenten aanpassen?
Jazeker, GroupDocs.Viewer voor .NET biedt diverse aanpassingsopties, waarmee u de uitvoeropmaak kunt afstemmen op uw eigen wensen.
### Waar kan ik aanvullende ondersteuning of hulp vinden voor GroupDocs.Viewer voor .NET?
U kunt het GroupDocs.Viewer-forum bezoeken [hier](https://forum.groupdocs.com/c/viewer/9) om ondersteuning te krijgen, vragen te stellen en contact te leggen met de community.