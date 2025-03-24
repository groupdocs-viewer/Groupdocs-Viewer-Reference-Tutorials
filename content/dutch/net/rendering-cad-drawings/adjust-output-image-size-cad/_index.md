---
title: Pas de uitvoerafbeeldingsgrootte aan voor CAD-tekeningen
linktitle: Pas de uitvoerafbeeldingsgrootte aan voor CAD-tekeningen
second_title: GroupDocs.Viewer .NET-API
description: Leer hoe u de uitvoerafbeeldingsgrootte voor CAD-tekeningen kunt aanpassen met GroupDocs.Viewer voor .NET. Verbeter moeiteloos de zichtbaarheid en bruikbaarheid.
weight: 15
url: /nl/net/rendering-cad-drawings/adjust-output-image-size-cad/
---

# Pas de uitvoerafbeeldingsgrootte aan voor CAD-tekeningen

## Invoering
CAD-tekeningen vereisen vaak specifieke aanpassingen voor een optimale weergave en presentatie. GroupDocs.Viewer voor .NET biedt een krachtige toolset voor het beheren en aanpassen van de uitvoer van CAD-tekeningen. In deze zelfstudie begeleiden we u stap voor stap bij het aanpassen van de uitvoerafbeeldingsgrootte voor CAD-tekeningen.
## Vereisten
Voordat u begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1.  GroupDocs.Viewer voor .NET: Download en installeer GroupDocs.Viewer voor .NET van[hier](https://releases.groupdocs.com/viewer/net/).
2. Documentmap: bereid de map voor waarin uw document zich bevindt.
3. Basiskennis: maak uzelf vertrouwd met de basisconcepten van .NET-programmering.

## Naamruimten importeren
Zorg er eerst voor dat u de benodigde naamruimten importeert om toegang te krijgen tot de functionaliteiten van GroupDocs.Viewer:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Stap 1: Stel de uitvoermap in
Definieer de map waarin u de uitvoerafbeeldingen van CAD-tekeningen wilt opslaan:
```csharp
string outputDirectory = "Your Document Directory";
```
## Stap 2: Definieer het paginabestandspadformaat
Stel de indeling voor paginabestandspaden in. Dit formaat wordt gebruikt om individuele pagina's een naam te geven en op te slaan als HTML-bestanden:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Stap 3: Pas de afbeeldingsgrootte aan
Pas binnen een gebruiksblok voor het Viewer-object de afbeeldingsgrootte voor CAD-tekeningen aan door de juiste opties in te stellen:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## Stap 4: Geef de uitvoerdirectory weer
Nadat het document is weergegeven, geeft u een bericht weer dat de succesvolle weergave aangeeft en geeft u de locatie van de uitvoermap op:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusie
Het aanpassen van de uitvoerafbeeldingsgrootte voor CAD-tekeningen is cruciaal voor het verbeteren van de zichtbaarheid en bruikbaarheid ervan. Met GroupDocs.Viewer voor .NET wordt dit proces gestroomlijnd en efficiënt, waardoor u de uitvoer kunt aanpassen aan uw specifieke vereisten.
## Veelgestelde vragen
### Kan ik de uitvoerafbeeldingsgrootte aanpassen voor andere soorten documenten dan CAD-tekeningen?
Ja, GroupDocs.Viewer voor .NET ondersteunt verschillende documenttypen en u kunt de uitvoerafbeeldingsgrootte aanpassen voor de meeste documentindelingen.
### Is GroupDocs.Viewer voor .NET compatibel met verschillende versies van het .NET-framework?
Ja, GroupDocs.Viewer voor .NET is compatibel met meerdere versies van het .NET-framework, waardoor flexibiliteit en bruikbaarheid in verschillende omgevingen wordt gegarandeerd.
### Zijn er licentieopties beschikbaar voor GroupDocs.Viewer voor .NET?
Ja, u kunt verschillende licentieopties verkennen, waaronder tijdelijke licenties en commerciële licenties, om aan uw behoeften te voldoen.
### Kan ik het uitvoerformaat van weergegeven documenten aanpassen?
Absoluut, GroupDocs.Viewer voor .NET biedt verschillende aanpassingsopties, waardoor u het uitvoerformaat kunt aanpassen aan uw voorkeuren.
### Waar kan ik aanvullende ondersteuning of assistentie vinden met GroupDocs.Viewer voor .NET?
 U kunt het GroupDocs.Viewer-forum bezoeken[hier](https://forum.groupdocs.com/c/viewer/9) om ondersteuning te krijgen, vragen te stellen en deel te nemen aan de gemeenschap.