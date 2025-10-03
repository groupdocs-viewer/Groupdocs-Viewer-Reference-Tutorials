---
"description": "Ontdek de magie van GroupDocs.Viewer voor .NET – integreer documentweergave naadloos in uw applicaties. Probeer nu de gratis proefversie!"
"linktitle": "Werkbladnamen ophalen"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Werkbladnamen ophalen"
"url": "/nl/net/spreadsheet-rendering-options/get-worksheets-names/"
"weight": 11
type: docs
---
# Werkbladnamen ophalen

## Invoering
Welkom in de fascinerende wereld van GroupDocs.Viewer voor .NET! Ben je een ontwikkelaar of enthousiasteling die graag de krachtige mogelijkheden voor documentweergave in je .NET-applicaties wil verkennen? Dan staat je een verrassing te wachten. In deze uitgebreide handleiding verdiepen we ons in de complexiteit van het ophalen van werkbladnamen met GroupDocs.Viewer. Dus, maak je klaar en laten we beginnen aan deze spannende reis!
## Vereisten
Voordat we aan de slag gaan met de codeermagie, willen we ervoor zorgen dat alles klaar staat:
1. GroupDocs.Viewer voor .NET installeren: Ga naar de [downloadlink](https://releases.groupdocs.com/viewer/net/) om de nieuwste versie van GroupDocs.Viewer voor .NET te downloaden. Volg de installatie-instructies om deze naadloos in uw ontwikkelomgeving te integreren.
2. Zorg dat uw document gereed is: zorg dat u een doeldocument hebt, bijvoorbeeld een Excel-bestand met de naam 'file.xlsx', in de aangewezen documentmap.
## Naamruimten importeren
Nu de vereisten zijn vervuld, kunnen we beginnen met het importeren van de benodigde naamruimten. Dit zorgt ervoor dat uw applicatie de functionaliteiten van GroupDocs.Viewer voor .NET herkent en kan gebruiken.
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
Vervang "Uw documentenmap" door het pad naar de map waarin uw doeldocument zich bevindt.
## 2. De viewer initialiseren
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
In deze stap maken we een exemplaar van de Viewer-klasse en geven we het pad naar uw Excel-bestand op.
## 3. Opties voor weergave-informatie configureren
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
Hier configureren we de ViewInfoOptions om HTML-weergaven te genereren en stellen we extra opties in voor het renderen van spreadsheets.
## 4. Weergave-informatie ophalen
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
Gebruik het Viewer-exemplaar om weergavegegevens op te halen op basis van de geconfigureerde opties.
## 5. Werkbladnamen weergeven
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
Doorloop de opgehaalde pagina's en druk de naam van elk werkblad af op de console.
## Conclusie
Gefeliciteerd! U hebt het proces van het ophalen van werkbladnamen met GroupDocs.Viewer voor .NET succesvol doorlopen. Dit opent talloze mogelijkheden voor het verbeteren van de documentweergave in uw applicaties.
## Veelgestelde vragen
### Kan ik GroupDocs.Viewer voor .NET gebruiken met andere documentformaten?
Absoluut! GroupDocs.Viewer ondersteunt een breed scala aan documentformaten, waaronder PDF, Microsoft Office en meer.
### Is er een gratis proefperiode beschikbaar?
Ja, u kunt GroupDocs.Viewer voor .NET verkennen met onze [gratis proefperiode](https://releases.groupdocs.com/).
### Waar kan ik extra ondersteuning vinden?
Ga naar de [GroupDocs.Viewer-forum](https://forum.groupdocs.com/c/viewer/9) voor ondersteuning en discussies vanuit de gemeenschap.
### Kan ik een tijdelijk rijbewijs krijgen?
Zeker! Bezoek [deze link](https://purchase.groupdocs.com/temporary-license/) om uw tijdelijke rijbewijs te verkrijgen.
### Zijn er gedetailleerde documentatiebronnen beschikbaar?
Absoluut! Bekijk de [officiële documentatie](https://tutorials.groupdocs.com/viewer/net/) voor diepgaande informatie en gidsen.