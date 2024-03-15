---
title: Få kalkylbladsnamn
linktitle: Få kalkylbladsnamn
second_title: GroupDocs.Viewer .NET API
description: Utforska magin med GroupDocs.Viewer för .NET – integrera dokumentvisning sömlöst i dina applikationer. Prova den kostnadsfria provperioden nu!
type: docs
weight: 11
url: /sv/net/spreadsheet-rendering-options/get-worksheets-names/
---
## Introduktion
Välkommen till den fascinerande världen av GroupDocs.Viewer för .NET! Om du är en utvecklare eller entusiast som är sugen på att utforska kraftfulla dokumentvisningsmöjligheter i dina .NET-applikationer, har du en njutning. I den här omfattande guiden kommer vi att fördjupa oss i krångligheterna med att hämta kalkylbladsnamn med GroupDocs.Viewer. Så spänn fast säkerhetsbältet och låt oss ge oss ut på denna spännande resa!
## Förutsättningar
Innan vi dyker in i kodningsmagin, låt oss se till att du har allt konfigurerat:
1.  Installera GroupDocs.Viewer för .NET: Gå över till[nedladdningslänk](https://releases.groupdocs.com/viewer/net/)för att hämta den senaste versionen av GroupDocs.Viewer för .NET. Följ installationsinstruktionerna för att integrera den sömlöst i din utvecklingsmiljö.
2. Förbered ditt dokument: Se till att du har ett måldokument, låt oss säga en Excel-fil med namnet "file.xlsx," i din utsedda dokumentkatalog.
## Importera namnområden
Nu när du har förutsättningarna på plats, låt oss börja med att importera de nödvändiga namnrymden. Detta säkerställer att din applikation känner igen och kan använda funktionerna som tillhandahålls av GroupDocs.Viewer för .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## 1. Konfigurera dokumentkatalogen
```csharp
string outputDirectory = "Your Document Directory";
```
Ersätt "Din dokumentkatalog" med sökvägen till katalogen där ditt måldokument finns.
## 2. Initiera Viewer
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
I det här steget skapar vi en instans av Viewer-klassen och ger sökvägen till din Excel-fil.
## 3. Konfigurera vyinformationsalternativ
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
Här konfigurerar vi ViewInfoOptions för att generera HTML-vyer och ställer in ytterligare alternativ för kalkylbladsrendering.
## 4. Hämta vyinformation
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
Använd Viewer-instansen för att hämta vyinformation baserat på de konfigurerade alternativen.
## 5. Visa arbetsbladsnamn
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
Gå igenom de hämtade sidorna och skriv ut namnet på varje kalkylblad till konsolen.
## Slutsats
Grattis! Du har framgångsrikt navigerat genom processen att hämta kalkylbladsnamn med GroupDocs.Viewer för .NET. Detta öppnar upp en myriad av möjligheter för att förbättra dokumentvisningsfunktionerna i dina applikationer.
## Vanliga frågor
### Kan jag använda GroupDocs.Viewer för .NET med andra dokumentformat?
Absolut! GroupDocs.Viewer stöder ett brett utbud av dokumentformat, inklusive PDF, Microsoft Office och mer.
### Finns det en gratis provperiod?
 Ja, du kan utforska GroupDocs.Viewer för .NET med vår[gratis provperiod](https://releases.groupdocs.com/).
### Var kan jag hitta ytterligare support?
 Gå till[GroupDocs.Viewer-forum](https://forum.groupdocs.com/c/viewer/9) för samhällsstöd och diskussioner.
### Kan jag få en tillfällig licens?
 Säkert! Besök[den här länken](https://purchase.groupdocs.com/temporary-license/) för att få din tillfälliga licens.
### Finns det detaljerade dokumentationsresurser tillgängliga?
 Absolut! Kolla in[officiell dokumentation](https://reference.groupdocs.com/viewer/net/) för djupgående information och guider.