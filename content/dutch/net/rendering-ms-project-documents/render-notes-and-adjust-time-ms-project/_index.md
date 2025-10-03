---
"description": "Beheers het renderen van MS Project-documenten met GroupDocs.Viewer voor .NET. Render notities, pas tijdseenheden aan en verken moeiteloos verschillende uitvoerformaten."
"linktitle": "Notities weergeven en tijdseenheden aanpassen (MS Project)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Notities weergeven en tijdseenheden aanpassen (MS Project)"
"url": "/nl/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/"
"weight": 11
type: docs
---
# Notities weergeven en tijdseenheden aanpassen (MS Project)

## Invoering
GroupDocs.Viewer voor .NET is een krachtige API voor documentweergave waarmee ontwikkelaars verschillende documentformaten in hun .NET-applicaties kunnen bekijken en bewerken. In deze tutorial richten we ons op het weergeven van notities en het aanpassen van tijdseenheden, specifiek voor MS Project-documenten.
## Vereisten
Voordat we beginnen, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. GroupDocs.Viewer voor .NET: Zorg ervoor dat u de GroupDocs.Viewer voor .NET-bibliotheek hebt gedownload en geïnstalleerd. U kunt deze downloaden van [hier](https://releases.groupdocs.com/viewer/net/).
2. Ontwikkelomgeving: Stel uw favoriete ontwikkelomgeving in met .NET-ondersteuning.
3. MS Project-document: Zorg dat u een voorbeeld van een MS Project-document bij de hand hebt om te testen.
## Naamruimten importeren
Laten we eerst de benodigde naamruimten importeren om te beginnen met het renderen van MS Project-documenten:
## Stap 1: Naamruimten importeren
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Nu we de vereiste naamruimten hebben geïmporteerd, gaan we elk voorbeeld opsplitsen in meerdere stappen voor een beter begrip.
## MS-projectdocument naar HTML renderen
Om een MS Project-document inclusief notities in HTML-formaat te converteren, volgt u deze stappen:
### Stap 2: Stel de uitvoermap en het bestandsformaat in
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### Stap 3: Viewerobject initialiseren en opties instellen
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### Stap 4: Document naar HTML renderen
```csharp
viewer.View(options);
```
## MS Project-documenten renderen naar afbeeldingsformaten
Je kunt MS Project-documenten ook omzetten naar afbeeldingsformaten zoals JPG en PNG. Zo doe je dat:
### Stap 5: Stel de uitvoermap en het bestandsformaat voor JPG in
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### Stap 6: Viewerobject initialiseren en JPG-opties instellen
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Stap 7: Document naar JPG renderen
```csharp
viewer.View(options);
```
Herhaal deze stappen voor het renderen naar PNG en andere afbeeldingsformaten.
## MS-projectdocument naar PDF renderen
Ga als volgt te werk om een MS Project-document naar PDF-formaat te converteren:
### Stap 8: Stel de uitvoermap en het bestandsformaat voor PDF in
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### Stap 9: Viewerobject initialiseren en PDF-opties instellen
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
Gefeliciteerd! U hebt succesvol geleerd hoe u MS Project-documenten kunt renderen en tijdseenheden kunt aanpassen met GroupDocs.Viewer voor .NET. Integreer deze kennis in uw projecten om de mogelijkheden voor het bekijken van documenten te verbeteren.
## Veelgestelde vragen
### Kan ik MS Project-documenten weergeven in andere formaten dan HTML, afbeeldingen en PDF?
Ja, GroupDocs.Viewer voor .NET ondersteunt rendering naar verschillende formaten, zoals DOCX, XLSX, PPTX en meer.
### Is er een proefversie beschikbaar voor GroupDocs.Viewer voor .NET?
Ja, u kunt een gratis proefperiode krijgen van [hier](https://releases.groupdocs.com/).
### Hoe kan ik een tijdelijke licentie voor GroupDocs.Viewer voor .NET krijgen?
Bezoek [deze link](https://purchase.groupdocs.com/temporary-license/) om een tijdelijke vergunning te verkrijgen.
### Waar kan ik documentatie vinden voor GroupDocs.Viewer voor .NET?
Raadpleeg de documentatie [hier](https://tutorials.groupdocs.com/viewer/net/).
### Waar kan ik ondersteuning krijgen of vragen stellen over GroupDocs.Viewer voor .NET?
U kunt het ondersteuningsforum bezoeken [hier](https://forum.groupdocs.com/c/viewer/9).