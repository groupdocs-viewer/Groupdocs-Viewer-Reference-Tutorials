---
title: Geef een enkele lay-out weer in CAD-tekeningen
linktitle: Geef een enkele lay-out weer in CAD-tekeningen
second_title: GroupDocs.Viewer .NET-API
description: Leer hoe u een enkele lay-out in CAD-tekeningen kunt weergeven met GroupDocs.Viewer voor .NET. Eenvoudige stappen voor naadloze integratie in uw .NET-applicaties.
type: docs
weight: 14
url: /nl/net/rendering-cad-drawings/render-single-layout-cad/
---
## Invoering
Op het gebied van .NET-ontwikkeling is het hanteren en bekijken van CAD-tekeningen een veel voorkomende vereiste. GroupDocs.Viewer voor .NET vereenvoudigt deze taak door een uitgebreide oplossing te bieden voor het weergeven van CAD-tekeningen binnen .NET-toepassingen. In deze zelfstudie gaan we dieper in op het renderen van een enkele lay-out in CAD-tekeningen met behulp van GroupDocs.Viewer voor .NET.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Basiskennis van de programmeertaal C# en het .NET-framework.
- Visual Studio is op uw systeem geïnstalleerd.
-  GroupDocs.Viewer voor .NET-bibliotheek gedownload en waarnaar wordt verwezen in uw project. Je kunt het downloaden van[hier](https://releases.groupdocs.com/viewer/net/).
- Bekendheid met CAD-bestandsformaten en hun structuren.

## Naamruimten importeren
Importeer eerst de benodigde naamruimten in uw C#-code om toegang te krijgen tot de functionaliteiten van GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Stap 1: Definieer de uitvoerdirectory
Geef de map op waar u de gerenderde uitvoer wilt opslaan.
```csharp
string outputDirectory = "Your Document Directory";
```
## Stap 2: Definieer het paginabestandspadformaat
Definieer het formaat voor het bestandspad van elke gerenderde pagina.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Stap 3: Instantie van Viewer-object
Maak een exemplaar van de klasse Viewer die wordt geleverd door GroupDocs.Viewer.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## Stap 4: Configureer HTML-weergaveopties
Configureer opties voor het weergeven van HTML-uitvoer met ingesloten bronnen.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Stap 5: Geef de CAD-lay-outnaam op
Geef de naam op van de CAD-lay-out die u wilt renderen.
```csharp
options.CadOptions.LayoutName = "Model";
```
## Stap 6: Render CAD-tekening
Roep de View-methode van het Viewer-object aan met de opgegeven opties.
```csharp
viewer.View(options);
```
## Stap 7: Succesbericht weergeven
Informeer de gebruiker over de succesvolle weergave van het brondocument.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusie
Het renderen van CAD-tekeningen, vooral als het om lay-outs gaat, kan een hele klus zijn. Met GroupDocs.Viewer voor .NET wordt het proces echter naadloos en efficiënt. Door de stappen in deze tutorial te volgen, kunt u moeiteloos één lay-out in CAD-tekeningen renderen binnen uw .NET-applicaties.
## Veelgestelde vragen
### Kan ik meerdere lay-outs tegelijkertijd weergeven met GroupDocs.Viewer voor .NET?
Ja, GroupDocs.Viewer voor .NET ondersteunt het weergeven van meerdere lay-outs op basis van CAD-tekeningen.
### Is GroupDocs.Viewer compatibel met verschillende CAD-bestandsformaten?
Absoluut, GroupDocs.Viewer ondersteunt een breed scala aan CAD-bestandsindelingen, waaronder DWG, DXF, DGN en meer.
### Kan ik de weergaveopties voor CAD-tekeningen aanpassen?
Ja, GroupDocs.Viewer biedt uitgebreide opties om de weergave-instellingen aan uw wensen aan te passen.
### Is er een gratis proefversie beschikbaar voor GroupDocs.Viewer voor .NET?
 Ja, u kunt de functies van GroupDocs.Viewer verkennen met een gratis proefversie[hier](https://releases.groupdocs.com/).
### Waar kan ik ondersteuning krijgen voor GroupDocs.Viewer voor .NET?
 Voor vragen of hulp kunt u het GroupDocs.Viewer-forum bezoeken[hier](https://forum.groupdocs.com/c/viewer/9).