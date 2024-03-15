---
title: Ange timeout för resursladdning (avancerat)
linktitle: Ange timeout för resursladdning (avancerat)
second_title: GroupDocs.Viewer .NET API
description: Lär dig hur du konfigurerar tidsgränser för resursladdning i GroupDocs.Viewer för .NET effektivt. Masterdokumentåtergivning med precision och stabilitet.
type: docs
weight: 13
url: /sv/net/advanced-loading/set-resource-loading-timeout/
---
## Introduktion
Inom .NET-utvecklingsområdet tillhandahåller GroupDocs.Viewer en kraftfull verktygsuppsättning för att rendera dokument och bilder med precision och effektivitet. Att utnyttja dess kapacitet kräver att du förstår dess krångligheter, inklusive att ställa in tidsgränser för resursladdning. I den här självstudien kommer vi att fördjupa oss i processen att konfigurera resursladdningstidsgränser i GroupDocs.Viewer för .NET.
## Förutsättningar
Innan du börjar med den här handledningen, se till att du har följande förutsättningar:
1. Grundläggande kunskaper om .NET-utveckling: Kännedom om C#-programmering och grunderna i .NET-ramverket är viktigt.
2.  Installation av GroupDocs.Viewer för .NET: Ladda ner och installera GroupDocs.Viewer för .NET-biblioteket från[nedladdningssida](https://releases.groupdocs.com/viewer/net/).
3. Integrated Development Environment (IDE): Ha en IDE som Visual Studio installerad på ditt system.

## Importera namnområden
Innan du dyker in i kodningsprocessen, importera de nödvändiga namnrymden:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Steg 1: Definiera utdatakatalog
Först definierar du katalogen där de renderade dokumenten ska sparas:
```csharp
string outputDirectory = "Your Document Directory";
```
 Byta ut`"Your Document Directory"`med sökvägen där du vill spara de renderade dokumenten.
## Steg 2: Definiera sidfilssökvägsformat
Definiera formatet för filsökvägarna för enskilda sidor:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
 Detta format kommer att generera filnamn som`page_1.html`, `page_2.html`, etc., inom den angivna utdatakatalogen.
## Steg 3: Konfigurera laddningsalternativ
Konfigurera laddningsalternativen, inklusive tidsgränsen för resursladdning:
```csharp
LoadOptions loadOptions = new LoadOptions
{
    ResourceLoadingTimeout = TimeSpan.FromSeconds(5)
};
```
I det här exemplet är en timeout på 5 sekunder inställd för resursladdning.
## Steg 4: Initiera Viewer Object
 Initiera`Viewer` objekt med dokumentet som ska renderas och de definierade laddningsalternativen:
```csharp
using (Viewer viewer = new Viewer(TestFiles.WITH_EXTERNAL_IMAGE_DOC, loadOptions))
```
 Byta ut`TestFiles.WITH_EXTERNAL_IMAGE_DOC` med sökvägen till dokumentet du vill rendera.
## Steg 5: Konfigurera HTML-vyalternativ
Konfigurera HTML-vyalternativ för inbäddade resurser:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
Denna konfiguration säkerställer att inbäddade resurser som bilder ingår i den renderade HTML-koden.
## Steg 6: Gör dokumentet
Återge dokumentet med de konfigurerade alternativen:
```csharp
viewer.View(options);
```
Detta steg initierar renderingsprocessen.
## Steg 7: Visa utdatakatalog
Visa ett meddelande som anger den lyckade renderingen och platsen för utdatakatalogen:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Slutsats
Att bemästra resursladdningstiden i GroupDocs.Viewer för .NET är avgörande för att säkerställa smidiga dokumentåtergivningsprocesser. Genom att följa den här handledningen har du fått insikter i hur du konfigurerar timeouts effektivt, vilket förbättrar dina kunskaper i .NET-utveckling.
## FAQ's
### Vad är betydelsen av att ställa in tidsgränser för resursladdning?
Att ställa in tidsgränser för resursladdning säkerställer att renderingsprocesserna inte hänger sig på obestämd tid, vilket förbättrar applikationsstabiliteten.
### Kan tidsgränser för resursladdning anpassas baserat på dokumenttyper?
Ja, tidsgränserna för resursladdning kan justeras baserat på komplexiteten och storleken på de dokument som renderas.
### Finns det några prestandakonsekvenser av att ställa in kortare timeouts?
Kortare tidsgränser kan leda till ofullständig rendering av komplexa dokument om resurser inte kan laddas inom den angivna varaktigheten.
### Är GroupDocs.Viewer lämplig för att rendera olika dokumentformat?
Ja, GroupDocs.Viewer stöder rendering av ett brett utbud av dokumentformat inklusive PDF, DOCX, XLSX och mer.
### Kan tidsgränser för resursladdning inaktiveras?
Även om det inte rekommenderas, kan tidsgränser för resursladdning ställas in på ett högt värde eller inaktiveras helt beroende på specifika krav.