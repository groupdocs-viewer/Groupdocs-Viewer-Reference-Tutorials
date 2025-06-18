---
"description": "Leer hoe u specifieke CAD-formaten zoals CF2 kunt renderen naar HTML, JPG, PNG en PDF met Groupdocs.Viewer voor .NET."
"linktitle": "Renderspecifieke CAD-formaten (CF2)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Renderspecifieke CAD-formaten (CF2)"
"url": "/nl/net/rendering-cad-drawings/render-specific-cad-formats/"
"weight": 12
---

# Renderspecifieke CAD-formaten (CF2)

## Invoering
In deze tutorial onderzoeken we hoe je specifieke CAD-formaten kunt renderen met Groupdocs.Viewer voor .NET. Groupdocs.Viewer is een krachtige API voor documentviewers waarmee ontwikkelaars meer dan 170 documenttypen in hun applicaties kunnen weergeven zonder externe software te hoeven installeren. We richten ons specifiek op het renderen van CAD-formaten zoals CF2 naar diverse uitvoerformaten zoals HTML, JPG, PNG en PDF.
## Vereisten
Voordat we met de tutorial beginnen, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Visual Studio op uw systeem geïnstalleerd.
- Groupdocs.Viewer voor .NET SDK. U kunt het downloaden van [hier](https://releases.groupdocs.com/viewer/net/).
- Basiskennis van de programmeertaal C#.
## Naamruimten importeren
Laten we eerst de benodigde naamruimten importeren die nodig zijn voor het renderen van CAD-indelingen.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Laten we elk voorbeeld nu opsplitsen in meerdere stappen:
## CF2 naar HTML renderen
### Stap 1: Definieer de uitvoermap waar de gerenderde HTML wordt opgeslagen.
```csharp
string outputDirectory = "Your Document Directory";
```
### Stap 2: Definieer het bestandspad voor de HTML-uitvoer.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### Stap 3: Initialiseer het Viewer-object en geef het invoer-CF2-bestand op.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // Stel indien nodig extra renderingopties in
    // opties.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2 naar JPG renderen
### Stap 1: Definieer het bestandspadformaat voor de JPG-uitvoer.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### Stap 2: Initialiseer het Viewer-object en geef het invoer-CF2-bestand op.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // Stel indien nodig extra renderingopties in
    // opties.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2 naar PNG renderen

### Stap 1: Definieer het bestandspadformaat voor de PNG-uitvoer.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### Stap 2: Initialiseer het Viewer-object en geef het invoer-CF2-bestand op.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // Stel indien nodig extra renderingopties in
    // opties.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2 naar PDF renderen
### Stap 1: Definieer het bestandspad voor de PDF-uitvoer.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### Stap 2: Initialiseer het Viewer-object en geef het invoer-CF2-bestand op.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // Stel indien nodig extra renderingopties in
    // opties.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## Conclusie
In deze tutorial hebben we geleerd hoe je specifieke CAD-formaten zoals CF2 kunt renderen met Groupdocs.Viewer voor .NET. Door de stapsgewijze handleiding te volgen, kun je eenvoudig mogelijkheden voor documentrendering integreren in je .NET-applicaties.
## Veelgestelde vragen
### Kan Groupdocs.Viewer andere CAD-formaten weergeven dan CF2?
Ja, Groupdocs.Viewer ondersteunt een breed scala aan CAD-formaten, waaronder DWG, DXF, DGN en meer.
### Is Groupdocs.Viewer geschikt voor het weergeven van documenten in webapplicaties?
Jazeker, Groupdocs.Viewer kan naadloos worden geïntegreerd in webapplicaties, zodat documenten rechtstreeks in de browser kunnen worden weergegeven.
### Heeft Groupdocs.Viewer externe afhankelijkheden nodig voor rendering?
Nee, Groupdocs.Viewer is een zelfstandige API en vereist geen externe afhankelijkheden of software-installaties.
### Kan ik de renderopties aanpassen aan mijn wensen?
Ja, Groupdocs.Viewer biedt verschillende weergaveopties die u kunt aanpassen aan uw specifieke behoeften.
### Is er een proefversie beschikbaar voor Groupdocs.Viewer?
Ja, u kunt een gratis proefversie van Groupdocs.Viewer verkrijgen via [hier](https://releases.groupdocs.com/).