---
"date": "2025-04-25"
"description": "Leer hoe u TXT-bestanden kunt converteren naar verschillende formaten, zoals HTML, JPG, PNG en PDF, met behulp van GroupDocs.Viewer voor .NET met behulp van deze uitgebreide handleiding."
"title": "Converteer TXT naar HTML, JPG, PNG, PDF met GroupDocs.Viewer .NET&#58; een complete handleiding"
"url": "/nl/net/export-conversion/groupdocs-viewer-dotnet-txt-conversion-guide/"
"weight": 1
type: docs
---
# Converteer TXT naar meerdere formaten met GroupDocs.Viewer .NET

## Invoering

Wilt u tekstdocumenten moeiteloos converteren naar verschillende formaten zoals HTML, JPG, PNG of PDF? Het converteren van documenten kan een uitdaging zijn, vooral wanneer u meerdere pagina's of specifieke formaatvereisten hebt. **GroupDocs.Viewer voor .NET** vereenvoudigt het proces van het weergeven van TXT-bestanden in diverse uitvoerformaten, waardoor uw gegevens toegankelijk en visueel aantrekkelijk zijn.

![Converteer TXT naar HTML, JPG, PNG, PDF met GroupDocs.Viewer voor .NET](/viewer/export-conversion/convert-txt-to-html-jpg-png-pdf.png)

In deze handleiding leggen we uit hoe je GroupDocs.Viewer voor .NET kunt gebruiken om TXT-documenten om te zetten naar HTML met meerdere pagina's, HTML met één pagina, JPG, PNG en PDF. Aan het eind beheers je:
- TXT-bestanden converteren met C# met GroupDocs.Viewer
- Implementeren van verschillende renderingopties voor uw behoeften
- Prestaties optimaliseren tijdens conversies

Laten we eens kijken wat de oplossingen zijn voor uw uitdagingen op het gebied van documentconversie.

## Vereisten

Zorg ervoor dat u het volgende bij de hand heeft voordat u begint:
- **Ontwikkelomgeving**: Visual Studio 2019 of later.
- **.NET Framework**: Versie 4.6.1 of hoger.
- **GroupDocs.Viewer voor .NET-bibliotheek**:
  - Via de NuGet Package Manager Console: `Install-Package GroupDocs.Viewer -Version 25.3.0`
  - Met behulp van .NET CLI: `dotnet add package GroupDocs.Viewer --version 25.3.0`

Om de cursus gemakkelijk te kunnen volgen, is kennis van C#-programmering en basisbestandsbewerkingen in .NET aan te raden.

## GroupDocs.Viewer instellen voor .NET

### Installatie

Om te beginnen installeert u de **GroupDocs.Viewer** bibliotheek met behulp van uw favoriete pakketbeheerder:

#### NuGet-pakketbeheerconsole
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

#### .NET CLI
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Licentieverlening

