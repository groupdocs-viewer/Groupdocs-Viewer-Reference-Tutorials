---
title: Afbeeldingsgrootte en -kwaliteit aanpassen (JPG)
linktitle: Afbeeldingsgrootte en -kwaliteit aanpassen (JPG)
second_title: GroupDocs.Viewer .NET-API
description: Leer hoe u de afbeeldingsgrootte en -kwaliteit in JPEG-indeling kunt optimaliseren met Groupdocs.Viewer voor .NET. Verbeter uw documentkijkervaring.
weight: 11
url: /nl/net/rendering-documents-images/adjust-image-size-and-quality-jpg/
---

# Afbeeldingsgrootte en -kwaliteit aanpassen (JPG)

## Invoering
Groupdocs.Viewer voor .NET is een krachtige bibliotheek waarmee ontwikkelaars de functionaliteit voor het bekijken van documenten naadloos kunnen integreren in hun .NET-applicaties. Een veel voorkomende vereiste bij het bekijken van documenten is de mogelijkheid om de grootte en kwaliteit van afbeeldingen aan te passen, vooral als het om JPEG (JPG)-afbeeldingen gaat. In deze zelfstudie leiden we u door het proces van het aanpassen van de afbeeldingsgrootte en -kwaliteit met Groupdocs.Viewer voor .NET.
## Vereisten
Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:
1. Basiskennis van de programmeertaal C#.
2. Visual Studio is op uw systeem geïnstalleerd.
3.  Groupdocs.Viewer voor .NET-bibliotheek geïnstalleerd. Je kunt het downloaden van[hier](https://releases.groupdocs.com/viewer/net/).

## Naamruimten importeren
Eerst moet u de benodigde naamruimten in uw C#-code importeren. Deze naamruimten bieden toegang tot de klassen en methoden die nodig zijn voor het werken met Groupdocs.Viewer.
## Stap 1: Naamruimten importeren
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Laten we nu de voorbeeldcode in meerdere stappen opsplitsen voor een beter begrip.
## Stap 2: Stel de uitvoermap en het paginabestandspadformaat in
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
In deze stap specificeren we de uitvoermap waar de gerenderde afbeeldingen worden opgeslagen en definiëren we het formaat voor het bestandspad van elke paginaafbeelding.
## Stap 3: Initialiseer Viewer en configureer JPG-weergaveopties
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
Hier initialiseren we het Viewer-object met het pad naar het document dat moet worden bekeken. Vervolgens maken we een exemplaar van JpgViewOptions en stellen we de gewenste breedte en hoogte in voor de JPEG-afbeeldingen.
## Stap 4: Geef het brondocument weer
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Ten slotte drukken we een bericht af waarin de succesvolle weergave van het brondocument wordt aangegeven en de locatie waar de uitvoerafbeeldingen worden opgeslagen.

## Conclusie
In deze zelfstudie hebben we geleerd hoe u de grootte en kwaliteit van JPEG-afbeeldingen kunt aanpassen met Groupdocs.Viewer voor .NET. Door de hierboven beschreven stappen te volgen, kunt u deze functionaliteit eenvoudig in uw .NET-toepassingen integreren, waardoor gebruikers een geoptimaliseerde beeldkijkervaring krijgen.
## Veelgestelde vragen
### Kan ik de beeldkwaliteit ook aanpassen?
Ja, u kunt de beeldkwaliteit aanpassen door de eigenschap Quality in JpgViewOptions in te stellen.
### Welke documentformaten worden ondersteund door Groupdocs.Viewer voor .NET?
Groupdocs.Viewer voor .NET ondersteunt een breed scala aan documentformaten, waaronder DOCX, PDF, PPTX, XLSX en meer.
### Is Groupdocs.Viewer voor .NET compatibel met .NET Core?
Ja, Groupdocs.Viewer voor .NET is compatibel met .NET Core en het traditionele .NET Framework.
### Kan ik de naamgevingsindeling van het uitvoerbestand aanpassen?
Ja, u kunt de naamgevingsindeling van het uitvoerbestand aanpassen door de variabele pageFilePathFormat in de code te wijzigen.
### Ondersteunt Groupdocs.Viewer voor .NET documentannotaties?
Ja, Groupdocs.Viewer voor .NET biedt uitgebreide ondersteuning voor documentannotaties, inclusief tekstmarkering, onderstreping en commentaar.