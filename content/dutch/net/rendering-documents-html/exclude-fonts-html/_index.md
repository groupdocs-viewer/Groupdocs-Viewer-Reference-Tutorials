---
"description": "Leer hoe u lettertypen uit gerenderde HTML kunt uitsluiten met GroupDocs.Viewer voor .NET. Volg deze stapsgewijze handleiding voor een naadloze weergave van uw documenten."
"linktitle": "Lettertypen uitsluiten van gerenderde HTML"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Lettertypen uitsluiten van gerenderde HTML"
"url": "/nl/net/rendering-documents-html/exclude-fonts-html/"
"weight": 10
type: docs
---
# Lettertypen uitsluiten van gerenderde HTML

## Invoering
GroupDocs.Viewer voor .NET is een krachtige bibliotheek voor documentweergave waarmee ontwikkelaars meer dan 50 documentformaten in hun .NET-applicaties kunnen weergeven zonder externe afhankelijkheden. In deze tutorial richten we ons op een specifieke functie van GroupDocs.Viewer: het uitsluiten van lettertypen in gerenderde HTML-uitvoer. 
## Vereisten
Voordat u begint, moet u ervoor zorgen dat u het volgende heeft:
1. Basiskennis van C#- en .NET-ontwikkeling.
2. GroupDocs.Viewer voor .NET geïnstalleerd. U kunt het downloaden van [hier](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio of een andere IDE voor C#-ontwikkeling.

## Naamruimten importeren
Zorg ervoor dat u de nodige naamruimten in uw C#-code opneemt:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Stap 1: Definieer de uitvoermap
Geef de map op waarin u de gerenderde HTML-bestanden wilt opslaan.
```csharp
string outputDirectory = "Your Document Directory";
```
## Stap 2: Definieer het padformaat van het paginabestand
Geef de indeling op voor de bestandspaden van de afzonderlijke pagina's van het gerenderde document.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Stap 3: Viewerobject initialiseren
Instantieer het Viewer-object met het document dat u wilt renderen.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // Hier komt uw code
}
```
## Stap 4: HTML-weergaveopties instellen
Definieer de opties voor HTML-rendering, inclusief de opmaak van ingesloten bronnen en uit te sluiten lettertypen.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## Stap 5: Document renderen
Geef de HTML-weergaveopties door aan het Viewer-object om het document te renderen.
```csharp
viewer.View(options);
```
## Stap 6: Uitvoer gerenderde documentlocatie
Informeer de gebruiker over de locatie waar de gerenderde HTML-bestanden worden opgeslagen.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusie
In deze tutorial hebben we geleerd hoe je GroupDocs.Viewer voor .NET kunt gebruiken om lettertypen uit te sluiten van gerenderde HTML-uitvoer. Door de bovenstaande stappen te volgen, kunt u het renderingproces aanpassen aan uw specifieke vereisten en zo een optimale weergave van documenten in uw applicaties garanderen.
## Veelgestelde vragen
### Kan ik meerdere lettertypen uitsluiten uit de weergegeven HTML?
Ja, u kunt meerdere lettertypenamen toevoegen aan de `FontsToExclude` lijst in de HTML-weergaveopties.
### Is GroupDocs.Viewer compatibel met alle .NET-frameworks?
Ja, GroupDocs.Viewer ondersteunt .NET Framework 4.6.1 en hoger.
### Kan ik documenten weergeven vanaf externe opslaglocaties?
Ja, GroupDocs.Viewer ondersteunt het renderen van documenten vanaf lokale opslaglocaties, maar ook vanaf externe opslaglocaties en streams.
### Ondersteunt GroupDocs.Viewer responsief ontwerp voor HTML-uitvoer?
Ja, u kunt responsieve rendering inschakelen door de HTML-weergaveopties dienovereenkomstig aan te passen.
### Is er technische ondersteuning beschikbaar voor GroupDocs.Viewer?
Ja, u kunt hulp zoeken en deelnemen aan discussies op de [GroupDocs.Viewer-forum](https://forum.groupdocs.com/c/viewer/9).