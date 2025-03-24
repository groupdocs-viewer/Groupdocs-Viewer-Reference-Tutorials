---
title: Pagina's omdraaien en roteren
linktitle: Pagina's omdraaien en roteren
second_title: GroupDocs.Viewer .NET-API
description: Leer hoe u Groupdocs.Viewer voor .NET in uw toepassingen kunt integreren voor een naadloze weergave, omdraaien en roteren van documenten.
weight: 12
url: /nl/net/rendering-options/flip-rotate-pages/
---
## Invoering
In deze tutorial gaan we dieper in op de functionaliteiten van Groupdocs.Viewer voor .NET, waarbij we ons specifiek richten op het omdraaien en roteren van pagina's. Groupdocs.Viewer voor .NET is een krachtig hulpmiddel dat is ontworpen om documenten in verschillende formaten weer te geven binnen .NET-toepassingen. Of u nu een documentbeheersysteem ontwikkelt of de weergavemogelijkheden van documenten in uw software wilt integreren, Groupdocs.Viewer voor .NET biedt een efficiënte oplossing.
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
### Groupdocs.Viewer voor .NET installeren
 Om Groupdocs.Viewer voor .NET te gebruiken, moet u het pakket installeren via NuGet Package Manager. Gedetailleerde installatie-instructies vindt u in de[documentatie](https://tutorials.groupdocs.com/viewer/net/).

## Naamruimten importeren
Zorg ervoor dat u de benodigde naamruimten in uw project importeert om Groupdocs.Viewer voor .NET effectief te kunnen gebruiken.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Laten we het proces van het omdraaien en roteren van pagina's met Groupdocs.Viewer voor .NET in eenvoudige stappen opsplitsen:
## Stap 1: Stel de uitvoermap en het bestandspad in
Definieer de map waar u het uitvoerbestand wilt opslaan en geef het pad naar het uitvoerbestand op.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## Stap 2: Initialiseer het Viewer-object
Maak een exemplaar van de klasse Viewer door het pad door te geven aan het document dat u wilt bekijken.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## Stap 3: Configureer weergaveopties
Stel de weergaveopties in, zoals het opgeven van het uitvoerbestandsformaat en eventuele aanvullende instellingen zoals paginarotatie.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## Stap 4: Document renderen
Roep de View-methode van het Viewer-object aan en geef de weergave-opties door.
```csharp
viewer.View(viewOptions);
```
## Stap 5: Succesbericht weergeven
Informeer de gebruiker dat het document met succes is weergegeven en geef de uitvoermap op ter verificatie.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusie
Concluderend biedt Groupdocs.Viewer voor .NET krachtige mogelijkheden voor het weergeven van documenten, inclusief het omdraaien en roteren van pagina's. Door de stappen te volgen die in deze zelfstudie worden beschreven, kunt u deze functies naadloos integreren in uw .NET-toepassingen, waardoor de kijkervaring voor uw gebruikers wordt verbeterd.
## Veelgestelde vragen
### Is Groupdocs.Viewer voor .NET compatibel met alle documentformaten?
Ja, Groupdocs.Viewer voor .NET ondersteunt een breed scala aan documentformaten, waaronder DOCX, PDF, PPTX en meer.
### Kan ik de weergaveopties aanpassen, behalve het omdraaien en roteren van pagina's?
Absoluut, Groupdocs.Viewer voor .NET biedt verschillende aanpassingsopties voor het bekijken van documenten, zodat u de ervaring kunt afstemmen op uw vereisten.
### Is er een gratis proefversie beschikbaar voor Groupdocs.Viewer voor .NET?
 Ja, u kunt profiteren van een gratis proefversie van Groupdocs.Viewer voor .NET door naar de[website](https://releases.groupdocs.com/).
### Hoe kan ik ondersteuning krijgen voor Groupdocs.Viewer voor .NET?
 U kunt hulp zoeken en in contact komen met de gemeenschap via de[Groupdocs.Viewer-forum](https://forum.groupdocs.com/c/viewer/9).
### Waar kan ik een tijdelijke licentie verkrijgen voor Groupdocs.Viewer voor .NET?
 Tijdelijke licenties voor Groupdocs.Viewer voor .NET zijn verkrijgbaar bij de[aankooppagina](https://purchase.groupdocs.com/temporary-license/).