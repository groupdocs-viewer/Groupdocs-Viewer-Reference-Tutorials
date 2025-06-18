---
"description": "Leer hoe u naadloos watermerken aan documenten kunt toevoegen met GroupDocs.Viewer voor .NET. Verbeter de beveiliging en branding van uw documenten met deze eenvoudig te volgen tutorial."
"linktitle": "Watermerk toevoegen in document"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Watermerk toevoegen in document"
"url": "/nl/net/rendering-options/add-watermark/"
"weight": 10
---

# Watermerk toevoegen in document

## Invoering
In het huidige digitale tijdperk is het naadloos beheren en bekijken van verschillende documentformaten een noodzaak voor veel bedrijven en particulieren. Gelukkig wordt het werken met documenten een fluitje van een cent met tools zoals GroupDocs.Viewer voor .NET. Deze krachtige .NET-bibliotheek stelt ontwikkelaars in staat om moeiteloos functionaliteit voor het bekijken van documenten te integreren in hun applicaties, waardoor gebruikers documenten kunnen bekijken zonder de originele software waarmee ze zijn gemaakt.
## Vereisten
Voordat u GroupDocs.Viewer voor .NET gaat gebruiken om watermerken aan documenten toe te voegen, moet u het volgende doen:
1. Omgeving instellen: Zorg dat er een ontwikkelomgeving is ingesteld met .NET Framework of .NET Core geïnstalleerd.
2. GroupDocs.Viewer voor .NET: Download en installeer GroupDocs.Viewer voor .NET-bibliotheek vanuit de [downloadpagina](https://releases.groupdocs.com/viewer/net/).
3. Documentbestanden: bereid de documentbestanden voor waarmee u wilt werken, zoals DOCX, PDF en andere.
4. Basiskennis van C#: Kennis van de programmeertaal C# is noodzakelijk om de codevoorbeelden te implementeren.

## Naamruimten importeren
Voordat u begint met het toevoegen van watermerken aan documenten met GroupDocs.Viewer voor .NET, moet u ervoor zorgen dat u de vereiste naamruimten in uw C#-code importeert. Deze stap geeft u naadloos toegang tot de klassen en methoden die door de bibliotheek worden aangeboden.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Laten we nu het proces doorlopen van het toevoegen van een watermerk aan een document met GroupDocs.Viewer voor .NET. Volg deze stappen om watermerkfunctionaliteit naadloos in uw applicatie te integreren.
## Stap 1: Uitvoermap instellen
```csharp
string outputDirectory = "Your Document Directory";
```
Geef de map op waarin u de uitvoerbestanden wilt opslaan nadat u het watermerk hebt toegepast.
## Stap 2: Definieer het padformaat van het paginabestand
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Stel de indeling in voor de bestandspaden van de gerenderde pagina's. In dit voorbeeld worden HTML-bestanden met paginanummers gegenereerd.
## Stap 3: Viewerobject instantiëren
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // De code gaat verder in de volgende stap...
}
```
Maak een instantie van de Viewer-klasse en geef het pad naar het documentbestand als parameter door. In dit voorbeeld gebruiken we een voorbeeld van een DOCX-bestand.
## Stap 4: HTML-weergaveopties configureren
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
Configureer de HTML-weergaveopties, inclusief de watermerktekst die u aan het document wilt toevoegen.
## Stap 5: Bekijk document met watermerk
```csharp
viewer.View(options);
```
Roep de View-methode van het Viewer-object aan en geef de geconfigureerde opties door. Dit zal het document met het opgegeven watermerk weergeven.
## Stap 6: Weergave van het pad van de uitvoermap
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Informeer de gebruiker over het succesvol renderen van het document en geef de map aan waar de uitvoerbestanden worden opgeslagen.

## Conclusie
GroupDocs.Viewer voor .NET biedt een handige manier om watermerken programmatisch aan documenten toe te voegen. Door de stappen in deze tutorial te volgen, kunt u watermerkfunctionaliteit naadloos integreren in uw .NET-applicaties, waardoor de beveiliging en branding van uw documenten worden verbeterd.
## Veelgestelde vragen
### Kan ik het uiterlijk van het watermerk aanpassen?
Ja, u kunt verschillende eigenschappen van het watermerk aanpassen, zoals tekst, lettertype, kleur, grootte en positie.
### Ondersteunt GroupDocs.Viewer het bekijken van documenten van externe bronnen?
Ja, GroupDocs.Viewer ondersteunt het bekijken van documenten vanaf lokale opslag en externe URL's.
### Is er een proefversie beschikbaar voor GroupDocs.Viewer voor .NET?
Ja, u kunt een gratis proefversie downloaden van [hier](https://releases.groupdocs.com/).
### Kan ik watermerken aan meerdere pagina's van een document toevoegen?
Jazeker, met GroupDocs.Viewer kunt u watermerken toevoegen aan afzonderlijke pagina's of aan alle pagina's van een document.
### Hoe kan ik ondersteuning of hulp krijgen als ik problemen ondervind?
kunt hulp en ondersteuning zoeken in de communityforums van GroupDocs [hier](https://forum.groupdocs.com/c/viewer/9).