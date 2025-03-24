---
title: Ersätt saknad teckensnitt
linktitle: Ersätt saknad teckensnitt
second_title: GroupDocs.Viewer .NET API
description: Lär dig hur du ersätter saknade teckensnitt i .NET-dokument utan ansträngning med GroupDocs.Viewer. Säkerställ korrekt rendering med enkla steg.
weight: 20
url: /sv/net/rendering-options/replace-missing-font/
---

# Ersätt saknad teckensnitt

## Introduktion
I en värld av .NET-utveckling är effektiv dokumenthantering avgörande. GroupDocs.Viewer för .NET tillhandahåller en kraftfull lösning för att visa olika dokumentformat i dina .NET-applikationer. I den här handledningen kommer vi att utforska hur du använder GroupDocs.Viewer för .NET för att ersätta saknade teckensnitt i dokument. Oavsett om du har att göra med PDF-filer, PowerPoint-presentationer eller Word-dokument, förenklar GroupDocs.Viewer processen och säkerställer att dina dokument återges korrekt, även när teckensnitt saknas.
## Förutsättningar
Innan du dyker in i den här handledningen, se till att du har följande:
1. GroupDocs.Viewer för .NET: Ladda ner och installera GroupDocs.Viewer-biblioteket från webbplatsen](https://releases.groupdocs.com/viewer/net/).
2. Utvecklingsmiljö: Konfigurera en .NET-utvecklingsmiljö, till exempel Visual Studio.
3. Grundläggande C#-kunskaper: Bekantskap med C#-programmeringsspråk och .NET-ramverk.

## Importera namnområden
I din C#-kod, importera de nödvändiga namnrymden för att komma åt GroupDocs.Viewer-funktioner.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Låt oss nu gå igenom processen att ersätta saknade teckensnitt i dokument med GroupDocs.Viewer för .NET.
## Steg 1: Definiera utdatakatalog
```csharp
string outputDirectory = "Your Document Directory";
```
Ställ in katalogen där de renderade dokumentsidorna ska sparas.
## Steg 2: Definiera sidfilssökvägsformat
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Ange formatet för att namnge de utgående HTML-filerna. I det här exemplet kommer varje sida att sparas som en HTML-fil med namnkonventionen "page_{page_number}.html".
## Steg 3: Initiera Viewer Object
```csharp
using (Viewer viewer = new Viewer(TestFiles.MISSING_FONT_PPTX))
```
Initiera en ny instans av Viewer-klassen och skicka sökvägen till dokumentfilen (i det här fallet en PowerPoint-presentation med saknade teckensnitt) som en parameter.
## Steg 4: Ställ in HTML-vyalternativ
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.DefaultFontName = "Courier New";
```
Skapa en instans av HtmlViewOptions och konfigurera den för att bädda in resurser i HTML-utdata. Ange ett standardtypsnittsnamn som ska användas som ersättning för saknade teckensnitt.
## Steg 5: Gör dokumentet
```csharp
viewer.View(options);
```
Anropa View-metoden för Viewer-objektet och skicka HTML-vyalternativen. Detta kommer att återge dokumentsidorna med de angivna alternativen.
## Steg 6: Visa utdatasökväg
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Skriv ut ett meddelande som indikerar framgångsrik rendering av dokumentet och ange sökvägen där de utgående HTML-filerna sparas.

## Slutsats
I den här handledningen har vi lärt oss hur man använder GroupDocs.Viewer för .NET för att ersätta saknade teckensnitt i dokument. Genom att följa dessa steg kan du säkerställa att dina dokument återges korrekt, även när vissa teckensnitt inte är tillgängliga. GroupDocs.Viewer förenklar processen, så att du kan fokusera på att bygga robusta .NET-applikationer utan att behöva oroa dig för teckensnittskompatibilitetsproblem.
## FAQ's
### Kan GroupDocs.Viewer hantera andra typer av teckensnittsrelaterade problem?
Ja, GroupDocs.Viewer tillhandahåller olika teckensnittsrelaterade funktioner, inklusive teckensnittsersättning och teckensnittsidentifiering.
### Är GroupDocs.Viewer kompatibel med alla .NET-ramverk?
GroupDocs.Viewer stöder ett brett utbud av .NET-ramverk, inklusive .NET Core och .NET Standard.
### Kan jag anpassa standardtypsnittsersättningen i GroupDocs.Viewer?
Absolut, du kan ange valfritt typsnitt som standardersättning för saknade teckensnitt.
### Stöder GroupDocs.Viewer batchbehandling av dokument?
Ja, GroupDocs.Viewer låter dig bearbeta flera dokument samtidigt, vilket gör den idealisk för batchbearbetningsscenarier.
### Var kan jag hitta ytterligare hjälp eller support för GroupDocs.Viewer?
 Du kan besöka forumet GroupDocs.Viewer[här](https://forum.groupdocs.com/c/viewer/9) för hjälp eller supportfrågor.