---
title: Specificeer het bestandstype bij het laden van documenten
linktitle: Specificeer het bestandstype bij het laden van documenten
second_title: GroupDocs.Viewer .NET-API
description: Leer hoe u het bestandstype kunt opgeven bij het laden van documenten met GroupDocs.Viewer voor .NET. Geef verschillende formaten nauwkeurig weer in uw .NET-applicaties.
weight: 10
url: /nl/net/advanced-loading/specify-file-type/
---

# Specificeer het bestandstype bij het laden van documenten

## Invoering
GroupDocs.Viewer voor .NET is een veelzijdige API voor documentweergave die een breed scala aan bestandsindelingen ondersteunt, waaronder DOCX, PDF, PPTX en meer. Door het bestandstype op te geven bij het laden van documenten, kunt u een nauwkeurige weergave en een soepele kijkervaring voor uw gebruikers garanderen.
## Vereisten
Voordat u begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Basiskennis van C# en .NET framework.
- Visual Studio is op uw systeem geïnstalleerd.
- GroupDocs.Viewer voor .NET geïnstalleerd in uw project. Je kunt het downloaden van[hier](https://releases.groupdocs.com/viewer/net/).
##
## Naamruimten importeren
Ten eerste moet u de benodigde naamruimten in uw C#-code importeren. Deze naamruimten bieden toegang tot de klassen en methoden die nodig zijn voor de weergave van documenten.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Stap 1: Stel de uitvoermap in
Definieer de map waarin u de weergegeven documentpagina's wilt opslaan.
```csharp
string outputDirectory = "Your Document Directory";
```
## Stap 2: Definieer het paginabestandspadformaat
Geef de indeling op voor de naamgeving van de uitvoer-HTML-bestanden voor elke pagina van het document.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Stap 3: Geef laadopties op
 Maak een exemplaar van de`LoadOptions` class en stel het gewenste bestandstype in.
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## Stap 4: Document laden en renderen
 Gebruik de`Viewer` class om het document te laden en in HTML-indeling weer te geven.
```csharp
using (Viewer viewer = new Viewer("YourDocument.docx", loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Stap 5: Succesbericht weergeven
Informeer de gebruiker dat het document succesvol is weergegeven en geef de locatie van de uitvoerbestanden op.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusie
In deze zelfstudie hebben we geleerd hoe u GroupDocs.Viewer voor .NET kunt gebruiken om het bestandstype op te geven bij het laden van documenten. Door deze eenvoudige stappen te volgen, kunt u zorgen voor een nauwkeurige weergave van verschillende documentformaten in uw .NET-toepassingen.
## Veelgestelde vragen
### Kan ik andere documenten dan DOCX weergeven met GroupDocs.Viewer voor .NET?
Ja, GroupDocs.Viewer ondersteunt een breed scala aan bestandsindelingen, waaronder PDF, PPTX, XLSX en meer.
### Is GroupDocs.Viewer voor .NET compatibel met .NET Core?
Ja, GroupDocs.Viewer voor .NET is compatibel met zowel .NET Framework als .NET Core.
### Kan ik de door GroupDocs.Viewer gegenereerde HTML-uitvoerbestanden aanpassen?
Ja, u kunt de HTML-uitvoer aanpassen met behulp van verschillende opties van de API.
### Vereist GroupDocs.Viewer voor .NET externe afhankelijkheden?
Nee, GroupDocs.Viewer voor .NET is een zelfstandige bibliotheek en vereist geen externe afhankelijkheden.
### Is er een proefversie beschikbaar voor GroupDocs.Viewer voor .NET?
Ja, u kunt een gratis proefversie downloaden van[hier](https://releases.groupdocs.com/viewer/net/).