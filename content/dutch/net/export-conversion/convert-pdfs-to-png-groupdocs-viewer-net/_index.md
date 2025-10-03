---
"date": "2025-04-25"
"description": "Leer hoe u PDF-pagina's naar PNG-afbeeldingen kunt converteren met behoud van de oorspronkelijke afmetingen met GroupDocs.Viewer voor .NET. Deze handleiding behandelt installatie, configuratie en aanbevolen procedures."
"title": "PDF's converteren naar PNG met originele grootte met GroupDocs.Viewer voor .NET"
"url": "/nl/net/export-conversion/convert-pdfs-to-png-groupdocs-viewer-net/"
"weight": 1
type: docs
---
# PDF's converteren naar PNG met originele grootte met GroupDocs.Viewer voor .NET

## Invoering

Het converteren van PDF-bestanden naar PNG-afbeeldingen met behoud van de oorspronkelijke paginagrootte is essentieel voor hoogwaardige documentdigitalisering of webcontentvoorbereiding. Deze tutorial begeleidt u bij het gebruik van GroupDocs.Viewer voor .NET om PDF-pagina's als PNG-bestanden weer te geven, met behoud van hun oorspronkelijke afmetingen.

![Converteer PDF's naar PNG met originele grootte met GroupDocs.Viewer voor .NET](/viewer/export-conversion/convert-pdfs-to-png-with-original-size.png)

**Wat je leert:**
- Hoe u GroupDocs.Viewer voor .NET in uw project instelt en configureert
- Stapsgewijs proces voor het renderen van PDF's naar PNG-afbeeldingen met behoud van paginagroottes
- Belangrijkste configuratieopties en aanbevolen procedures voor optimale prestaties

Aan het einde van deze tutorial kunt u deze functionaliteit naadloos integreren in uw applicaties. Laten we beginnen met de vereisten om aan de slag te gaan.

## Vereisten

Voordat u GroupDocs.Viewer voor .NET in uw project implementeert, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

### Vereiste bibliotheken en versies
- **GroupDocs.Viewer voor .NET**: Versie 25.3.0 of later.

### Vereisten voor omgevingsinstellingen
- Een compatibele ontwikkelomgeving zoals Visual Studio.
- Basiskennis van C#-programmering.

### Kennisvereisten
- Kennis van NuGet-pakketbeheer.
- Ervaring met PDF's en beeldverwerking in .NET-toepassingen.

Zodra deze vereisten vervuld zijn, kunnen we doorgaan met het instellen van GroupDocs.Viewer voor .NET.

## GroupDocs.Viewer instellen voor .NET

Om GroupDocs.Viewer voor .NET te gaan gebruiken, volgt u de onderstaande installatiestappen:

### Installatie via NuGet Package Manager Console
Open uw project in Visual Studio en gebruik de volgende opdracht:
```plaintext
Install-Package GroupDocs.Viewer -Version 25.3.0
```

### Installatie via .NET CLI
U kunt het ook installeren via de .NET CLI met deze opdracht:
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### Stappen voor het verkrijgen van een licentie
1. **Gratis proefperiode**: Download een proefversie van [GroupDocs-downloads](https://releases.groupdocs.com/viewer/net/).
2. **Tijdelijke licentie**: Verkrijg een tijdelijke licentie om alle functies te verkennen op [Tijdelijke licentiepagina](https://purchase.groupdocs.com/temporary-license/).
3. **Aankoop**: Voor uitgebreid gebruik kunt u een licentie aanschaffen via de [Kooppagina](https://purchase.groupdocs.com/buy).

### Basisinitialisatie en -installatie
Volg deze stappen om GroupDocs.Viewer voor .NET in uw C#-project te initialiseren:
1. Importeer benodigde naamruimten:
    ```csharp
    using System;
    using GroupDocs.Viewer;
    using GroupDocs.Viewer.Options;
    ```
2. Stel de paden in voor uw invoer-PDF en uitvoermap.
3. Initialiseren `Viewer` met het pad naar uw brondocument, zoals weergegeven in dit fragment:
   ```csharp
   string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
   string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
   string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";

   using (Viewer viewer = new Viewer(documentPath))
   {
       PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
       viewer.View(viewOptions);
   }
   ```

## Implementatiegids
In dit gedeelte wordt de implementatie van het renderen van PDF-pagina's als PNG-afbeeldingen besproken, waarbij de oorspronkelijke grootte behouden blijft.

### PDF-pagina's renderen naar PNG met originele paginagrootte
#### Overzicht
Met deze functie kunt u elke pagina van een PDF-document omzetten in een PNG-afbeelding, met behoud van de oorspronkelijke afmetingen. Dit is met name handig voor toepassingen die een nauwkeurige visuele weergave van documenten vereisen.

##### Stap 1: Paden instellen en Viewer initialiseren
Maak variabelen voor het invoer-PDF-pad en de uitvoermap:
```csharp
string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";
```
Initialiseer de `Viewer` klasse met het pad van uw brondocument:
```csharp
using (Viewer viewer = new Viewer(documentPath))
{
    // Codeblok gaat verder in de volgende stap
}
```
##### Stap 2: PngViewOptions configureren
Maak een exemplaar van `PngViewOptions`, waarbij een bestandsnaamgevingspatroon voor de uitvoerafbeeldingen wordt opgegeven:
```csharp
PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
```
Configureer de vieweropties om elke pagina op de oorspronkelijke grootte weer te geven:
```csharp
viewOptions.PdfOptions.RenderOriginalPageSize = true;
```
##### Stap 3: Documentpagina's renderen
Bel de `View` methode op uw `Viewer` bijvoorbeeld door de geconfigureerde weergaveopties door te geven:
```csharp
viewer.View(viewOptions);
```
### Tips voor probleemoplossing
- Zorg ervoor dat de paden juist zijn en de mappen bestaan.
- Controleer of u over de benodigde machtigingen beschikt om te lezen van de invoermappen en te schrijven naar de uitvoermappen.

## Praktische toepassingen
1. **Documentdigitalisering**: Converteer archief-PDF-documenten naar digitale afbeeldingen voor eenvoudigere toegang en distributie.
2. **Webportalen**: Geef documentvoorbeelden weer op websites zonder dat u een PDF-lezer nodig hebt.
3. **Content Management Systemen (CMS)**: Integreer met CMS-platforms om grote hoeveelheden PDF-inhoud efficiënt te beheren en weer te geven.

## Prestatieoverwegingen
Optimaliseer de prestaties van uw applicatie met GroupDocs.Viewer voor .NET:
- Beperk het geheugengebruik door documenten in delen te verwerken als het om grote bestanden gaat.
- Gebruik waar mogelijk asynchrone methoden om te voorkomen dat threads tijdens het renderen worden geblokkeerd.
- Afvoeren `Viewer` instanties direct na gebruik om bronnen vrij te maken.

## Conclusie
In deze tutorial heb je geleerd hoe je PDF-pagina's kunt renderen als PNG-afbeeldingen met behoud van hun oorspronkelijke grootte met behulp van GroupDocs.Viewer voor .NET. We hebben het instellen van je omgeving en de benodigde opties voor optimale resultaten behandeld en praktische toepassingen van deze functionaliteit onderzocht.

De volgende stappen zijn het experimenteren met andere renderingopties die beschikbaar zijn in GroupDocs.Viewer of het integreren ervan in grotere projecten voor uitgebreidere mogelijkheden voor documentbeheer.

## FAQ-sectie
1. **Wat is de beste manier om grote PDF-bestanden te verwerken met GroupDocs.Viewer?**
   - Verwerk documenten in kleinere delen en gebruik asynchrone methoden om de prestaties te behouden.
2. **Kan ik de namen van de PNG-uitvoerbestanden aanpassen?**
   - Ja, door een naamgevingspatroon op te geven in `PngViewOptions`.
3. **Is het mogelijk om alleen specifieke pagina's weer te geven?**
   - Absoluut, u kunt configureren `PageNumbers` in `PngViewOptions` om aan te geven welke pagina's moeten worden weergegeven.
4. **Hoe regel ik de licentie voor GroupDocs.Viewer?**
   - kunt kiezen uit een gratis proefversie, een tijdelijke licentie of een volledige licentie aanschaffen.
5. **Kan deze opstelling gebruikt worden in webapplicaties?**
   - Ja, het is geschikt voor server-side rendering van PDF's in ASP.NET Core en andere op .NET gebaseerde webframeworks.

## Bronnen
- [Documentatie](https://docs.groupdocs.com/viewer/net/)
- [API-referentie](https://reference.groupdocs.com/viewer/net/)
- [GroupDocs.Viewer downloaden](https://releases.groupdocs.com/viewer/net/)
- [Licentie kopen](https://purchase.groupdocs.com/buy)
- [Gratis proefperiode](https://releases.groupdocs.com/viewer/net/)
- [Tijdelijke licentie](https://purchase.groupdocs.com/temporary-license/)
- [Ondersteuningsforum](https://forum.groupdocs.com/c/viewer/9)