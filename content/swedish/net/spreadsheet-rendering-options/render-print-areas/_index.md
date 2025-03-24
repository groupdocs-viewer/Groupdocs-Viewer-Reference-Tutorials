---
title: Rendera utskriftsområden med GroupDocs.Viewer för .NET
linktitle: Rendera utskriftsområden
second_title: GroupDocs.Viewer .NET API
description: Utforska GroupDocs.Viewer för .NET och rendera utskriftsområden utan ansträngning i olika dokumentformat. Prova den kostnadsfria provperioden nu! #GroupDocs.Viewer
weight: 17
url: /sv/net/spreadsheet-rendering-options/render-print-areas/
---
## Introduktion
Välkommen till den här omfattande guiden om hur du använder GroupDocs.Viewer för .NET för att återge utskriftsområden i dina dokument. Om du är en .NET-utvecklare som letar efter en robust lösning för dokumentrendering, är du på rätt plats. I den här självstudien går vi igenom processen att rendera utskriftsområden med GroupDocs.Viewer, vilket säkerställer en sömlös upplevelse i dina applikationer.
## Förutsättningar
Innan du dyker in i handledningen, se till att du har följande förutsättningar på plats:
- En praktisk kunskap om C# och .NET utveckling.
-  GroupDocs.Viewer för .NET installerat. Du kan ladda ner den[här](https://releases.groupdocs.com/viewer/net/).
- Ett exempeldokument (t.ex. "SAMPLE.XLSX") i din angivna dokumentkatalog.
## Importera namnområden
Se till att importera de nödvändiga namnrymden i din C#-kod för korrekt implementering:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Steg 1: Konfigurera dokumentkatalogen
Börja med att ange utdatakatalogen för de renderade HTML-sidorna:
```csharp
string outputDirectory = "Your Document Directory";
```
## Steg 2: Definiera sidfilssökvägsformat
Skapa ett format för sidfilens sökvägar, kombinera utdatakatalogen och en platshållare för sidnumret:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Steg 3: Initiera GroupDocs.Viewer
Instantiera Viewer-klassen med sökvägen till ditt exempeldokument:
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
```
## Steg 4: Konfigurera HTML-vyalternativ
Konfigurera HTML-vyalternativ, ange sökvägsformat för sidan och aktivera alternativ för att rendera utskriftsområden:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.SpreadsheetOptions = SpreadsheetOptions.ForRenderingPrintArea();
```
## Steg 5: Gör dokumentet
 Åberopa`View` metod för att rendera dokumentet med de angivna alternativen:
```csharp
viewer.View(options);
```
## Steg 6: Visa framgångsmeddelande
Skriv ut ett framgångsmeddelande som indikerar att källdokumentet har renderats:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du använder GroupDocs.Viewer för .NET för att återge utskriftsområden i dina dokument. Detta kraftfulla verktyg öppnar upp nya möjligheter för dokumentrendering i dina .NET-applikationer.
## Vanliga frågor
### Är GroupDocs.Viewer kompatibel med olika dokumentformat?
 Ja, GroupDocs.Viewer stöder ett brett utbud av dokumentformat, inklusive PDF, DOCX, XLSX och mer. Referera till[dokumentation](https://tutorials.groupdocs.com/viewer/net/) för en komplett lista.
### Kan jag prova GroupDocs.Viewer innan jag köper?
 Absolut! Du kan utforska verktyget med en gratis provperiod tillgänglig[här](https://releases.groupdocs.com/).
### Var kan jag hitta support eller söka hjälp för eventuella problem?
 Besök[GroupDocs.Viewer-forum](https://forum.groupdocs.com/c/viewer/9)att få kontakt med samhället och få hjälp.
### Finns det ett tillfälligt licensalternativ?
 Ja, du kan få en tillfällig licens[här](https://purchase.groupdocs.com/temporary-license/).
### Var kan jag köpa GroupDocs.Viewer för .NET?
 Du kan göra ditt köp[här](https://purchase.groupdocs.com/buy).