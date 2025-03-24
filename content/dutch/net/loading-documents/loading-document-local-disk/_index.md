---
title: Documenten laden vanaf de lokale schijf
linktitle: Documenten laden vanaf de lokale schijf
second_title: GroupDocs.Viewer .NET-API
description: Leer hoe u documenten naadloos vanaf uw lokale schijf kunt weergeven met Groupdocs.Viewer voor .NET. Verbeter uw .NET-applicaties met efficiënt document.
weight: 10
url: /nl/net/loading-documents/loading-document-local-disk/
---

# Documenten laden vanaf de lokale schijf

## Invoering
In het huidige digitale tijdperk is efficiënte documentweergave essentieel voor verschillende toepassingen. Groupdocs.Viewer voor .NET biedt een krachtige oplossing voor het rechtstreeks weergeven van documenten vanaf uw lokale schijf. In deze zelfstudie begeleiden we u bij het laden van documenten vanaf uw lokale schijf met Groupdocs.Viewer voor .NET. Of u nu een doorgewinterde ontwikkelaar bent of net begint, deze stapsgewijze handleiding helpt u bij het naadloos integreren van documentweergave in uw .NET-toepassingen.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1.  Groupdocs.Viewer voor .NET: Download en installeer de nieuwste versie van[hier](https://releases.groupdocs.com/viewer/net/).
2. .NET-ontwikkelomgeving: Zorg ervoor dat u een werkende .NET-ontwikkelomgeving op uw systeem hebt geïnstalleerd.
3. Lokale documenten: zorg ervoor dat de documenten die u wilt weergeven lokaal op uw schijf worden opgeslagen.

## Naamruimten importeren
Laten we eerst de benodigde naamruimten importeren om toegang te krijgen tot de functionaliteiten van Groupdocs.Viewer voor .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Stap 1: Laad documenten van de lokale schijf
Begin met het instellen van de uitvoermap waar de weergegeven HTML-pagina's worden opgeslagen.
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Stap 2: Initialiseer Viewer en render documenten
Initialiseer het Viewer-object met het pad van het document en render het met behulp van HTML-weergaveopties.
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Stap 3: Weergave-uitvoer
Zodra de weergave is voltooid, wordt een bericht weergegeven waarin de succesvolle weergave van het brondocument en de locatie van de uitvoerbestanden worden aangegeven.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusie
Gefeliciteerd! U heeft met succes geleerd hoe u documenten van uw lokale schijf kunt laden met Groupdocs.Viewer voor .NET. Deze krachtige tool opent een wereld aan mogelijkheden voor documentweergave binnen uw .NET-applicaties.
## Veelgestelde vragen
### Kan ik documenten van verschillende formaten weergeven met Groupdocs.Viewer voor .NET?
Ja, Groupdocs.Viewer voor .NET ondersteunt een breed scala aan documentformaten, waaronder DOCX, PDF, XLSX, PPTX en meer.
### Is Groupdocs.Viewer voor .NET compatibel met alle .NET-frameworks?
Groupdocs.Viewer voor .NET is compatibel met de meeste .NET-frameworks, waaronder .NET Core, .NET Framework en .NET Standard.
### Kan ik de weergaveopties voor mijn documenten aanpassen?
Absoluut! Groupdocs.Viewer voor .NET biedt uitgebreide aanpassingsopties waarmee u het weergaveproces kunt afstemmen op uw specifieke vereisten.
### Is er een proefversie beschikbaar voor Groupdocs.Viewer voor .NET?
Ja, u kunt een gratis proefversie downloaden van[hier](https://releases.groupdocs.com/).
### Waar kan ik ondersteuning of aanvullende bronnen vinden voor Groupdocs.Viewer voor .NET?
 Voor ondersteuning en aanvullende bronnen gaat u naar Groupdocs.Viewer voor .NET[forum](https://forum.groupdocs.com/c/viewer/9).