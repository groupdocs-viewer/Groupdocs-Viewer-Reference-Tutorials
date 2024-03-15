---
title: Werkbladnamen ophalen
linktitle: Werkbladnamen ophalen
second_title: GroupDocs.Viewer .NET-API
description: Ontdek de magie van GroupDocs.Viewer voor .NET – integreer de weergave van documenten naadloos in uw toepassingen. Probeer nu de gratis proefperiode!
type: docs
weight: 11
url: /nl/net/spreadsheet-rendering-options/get-worksheets-names/
---
## Invoering
Welkom in de fascinerende wereld van GroupDocs.Viewer voor .NET! Als u een ontwikkelaar of liefhebber bent en graag de krachtige mogelijkheden voor documentweergave binnen uw .NET-toepassingen wilt verkennen, staat u iets moois te wachten. In deze uitgebreide handleiding gaan we in op de fijne kneepjes van het ophalen van werkbladnamen met GroupDocs.Viewer. Dus maak je veiligheidsgordel vast en laten we aan deze spannende reis beginnen!
## Vereisten
Voordat we in de codeermagie duiken, moeten we ervoor zorgen dat je alles hebt ingesteld:
1.  Installeer GroupDocs.Viewer voor .NET: Ga naar de[download link](https://releases.groupdocs.com/viewer/net/)om de nieuwste versie van GroupDocs.Viewer voor .NET te downloaden. Volg de installatie-instructies om het naadloos in uw ontwikkelomgeving te integreren.
2. Maak uw document gereed: Zorg ervoor dat u een doeldocument hebt, bijvoorbeeld een Excel-bestand met de naam "file.xlsx", in de door u aangewezen documentmap.
## Naamruimten importeren
Nu u over de vereisten beschikt, gaan we van start met het importeren van de benodigde naamruimten. Dit zorgt ervoor dat uw applicatie de functionaliteiten van GroupDocs.Viewer voor .NET herkent en kan gebruiken.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## 1. De documentenmap instellen
```csharp
string outputDirectory = "Your Document Directory";
```
Vervang "Uw documentenmap" door het pad naar de map waar uw doeldocument zich bevindt.
## 2. Initialiseren van de viewer
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
In deze stap maken we een exemplaar van de Viewer-klasse, waarin we het pad naar uw Excel-bestand opgeven.
## 3. Opties voor weergave-informatie configureren
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
Hier configureren we de ViewInfoOptions om HTML-weergaven te genereren en aanvullende opties in te stellen voor het renderen van spreadsheets.
## 4. Weergave-informatie ophalen
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
Gebruik de Viewer-instantie om weergavegegevens op te halen op basis van de geconfigureerde opties.
## 5. Werkbladnamen weergeven
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
Loop door de opgehaalde pagina's en druk de naam van elk werkblad af op de console.
## Conclusie
Gefeliciteerd! U hebt met succes door het proces van het ophalen van werkbladnamen genavigeerd met GroupDocs.Viewer voor .NET. Dit opent een groot aantal mogelijkheden om de functionaliteit voor het bekijken van documenten binnen uw toepassingen te verbeteren.
## Veelgestelde vragen
### Kan ik GroupDocs.Viewer voor .NET gebruiken met andere documentformaten?
Absoluut! GroupDocs.Viewer ondersteunt een breed scala aan documentformaten, waaronder PDF, Microsoft Office en meer.
### Is er een gratis proefversie beschikbaar?
 Ja, u kunt GroupDocs.Viewer voor .NET verkennen met onze[gratis proefperiode](https://releases.groupdocs.com/).
### Waar kan ik aanvullende ondersteuning vinden?
 Ga naar de[GroupDocs.Viewer-forum](https://forum.groupdocs.com/c/viewer/9) voor gemeenschapsondersteuning en discussies.
### Kan ik een tijdelijke licentie krijgen?
 Zeker! Bezoek[deze link](https://purchase.groupdocs.com/temporary-license/) om uw tijdelijke licentie te verkrijgen.
### Zijn er gedetailleerde documentatiebronnen beschikbaar?
 Absoluut! Bekijk de[officiële documentatie](https://reference.groupdocs.com/viewer/net/) voor uitgebreide informatie en handleidingen.