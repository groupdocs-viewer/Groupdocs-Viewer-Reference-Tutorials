---
title: Byt namn på e-postfält under rendering
linktitle: Byt namn på e-postfält under rendering
second_title: GroupDocs.Viewer .NET API
description: Förbättra dokumentvisningsupplevelsen med GroupDocs.Viewer för .NET. Återge och anpassa e-postmeddelanden sömlöst.
weight: 12
url: /sv/net/rendering-email-messages/rename-email-fields/
---

# Byt namn på e-postfält under rendering

## Introduktion

dagens digitala tidsålder är hantering och visning av dokument effektivt av största vikt för både företag och privatpersoner. Oavsett om det är kontrakt, rapporter eller e-postmeddelanden, kan produktiviteten förbättras avsevärt genom att ha möjligheten att navigera genom dessa dokument sömlöst. Det är här GroupDocs.Viewer för .NET kommer in i bilden. Detta kraftfulla bibliotek tillåter utvecklare att integrera dokumentvisningsmöjligheter direkt i sina .NET-applikationer, och erbjuder ett brett utbud av funktioner för att rendera olika dokumentformat.

## Förutsättningar

Innan du dyker in i handledningen om att byta namn på e-postfält under rendering med GroupDocs.Viewer för .NET, se till att du har följande förutsättningar:

1.  GroupDocs.Viewer for .NET Library: Ladda ner och installera GroupDocs.Viewer for .NET-biblioteket från[här](https://releases.groupdocs.com/viewer/net/).

2. Utvecklingsmiljö: Se till att du har en lämplig utvecklingsmiljö inställd för .NET-utveckling, som Visual Studio.

3. Grundläggande förståelse för C#: Bekanta dig med grunderna i programmeringsspråket C# eftersom handledningen kommer att involvera C#-kodsnuttar.

4. Dokumentkatalog: Förbered en katalog där dokumenten som ska renderas lagras.

## Importera namnområden

För att kunna använda GroupDocs.Viewer-funktioner i din .NET-applikation måste du importera de nödvändiga namnrymden.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Låt oss nu dela upp processen att byta namn på e-postfält under rendering med GroupDocs.Viewer för .NET i flera steg:

## Steg 1: Definiera utdatakatalog

Ange först katalogen där de renderade HTML-sidorna ska sparas.

```csharp
string outputDirectory = "Your Document Directory";
```

## Steg 2: Definiera sidfilssökvägsformat

Definiera formatet för filsökvägarna för de renderade HTML-sidorna. Varje sida kommer att sparas som en separat HTML-fil.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## Steg 3: Initiera Viewer Object

Skapa en instans av klassen Viewer och skicka sökvägen till dokumentet som ska visas som en parameter.

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
{
```

## Steg 4: Konfigurera HTML-vyalternativ

Konfigurera alternativen för HTML-vyn, inklusive att ange utdatafilformatet och ställa in e-postfältmappningar.

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.EmailOptions.FieldTextMap[Field.From] = "Sender";
options.EmailOptions.FieldTextMap[Field.To] = "Receiver";
options.EmailOptions.FieldTextMap[Field.Sent] = "Date";
options.EmailOptions.FieldTextMap[Field.Subject] = "Topic";
```

## Steg 5: Gör dokumentet

Anropa View-metoden för Viewer-objektet och skicka de konfigurerade HTML-vyalternativen.

```csharp
viewer.View(options);
```

## Steg 6: Visa framgångsmeddelande

Informera användaren om att dokumentet har renderats.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Slutsats

Sammanfattningsvis erbjuder GroupDocs.Viewer för .NET en sömlös lösning för att rendera dokument i .NET-applikationer. Genom att följa stegen som beskrivs i denna handledning kan du enkelt byta namn på e-postfält under renderingen, vilket förbättrar läsbarheten och användbarheten av e-postdokument. Med sitt intuitiva API och omfattande funktioner ger GroupDocs.Viewer utvecklare möjlighet att effektivisera processer för dokumentvisning på ett effektivt sätt.

## FAQ's

### F: Kan jag rendera andra dokument än e-postmeddelanden med GroupDocs.Viewer för .NET?

S: Ja, GroupDocs.Viewer stöder rendering av olika dokumentformat inklusive PDF, Microsoft Office-dokument, bilder och mer.

### F: Är GroupDocs.Viewer kompatibel med .NET Core?

S: Ja, GroupDocs.Viewer stöder .NET Core tillsammans med det traditionella .NET Framework.

### F: Kan jag anpassa utseendet på renderade dokument?

S: Absolut, GroupDocs.Viewer erbjuder omfattande anpassningsalternativ för att kontrollera utseendet och beteendet hos renderade dokument.

### F: Stöder GroupDocs.Viewer streaming av dokument?

S: Ja, GroupDocs.Viewer tillåter streaming av dokument direkt till klientens webbläsare utan att behöva lagra dem på servern.

### F: Är GroupDocs.Viewer lämplig för applikationer på företagsnivå?

S: Visst är GroupDocs.Viewer designad för att möta kraven från applikationer på företagsnivå med dess skalbarhet, tillförlitlighet och robusta funktionsuppsättning.