Je kunt beginnen met een **gratis proefperiode** of een **tijdelijke licentie** om de volledige mogelijkheden van GroupDocs.Viewer voor .NET te verkennen zonder evaluatiebeperkingen:
- Gratis proefperiode: [Download hier](https://releases.groupdocs.com/viewer/net/)
- Tijdelijke licentie: [Hier aanvragen](https://purchase.groupdocs.com/temporary-license/)

Voor doorlopend gebruik kunt u overwegen een licentie rechtstreeks bij ons aan te schaffen. [Groepsdocumenten](https://purchase.groupdocs.com/buy).

### Basisinitialisatie

Ga als volgt te werk om GroupDocs.Viewer in uw project te installeren:

```csharp
using System.IO;
using GroupDocs.Viewer;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");

// Initialiseer het Viewer-object met een TXT-bestandspad.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Hier komt uw renderingcode te staan.
}
```

## Implementatiegids

Laten we nu dieper ingaan op elke functie en hoe u deze kunt implementeren.

### TXT-document renderen naar HTML met meerdere pagina's

#### Overzicht
Deze functie demonstreert het converteren van een TXT-document naar een HTML-bestand met meerdere pagina's. Elke pagina van het tekstbestand wordt weergegeven als een afzonderlijk HTML-bestand met ingesloten bronnen.

#### Stap 1: De viewer instellen

Maak een `Viewer` object voor uw bron-TXT-bestand:

```csharp
using System.IO;
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;

string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.html");

// Initialiseer de Viewer met een voorbeeldtekstbestand.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Ga door naar stap 2...
```

#### Stap 2: HTML-weergaveopties configureren

Opzetten `HtmlViewOptions` om elke pagina afzonderlijk weer te geven:

```csharp
// Stel HTML-weergaveopties in voor rendering op meerdere pagina's.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);

// Geef het document weer als HTML met meerdere pagina's.
viewer.View(options);
}
```

**Uitleg**: De `ForEmbeddedResources()` Deze methode zorgt ervoor dat bronnen zoals afbeeldingen en stijlen direct in het HTML-bestand worden ingesloten, waardoor ze eenvoudig kunnen worden gedeeld.

### TXT-document weergeven naar HTML op één pagina

#### Overzicht
Converteer een TXT-document naar één HTML-pagina, ideaal voor documenten die als één doorlopende webpagina moeten worden weergegeven.

#### Stap 1: De viewer instellen

Initialiseer de `Viewer` voorwerp:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result_single_page.html");

// Initialiseer een nieuw Viewer-exemplaar voor een ander tekstbestand.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample2.txt")))
{
    // Ga door naar stap 2...
```

#### Stap 2: Configureer HTML-opties voor één pagina

Configure `HtmlViewOptions` met de instelling voor één pagina ingeschakeld:

```csharp
// Stel opties in voor weergave op één HTML-pagina.
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
options.RenderToSinglePage = true;

// Weergeven als één HTML-pagina.
viewer.View(options);
}
```

**Uitleg**: De `RenderToSinglePage` zorgt ervoor dat de volledige inhoud op één pagina wordt weergegeven.

### TXT-document naar JPG renderen

#### Overzicht
Met deze functie kunt u een tekstdocument omzetten in een JPEG-afbeelding, wat handig is voor visuele presentaties of archiveringsdoeleinden.

#### Stap 1: De viewer instellen

Bereid je voor `Viewer` voorwerp:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.jpg");

// Initialiseer de viewer met een voorbeeldbestand.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Ga door naar stap 2...
```

#### Stap 2: JPG-weergaveopties configureren

Opzetten `JpgViewOptions` voor beeldweergave:

```csharp
// Stel opties in voor het renderen als JPG-afbeelding.
JpgViewOptions options = new JpgViewOptions(pageFileFullPath);

// Render het document als een JPEG-bestand.
viewer.View(options);
}
```

**Uitleg**: De `JpgViewOptions` klasse specificeert hoe elke pagina van uw document in JPEG-formaat moet worden weergegeven en opgeslagen.

### TXT-document naar PNG renderen

#### Overzicht
Converteer een tekstdocument naar PNG-formaat en krijg een uitvoer van hoge kwaliteit met ondersteuning voor transparantie.

#### Stap 1: De viewer instellen

Initialiseer de `Viewer` voorwerp:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.png");

// Maak een viewerinstantie voor uw TXT-bestand.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Ga door naar stap 2...
```

#### Stap 2: PNG-weergaveopties configureren

Opzetten `PngViewOptions`:

```csharp
// Weergaveopties instellen voor rendering als PNG-afbeelding.
PngViewOptions options = new PngViewOptions(pageFileFullPath);

// Render het document in PNG-formaat.
viewer.View(options);
}
```

**Uitleg**: De `PngViewOptions` klasse maakt het mogelijk om elke pagina transparant weer te geven, waardoor deze geschikt is voor gelaagde afbeeldingen.

### TXT-document naar PDF renderen

#### Overzicht
Deze functie is perfect voor het converteren van tekstdocumenten naar een universeel toegankelijk PDF-formaat.

#### Stap 1: De viewer instellen

Bereid je voor `Viewer` voorwerp:

```csharp
string outputDirectory = Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Output");
string pageFileFullPath = Path.Combine(outputDirectory, "Txt_result.pdf");

// Initialiseer een viewerinstantie voor uw voorbeeldtekstbestand.
using (Viewer viewer = new Viewer(Path.Combine("YOUR_DOCUMENT_DIRECTORY", "Sample.txt")))
{
    // Ga door naar stap 2...
```

#### Stap 2: PDF-weergaveopties configureren

Opzetten `PdfViewOptions`:

```csharp
// Weergaveopties instellen voor weergave als PDF-document.
PdfViewOptions options = new PdfViewOptions(pageFileFullPath);

// Converteer het document naar een PDF-bestand.
viewer.View(options);
}
```

**Uitleg**: De `PdfViewOptions` klasse geeft aan hoe u uw TXT-bestanden converteert en opslaat als PDF-documenten.

## Conclusie

Met GroupDocs.Viewer voor .NET is het converteren van tekstdocumenten naar verschillende formaten eenvoudig. Deze handleiding behandelde het converteren van TXT-bestanden naar HTML met meerdere pagina's, HTML met één pagina, JPG, PNG en PDF met behulp van C#. Of u nu de toegankelijkheid of compatibiliteit van documenten wilt verbeteren, deze methoden bieden robuuste oplossingen.

Voor verdere hulp of meer geavanceerde functies kunt u terecht op de [officiële GroupDocs.Viewer-documentatie](https://docs.groupdocs.com/viewer/net/)Veel plezier met coderen!