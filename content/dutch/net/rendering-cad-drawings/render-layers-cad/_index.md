---
title: Render lagen in CAD-tekeningen
linktitle: Render lagen in CAD-tekeningen
second_title: GroupDocs.Viewer .NET-API
description: Geef CAD-tekeningen naadloos weer in .NET-toepassingen met GroupDocs.Viewer voor .NET. Ontdek weergaveopties, pas lagen aan en meer.
type: docs
weight: 13
url: /nl/net/rendering-cad-drawings/render-layers-cad/
---
## Invoering
GroupDocs.Viewer voor .NET is een krachtig hulpmiddel waarmee ontwikkelaars de mogelijkheden voor documentweergave naadloos kunnen integreren in hun .NET-toepassingen. Of u nu CAD-tekeningen, PDF's, Microsoft Office-documenten of meer moet renderen, GroupDocs.Viewer biedt een uitgebreide oplossing.
## Vereisten
Voordat u GroupDocs.Viewer voor .NET gaat gebruiken, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Basiskennis van de programmeertaal C#.
- .NET-ontwikkelomgeving die op uw computer is ingesteld.
-  GroupDocs.Viewer voor .NET geïnstalleerd. Je kunt het downloaden van[hier](https://releases.groupdocs.com/viewer/net/).
-  Toegang tot de GroupDocs.Viewer voor .NET-documentatie ter referentie, die u kunt vinden[hier](https://reference.groupdocs.com/viewer/net/).

## Naamruimten importeren
Om GroupDocs.Viewer voor .NET te gaan gebruiken, moet u de vereiste naamruimten in uw project importeren. Volg deze stappen:

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Laten we het gegeven voorbeeld in meerdere stappen opsplitsen:
## Stap 1: Definieer de uitvoerdirectory
```csharp
string outputDirectory = "Your Document Directory";
```
## Stap 2: Definieer het paginabestandspadformaat
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Stap 3: Initialiseer het Viewer-object
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    // Codeblok gaat verder...
}
```
## Stap 4: Stel HTML-weergaveopties in
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Stap 5: CAD-lagen definiëren
```csharp
options.CadOptions.Layers = new List<Layer>
{
    new Layer("QUADRANT")
};
```
## Stap 6: Document renderen
```csharp
viewer.View(options);
```
## Stap 7: Uitvoer van gerenderde documentlocatie
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusie
Met GroupDocs.Viewer voor .NET wordt het renderen van CAD-tekeningen in uw .NET-applicaties een naadloos proces. Door de stappen in deze handleiding te volgen, kunt u eenvoudig documentweergavemogelijkheden in uw projecten integreren.
## Veelgestelde vragen
### Is GroupDocs.Viewer compatibel met alle soorten CAD-tekeningen?
Ja, GroupDocs.Viewer ondersteunt het weergeven van een breed scala aan CAD-tekeningformaten, waaronder DWG en DXF.
### Kan ik de weergaveopties voor CAD-tekeningen aanpassen?
Absoluut, GroupDocs.Viewer biedt verschillende aanpassingsopties, zoals het specificeren van lagen om te renderen of het instellen van uitvoerformaten.
### Heeft GroupDocs.Viewer een internetverbinding nodig voor het weergeven van documenten?
Nee, GroupDocs.Viewer voert de rendering lokaal uit zonder dat er een internetverbinding nodig is.
### Is er een gratis proefversie beschikbaar voor GroupDocs.Viewer voor .NET?
 Ja, u krijgt toegang tot een gratis proefversie van GroupDocs.Viewer voor .NET[hier](https://releases.groupdocs.com/).
### Waar kan ik ondersteuning krijgen voor GroupDocs.Viewer voor .NET?
 Voor technische hulp of vragen kunt u het GroupDocs.Viewer-forum bezoeken[hier](https://forum.groupdocs.com/c/viewer/9).