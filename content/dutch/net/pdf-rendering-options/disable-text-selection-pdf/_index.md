---
title: Schakel tekstselectie in PDF uit
linktitle: Schakel tekstselectie in PDF uit
second_title: GroupDocs.Viewer .NET-API
description: Leer hoe u tekstselectie in PDF kunt uitschakelen met GroupDocs.Viewer voor .NET. Volg onze stapsgewijze handleiding voor een naadloze integratie.
weight: 13
url: /nl/net/pdf-rendering-options/disable-text-selection-pdf/
---
## Invoering
GroupDocs.Viewer voor .NET is een krachtige documentweergave-API waarmee ontwikkelaars de weergavemogelijkheden van documenten moeiteloos in hun .NET-applicaties kunnen integreren. Een van de belangrijkste functionaliteiten van GroupDocs.Viewer is de mogelijkheid om tekstselectie in PDF-documenten uit te schakelen. Deze functie is met name handig in scenario's waarin u moet voorkomen dat gebruikers tekst uit gevoelige documenten kopiëren, zodat de veiligheid en integriteit van documenten wordt gewaarborgd.
## Vereisten
Voordat we ingaan op de stapsgewijze handleiding over het uitschakelen van tekstselectie in PDF met GroupDocs.Viewer voor .NET, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1.  Installatie van GroupDocs.Viewer voor .NET: Zorg ervoor dat u GroupDocs.Viewer voor .NET hebt gedownload en geïnstalleerd vanaf de[download link](https://releases.groupdocs.com/viewer/net/).
2. Documentmap: bereid een map voor waarin uw documenten worden opgeslagen. U moet deze map opgeven in het codefragment om het PDF-document weer te geven.

## Naamruimten importeren
Eerst moet u de benodigde naamruimten importeren om toegang te krijgen tot de functionaliteiten van GroupDocs.Viewer voor .NET. Hier ziet u hoe u het kunt doen:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Laten we nu het proces van het uitschakelen van tekstselectie in een PDF-document met GroupDocs.Viewer voor .NET in meerdere stappen opsplitsen:
## Stap 1: Geef de uitvoermap op
```csharp
string outputDirectory = "Your Document Directory";
```
 In deze stap vervangt u`"Your Document Directory"` met het directorypad waar uw PDF-document zich bevindt.
## Stap 2: Definieer het paginabestandspadformaat
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Deze stap definieert het formaat voor de bestandspaden van de weergegeven HTML-pagina's. Elke pagina van het PDF-document wordt geconverteerd naar een HTML-bestand met een doorlopend paginanummer.
## Stap 3: Render PDF-document met tekstselectie uitgeschakeld
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
 Vervangen`"Path to Your PDF Document"` met het daadwerkelijke pad naar uw PDF-bestand. Dit codefragment initialiseert een`Viewer` object, configureert HTML-weergaveopties om bronnen in te sluiten en schakelt tekstselectie uit door in te stellen`RenderTextAsImage` eigendom aan`true`.
## Stap 4: Succesbericht weergeven
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Na het renderen van het PDF-document geeft deze stap een succesbericht weer samen met de map waar de gerenderde HTML-pagina's zijn opgeslagen.

## Conclusie
In deze zelfstudie hebben we geleerd hoe u tekstselectie in PDF-documenten kunt uitschakelen met GroupDocs.Viewer voor .NET. Door de stapsgewijze handleiding te volgen, kunt u deze functie naadloos integreren in uw .NET-toepassingen, waardoor de documentbeveiliging wordt gegarandeerd en de gebruikerservaring wordt verbeterd.
## Veelgestelde vragen
### Kan ik de uitvoermap voor weergegeven HTML-pagina's aanpassen?
Ja, u kunt elk mappad opgeven waar u de weergegeven HTML-pagina's wilt opslaan.
### Is GroupDocs.Viewer voor .NET compatibel met verschillende versies van het .NET-framework?
Ja, GroupDocs.Viewer voor .NET is compatibel met verschillende versies van het .NET-framework, waaronder .NET Core en .NET Framework.
### Heeft het uitschakelen van tekstselectie invloed op andere functionaliteiten van het PDF-document?
Nee, het uitschakelen van tekstselectie voorkomt alleen dat gebruikers tekst uit het document selecteren en kopiëren. Overige functionaliteiten blijven intact.
### Kan ik tekstselectie opnieuw inschakelen nadat het document is weergegeven?
 Ja, u kunt tekstselectie inschakelen door simpelweg de`RenderTextAsImage` eigendom aan`false` in de HTML-weergaveopties.
### Is er een proefversie beschikbaar voor GroupDocs.Viewer voor .NET?
 Ja, u kunt toegang krijgen tot een gratis proefversie van GroupDocs.Viewer voor .NET via de[website](https://releases.groupdocs.com/).