---
"description": "Förbättra dokumentvisningsupplevelsen med GroupDocs.Viewer för .NET. Rendera och anpassa e-postmeddelanden sömlöst."
"linktitle": "Byt namn på e-postfält under rendering"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Byt namn på e-postfält under rendering"
"url": "/sv/net/rendering-email-messages/rename-email-fields/"
"weight": 12
type: docs
---
# Byt namn på e-postfält under rendering

## Introduktion

I dagens digitala tidsålder är det av yttersta vikt för både företag och privatpersoner att hantera och visa dokument effektivt. Oavsett om det gäller kontrakt, rapporter eller e-postmeddelanden kan möjligheten att navigera igenom dessa dokument sömlöst öka produktiviteten avsevärt. Det är här GroupDocs.Viewer för .NET kommer in i bilden. Detta kraftfulla bibliotek låter utvecklare integrera dokumentvisningsfunktioner direkt i sina .NET-applikationer och erbjuder ett brett utbud av funktioner för att rendera olika dokumentformat.

## Förkunskapskrav

Innan du går in i handledningen om att byta namn på e-postfält under rendering med GroupDocs.Viewer för .NET, se till att du har följande förutsättningar:

1. GroupDocs.Viewer för .NET-biblioteket: Ladda ner och installera GroupDocs.Viewer för .NET-biblioteket från [här](https://releases.groupdocs.com/viewer/net/).

2. Utvecklingsmiljö: Se till att du har en lämplig utvecklingsmiljö konfigurerad för .NET-utveckling, till exempel Visual Studio.

3. Grundläggande förståelse för C#: Bekanta dig med grunderna i programmeringsspråket C# eftersom handledningen kommer att innehålla kodavsnitt i C#.

4. Dokumentkatalog: Förbered en katalog där de dokument som ska renderas lagras.

## Importera namnrymder

För att kunna använda GroupDocs.Viewer-funktioner i din .NET-applikation måste du importera nödvändiga namnrymder.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nu ska vi dela upp processen att byta namn på e-postfält under rendering med GroupDocs.Viewer för .NET i flera steg:

## Steg 1: Definiera utdatakatalog

Först, ange katalogen där de renderade HTML-sidorna ska sparas.

```csharp
string outputDirectory = "Your Document Directory";
```

## Steg 2: Definiera format för sidfilens sökväg

Definiera formatet för sökvägarna till de renderade HTML-sidorna. Varje sida sparas som en separat HTML-fil.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Steg 3: Initiera visningsobjektet

Skapa en instans av Viewer-klassen och ange sökvägen till det dokument som ska visas som en parameter.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
{
```

## Steg 4: Konfigurera HTML-visningsalternativ

Konfigurera alternativen för HTML-vyn, inklusive att ange utdatafilformatet och konfigurera mappningar av e-postfält.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.EmailOptions.FieldTextMap[Field.From] = "Sender";
options.EmailOptions.FieldTextMap[Field.To] = "Receiver";
options.EmailOptions.FieldTextMap[Field.Sent] = "Date";
options.EmailOptions.FieldTextMap[Field.Subject] = "Topic";
```

## Steg 5: Rendera dokument

Anropa View-metoden för Viewer-objektet och skicka de konfigurerade HTML-visningsalternativen.

```csharp
viewer.View(options);
```

## Steg 6: Visa meddelande om framgång

Informera användaren om att dokumentet har renderats.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Slutsats

Sammanfattningsvis erbjuder GroupDocs.Viewer för .NET en sömlös lösning för att rendera dokument inom .NET-applikationer. Genom att följa stegen som beskrivs i den här handledningen kan du enkelt byta namn på e-postfält under rendering, vilket förbättrar läsbarheten och användbarheten hos e-postdokument. Med sitt intuitiva API och omfattande funktioner ger GroupDocs.Viewer utvecklare möjlighet att effektivisera dokumentvisningsprocesser.

## Vanliga frågor

### F: Kan jag rendera andra dokument än e-postmeddelanden med GroupDocs.Viewer för .NET?

A: Ja, GroupDocs.Viewer stöder rendering av olika dokumentformat, inklusive PDF, Microsoft Office-dokument, bilder och mer.

### F: Är GroupDocs.Viewer kompatibel med .NET Core?

A: Ja, GroupDocs.Viewer stöder .NET Core tillsammans med det traditionella .NET Framework.

### F: Kan jag anpassa utseendet på renderade dokument?

A: Absolut, GroupDocs.Viewer erbjuder omfattande anpassningsalternativ för att kontrollera utseendet och beteendet hos renderade dokument.

### F: Har GroupDocs.Viewer stöd för dokumentströmning?

A: Ja, GroupDocs.Viewer tillåter direktströmning av dokument till klientens webbläsare utan att de behöver lagras på servern.

### F: Är GroupDocs.Viewer lämplig för applikationer på företagsnivå?

A: GroupDocs.Viewer är definitivt utformad för att möta kraven från applikationer på företagsnivå med sin skalbarhet, tillförlitlighet och robusta funktionsuppsättning.