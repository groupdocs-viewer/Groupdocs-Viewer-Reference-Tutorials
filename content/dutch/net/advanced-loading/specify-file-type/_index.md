---
"description": "Leer hoe u het bestandstype kunt opgeven bij het laden van documenten met GroupDocs.Viewer voor .NET. Render verschillende formaten nauwkeurig in uw .NET-toepassingen."
"linktitle": "Geef het bestandstype op bij het laden van documenten"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Geef het bestandstype op bij het laden van documenten"
"url": "/nl/net/advanced-loading/specify-file-type/"
"weight": 10
type: docs
---
# Geef het bestandstype op bij het laden van documenten

## Invoering
GroupDocs.Viewer voor .NET is een veelzijdige API voor documentweergave die een breed scala aan bestandsformaten ondersteunt, waaronder DOCX, PDF, PPTX en meer. Door het bestandstype op te geven bij het laden van documenten, kunt u een nauwkeurige weergave en een soepele weergave voor uw gebruikers garanderen.

![Bestandstype opgeven bij het laden van documenten in GroupDocs.Viewer voor .NET](/viewer/advanced-loading/specify-file-type-when-loading-documents-img.png)

## Vereisten
Voordat u begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Basiskennis van C# en .NET Framework.
- Visual Studio op uw systeem geïnstalleerd.
- GroupDocs.Viewer voor .NET is geïnstalleerd in uw project. U kunt het downloaden van [hier](https://releases.groupdocs.com/viewer/net/).
##
## Naamruimten importeren
Allereerst moet u de benodigde naamruimten importeren in uw C#-code. Deze naamruimten bieden toegang tot de klassen en methoden die nodig zijn voor documentrendering.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Stap 1: Uitvoermap instellen
Definieer de map waarin u de gerenderde documentpagina's wilt opslaan.
```csharp
string outputDirectory = "Your Document Directory";
```
## Stap 2: Definieer het padformaat van het paginabestand
Geef de naamgeving voor de uitvoer-HTML-bestanden voor elke pagina van het document op.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Stap 3: Laadopties specificeren
Maak een exemplaar van de `LoadOptions` klasse en stel het gewenste bestandstype in.
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## Stap 4: Document laden en renderen
Gebruik de `Viewer` klasse om het document te laden en in HTML-formaat weer te geven.
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
In deze tutorial hebben we geleerd hoe je GroupDocs.Viewer voor .NET kunt gebruiken om het bestandstype te specificeren bij het laden van documenten. Door deze eenvoudige stappen te volgen, kunt u de accurate weergave van verschillende documentformaten in uw .NET-applicaties garanderen.
## Veelgestelde vragen
### Kan ik met GroupDocs.Viewer voor .NET andere documenten dan DOCX weergeven?
Ja, GroupDocs.Viewer ondersteunt een breed scala aan bestandsindelingen, waaronder PDF, PPTX, XLSX en meer.
### Is GroupDocs.Viewer voor .NET compatibel met .NET Core?
Ja, GroupDocs.Viewer voor .NET is compatibel met zowel .NET Framework als .NET Core.
### Kan ik de HTML-uitvoerbestanden aanpassen die GroupDocs.Viewer genereert?
Ja, u kunt de HTML-uitvoer aanpassen met behulp van diverse opties die de API biedt.
### Heeft GroupDocs.Viewer voor .NET externe afhankelijkheden nodig?
Nee, GroupDocs.Viewer voor .NET is een zelfstandige bibliotheek en vereist geen externe afhankelijkheden.
### Is er een proefversie beschikbaar voor GroupDocs.Viewer voor .NET?
Ja, u kunt een gratis proefversie downloaden van [hier](https://releases.groupdocs.com/viewer/net/).