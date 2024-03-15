---
title: Pagina's in document opnieuw rangschikken
linktitle: Pagina's in document opnieuw rangschikken
second_title: GroupDocs.Viewer .NET-API
description: Leer hoe u pagina's in een document opnieuw kunt rangschikken met GroupDocs.Viewer voor .NET. Volg onze stapsgewijze handleiding voor naadloos documentbeheer.
type: docs
weight: 19
url: /nl/net/rendering-options/reorder-pages/
---
## Invoering
In de wereld van .NET-ontwikkeling is het efficiënt beheren en manipuleren van documenten cruciaal. GroupDocs.Viewer voor .NET biedt een krachtige oplossing voor het bekijken van verschillende documentformaten binnen uw applicaties. Een van de essentiële taken die ontwikkelaars vaak tegenkomen, is het opnieuw ordenen van pagina's binnen een document. Of u nu met PDF's, Word-documenten of andere formaten werkt: het herschikken van pagina's kan de workflows stroomlijnen en de gebruikerservaring verbeteren. In deze zelfstudie gaan we dieper in op hoe u pagina's in een document opnieuw kunt rangschikken met GroupDocs.Viewer voor .NET.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
### 1. Installeer GroupDocs.Viewer voor .NET
 Zorg ervoor dat GroupDocs.Viewer voor .NET in uw ontwikkelomgeving is geïnstalleerd. Je kunt het downloaden van[hier](https://releases.groupdocs.com/viewer/net/) en volg de installatie-instructies in de documentatie.
### 2. Stel uw ontwikkelomgeving in
Zorg ervoor dat u een werkende .NET-ontwikkelomgeving op uw computer hebt ingesteld, inclusief Visual Studio of een andere gewenste IDE.
### 3. Verkrijg voorbeelddocumenten
Houd enkele voorbeelddocumenten gereed voor testdoeleinden. U kunt elk documentformaat gebruiken dat door GroupDocs.Viewer wordt ondersteund, zoals PDF, DOCX, XLSX, enz.

## Naamruimten importeren
Importeer in uw .NET-toepassing de benodigde naamruimten die nodig zijn voor het gebruik van de GroupDocs.Viewer-functionaliteit.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Stap 1: Geef de uitvoermap op
Definieer de map waarin u het opnieuw geordende document wilt opslaan.
```csharp
string outputDirectory = "Your Document Directory";
```
## Stap 2: Definieer het uitvoerbestandspad
Combineer de uitvoermap met de gewenste bestandsnaam voor het opnieuw geordende document.
```csharp
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## Stap 3: Instantie van Viewer-object
Maak een exemplaar van de klasse Viewer door het pad naar het invoerdocument op te geven.
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    // Hier vindt u de code voor het opnieuw ordenen van pagina's
}
```
## Stap 4: Stel de PDF-weergaveopties in
Geef de opties op voor het weergeven van het document als PDF en definieer het pad voor het uitvoerbestand.
```csharp
PdfViewOptions options = new PdfViewOptions(outputFilePath);
```
## Stap 5: Definieer de paginavolgorde
Geef de paginanummers in de gewenste volgorde door voor weergave.
```csharp
viewer.View(options, 2, 1);
```
## Stap 6: Succesbericht weergeven
Informeer de gebruiker dat het document succesvol is weergegeven.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusie
Kortom, het herschikken van pagina's in een document is eenvoudig gemaakt met GroupDocs.Viewer voor .NET. Door de stappen in deze zelfstudie te volgen, kunt u documentpagina's binnen uw .NET-toepassingen efficiënt beheren, waardoor de bruikbaarheid en productiviteit worden verbeterd.
## Veelgestelde vragen
### Kan GroupDocs.Viewer voor .NET meerdere documentformaten verwerken?
Ja, GroupDocs.Viewer ondersteunt een breed scala aan documentformaten, waaronder PDF, DOCX, XLSX, PPTX en meer.
### Is er een gratis proefversie beschikbaar voor GroupDocs.Viewer voor .NET?
 Ja, u heeft toegang tot een gratis proefversie van GroupDocs.Viewer vanaf[hier](https://releases.groupdocs.com/).
### Heeft GroupDocs.Viewer voor .NET een permanente licentie nodig voor ontwikkeling?
 Hoewel er een tijdelijke licentie beschikbaar is voor testen en ontwikkelen, is voor productiegebruik een permanente licentie vereist. U kunt een tijdelijke licentie verkrijgen[hier](https://purchase.groupdocs.com/temporary-license/).
### Kan ik het uiterlijk van het weergegeven document aanpassen met GroupDocs.Viewer voor .NET?
Ja, GroupDocs.Viewer biedt verschillende opties voor het aanpassen van de weergave-uitvoer, inclusief paginarotatie, watermerken en meer.
### Waar kan ik verdere hulp of ondersteuning vinden voor GroupDocs.Viewer voor .NET?
 U kunt het GroupDocs.Viewer-forum bezoeken[hier](https://forum.groupdocs.com/c/viewer/9) voor eventuele vragen of ondersteuningsbehoeften.