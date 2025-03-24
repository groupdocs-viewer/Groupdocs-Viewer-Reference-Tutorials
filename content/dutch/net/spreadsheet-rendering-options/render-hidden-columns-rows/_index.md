---
title: Geef verborgen kolommen en rijen weer
linktitle: Geef verborgen kolommen en rijen weer
second_title: GroupDocs.Viewer .NET-API
description: Ontgrendel moeiteloos verborgen gegevens in spreadsheets met GroupDocs.Viewer voor .NET. Volg onze stapsgewijze handleiding om verborgen kolommen en rijen zichtbaar te maken.
weight: 13
url: /nl/net/spreadsheet-rendering-options/render-hidden-columns-rows/
---

# Geef verborgen kolommen en rijen weer

## Invoering
Op het gebied van documentvisualisatie staat GroupDocs.Viewer voor .NET overeind als een robuust hulpmiddel dat een naadloze weergave van verschillende documentformaten mogelijk maakt. Een intrigerende mogelijkheid is de mogelijkheid om verborgen kolommen en rijen in spreadsheets zichtbaar te maken. In deze zelfstudie gaan we dieper in op de stappen om deze functie te ontgrendelen en het potentieel van uw gegevens te benutten.
## Vereisten
Voordat u aan deze reis begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- GroupDocs.Viewer voor .NET: Zorg ervoor dat u de nieuwste versie hebt geïnstalleerd. Als dit niet het geval is, kunt u deze downloaden van de[officiële website](https://releases.groupdocs.com/viewer/net/).
- Documentbestand: maak een voorbeelddocument in spreadsheetformaat (bijvoorbeeld SAMPLE.XLSX) om te experimenteren met verborgen kolommen en rijen.
- Ontwikkelomgeving: Zet een werkomgeving op, bij voorkeur met behulp van Visual Studio of een andere geschikte IDE voor .NET-ontwikkeling.
## Naamruimten importeren
Importeer in uw .NET-project de benodigde naamruimten om de GroupDocs.Viewer-functionaliteiten effectief te benutten:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Stap 1: Stel de uitvoermap in
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Definieer de uitvoermap waar de weergegeven HTML-pagina's worden opgeslagen. Pas het bestandspadformaat dienovereenkomstig aan.
## Stap 2: Initialiseer Viewer en configureer opties
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHiddenColumns = true;
    options.SpreadsheetOptions.RenderHiddenRows = true;
```
Maak een Viewer-instantie door het pad naar uw spreadsheetdocument op te geven. Configureer HTML-weergaveopties om bronnen in te sluiten en de weergave van verborgen kolommen en rijen mogelijk te maken.
## Stap 3: Voer het weergaveproces uit
```csharp
    viewer.View(options);
}
```
Roep de View-methode aan op het viewerobject en geef de geconfigureerde opties door. Hiermee wordt het weergaveproces gestart.
## Stap 4: Controleer de uitvoer
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Controleer de succesvolle weergave van het brondocument en zoek de uitvoer in de opgegeven map.
## Conclusie
Het ontgrendelen van verborgen kolommen en rijen in uw spreadsheets wordt een fluitje van een cent met GroupDocs.Viewer voor .NET. Deze tutorial heeft u voorzien van de essentiële stappen om verborgen gegevens te onthullen, waardoor u een uitgebreider beeld van uw documenten krijgt.
## Veel Gestelde Vragen
### Kan ik verborgen kolommen en rijen in andere documentformaten dan spreadsheets weergeven?
Ja, GroupDocs.Viewer ondersteunt naast spreadsheets ook verschillende documentformaten, waaronder Word, PDF en PowerPoint.
### Is er een limiet aan het aantal verborgen kolommen en rijen dat kan worden weergegeven?
GroupDocs.Viewer zorgt voor een efficiënte verwerking van een groot aantal verborgen kolommen en rijen. Extreme gevallen met een grote hoeveelheid verborgen gegevens kunnen echter de prestaties beïnvloeden.
### Kan ik het uitvoerformaat van de weergegeven gegevens aanpassen?
Absoluut! GroupDocs.Viewer biedt flexibele opties om de uitvoer aan te passen, zodat u de weergegeven gegevens kunt afstemmen op uw specifieke behoeften.
### Zijn er licentieoverwegingen voor het gebruik van GroupDocs.Viewer?
 Ja, zorg ervoor dat u over de juiste licentie voor uw gebruik beschikt. Ontdek licentieopties op[GroupDocs-aankoop](https://purchase.groupdocs.com/buy) of verkrijgen van een[tijdelijke licentie](https://purchase.groupdocs.com/temporary-license/) om uit te proberen.
### Waar kan ik hulp zoeken of contact opnemen met de GroupDocs-gemeenschap voor ondersteuning?
 Bezoek de[GroupDocs.Viewer-forum](https://forum.groupdocs.com/c/viewer/9) voor ondersteuning, discussies en interactie met de gemeenschap.