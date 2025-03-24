---
title: Watermerk toevoegen aan document
linktitle: Watermerk toevoegen aan document
second_title: GroupDocs.Viewer .NET-API
description: Leer hoe u naadloos watermerken aan documenten kunt toevoegen met GroupDocs.Viewer voor .NET. Verbeter de documentbeveiliging en branding met deze eenvoudig te volgen tutorial.
weight: 10
url: /nl/net/rendering-options/add-watermark/
---

# Watermerk toevoegen aan document

## Invoering
In het huidige digitale tijdperk is het naadloos beheren en bekijken van verschillende documentformaten een noodzaak voor veel bedrijven en particulieren. Gelukkig wordt het verwerken van documenten met tools als GroupDocs.Viewer voor .NET een fluitje van een cent. Met deze krachtige .NET-bibliotheek kunnen ontwikkelaars moeiteloos de functionaliteit voor het bekijken van documenten in hun applicaties integreren, waardoor gebruikers documenten kunnen bekijken zonder dat ze de originele software nodig hebben waarmee ze zijn gemaakt.
## Vereisten
Voordat u GroupDocs.Viewer voor .NET gaat gebruiken om watermerken aan documenten toe te voegen, moet u ervoor zorgen dat u over het volgende beschikt:
1. Omgeving instellen: Zorg dat u een ontwikkelomgeving hebt opgezet waarop .NET Framework of .NET Core is geïnstalleerd.
2.  GroupDocs.Viewer voor .NET: Download en installeer de GroupDocs.Viewer voor .NET-bibliotheek vanuit de[downloadpagina](https://releases.groupdocs.com/viewer/net/).
3. Documentbestanden: Bereid de documentbestanden voor waarmee u wilt werken, zoals DOCX, PDF of andere.
4. Basiskennis van C#: Bekendheid met de programmeertaal C# is noodzakelijk om de codevoorbeelden te implementeren.

## Naamruimten importeren
Voordat u begint met het toevoegen van watermerken aan documenten met GroupDocs.Viewer voor .NET, moet u ervoor zorgen dat u de vereiste naamruimten in uw C#-code importeert. Met deze stap hebt u naadloos toegang tot de klassen en methoden die door de bibliotheek worden aangeboden.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Laten we nu het proces doorlopen van het toevoegen van een watermerk aan een document met behulp van GroupDocs.Viewer voor .NET. Volg deze stappen om de watermerkfunctionaliteit naadloos in uw toepassing te integreren.
## Stap 1: Stel de uitvoermap in
```csharp
string outputDirectory = "Your Document Directory";
```
Geef de map op waar u de uitvoerbestanden wilt opslaan nadat u het watermerk hebt toegepast.
## Stap 2: Definieer het paginabestandspadformaat
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Stel het formaat in voor de bestandspaden van de gerenderde pagina's. In dit voorbeeld worden HTML-bestanden met paginanummers gegenereerd.
## Stap 3: Instantie van Viewer-object
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // De code gaat verder in de volgende stap...
}
```
Maak een exemplaar van de klasse Viewer, waarbij u het pad naar het documentbestand als parameter doorgeeft. In dit voorbeeld gebruiken we een voorbeeld-DOCX-bestand.
## Stap 4: Configureer HTML-weergaveopties
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
Configureer de HTML-weergaveopties, inclusief de watermerktekst die u aan het document wilt toevoegen.
## Stap 5: Bekijk document met watermerk
```csharp
viewer.View(options);
```
Roep de View-methode van het Viewer-object aan en geef de geconfigureerde opties door. Hierdoor wordt het document weergegeven met het opgegeven watermerk.
## Stap 6: Geef het pad naar de uitvoermap weer
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Informeer de gebruiker over de succesvolle weergave van het document en geef de map aan waar de uitvoerbestanden zijn opgeslagen.

## Conclusie
GroupDocs.Viewer voor .NET biedt een handige manier om programmatisch watermerken aan documenten toe te voegen. Door de stappen in deze zelfstudie te volgen, kunt u de watermerkfunctionaliteit naadloos integreren in uw .NET-toepassingen, waardoor de documentbeveiliging en branding worden verbeterd.
## Veelgestelde vragen
### Kan ik het uiterlijk van het watermerk aanpassen?
Ja, u kunt verschillende eigenschappen van het watermerk aanpassen, zoals tekst, lettertype, kleur, grootte en positie.
### Ondersteunt GroupDocs.Viewer het bekijken van documenten van externe bronnen?
Ja, GroupDocs.Viewer ondersteunt het bekijken van documenten vanuit lokale opslag en externe URL's.
### Is er een proefversie beschikbaar voor GroupDocs.Viewer voor .NET?
Ja, u kunt een gratis proefversie downloaden van[hier](https://releases.groupdocs.com/).
### Kan ik watermerken toevoegen aan meerdere pagina's van een document?
Absoluut, met GroupDocs.Viewer kunt u watermerken toevoegen aan individuele pagina's of aan alle pagina's van een document.
### Hoe kan ik ondersteuning of hulp krijgen als ik problemen ondervind?
 U kunt hulp en ondersteuning zoeken op de GroupDocs-communityforums[hier](https://forum.groupdocs.com/c/viewer/9).