---
title: Geef Visio-figuren weer
linktitle: Geef Visio-figuren weer
second_title: GroupDocs.Viewer .NET-API
description: Leer hoe u Visio-cijfers kunt weergeven met GroupDocs.Viewer voor .NET met deze uitgebreide versie. Verbeter de mogelijkheden voor documentweergave in uw .NET-toepassingen.
type: docs
weight: 10
url: /nl/net/rendering-visio-documents/render-visio-figures/
---
## Invoering
In het huidige digitale tijdperk speelt documentweergave een cruciale rol in verschillende toepassingen. Of het nu gaat om het weergeven van documenten op een website of het converteren ervan naar verschillende formaten, efficiënte weergave is essentieel. GroupDocs.Viewer voor .NET biedt een robuuste oplossing voor het bekijken en manipuleren van documenten binnen .NET-toepassingen. In deze zelfstudie gaan we dieper in op het renderen van Visio-figuren met GroupDocs.Viewer voor .NET, waarbij we het proces in eenvoudige stappen opsplitsen.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. Omgevingsinstellingen: Zorg ervoor dat u een werkomgeving hebt voor .NET-ontwikkeling.
2.  GroupDocs.Viewer voor .NET: Download en installeer GroupDocs.Viewer voor .NET vanaf de[download link](https://releases.groupdocs.com/viewer/net/).
3. Basiskennis van C#: maak uzelf vertrouwd met de grondbeginselen van de programmeertaal C#.
4. Voorbeeld van een Visio-document: Zorg ervoor dat u een voorbeeld van een Visio-document gereed heeft voor weergave.

## Naamruimten importeren
Begin in uw C#-project met het importeren van de benodigde naamruimten:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. Renderen naar HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "result_page.html");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Uitvoermap: definieer de map waar de weergegeven HTML wordt opgeslagen.
- Paginabestandspadformaat: Geef het padformaat voor de HTML-pagina op.
- Viewer-initialisatie: Initialiseer het Viewer-object met het pad naar het Visio-document.
- HTML-weergaveopties: Configureer opties voor het weergeven van HTML.
- Visio-renderingopties: stel opties in die specifiek zijn voor Visio-rendering, zoals alleen het renderen van figuren en de figuurbreedte.
## 2. Renderen naar JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.jpg");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Configureer, net als bij het renderen naar HTML, opties voor het renderen naar JPG-formaat.
## 3. Renderen naar PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.png");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- De configuratie voor weergave naar PNG-indeling volgt een soortgelijk patroon als JPG-weergave.
## 4. Renderen naar PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.pdf");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Voor weergave naar PDF configureert u opties die specifiek zijn voor de PDF-indeling.

## Conclusie
In deze zelfstudie hebben we onderzocht hoe u Visio-figuren kunt weergeven met GroupDocs.Viewer voor .NET. Door de stapsgewijze handleiding te volgen, kunt u de mogelijkheden voor documentweergave naadloos integreren in uw .NET-toepassingen, waardoor de gebruikerservaring en productiviteit worden verbeterd.
## Veelgestelde vragen
### Kan ik de weergaveopties voor Visio-figuren aanpassen?
Ja, GroupDocs.Viewer voor .NET biedt uitgebreide opties voor het aanpassen van de weergave, inclusief figuurbreedte, weergave van alleen cijfers en meer.
### Is GroupDocs.Viewer voor .NET geschikt voor grootschalige documentweergave?
Absoluut, GroupDocs.Viewer voor .NET is geoptimaliseerd voor het efficiënt verwerken van grootschalige documentweergave.
### Ondersteunt GroupDocs.Viewer andere documentformaten dan Visio?
Ja, GroupDocs.Viewer ondersteunt een breed scala aan documentformaten, waaronder PDF, Microsoft Office, AutoCAD en meer.
### Kan ik GroupDocs.Viewer integreren in webapplicaties?
Ja, GroupDocs.Viewer kan naadloos worden geïntegreerd in webapplicaties voor het bekijken en manipuleren van documenten.
### Is er een proefversie beschikbaar om te testen voordat u deze aanschaft?
Ja, u kunt gebruikmaken van een gratis proefperiode van de[website](https://releases.groupdocs.com/) om de mogelijkheden van GroupDocs.Viewer voor .NET te testen.