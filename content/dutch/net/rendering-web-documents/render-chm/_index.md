---
"description": "Leer hoe u CHM-bestanden in .NET kunt renderen met GroupDocs.Viewer. Converteer CHM moeiteloos naar HTML-, JPG-, PNG- en PDF-formaten."
"linktitle": "CHM-bestanden renderen"
"second_title": "GroupDocs.Viewer .NET API"
"title": "CHM-bestanden renderen"
"url": "/nl/net/rendering-web-documents/render-chm/"
"weight": 10
type: docs
---
# CHM-bestanden renderen

## Invoering
In deze tutorial leggen we uit hoe u CHM-bestanden (Compiled HTML Help) kunt renderen met GroupDocs.Viewer voor .NET. GroupDocs.Viewer voor .NET is een krachtige API voor het renderen van documenten waarmee ontwikkelaars meer dan 170 documenttypen in hun .NET-toepassingen kunnen weergeven zonder dat er externe software geïnstalleerd hoeft te worden.

## Vereisten

Voordat we beginnen met het renderen van CHM-bestanden, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

### GroupDocs.Viewer voor .NET installeren

Om te beginnen moet u GroupDocs.Viewer voor .NET installeren. U kunt de bibliotheek downloaden van de [GroupDocs-website](https://releases.groupdocs.com/viewer/net/) of installeer het via NuGet Package Manager door de volgende opdracht uit te voeren in de Package Manager Console:

```bash
Install-Package GroupDocs.Viewer
```

## Naamruimten importeren

Zorg ervoor dat u de benodigde naamruimten in uw project importeert:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

Laten we het renderingproces nu opsplitsen in meerdere stappen:

## Stap 1: Definieer de uitvoermap

Definieer de map waarin u de gerenderde bestanden wilt opslaan:

```csharp
string outputDirectory = "Your Document Directory";
```

## Stap 2: Renderen naar HTML

Gebruik het volgende codefragment om CHM-bestanden naar HTML te renderen:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // Instellen op 'true' om alle CHM-inhoud naar één pagina te converteren

    viewer.View(options); // Converteer alle pagina's
}
```

## Stap 3: Renderen naar JPG

Gebruik het volgende codefragment om CHM-bestanden naar JPG-afbeeldingen te renderen:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Converteer alleen pagina's 1, 2, 3
}
```

## Stap 4: Renderen naar PNG

Gebruik het volgende codefragment om CHM-bestanden naar PNG-afbeeldingen te renderen:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Converteer alleen pagina's 1, 2, 3
}
```

## Stap 5: Renderen naar PDF

Gebruik het volgende codefragment om CHM-bestanden naar een PDF-document te renderen:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); // Converteer alle pagina's
}
```

## Stap 6: Controleer de uitvoer

Zodra het renderingproces is voltooid, controleert u de opgegeven uitvoermap op de gerenderde bestanden:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusie

Het renderen van CHM-bestanden met GroupDocs.Viewer voor .NET is een eenvoudig proces. Door de stappen in deze tutorial te volgen, kunt u CHM-documenten efficiënt converteren naar verschillende formaten, zoals HTML, afbeeldingen (JPG, PNG) en PDF, binnen uw .NET-applicaties.

## Veelgestelde vragen

### V1: Kan GroupDocs.Viewer andere documentformaten weergeven dan CHM?

A1: Ja, GroupDocs.Viewer ondersteunt de weergave van meer dan 170 documentformaten, waaronder PDF, DOCX, XLSX, PPTX en meer.

### V2: Is GroupDocs.Viewer compatibel met .NET Core?

A2: Ja, GroupDocs.Viewer ondersteunt .NET Core naast het traditionele .NET Framework.

### V3: Kan ik de weergaveopties voor verschillende uitvoerformaten aanpassen?

A3: Ja, GroupDocs.Viewer biedt verschillende opties voor het aanpassen van het renderingproces, zoals het opgeven van paginanummers, het instellen van de beeldkwaliteit en het configureren van uitvoerpaden.

### V4: Heeft GroupDocs.Viewer externe afhankelijkheden nodig voor het weergeven van documenten?

A4: Nee, GroupDocs.Viewer is een zelfstandige bibliotheek en vereist geen externe afhankelijkheden of installatie van software van derden.

### V5: Is er een gratis proefversie beschikbaar voor GroupDocs.Viewer?

A5: Ja, u kunt GroupDocs.Viewer gratis uitproberen door naar de website te gaan. [website](https://releases.groupdocs.com/).