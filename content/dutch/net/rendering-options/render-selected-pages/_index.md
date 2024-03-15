---
title: Geef geselecteerde pagina's weer
linktitle: Geef geselecteerde pagina's weer
second_title: GroupDocs.Viewer .NET-API
description: Leer hoe u geselecteerde pagina's uit documenten kunt weergeven met Groupdocs.Viewer voor .NET. Stapsgewijze zelfstudie met codevoorbeelden inbegrepen.
type: docs
weight: 17
url: /nl/net/rendering-options/render-selected-pages/
---
## Invoering

In deze zelfstudie gaan we dieper in op het gebruik van Groupdocs.Viewer voor .NET om geselecteerde pagina's uit een document weer te geven. Of u nu een doorgewinterde ontwikkelaar bent of net begint, deze stapsgewijze handleiding leidt u gemakkelijk door het proces.

## Vereisten

Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:

### 1. Installatie

 Zorg ervoor dat Groupdocs.Viewer voor .NET in uw ontwikkelomgeving is geïnstalleerd. Als dit niet het geval is, kunt u deze downloaden van de[Download link](https://releases.groupdocs.com/viewer/net/).

## Naamruimten importeren

Importeer in uw C#-codebestand de benodigde naamruimten om toegang te krijgen tot de vereiste klassen en methoden. Dit kunt u doen met behulp van de`using` richtlijn:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Laten we nu de voorbeeldcode in meerdere stappen opsplitsen:

## Stap 1: Stel de uitvoermap in

 Definieer de map waar u de gerenderde pagina's wilt opslaan. Vervangen`"Your Document Directory"` met het gewenste mappad.

```csharp
string outputDirectory = "Your Document Directory";
```

## Stap 2: Definieer het paginabestandspadformaat

Geef het formaat op voor de bestandspaden van de gerenderde pagina's. Dit wordt gebruikt om elke pagina op te slaan als een HTML-bestand in de uitvoermap.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Stap 3: Instantie van Viewer-object

Maak een exemplaar van de klasse Viewer, waarbij u het pad van het document dat u wilt weergeven als argument doorgeeft.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## Stap 4: Configureer HTML-weergaveopties

Stel de HTML-weergaveopties voor weergave in. In dit voorbeeld configureren we opties om bronnen in de HTML-uitvoer in te sluiten.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## Stap 5: Render geselecteerde pagina's

Geef de paginanummers op die u wilt weergeven. In dit geval renderen we pagina's 1 tot en met 3. Roep vervolgens de View-methode aan op het Viewer-object en geef de opties en paginanummers door als argumenten.

```csharp
viewer.View(options, 1, 3);
```

## Stap 6: Uitvoerresultaat

Geef ten slotte een bericht weer dat de succesvolle weergave van het document aangeeft en de locatie waar de uitvoerbestanden zijn opgeslagen.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusie

Gefeliciteerd! U hebt met succes geleerd hoe u geselecteerde pagina's uit een document kunt weergeven met Groupdocs.Viewer voor .NET. Met deze kennis kunt u nu eenvoudig documentweergavemogelijkheden in uw .NET-applicaties integreren.

## Veelgestelde vragen

### Vraag: Kan ik pagina's uit verschillende soorten documenten weergeven, zoals PDF's of afbeeldingen?

A: Ja, Groupdocs.Viewer voor .NET ondersteunt het renderen van pagina's uit verschillende documentformaten, waaronder PDF's, Microsoft Office-documenten en afbeeldingsbestanden.

### Vraag: Is er een proefversie beschikbaar om te testen voordat u deze aanschaft?

 A: Ja, u kunt toegang krijgen tot een gratis proefversie van Groupdocs.Viewer voor .NET via de[website](https://releases.groupdocs.com/).

### Vraag: Kan ik het uitvoerformaat anders dan HTML aanpassen?

A: Absoluut, Groupdocs.Viewer voor .NET biedt opties om pagina's weer te geven als afbeeldingen, PDF's en meer, naast HTML.

### Vraag: Hoe kan ik tijdelijke licenties verkrijgen voor testdoeleinden?

A: Tijdelijke licenties kunnen worden verkregen bij de[tijdelijke licentiepagina](https://purchase.groupdocs.com/temporary-license/) op de Groupdocs-website.

### Vraag: Waar kan ik hulp zoeken of hulp krijgen bij eventuele problemen die ik tegenkom?

 A: U kunt een bezoek brengen aan de[Groupdocs.Viewer-forum](https://forum.groupdocs.com/c/viewer/9) voor ondersteuning en begeleiding van de community en ontwikkelaars.