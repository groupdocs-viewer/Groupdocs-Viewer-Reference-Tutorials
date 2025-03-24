---
title: Datum/tijd-notatie en tijdzone-offset instellen (e-mail)
linktitle: Datum/tijd-notatie en tijdzone-offset instellen (e-mail)
second_title: GroupDocs.Viewer .NET-API
description: Integreer GroupDocs.Viewer voor .NET naadloos in uw toepassingen voor krachtige documentweergavemogelijkheden. Verbeter de gebruikerservaring met aanpasbare opties.
weight: 11
url: /nl/net/rendering-email-messages/set-date-time-format-offset-email/
---

## Invoering
GroupDocs.Viewer voor .NET is een krachtig hulpmiddel waarmee ontwikkelaars de weergavemogelijkheden van documenten naadloos kunnen integreren in hun .NET-toepassingen. Met GroupDocs.Viewer kunt u een breed scala aan documentformaten weergeven, waaronder PDF's, Microsoft Office-documenten, afbeeldingen en meer, rechtstreeks in uw toepassing, zonder dat u externe plug-ins of viewers nodig hebt. In deze uitgebreide zelfstudie begeleiden we u bij het instellen van GroupDocs.Viewer voor .NET, verkennen we de functies ervan en demonstreren we hoe u deze effectief kunt gebruiken om de documentweergavemogelijkheden van uw toepassing te verbeteren.
## Vereisten
Voordat u in deze zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. Visual Studio: Zorg ervoor dat Visual Studio op uw systeem is geïnstalleerd. GroupDocs.Viewer voor .NET is volledig compatibel met Visual Studio, waardoor naadloze integratie in uw .NET-projecten mogelijk is.
2.  GroupDocs.Viewer voor .NET: Download en installeer GroupDocs.Viewer voor .NET vanaf de[download link](https://releases.groupdocs.com/viewer/net/). Volg de meegeleverde installatie-instructies om de bibliotheek in uw ontwikkelomgeving in te stellen.
3. .NET Framework: Zorg ervoor dat u de juiste versie van .NET Framework hebt geïnstalleerd. GroupDocs.Viewer voor .NET ondersteunt verschillende versies van .NET Framework, waaronder .NET Core en .NET Standard.

## Naamruimten importeren
Om GroupDocs.Viewer voor .NET effectief te kunnen gebruiken, moet u de benodigde naamruimten in uw project importeren. Volg deze stappen om de vereiste naamruimten te importeren:

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
In deze stap definiëren we de uitvoermap waar het gerenderde document zal worden opgeslagen en specificeren we het bestandspad voor het uitvoer-HTML-bestand.
## Stap 2: Instantie van Viewer-object
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
 Hier maken we een nieuw exemplaar van de`Viewer` class, waarbij het pad van het te bekijken document (in dit geval een voorbeeld van een EML-bestand) als parameter wordt doorgegeven.
## Stap 3: Definieer HTML-weergaveopties
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
In deze stap configureren we de HTML-weergaveopties voor de documentweergave, waarbij we het uitvoerbestandspad voor het gerenderde HTML-document specificeren.
## Stap 4: Stel het datum-tijdformaat en de tijdzone-offset in
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Hier passen we het datum- en tijdformaat voor e-mailberichten aan en stellen we de tijdzone-offset in op basis van de gewenste tijdzone.
## Stap 5: Document renderen
```csharp
viewer.View(options);
```
 Tenslotte noemen wij de`View` werkwijze van de`Viewer` object, waarbij de geconfigureerde HTML-weergaveopties worden doorgegeven om het document in HTML-indeling weer te geven.
## Stap 6: Geef de uitvoerdirectory weer
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Deze stap geeft eenvoudigweg een bericht weer dat de succesvolle weergave van het document aangeeft en geeft het pad naar de uitvoermap waar het weergegeven HTML-document zich bevindt.

## Conclusie
GroupDocs.Viewer voor .NET biedt een robuuste oplossing voor het integreren van documentweergavemogelijkheden in uw .NET-toepassingen. Door de stappen in deze zelfstudie te volgen, kunt u eenvoudig GroupDocs.Viewer instellen, de benodigde naamruimten importeren en de functies ervan gebruiken om documenten met aanpasbare opties weer te geven. Of u nu werkt met PDF's, Microsoft Office-documenten of andere formaten, GroupDocs.Viewer vereenvoudigt het proces van het bekijken van documenten, waardoor de gebruikerservaring van uw toepassingen wordt verbeterd.
## Veelgestelde vragen
### Is GroupDocs.Viewer compatibel met .NET Core?
Ja, GroupDocs.Viewer voor .NET ondersteunt .NET Core, waardoor platformonafhankelijke compatibiliteit voor uw toepassingen mogelijk wordt.
### Kan ik het uiterlijk van de weergegeven documenten aanpassen?
Absoluut! GroupDocs.Viewer biedt verschillende aanpassingsopties, waaronder zoomniveaus, paginarotatie en meer, om de kijkervaring aan uw voorkeuren aan te passen.
### Is er een proefversie beschikbaar voor testdoeleinden?
 Ja, u kunt een gratis proefversie van GroupDocs.Viewer voor .NET downloaden van de[website link](https://releases.groupdocs.com/viewer/net/) om de kenmerken ervan te evalueren voordat u een aankoop doet.
### Ondersteunt GroupDocs.Viewer het weergeven van met een wachtwoord beveiligde documenten?
Ja, GroupDocs.Viewer heeft ingebouwde ondersteuning voor het weergeven van met een wachtwoord beveiligde documenten, zodat documenten veilig kunnen worden bekeken binnen uw toepassingen.
### Waar kan ik aanvullende ondersteuning of assistentie vinden met GroupDocs.Viewer?
 Voor technische vragen of hulp kunt u de GroupDocs.Viewer bezoeken[forum](https://forum.groupdocs.com/c/viewer/9) of neem contact op met hun ondersteuningsteam voor snelle hulp en begeleiding.