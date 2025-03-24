---
title: Render alle lay-outs in CAD-tekeningen
linktitle: Render alle lay-outs in CAD-tekeningen
second_title: GroupDocs.Viewer .NET-API
description: Leer hoe u alle lay-outs in CAD-tekeningen kunt weergeven met GroupDocs.Viewer voor .NET. Volg onze uitgebreide tutorial voor naadloze integratie.
weight: 11
url: /nl/net/rendering-cad-drawings/render-all-layouts-cad/
---
## Invoering
Op het gebied van documentbeheer en visualisatie staat GroupDocs.Viewer voor .NET overeind als een veelzijdige oplossing, waarmee ontwikkelaars moeiteloos verschillende documenttypen binnen hun .NET-toepassingen kunnen weergeven. Tot de talloze mogelijkheden behoort de mogelijkheid om CAD-tekeningen efficiënt weer te geven, inclusief de ingewikkelde lay-outs die ze met zich meebrengen. In deze zelfstudie verdiepen we ons in het proces van het gebruik van GroupDocs.Viewer voor .NET om alle lay-outs in CAD-tekeningen weer te geven. 
## Vereisten
Voordat u aan deze zelfstudie begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. Basiskennis van .NET-ontwikkeling: Bekendheid met de basisprincipes van .NET-ontwikkeling zal nuttig zijn bij het begrijpen van de implementatiestappen die in deze zelfstudie worden beschreven.
2.  Installatie van GroupDocs.Viewer voor .NET: Zorg ervoor dat u de GroupDocs.Viewer voor .NET-bibliotheek hebt geïnstalleerd. Je kunt het downloaden van de[website](https://releases.groupdocs.com/viewer/net/).
3. CAD-tekeningbestanden: verkrijg de CAD-tekeningbestanden die u wilt renderen. Dit kunnen DWG-bestanden met meerdere lay-outs zijn.
4. Ontwikkelomgeving: Stel uw favoriete ontwikkelomgeving in met de benodigde tools en afhankelijkheden.

## Naamruimten importeren
Zorg er eerst voor dat u de vereiste naamruimten in uw .NET-project importeert. Deze naamruimten bieden toegang tot de functionaliteiten die nodig zijn voor het renderen van CAD-tekeningen met GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Stap 2: Importeer System.IO-naamruimte
```csharp
using System.IO;
```
## Stap 1: Geef de uitvoermap op
```csharp
string outputDirectory = "Your Document Directory";
```
Definieer de map waar u de gerenderde uitvoer wilt opslaan.
## Stap 2: Definieer het paginabestandspadformaat
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Stel het formaat in voor de bestandspaden van de gerenderde pagina's. In dit geval worden de pagina's opgeslagen als HTML-bestanden.
## Stap 3: Instantie van Viewer-object
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
Maak een exemplaar van de klasse Viewer, waarbij u het pad naar het CAD-tekeningbestand als parameter doorgeeft.
## Stap 4: Configureer HTML-weergaveopties
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.CadOptions.RenderLayouts = true;
```
Configureer de HTML-weergaveopties, waarbij u specificeert dat lay-outs moeten worden weergegeven voor CAD-tekeningen.
## Stap 5: Render CAD-tekening
```csharp
viewer.View(options);
```
Roep de View-methode van het Viewer-object op en geef de geconfigureerde opties door om de CAD-tekening weer te geven.
## Stap 6: Geef de uitvoerdirectory weer
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Informeer de gebruiker over de succesvolle weergave en de locatie van de uitvoermap.

## Conclusie
In deze zelfstudie hebben we onderzocht hoe u GroupDocs.Viewer voor .NET kunt gebruiken om alle lay-outs in CAD-tekeningen weer te geven. Door de stapsgewijze handleiding te volgen en de meegeleverde codefragmenten te implementeren, kunt u deze functionaliteit naadloos integreren in uw .NET-applicaties, waardoor de mogelijkheden voor documentvisualisatie worden verbeterd.
## Veelgestelde vragen
### Is GroupDocs.Viewer compatibel met verschillende CAD-formaten?
Ja, GroupDocs.Viewer ondersteunt het weergeven van CAD-tekeningen in formaten zoals DWG en DXF.
### Kan ik de weergave-uitvoer aanpassen aan de vereisten van mijn toepassing?
Absoluut, GroupDocs.Viewer biedt een breed scala aan opties voor het aanpassen van de weergave-uitvoer, inclusief afbeeldingskwaliteit, paginagrootte en meer.
### Heeft GroupDocs.Viewer aanvullende licenties nodig voor commercieel gebruik?
Ja, voor commercieel gebruik moet u mogelijk een licentie aanschaffen. U kunt tijdelijke licenties verkrijgen voor testdoeleinden of een commerciële licentie aanschaffen via de website.
### Kan ik CAD-tekeningen asynchroon weergeven met GroupDocs.Viewer?
Ja, GroupDocs.Viewer biedt asynchrone weergavemogelijkheden, waardoor grote CAD-tekeningen efficiënt kunnen worden verwerkt zonder de hoofdthread te blokkeren.
### Biedt GroupDocs.Viewer ondersteuning voor probleemoplossing en technische ondersteuning?
 Natuurlijk kunt u ondersteuning en hulp zoeken op het GroupDocs.Viewer-communityforum, dat toegankelijk is[hier](https://forum.groupdocs.com/c/viewer/9).