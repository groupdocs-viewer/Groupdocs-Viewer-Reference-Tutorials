---
"description": "Leer hoe u tekstselectie in PDF kunt uitschakelen met GroupDocs.Viewer voor .NET. Volg onze stapsgewijze handleiding voor naadloze integratie."
"linktitle": "Tekstselectie in PDF uitschakelen"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Tekstselectie in PDF uitschakelen"
"url": "/nl/net/pdf-rendering-options/disable-text-selection-pdf/"
"weight": 13
type: docs
---
# Tekstselectie in PDF uitschakelen

## Invoering
GroupDocs.Viewer voor .NET is een krachtige API voor documentweergave waarmee ontwikkelaars moeiteloos documentweergavemogelijkheden in hun .NET-applicaties kunnen integreren. Een van de belangrijkste functies van GroupDocs.Viewer is de mogelijkheid om tekstselectie in PDF-documenten uit te schakelen. Deze functie is met name handig in scenario's waarin u wilt voorkomen dat gebruikers tekst uit vertrouwelijke documenten kopiëren, om zo de veiligheid en integriteit van documenten te waarborgen.

![Tekstselectie in PDF uitschakelen met GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/disable-text-selection-in-pdf.png)

## Vereisten
Voordat we ingaan op de stapsgewijze handleiding voor het uitschakelen van tekstselectie in PDF met behulp van GroupDocs.Viewer voor .NET, moet u ervoor zorgen dat aan de volgende vereisten is voldaan:
1. Installatie van GroupDocs.Viewer voor .NET: Zorg ervoor dat u GroupDocs.Viewer voor .NET hebt gedownload en geïnstalleerd vanaf de [downloadlink](https://releases.groupdocs.com/viewer/net/).
2. Documentmap: Bereid een map voor waar uw documenten worden opgeslagen. U moet deze map opgeven in het codefragment om het PDF-document te renderen.

## Naamruimten importeren
Eerst moet u de benodigde naamruimten importeren om toegang te krijgen tot de functionaliteiten van GroupDocs.Viewer voor .NET. Zo doet u dat:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Laten we het proces voor het uitschakelen van tekstselectie in een PDF-document met behulp van GroupDocs.Viewer voor .NET opsplitsen in meerdere stappen:
## Stap 1: Geef de uitvoermap op
```csharp
string outputDirectory = "Your Document Directory";
```
Vervang in deze stap `"Your Document Directory"` met het pad naar de map waar uw PDF-document zich bevindt.
## Stap 2: Definieer het padformaat van het paginabestand
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Deze stap definieert de opmaak voor de bestandspaden van de gerenderde HTML-pagina's. Elke pagina van het PDF-document wordt geconverteerd naar een HTML-bestand met een opeenvolgend paginanummer.
## Stap 3: PDF-document renderen met tekstselectie uitgeschakeld
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
Vervangen `"Path to Your PDF Document"` met het daadwerkelijke pad naar uw PDF-bestand. Dit codefragment initialiseert een `Viewer` object, configureert HTML-weergaveopties om bronnen in te sluiten en schakelt tekstselectie uit door in te stellen `RenderTextAsImage` eigendom van `true`.
## Stap 4: Succesbericht weergeven
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Nadat het PDF-document is weergegeven, wordt in deze stap een succesbericht weergegeven, samen met de map waarin de weergegeven HTML-pagina's zijn opgeslagen.

## Conclusie
In deze tutorial hebben we geleerd hoe je tekstselectie in PDF-documenten kunt uitschakelen met GroupDocs.Viewer voor .NET. Door de stapsgewijze handleiding te volgen, kun je deze functie naadloos integreren in je .NET-applicaties, waardoor de documentbeveiliging wordt gewaarborgd en de gebruikerservaring wordt verbeterd.
## Veelgestelde vragen
### Kan ik de uitvoermap voor gerenderde HTML-pagina's aanpassen?
Ja, u kunt elk gewenst pad opgeven waar u de gerenderde HTML-pagina's wilt opslaan.
### Is GroupDocs.Viewer voor .NET compatibel met verschillende versies van het .NET Framework?
Ja, GroupDocs.Viewer voor .NET is compatibel met verschillende versies van het .NET Framework, waaronder .NET Core en .NET Framework.
### Heeft het uitschakelen van tekstselectie invloed op andere functionaliteiten van het PDF-document?
Nee, het uitschakelen van tekstselectie voorkomt alleen dat gebruikers tekst uit het document kunnen selecteren en kopiëren. Andere functionaliteiten blijven intact.
### Kan ik tekstselectie weer inschakelen nadat het document is weergegeven?
Ja, u kunt tekstselectie inschakelen door eenvoudigweg de `RenderTextAsImage` eigendom van `false` in de HTML-weergaveopties.
### Is er een proefversie beschikbaar voor GroupDocs.Viewer voor .NET?
Ja, u kunt een gratis proefversie van GroupDocs.Viewer voor .NET openen via de [website](https://releases.groupdocs.com/).