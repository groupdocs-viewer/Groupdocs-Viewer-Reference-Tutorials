---
"description": "Utforska magin hos GroupDocs.Viewer för .NET – integrera dokumentvisning sömlöst i dina applikationer. Prova den kostnadsfria testversionen nu!"
"linktitle": "Hämta namn på arbetsblad"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Hämta namn på arbetsblad"
"url": "/sv/net/spreadsheet-rendering-options/get-worksheets-names/"
"weight": 11
---

# Hämta namn på arbetsblad

## Introduktion
Välkommen till GroupDocs.Viewers fascinerande värld för .NET! Om du är en utvecklare eller entusiast som vill utforska kraftfulla dokumentvisningsfunktioner i dina .NET-applikationer, har du något att vänta dig. I den här omfattande guiden går vi in på hur man hämtar kalkylbladsnamn med GroupDocs.Viewer. Så, spänn fast säkerhetsbältet och låt oss ge oss ut på denna spännande resa!
## Förkunskapskrav
Innan vi dyker in i kodningsmagin, låt oss se till att du har allt konfigurerat:
1. Installera GroupDocs.Viewer för .NET: Gå till [nedladdningslänk](https://releases.groupdocs.com/viewer/net/) för att hämta den senaste versionen av GroupDocs.Viewer för .NET. Följ installationsanvisningarna för att integrera den sömlöst i din utvecklingsmiljö.
2. Förbered ditt dokument: Se till att du har ett måldokument, låt oss säga en Excel-fil med namnet "file.xlsx", i din angivna dokumentkatalog.
## Importera namnrymder
Nu när du har förutsättningarna på plats kan vi sätta igång genom att importera de nödvändiga namnrymderna. Detta säkerställer att din applikation känner igen och kan använda funktionerna som tillhandahålls av GroupDocs.Viewer för .NET.
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
## 2. Initiera visaren
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
I det här steget skapar vi en instans av Viewer-klassen och anger sökvägen till din Excel-fil.
## 3. Konfigurera alternativ för visning av information
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
Här konfigurerar vi ViewInfoOptions för att generera HTML-vyer och anger ytterligare alternativ för kalkylbladsrendering.
## 4. Hämta vyinformation
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
Använd Viewer-instansen för att hämta vyinformation baserat på de konfigurerade alternativen.
## 5. Visa namn på arbetsblad
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
Bläddra igenom de hämtade sidorna och skriv ut namnet på varje kalkylblad till konsolen.
## Slutsats
Grattis! Du har nu lyckats navigera dig igenom processen att hämta kalkylbladsnamn med GroupDocs.Viewer för .NET. Detta öppnar upp en mängd möjligheter för att förbättra dokumentvisningsfunktionerna i dina applikationer.
## Vanliga frågor
### Kan jag använda GroupDocs.Viewer för .NET med andra dokumentformat?
Absolut! GroupDocs.Viewer stöder en mängd olika dokumentformat, inklusive PDF, Microsoft Office och mer.
### Finns det en gratis provperiod tillgänglig?
Ja, du kan utforska GroupDocs.Viewer för .NET med vår [gratis provperiod](https://releases.groupdocs.com/).
### Var kan jag hitta ytterligare stöd?
Gå till [GroupDocs.Viewer-forum](https://forum.groupdocs.com/c/viewer/9) för stöd och diskussioner i samhället.
### Kan jag få en tillfällig licens?
Absolut! Besök [den här länken](https://purchase.groupdocs.com/temporary-license/) för att få ditt tillfälliga körkort.
### Finns det detaljerade dokumentationsresurser tillgängliga?
Absolut! Kolla in [officiell dokumentation](https://tutorials.groupdocs.com/viewer/net/) för djupgående information och guider.