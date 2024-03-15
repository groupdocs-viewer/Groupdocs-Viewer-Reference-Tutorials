---
title: Sluit lettertypen uit van gerenderde HTML
linktitle: Sluit lettertypen uit van gerenderde HTML
second_title: GroupDocs.Viewer .NET-API
description: Leer hoe u lettertypen uitsluit van weergegeven HTML met GroupDocs.Viewer voor .NET. Volg deze stapsgewijze handleiding voor een naadloze documentweergave.
type: docs
weight: 10
url: /nl/net/rendering-documents-html/exclude-fonts-html/
---
## Invoering
GroupDocs.Viewer voor .NET is een krachtige documentweergavebibliotheek waarmee ontwikkelaars meer dan 50 documentformaten in hun .NET-applicaties kunnen weergeven zonder de noodzaak van externe afhankelijkheden. In deze zelfstudie concentreren we ons op een specifieke functie van GroupDocs.Viewer: lettertypen uitsluiten van weergegeven HTML-uitvoer. 
## Vereisten
Zorg ervoor dat u over het volgende beschikt voordat u begint:
1. Basiskennis van C# en .NET-ontwikkeling.
2.  GroupDocs.Viewer voor .NET geïnstalleerd. Je kunt het downloaden van[hier](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio of een andere IDE voor C#-ontwikkeling.

## Naamruimten importeren
Zorg ervoor dat u in uw C#-code de benodigde naamruimten opneemt:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Stap 1: Definieer de uitvoerdirectory
Stel de map in waar u de gerenderde HTML-bestanden wilt opslaan.
```csharp
string outputDirectory = "Your Document Directory";
```
## Stap 2: Definieer het paginabestandspadformaat
Geef het formaat op voor de bestandspaden van afzonderlijke pagina's van het weergegeven document.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Stap 3: Initialiseer het Viewer-object
Instantieer het Viewer-object met het document dat u wilt renderen.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // Je code komt hier
}
```
## Stap 4: Stel HTML-weergaveopties in
Definieer de opties voor HTML-weergave, inclusief de indeling van ingesloten bronnen en lettertypen die moeten worden uitgesloten.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## Stap 5: Document renderen
Geef de HTML-weergaveopties door aan het Viewer-object om het document weer te geven.
```csharp
viewer.View(options);
```
## Stap 6: Uitvoer van gerenderde documentlocatie
Informeer de gebruiker over de locatie waar de weergegeven HTML-bestanden worden opgeslagen.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u GroupDocs.Viewer voor .NET kunt gebruiken om lettertypen uit te sluiten van weergegeven HTML-uitvoer. Door de hierboven beschreven stappen te volgen, kunt u het weergaveproces aanpassen aan uw specifieke vereisten, zodat u verzekerd bent van een optimale weergave van documenten in uw toepassingen.
## Veelgestelde vragen
### Kan ik meerdere lettertypen uitsluiten van de weergegeven HTML?
 Ja, u kunt meerdere lettertypenamen toevoegen aan het`FontsToExclude` lijst in de HTML-weergaveopties.
### Is GroupDocs.Viewer compatibel met alle .NET-frameworks?
Ja, GroupDocs.Viewer ondersteunt .NET Framework 4.6.1 en hoger.
### Kan ik documenten weergeven vanaf externe opslaglocaties?
Ja, GroupDocs.Viewer ondersteunt het weergeven van documenten vanuit lokale opslag en externe opslaglocaties en streams.
### Ondersteunt GroupDocs.Viewer responsief ontwerp voor HTML-uitvoer?
Ja, u kunt responsieve weergave inschakelen door de HTML-weergaveopties dienovereenkomstig aan te passen.
### Is er technische ondersteuning beschikbaar voor GroupDocs.Viewer?
 Ja, u kunt hulp zoeken en deelnemen aan discussies over de[GroupDocs.Viewer-forum](https://forum.groupdocs.com/c/viewer/9).