---
"description": "Integreer GroupDocs.Viewer voor .NET naadloos in uw applicaties voor krachtige documentweergavemogelijkheden. Verbeter de gebruikerservaring met aanpasbare opties."
"linktitle": "Datum/tijd-indeling en tijdzone-offset instellen (e-mail)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Datum/tijd-indeling en tijdzone-offset instellen (e-mail)"
"url": "/nl/net/rendering-email-messages/set-date-time-format-offset-email/"
"weight": 11
type: docs
---
# Datum/tijd-indeling en tijdzone-offset instellen (e-mail)


## Invoering
GroupDocs.Viewer voor .NET is een krachtige tool waarmee ontwikkelaars naadloos documentweergavemogelijkheden kunnen integreren in hun .NET-applicaties. Met GroupDocs.Viewer kunt u een breed scala aan documentformaten, waaronder PDF's, Microsoft Office-documenten, afbeeldingen en meer, rechtstreeks in uw applicatie weergeven, zonder dat u externe plug-ins of viewers nodig hebt. In deze uitgebreide tutorial begeleiden we u bij het instellen van GroupDocs.Viewer voor .NET, verkennen we de functies ervan en laten we zien hoe u het effectief kunt gebruiken om de documentweergavemogelijkheden van uw applicatie te verbeteren.
## Vereisten
Voordat u met deze tutorial aan de slag gaat, moet u ervoor zorgen dat u aan de volgende vereisten hebt voldaan:
1. Visual Studio: Zorg ervoor dat Visual Studio op uw systeem is geïnstalleerd. GroupDocs.Viewer voor .NET is volledig compatibel met Visual Studio, wat zorgt voor naadloze integratie in uw .NET-projecten.
2. GroupDocs.Viewer voor .NET: Download en installeer GroupDocs.Viewer voor .NET van de [downloadlink](https://releases.groupdocs.com/viewer/net/)Volg de installatie-instructies om de bibliotheek in uw ontwikkelomgeving in te stellen.
3. .NET Framework: Zorg ervoor dat u de juiste versie van .NET Framework hebt geïnstalleerd. GroupDocs.Viewer voor .NET ondersteunt verschillende versies van .NET Framework, waaronder .NET Core en .NET Standard.

## Naamruimten importeren
Om GroupDocs.Viewer voor .NET effectief te kunnen gebruiken, moet u de benodigde naamruimten in uw project importeren. Volg deze stappen om de benodigde naamruimten te importeren:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


Laten we het gegeven voorbeeld opsplitsen in meerdere stappen om elk onderdeel en de functionaliteit ervan te begrijpen.
## Stap 1: Stel de uitvoermap en het bestandspad in
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
In deze stap definiëren we de uitvoermap waar het gerenderde document wordt opgeslagen en specificeren we het bestandspad voor het HTML-uitvoerbestand.
## Stap 2: Viewerobject instantiëren
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
Hier maken we een nieuw exemplaar van de `Viewer` klasse, waarbij het pad van het te bekijken document (in dit geval een voorbeeld-EML-bestand) als parameter wordt doorgegeven.
## Stap 3: HTML-weergaveopties definiëren
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
In deze stap configureren we de HTML-weergaveopties voor het renderen van het document. Hierbij geven we het pad naar het uitvoerbestand voor het gerenderde HTML-document op.
## Stap 4: Datum/tijd-indeling en tijdzone-offset instellen
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Hier passen we de datum- en tijdnotatie voor e-mailberichten aan en stellen we de tijdzone-offset in op basis van de gewenste tijdzone.
## Stap 5: Document renderen
```csharp
viewer.View(options);
```
Ten slotte noemen we de `View` methode van de `Viewer` object, waarbij de geconfigureerde HTML-weergaveopties worden doorgegeven om het document in HTML-formaat weer te geven.
## Stap 6: Uitvoermap weergeven
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Met deze stap wordt eenvoudigweg een bericht weergegeven dat aangeeft dat het document succesvol is weergegeven. Ook wordt het pad naar de uitvoermap weergegeven waar het weergegeven HTML-document zich bevindt.

## Conclusie
GroupDocs.Viewer voor .NET biedt een robuuste oplossing voor het integreren van documentweergavemogelijkheden in uw .NET-applicaties. Door de stappen in deze tutorial te volgen, kunt u GroupDocs.Viewer eenvoudig instellen, de benodigde naamruimten importeren en de functies gebruiken om documenten met aanpasbare opties weer te geven. Of u nu werkt met PDF's, Microsoft Office-documenten of andere formaten, GroupDocs.Viewer vereenvoudigt het proces van documentweergave en verbetert de gebruikerservaring van uw applicaties.
## Veelgestelde vragen
### Is GroupDocs.Viewer compatibel met .NET Core?
Ja, GroupDocs.Viewer voor .NET ondersteunt .NET Core, waardoor uw applicaties compatibel zijn met meerdere platformen.
### Kan ik het uiterlijk van de gerenderde documenten aanpassen?
Absoluut! GroupDocs.Viewer biedt diverse aanpassingsopties, zoals zoomniveaus, paginarotatie en meer, om de kijkervaring af te stemmen op jouw wensen.
### Is er een proefversie beschikbaar voor testdoeleinden?
Ja, u kunt een gratis proefversie van GroupDocs.Viewer voor .NET downloaden van de [website-link](https://releases.groupdocs.com/viewer/net/) om de functies ervan te evalueren voordat u tot aankoop overgaat.
### Ondersteunt GroupDocs.Viewer het weergeven van wachtwoordbeveiligde documenten?
Ja, GroupDocs.Viewer biedt ingebouwde ondersteuning voor het weergeven van met een wachtwoord beveiligde documenten. Zo bent u verzekerd van een veilige weergave van uw documenten in uw toepassingen.
### Waar kan ik aanvullende ondersteuning of hulp vinden voor GroupDocs.Viewer?
Voor technische vragen of hulp kunt u terecht op de GroupDocs.Viewer [forum](https://forum.groupdocs.com/c/viewer/9) kunt ook contact opnemen met hun ondersteuningsteam voor snelle hulp en begeleiding.