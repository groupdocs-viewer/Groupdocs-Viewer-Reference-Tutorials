---
title: Time-out voor het laden van bronnen instellen (geavanceerd)
linktitle: Time-out voor het laden van bronnen instellen (geavanceerd)
second_title: GroupDocs.Viewer .NET-API
description: Leer hoe u time-outs voor het laden van bronnen in GroupDocs.Viewer voor .NET efficiënt configureert. Master documentweergave met precisie en stabiliteit.
weight: 13
url: /nl/net/advanced-loading/set-resource-loading-timeout/
---

# Time-out voor het laden van bronnen instellen (geavanceerd)

## Invoering
Op het gebied van .NET-ontwikkeling biedt GroupDocs.Viewer een krachtige toolset voor het nauwkeurig en efficiënt weergeven van documenten en afbeeldingen. Om de mogelijkheden ervan te kunnen benutten, is inzicht nodig in de complexiteit ervan, inclusief het instellen van time-outs voor het laden van bronnen. In deze zelfstudie gaan we in op het proces van het configureren van time-outs voor het laden van bronnen in GroupDocs.Viewer voor .NET.
## Vereisten
Voordat u aan deze zelfstudie begint, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. Basiskennis van .NET-ontwikkeling: Bekendheid met C#-programmeren en de fundamenten van het .NET-framework is essentieel.
2.  Installatie van GroupDocs.Viewer voor .NET: Download en installeer de GroupDocs.Viewer voor .NET-bibliotheek vanaf de[downloadpagina](https://releases.groupdocs.com/viewer/net/).
3. Integrated Development Environment (IDE): Zorg ervoor dat een IDE zoals Visual Studio op uw systeem is geïnstalleerd.

## Naamruimten importeren
Voordat u in het codeerproces duikt, importeert u de benodigde naamruimten:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Stap 1: Definieer de uitvoerdirectory
Definieer eerst de map waar de weergegeven documenten zullen worden opgeslagen:
```csharp
string outputDirectory = "Your Document Directory";
```
 Vervangen`"Your Document Directory"`met het pad waar u de gerenderde documenten wilt opslaan.
## Stap 2: Definieer het paginabestandspadformaat
Definieer het formaat voor de bestandspaden van afzonderlijke pagina's:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Dit formaat genereert bestandsnamen zoals`page_1.html`, `page_2.html`, enz., binnen de opgegeven uitvoermap.
## Stap 3: Laadopties configureren
Configureer de laadopties, inclusief de time-out voor het laden van bronnen:
```csharp
LoadOptions loadOptions = new LoadOptions
{
    ResourceLoadingTimeout = TimeSpan.FromSeconds(5)
};
```
In dit voorbeeld is een time-out van 5 seconden ingesteld voor het laden van bronnen.
## Stap 4: Initialiseer het Viewer-object
 Initialiseer de`Viewer` object met het te renderen document en de gedefinieerde laadopties:
```csharp
using (Viewer viewer = new Viewer(TestFiles.WITH_EXTERNAL_IMAGE_DOC, loadOptions))
```
 Vervangen`TestFiles.WITH_EXTERNAL_IMAGE_DOC` met het pad naar het document dat u wilt weergeven.
## Stap 5: Configureer HTML-weergaveopties
Configureer HTML-weergaveopties voor ingesloten bronnen:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Deze configuratie zorgt ervoor dat ingebedde bronnen zoals afbeeldingen worden opgenomen in de weergegeven HTML.
## Stap 6: Document renderen
Render het document met behulp van de geconfigureerde opties:
```csharp
viewer.View(options);
```
Met deze stap wordt het weergaveproces gestart.
## Stap 7: Geef de uitvoerdirectory weer
Geef een bericht weer dat de succesvolle weergave en de locatie van de uitvoermap aangeeft:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusie
Het beheersen van time-outs bij het laden van bronnen in GroupDocs.Viewer voor .NET is van cruciaal belang voor het garanderen van soepele documentweergaveprocessen. Door deze zelfstudie te volgen, heeft u inzicht gekregen in het effectief configureren van time-outs, waardoor uw vaardigheid in .NET-ontwikkeling wordt vergroot.
## Veelgestelde vragen
### Wat is de betekenis van het instellen van time-outs voor het laden van bronnen?
Het instellen van time-outs voor het laden van bronnen zorgt ervoor dat weergaveprocessen niet voor onbepaalde tijd blijven hangen, waardoor de stabiliteit van de applicatie wordt verbeterd.
### Kunnen time-outs voor het laden van bronnen worden aangepast op basis van documenttypen?
Ja, time-outs voor het laden van bronnen kunnen worden aangepast op basis van de complexiteit en grootte van de documenten die worden weergegeven.
### Zijn er gevolgen voor de prestaties als u kortere time-outs instelt?
Kortere time-outs kunnen leiden tot onvolledige weergave van complexe documenten als bronnen niet binnen de opgegeven tijdsduur kunnen worden geladen.
### Is GroupDocs.Viewer geschikt voor het weergeven van verschillende documentformaten?
Ja, GroupDocs.Viewer ondersteunt het weergeven van een breed scala aan documentformaten, waaronder PDF, DOCX, XLSX en meer.
### Kunnen time-outs voor het laden van bronnen worden uitgeschakeld?
Hoewel het niet wordt aanbevolen, kunnen time-outs voor het laden van bronnen op een hoge waarde worden ingesteld of helemaal worden uitgeschakeld, afhankelijk van specifieke vereisten.