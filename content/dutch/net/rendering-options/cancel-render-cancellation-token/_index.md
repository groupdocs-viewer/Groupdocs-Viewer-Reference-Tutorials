---
"description": "Integreer Groupdocs.Viewer voor .NET naadloos in uw .NET-projecten voor efficiënte documentweergave."
"linktitle": "Annuleer Render met Annuleringstoken"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Annuleer Render met Annuleringstoken"
"url": "/nl/net/rendering-options/cancel-render-cancellation-token/"
"weight": 11
---

# Annuleer Render met Annuleringstoken

## Invoering
Groupdocs.Viewer voor .NET is een krachtige tool die is ontworpen om het bekijken en verwerken van documenten in .NET-applicaties te vereenvoudigen. Of u nu werkt met PDF's, Microsoft Office-documenten of andere gangbare formaten, deze bibliotheek biedt robuuste functionaliteit om documentweergave naadloos te integreren in uw .NET-projecten.
## Vereisten
Voordat u begint met de integratie van Groupdocs.Viewer voor .NET, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. Installatie: Download en installeer de Groupdocs.Viewer voor .NET-bibliotheek van de meegeleverde [downloadlink](https://releases.groupdocs.com/viewer/net/).
   
2. Licentie: Verkrijg een licentie van [Groepsdocs](https://purchase.groupdocs.com/buy) om het volledige potentieel van de bibliotheek te benutten. U kunt ook beginnen met een gratis proefperiode via de [tijdelijke licentie](https://purchase.groupdocs.com/temporary-license/).
   
3. Ontwikkelomgeving: Zorg ervoor dat u een compatibele ontwikkelomgeving hebt ingesteld, inclusief Visual Studio of een andere .NET IDE naar keuze.

## Naamruimten importeren
Om Groupdocs.Viewer voor .NET effectief te kunnen gebruiken, moet u de benodigde naamruimten in uw project importeren. Volg deze stappen:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Laten we het gegeven voorbeeld nu opsplitsen in meerdere stappen, zodat u het beter kunt begrijpen en implementeren:
## Stap 1: Definieer de uitvoermap
```csharp
string outputDirectory = "Your Document Directory";
```
Met deze stap stelt u de map in waar de gerenderde documentpagina's worden opgeslagen.
## Stap 2: Definieer het padformaat van het paginabestand
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Hier definiëren we de opmaak voor de bestandspaden van de afzonderlijke documentpagina's.
## Stap 3: Initialiseer CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource wordt gebruikt om CancellationToken-instanties te genereren die kunnen worden gebruikt om asynchrone bewerkingen te annuleren.
## Stap 4: Annuleringstoken verkrijgen
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
Met deze stap wordt het token opgehaald uit de CancellationTokenSource. Dit token wordt gebruikt om de renderbewerking te annuleren.
## Stap 5: Documentpagina's renderen
```csharp
Task.Run(() =>
{
    using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX, new ViewerSettings(new GroupDocs.Viewer.Logging.ConsoleLogger())))
    {
        HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
        options.RenderComments = true;
        viewer.View(options, cancellationToken);
    }
}, cancellationToken);
```
Hier starten we het asynchroon renderen van documentpagina's met behulp van Task.Run(). De Viewer-instantie wordt aangemaakt met het opgegeven documentbestand (SAMPLE_DOCX) en de renderingopties worden geconfigureerd. Het renderingproces wordt vervolgens gestart met de View-methode van de Viewer-klasse.
## Stap 6: Stel render-time-out in
```csharp
cancellationTokenSource.CancelAfter(10);
```
Deze stap stelt een time-out van 10 milliseconden in voor de renderbewerking. Als de bewerking deze time-out overschrijdt, wordt deze automatisch geannuleerd.
## Stap 7: Succesbericht weergeven
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Tot slot wordt er een succesbericht weergegeven dat aangeeft dat het document succesvol is weergegeven.

## Conclusie
In deze tutorial hebben we de basisprincipes behandeld van het integreren van Groupdocs.Viewer voor .NET in uw projecten. Door de bovenstaande stappen te volgen, kunt u naadloos documentweergavemogelijkheden integreren in uw .NET-applicaties, wat de gebruikerservaring en productiviteit verbetert.
## Veelgestelde vragen
### Is Groupdocs.Viewer voor .NET compatibel met alle documentformaten?
Groupdocs.Viewer voor .NET ondersteunt een breed scala aan documentindelingen, waaronder PDF, Microsoft Office-documenten, afbeeldingen en meer.
### Kan ik het uiterlijk van de weergegeven documentpagina's aanpassen?
Ja, u kunt verschillende aspecten van het renderproces aanpassen, zoals de paginagrootte, kwaliteit, watermerken en meer.
### Heeft Groupdocs.Viewer voor .NET een internetverbinding nodig?
Nee, Groupdocs.Viewer voor .NET werkt lokaal binnen uw .NET-omgeving en vereist geen internetverbinding om documenten te bekijken.
### Is er technische ondersteuning beschikbaar voor Groupdocs.Viewer voor .NET?
Ja, technische ondersteuning is beschikbaar via de [Groupdocs-forum](https://forum.groupdocs.com/c/viewer/9), waar u vragen kunt stellen, problemen kunt melden en met de community kunt communiceren.
### Kan ik Groupdocs.Viewer voor .NET uitproberen voordat ik het koop?
Ja, u kunt beginnen met een gratis proefperiode met behulp van de meegeleverde [proefversie](https://releases.groupdocs.com/).