---
"description": "Leer hoe u de afbeeldingsgrootte en -kwaliteit in JPEG-formaat kunt optimaliseren met Groupdocs.Viewer voor .NET. Verbeter de weergave van uw documenten."
"linktitle": "Pas de afbeeldingsgrootte en -kwaliteit aan (JPG)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Pas de afbeeldingsgrootte en -kwaliteit aan (JPG)"
"url": "/nl/net/rendering-documents-images/adjust-image-size-and-quality-jpg/"
"weight": 11
---

# Pas de afbeeldingsgrootte en -kwaliteit aan (JPG)

## Invoering
Groupdocs.Viewer voor .NET is een krachtige bibliotheek waarmee ontwikkelaars de functionaliteit voor het bekijken van documenten naadloos kunnen integreren in hun .NET-applicaties. Een veelvoorkomende vereiste in applicaties voor het bekijken van documenten is de mogelijkheid om de grootte en kwaliteit van afbeeldingen aan te passen, met name bij het werken met JPEG (JPG)-afbeeldingen. In deze tutorial leiden we je door het proces van het aanpassen van de afbeeldingsgrootte en -kwaliteit met Groupdocs.Viewer voor .NET.
## Vereisten
Voordat we beginnen, zorg ervoor dat u het volgende heeft:
1. Basiskennis van de programmeertaal C#.
2. Visual Studio op uw systeem geïnstalleerd.
3. Groupdocs.Viewer voor .NET-bibliotheek geïnstalleerd. U kunt het downloaden van [hier](https://releases.groupdocs.com/viewer/net/).

## Naamruimten importeren
Eerst moet u de benodigde naamruimten importeren in uw C#-code. Deze naamruimten bieden toegang tot de klassen en methoden die nodig zijn om met Groupdocs.Viewer te werken.
## Stap 1: Naamruimten importeren
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Laten we de voorbeeldcode opsplitsen in meerdere stappen, zodat we het beter kunnen begrijpen.
## Stap 2: Stel de uitvoermap en het pad naar het paginabestand in
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
In deze stap geven we de uitvoermap op waar de gerenderde afbeeldingen worden opgeslagen en definiëren we de indeling voor het bestandspad van elke pagina-afbeelding.
## Stap 3: Viewer initialiseren en JPG-weergaveopties configureren
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
Hier initialiseren we het Viewer-object met het pad naar het te bekijken document. Vervolgens maken we een instantie van JpgViewOptions en stellen we de gewenste breedte en hoogte voor de JPEG-afbeeldingen in.
## Stap 4: Brondocument renderen
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Tot slot printen we een bericht dat het renderen van het bronbestand succesvol is verlopen en de locatie waar de uitvoerafbeeldingen zijn opgeslagen.

## Conclusie
In deze tutorial hebben we geleerd hoe je de grootte en kwaliteit van JPEG-afbeeldingen kunt aanpassen met Groupdocs.Viewer voor .NET. Door de bovenstaande stappen te volgen, kun je deze functionaliteit eenvoudig integreren in je .NET-applicaties en gebruikers een geoptimaliseerde weergave van afbeeldingen bieden.
## Veelgestelde vragen
### Kan ik ook de beeldkwaliteit aanpassen?
Ja, u kunt de beeldkwaliteit aanpassen door de eigenschap Kwaliteit in te stellen in JpgViewOptions.
### Welke documentformaten worden ondersteund door Groupdocs.Viewer voor .NET?
Groupdocs.Viewer voor .NET ondersteunt een breed scala aan documentindelingen, waaronder DOCX, PDF, PPTX, XLSX en meer.
### Is Groupdocs.Viewer voor .NET compatibel met .NET Core?
Ja, Groupdocs.Viewer voor .NET is compatibel met .NET Core en het traditionele .NET Framework.
### Kan ik de naamgeving van uitvoerbestanden aanpassen?
Ja, u kunt de naamgeving van het uitvoerbestand aanpassen door de variabele pageFilePathFormat in de code te wijzigen.
### Ondersteunt Groupdocs.Viewer voor .NET documentannotaties?
Ja, Groupdocs.Viewer voor .NET biedt uitgebreide ondersteuning voor documentannotaties, waaronder tekstmarkering, onderstreping en commentaar.