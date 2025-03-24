---
title: Rendering annuleren met annuleringstoken
linktitle: Rendering annuleren met annuleringstoken
second_title: GroupDocs.Viewer .NET-API
description: Integreer Groupdocs.Viewer voor .NET naadloos in uw .NET-projecten voor efficiënte documentweergave.
weight: 11
url: /nl/net/rendering-options/cancel-render-cancellation-token/
---

# Rendering annuleren met annuleringstoken

## Invoering
Groupdocs.Viewer voor .NET is een krachtig hulpmiddel dat is ontworpen om het bekijken en verwerken van documenten binnen .NET-toepassingen te vereenvoudigen. Of u nu te maken heeft met PDF's, Microsoft Office-documenten of andere veelgebruikte formaten, deze bibliotheek biedt robuuste functionaliteit om de weergavemogelijkheden van documenten naadloos te integreren in uw .NET-projecten.
## Vereisten
Voordat u zich verdiept in de integratie van Groupdocs.Viewer voor .NET, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1.  Installatie: Download en installeer de Groupdocs.Viewer voor .NET-bibliotheek uit de meegeleverde bibliotheek[download link](https://releases.groupdocs.com/viewer/net/).
   
2.  Licentie: Verkrijg een licentie van[Groepsdocumenten](https://purchase.groupdocs.com/buy) om het volledige potentieel van de bibliotheek te ontsluiten. Als alternatief kunt u beginnen met een gratis proefperiode via de[tijdelijke licentie](https://purchase.groupdocs.com/temporary-license/).
   
3. Ontwikkelomgeving: Zorg ervoor dat u een compatibele ontwikkelomgeving hebt ingesteld, inclusief Visual Studio of een andere .NET IDE van uw keuze.

## Naamruimten importeren
Om Groupdocs.Viewer voor .NET effectief te kunnen gebruiken, moet u de benodigde naamruimten in uw project importeren. Volg deze stappen:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Laten we nu het gegeven voorbeeld opsplitsen in meerdere stappen voor een beter begrip en implementatie:
## Stap 1: Definieer de uitvoerdirectory
```csharp
string outputDirectory = "Your Document Directory";
```
Met deze stap wordt de map ingesteld waar de gerenderde documentpagina's worden opgeslagen.
## Stap 2: Definieer het paginabestandspadformaat
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Hier definiëren we het formaat voor de bestandspaden van afzonderlijke documentpagina's.
## Stap 3: Initialiseer CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource wordt gebruikt om CancellationToken-instanties te genereren die kunnen worden gebruikt om asynchrone bewerkingen te annuleren.
## Stap 4: Verkrijg CancellationToken
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
Met deze stap wordt het token opgehaald uit de CancellationTokenSource, dat wordt gebruikt om de weergavebewerking te annuleren.
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
Hier starten we de weergave van documentpagina's asynchroon met behulp van Task.Run(). De Viewer-instantie wordt gemaakt met het opgegeven documentbestand (SAMPLE_DOCX) en de weergaveopties worden geconfigureerd. Het weergaveproces wordt vervolgens gestart met behulp van de View-methode van de Viewer-klasse.
## Stap 6: Stel de rendertime-out in
```csharp
cancellationTokenSource.CancelAfter(10);
```
Met deze stap wordt een time-out van 10 milliseconden ingesteld voor de weergavebewerking. Als de bewerking deze time-out overschrijdt, wordt deze automatisch geannuleerd.
## Stap 7: Succesbericht weergeven
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Ten slotte wordt een succesbericht weergegeven dat aangeeft dat het document met succes is weergegeven.

## Conclusie
In deze zelfstudie hebben we de basisbeginselen besproken van het integreren van Groupdocs.Viewer voor .NET in uw projecten. Door de hierboven beschreven stappen te volgen, kunt u de mogelijkheden voor documentweergave naadloos integreren in uw .NET-toepassingen, waardoor de gebruikerservaring en productiviteit worden verbeterd.
## Veelgestelde vragen
### Is Groupdocs.Viewer voor .NET compatibel met alle documentformaten?
Groupdocs.Viewer voor .NET ondersteunt een breed scala aan documentformaten, waaronder PDF, Microsoft Office-documenten, afbeeldingen en meer.
### Kan ik het uiterlijk van de weergegeven documentpagina's aanpassen?
Ja, u kunt verschillende aspecten van het weergaveproces aanpassen, waaronder paginaformaat, kwaliteit, watermerken en meer.
### Heeft Groupdocs.Viewer voor .NET een internetverbinding nodig?
Nee, Groupdocs.Viewer voor .NET werkt lokaal binnen uw .NET-omgeving en vereist geen internetverbinding om documenten te bekijken.
### Is er technische ondersteuning beschikbaar voor Groupdocs.Viewer voor .NET?
 Ja, technische ondersteuning is beschikbaar via de[Groupdocs-forum](https://forum.groupdocs.com/c/viewer/9), waar u vragen kunt stellen, problemen kunt melden en kunt communiceren met de community.
### Kan ik Groupdocs.Viewer voor .NET uitproberen voordat ik het aanschaf?
 Ja, u kunt beginnen met een gratis proefperiode met behulp van de meegeleverde versie[probeerversie](https://releases.groupdocs.com/).