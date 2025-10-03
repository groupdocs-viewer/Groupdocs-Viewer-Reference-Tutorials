---
"description": "Leer hoe u een enkele lay-out in CAD-tekeningen kunt renderen met GroupDocs.Viewer voor .NET. Eenvoudige stappen voor naadloze integratie in uw .NET-applicaties."
"linktitle": "Enkele lay-out weergeven in CAD-tekeningen"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Enkele lay-out weergeven in CAD-tekeningen"
"url": "/nl/net/rendering-cad-drawings/render-single-layout-cad/"
"weight": 14
type: docs
---
# Enkele lay-out weergeven in CAD-tekeningen

## Invoering
In de wereld van .NET-ontwikkeling is het verwerken en bekijken van CAD-tekeningen een veelvoorkomende vereiste. GroupDocs.Viewer voor .NET vereenvoudigt deze taak door een uitgebreide oplossing te bieden voor het renderen van CAD-tekeningen binnen .NET-applicaties. In deze tutorial verdiepen we ons in het renderen van één lay-out in CAD-tekeningen met behulp van GroupDocs.Viewer voor .NET.
## Vereisten
Voordat u met de tutorial begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Basiskennis van de programmeertaal C# en het .NET Framework.
- Visual Studio op uw systeem geïnstalleerd.
- GroupDocs.Viewer voor .NET-bibliotheek gedownload en tutorials toegevoegd aan uw project. U kunt het downloaden van [hier](https://releases.groupdocs.com/viewer/net/).
- Kennis van CAD-bestandsindelingen en hun structuren.

## Naamruimten importeren
Importeer eerst de benodigde naamruimten in uw C#-code om toegang te krijgen tot de GroupDocs.Viewer-functionaliteiten.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Stap 1: Definieer de uitvoermap
Geef de map op waarin u de gerenderde uitvoer wilt opslaan.
```csharp
string outputDirectory = "Your Document Directory";
```
## Stap 2: Definieer het padformaat van het paginabestand
Definieer de indeling voor het bestandspad van elke gerenderde pagina.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Stap 3: Viewerobject instantiëren
Maak een exemplaar van de Viewer-klasse die wordt geleverd door GroupDocs.Viewer.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## Stap 4: HTML-weergaveopties configureren
Configureer opties voor het renderen van HTML-uitvoer met ingesloten bronnen.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Stap 5: Geef de CAD-layoutnaam op
Geef de naam op van de CAD-layout die u wilt renderen.
```csharp
options.CadOptions.LayoutName = "Model";
```
## Stap 6: CAD-tekening renderen
Roep de View-methode van het Viewer-object aan met de opgegeven opties.
```csharp
viewer.View(options);
```
## Stap 7: Succesbericht weergeven
Informeer de gebruiker over het succesvol renderen van het brondocument.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusie
Het renderen van CAD-tekeningen, vooral bij lay-outs, kan een lastige klus zijn. Met GroupDocs.Viewer voor .NET verloopt dit proces echter soepel en efficiënt. Door de stappen in deze tutorial te volgen, kunt u moeiteloos één lay-out renderen in CAD-tekeningen binnen uw .NET-applicaties.
## Veelgestelde vragen
### Kan ik meerdere lay-outs tegelijkertijd renderen met GroupDocs.Viewer voor .NET?
Ja, GroupDocs.Viewer voor .NET ondersteunt het renderen van meerdere lay-outs vanuit CAD-tekeningen.
### Is GroupDocs.Viewer compatibel met verschillende CAD-bestandsformaten?
Jazeker, GroupDocs.Viewer ondersteunt een breed scala aan CAD-bestandsindelingen, waaronder DWG, DXF, DGN en meer.
### Kan ik de renderopties voor CAD-tekeningen aanpassen?
Ja, GroupDocs.Viewer biedt uitgebreide opties om de weergave-instellingen aan te passen aan uw wensen.
### Is er een gratis proefversie beschikbaar voor GroupDocs.Viewer voor .NET?
Ja, u kunt de functies van GroupDocs.Viewer verkennen met een gratis proefversie die beschikbaar is [hier](https://releases.groupdocs.com/).
### Waar kan ik ondersteuning krijgen voor GroupDocs.Viewer voor .NET?
Voor vragen of hulp kunt u terecht op het GroupDocs.Viewer-forum [hier](https://forum.groupdocs.com/c/viewer/9).