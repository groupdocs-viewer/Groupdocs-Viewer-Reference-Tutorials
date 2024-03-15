---
title: Notities renderen en tijdseenheden aanpassen (MS Project)
linktitle: Notities renderen en tijdseenheden aanpassen (MS Project)
second_title: GroupDocs.Viewer .NET-API
description: Master rendering MS Project-documenten met GroupDocs.Viewer voor .NET. Render notities, pas tijdseenheden aan en verken moeiteloos verschillende uitvoerformaten.
type: docs
weight: 11
url: /nl/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/
---
## Invoering
GroupDocs.Viewer voor .NET is een krachtige API voor documentweergave waarmee ontwikkelaars verschillende documentformaten binnen hun .NET-applicaties kunnen bekijken en manipuleren. In deze zelfstudie concentreren we ons op het weergeven van notities en het aanpassen van tijdseenheden specifiek voor MS Project-documenten.
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
1. GroupDocs.Viewer voor .NET: Zorg ervoor dat u de GroupDocs.Viewer voor .NET-bibliotheek hebt gedownload en geïnstalleerd. Je kunt het downloaden van[hier](https://releases.groupdocs.com/viewer/net/).
2. Ontwikkelomgeving: Stel uw favoriete ontwikkelomgeving in met .NET-ondersteuning.
3. MS-projectdocument: Zorg ervoor dat u een voorbeeld van een MS-projectdocument gereed heeft om te testen.
## Naamruimten importeren
Laten we eerst de benodigde naamruimten importeren om aan de slag te gaan met het weergeven van MS Project-documenten:
## Stap 1: Naamruimten importeren
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Nu we de vereiste naamruimten hebben geïmporteerd, gaan we elk voorbeeld in meerdere stappen opsplitsen voor een beter begrip.
## Renderen van MS-projectdocument naar HTML
Volg deze stappen om een MS Project-document naar HTML-indeling te converteren, inclusief de aantekeningen:
### Stap 2: Stel de uitvoermap en het bestandsformaat in
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### Stap 3: Initialiseer het Viewer-object en stel opties in
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### Stap 4: Document renderen naar HTML
```csharp
viewer.View(options);
```
## MS-projectdocument weergeven in afbeeldingsformaten
U kunt MS Project-documenten ook renderen naar afbeeldingsformaten zoals JPG en PNG. Hier is hoe:
### Stap 5: Stel de uitvoermap en het bestandsformaat in voor JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### Stap 6: Initialiseer het Viewer-object en stel de JPG-opties in
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Stap 7: Document renderen naar JPG
```csharp
viewer.View(options);
```
Herhaal soortgelijke stappen voor weergave naar PNG en andere afbeeldingsindelingen.
## Renderen van MS-projectdocument naar PDF
Ga als volgt te werk om een MS Project-document naar PDF-formaat te converteren:
### Stap 8: Stel de uitvoermap en het bestandsformaat voor PDF in
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### Stap 9: Initialiseer het Viewer-object en stel de PDF-opties in
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Stap 10: Document naar PDF renderen
```csharp
viewer.View(options);
```

## Conclusie
Gefeliciteerd! U hebt met succes geleerd hoe u MS Project-documenten kunt weergeven en tijdseenheden kunt aanpassen met GroupDocs.Viewer voor .NET. Neem deze kennis op in uw projecten om de weergavemogelijkheden van documenten te verbeteren.
## Veelgestelde vragen
### Kan ik MS Project-documenten in andere formaten weergeven dan HTML, afbeeldingen en PDF?
Ja, GroupDocs.Viewer voor .NET ondersteunt rendering naar verschillende formaten zoals DOCX, XLSX, PPTX en meer.
### Is er een proefversie beschikbaar voor GroupDocs.Viewer voor .NET?
 Ja, u kunt een gratis proefperiode krijgen van[hier](https://releases.groupdocs.com/).
### Hoe kan ik tijdelijke licenties krijgen voor GroupDocs.Viewer voor .NET?
 Bezoek[deze link](https://purchase.groupdocs.com/temporary-license/) om een tijdelijke vergunning te verkrijgen.
### Waar kan ik documentatie vinden voor GroupDocs.Viewer voor .NET?
 Raadpleeg de documentatie[hier](https://reference.groupdocs.com/viewer/net/).
### Waar kan ik ondersteuning zoeken of vragen stellen met betrekking tot GroupDocs.Viewer voor .NET?
 U kunt het ondersteuningsforum bezoeken[hier](https://forum.groupdocs.com/c/viewer/9).