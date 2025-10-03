---
"description": "Ontdek hoe u Groupdocs.Viewer voor .NET kunt integreren in uw applicaties voor naadloze weergave, omkering en rotatie van documenten."
"linktitle": "Pagina's omdraaien en roteren"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Pagina's omdraaien en roteren"
"url": "/nl/net/rendering-options/flip-rotate-pages/"
"weight": 12
type: docs
---
# Pagina's omdraaien en roteren

## Invoering
In deze tutorial verdiepen we ons in de functionaliteiten van Groupdocs.Viewer voor .NET, met name het omdraaien en roteren van pagina's. Groupdocs.Viewer voor .NET is een krachtige tool, ontworpen om documenten in verschillende formaten weer te geven binnen .NET-applicaties. Of u nu een documentbeheersysteem ontwikkelt of documentweergavemogelijkheden in uw software wilt integreren, Groupdocs.Viewer voor .NET biedt een efficiënte oplossing.
## Vereisten
Voordat we beginnen, moet u ervoor zorgen dat de volgende vereisten zijn ingesteld:
### Groupdocs.Viewer voor .NET installeren
Om Groupdocs.Viewer voor .NET te gebruiken, moet u het pakket installeren via NuGet Package Manager. Gedetailleerde installatie-instructies vindt u in de [documentatie](https://tutorials.groupdocs.com/viewer/net/).

## Naamruimten importeren
Zorg ervoor dat u de benodigde naamruimten in uw project hebt geïmporteerd om Groupdocs.Viewer voor .NET effectief te kunnen gebruiken.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Laten we het proces van het omdraaien en roteren van pagina's met behulp van Groupdocs.Viewer voor .NET opsplitsen in eenvoudige stappen:
## Stap 1: Stel de uitvoermap en het bestandspad in
Definieer de map waarin u het uitvoerbestand wilt opslaan en geef het pad naar het uitvoerbestand op.
```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## Stap 2: Viewerobject initialiseren
Maak een instantie van de Viewer-klasse door het pad door te geven naar het document dat u wilt bekijken.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```
## Stap 3: Weergaveopties configureren
Stel de weergaveopties in, zoals het opgeven van de uitvoerbestandsindeling en eventuele aanvullende instellingen, zoals paginarotatie.
```csharp
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
viewOptions.RotatePage(1, Rotation.On90Degree);
```
## Stap 4: Document renderen
Roep de View-methode van het Viewer-object aan en geef de weergaveopties door.
```csharp
viewer.View(viewOptions);
```
## Stap 5: Succesbericht weergeven
Informeer de gebruiker dat het document succesvol is weergegeven en geef de uitvoermap op voor verificatie.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusie
Kortom, Groupdocs.Viewer voor .NET biedt krachtige mogelijkheden voor het weergeven van documenten, waaronder het omdraaien en roteren van pagina's. Door de stappen in deze tutorial te volgen, kunt u deze functies naadloos integreren in uw .NET-applicaties en zo de weergave van documenten voor uw gebruikers verbeteren.
## Veelgestelde vragen
### Is Groupdocs.Viewer voor .NET compatibel met alle documentformaten?
Ja, Groupdocs.Viewer voor .NET ondersteunt een breed scala aan documentformaten, waaronder DOCX, PDF, PPTX en meer.
### Kan ik de weergaveopties aanpassen naar andere opties dan alleen pagina's omslaan en roteren?
Jazeker, Groupdocs.Viewer voor .NET biedt diverse aanpassingsopties voor het bekijken van documenten, zodat u de ervaring kunt afstemmen op uw wensen.
### Is er een gratis proefversie beschikbaar voor Groupdocs.Viewer voor .NET?
Ja, u kunt een gratis proefversie van Groupdocs.Viewer voor .NET gebruiken door naar de website te gaan [website](https://releases.groupdocs.com/).
### Hoe kan ik ondersteuning krijgen voor Groupdocs.Viewer voor .NET?
kunt hulp zoeken en contact maken met de gemeenschap via de [Groupdocs.Viewer-forum](https://forum.groupdocs.com/c/viewer/9).
### Waar kan ik een tijdelijke licentie voor Groupdocs.Viewer voor .NET verkrijgen?
Tijdelijke licenties voor Groupdocs.Viewer voor .NET zijn verkrijgbaar bij de [aankooppagina](https://purchase.groupdocs.com/temporary-license/).