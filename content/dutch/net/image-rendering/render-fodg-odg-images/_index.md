---
title: Geef FODG- en ODG-afbeeldingen weer
linktitle: Geef FODG- en ODG-afbeeldingen weer
second_title: GroupDocs.Viewer .NET-API
description: Leer hoe u FODG- en ODG-afbeeldingen kunt renderen naar HTML, JPG, PNG en PDF met GroupDocs.Viewer voor .NET. Verbeter uw documentverwerking.
weight: 15
url: /nl/net/image-rendering/render-fodg-odg-images/
---
## Invoering
In de wereld van softwareontwikkeling staat een efficiënte omgang met documentformaten voorop. GroupDocs.Viewer voor .NET is een krachtig hulpmiddel dat is ontworpen om het proces van het weergeven van FODG- en ODG-afbeeldingen binnen .NET-toepassingen te vereenvoudigen. In deze zelfstudie wordt u door de stappen geleid die nodig zijn om deze afbeeldingen in verschillende formaten weer te geven, zoals HTML, JPG, PNG en PDF, met behulp van GroupDocs.Viewer voor .NET.
## Vereisten
Voordat u in de zelfstudie duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1.  GroupDocs.Viewer voor .NET: Download en installeer GroupDocs.Viewer voor .NET van[hier](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Zorg ervoor dat .NET Framework op uw systeem is geïnstalleerd.
3. Basiskennis van C#: Bekendheid met de programmeertaal C# is nuttig.

## Naamruimten importeren
Voordat u met de implementatie begint, importeert u de benodigde naamruimten:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Stap 1: Stel de uitvoermap in
```csharp
string outputDirectory = "Your Document Directory";
```
 Vervangen`"Your Document Directory"`met het mappad waar u de gerenderde afbeeldingen wilt opslaan.
## Stap 2: Renderen naar HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
Deze stap rendert de FODG-afbeelding naar HTML-formaat.
## Stap 3: Renderen naar JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Hier wordt de FODG-afbeelding weergegeven in JPG-formaat.
## Stap 4: Renderen naar PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Met deze stap wordt de FODG-afbeelding geconverteerd naar PNG-indeling.
## Stap 5: Renderen naar PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Ten slotte wordt de FODG-afbeelding weergegeven in PDF-formaat.

## Conclusie
In deze zelfstudie hebben we onderzocht hoe u FODG- en ODG-afbeeldingen in verschillende indelingen kunt weergeven met behulp van GroupDocs.Viewer voor .NET. Door deze stappen te volgen, kunt u de mogelijkheden voor documentweergave naadloos integreren in uw .NET-toepassingen.
## Veelgestelde vragen
### Is GroupDocs.Viewer voor .NET compatibel met alle versies van .NET Framework?
GroupDocs.Viewer voor .NET is compatibel met een breed scala aan .NET Framework-versies, inclusief de nieuwste versies.
### Kan ik documenten asynchroon weergeven met GroupDocs.Viewer voor .NET?
Ja, GroupDocs.Viewer voor .NET biedt asynchrone weergavemogelijkheden voor betere prestaties.
### Ondersteunt GroupDocs.Viewer voor .NET het weergeven van gecodeerde documenten?
Ja, GroupDocs.Viewer voor .NET ondersteunt het weergeven van gecodeerde documenten met de juiste decoderingssleutels.
### Is het mogelijk om de weergave-uitvoer aan te passen met GroupDocs.Viewer voor .NET?
Absoluut, GroupDocs.Viewer voor .NET biedt verschillende aanpassingsopties om de weergave-uitvoer aan uw vereisten aan te passen.
### Kan ik documenten weergeven vanaf externe opslaglocaties met GroupDocs.Viewer voor .NET?
Ja, GroupDocs.Viewer voor .NET ondersteunt het weergeven van documenten vanaf zowel lokale als externe opslaglocaties.