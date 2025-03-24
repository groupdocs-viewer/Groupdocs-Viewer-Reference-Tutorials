---
title: Ställ in datum- och tidsformat och tidszonförskjutning (e-post)
linktitle: Ställ in datum- och tidsformat och tidszonförskjutning (e-post)
second_title: GroupDocs.Viewer .NET API
description: Integrera GroupDocs.Viewer för .NET sömlöst i dina applikationer för kraftfulla dokumentvisningsmöjligheter. Förbättra användarupplevelsen med anpassningsbara alternativ.
weight: 11
url: /sv/net/rendering-email-messages/set-date-time-format-offset-email/
---

## Introduktion
GroupDocs.Viewer för .NET är ett kraftfullt verktyg som gör det möjligt för utvecklare att sömlöst integrera dokumentvisningsmöjligheter i sina .NET-applikationer. Med GroupDocs.Viewer kan du visa ett brett utbud av dokumentformat inklusive PDF-filer, Microsoft Office-dokument, bilder och mer direkt i din applikation, utan att behöva använda några externa plugins eller tittare. I den här omfattande självstudien guidar vi dig genom processen att ställa in GroupDocs.Viewer för .NET, utforska dess funktioner och demonstrera hur du använder den effektivt för att förbättra din applikations dokumentvisningsmöjligheter.
## Förutsättningar
Innan du dyker in i denna handledning, se till att du har följande förutsättningar inställda:
1. Visual Studio: Se till att du har Visual Studio installerat på ditt system. GroupDocs.Viewer för .NET är helt kompatibel med Visual Studio, vilket möjliggör sömlös integrering i dina .NET-projekt.
2.  GroupDocs.Viewer för .NET: Ladda ner och installera GroupDocs.Viewer för .NET från[nedladdningslänk](https://releases.groupdocs.com/viewer/net/). Följ installationsinstruktionerna för att ställa in biblioteket i din utvecklingsmiljö.
3. .NET Framework: Se till att du har rätt version av .NET Framework installerad. GroupDocs.Viewer för .NET stöder olika versioner av .NET Framework, inklusive .NET Core och .NET Standard.

## Importera namnområden
För att kunna använda GroupDocs.Viewer för .NET effektivt måste du importera de nödvändiga namnrymden till ditt projekt. Följ dessa steg för att importera de nödvändiga namnrymden:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


Låt oss dela upp exemplet i flera steg för att förstå varje komponent och dess funktionalitet.
## Steg 1: Ställ in utdatakatalog och filsökväg
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
I det här steget definierar vi utdatakatalogen där det renderade dokumentet ska sparas och anger filsökvägen för utdata-HTML-filen.
## Steg 2: Instantiera Viewer Object
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
 Här skapar vi en ny instans av`Viewer` klass och skickar sökvägen till dokumentet som ska visas (i det här fallet en EML-exempelfil) som en parameter.
## Steg 3: Definiera HTML-vyalternativ
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
det här steget konfigurerar vi HTML-vyalternativen för dokumentrenderingen, och anger utdatafilens sökväg för det renderade HTML-dokumentet.
## Steg 4: Ställ in DateTime Format och Time Zone Offset
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Här anpassar vi datum- och tidsformatet för e-postmeddelanden och ställer in tidszonsförskjutningen enligt önskad tidszon.
## Steg 5: Gör dokumentet
```csharp
viewer.View(options);
```
 Slutligen kallar vi`View` metod för`Viewer` objekt och skickar de konfigurerade HTML-vyalternativen för att rendera dokumentet till HTML-format.
## Steg 6: Visa utdatakatalog
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Det här steget visar helt enkelt ett meddelande som indikerar framgångsrik rendering av dokumentet och ger sökvägen till utdatakatalogen där det renderade HTML-dokumentet finns.

## Slutsats
GroupDocs.Viewer för .NET erbjuder en robust lösning för att integrera dokumentvisningsmöjligheter i dina .NET-applikationer. Genom att följa stegen som beskrivs i den här handledningen kan du enkelt ställa in GroupDocs.Viewer, importera nödvändiga namnområden och använda dess funktioner för att rendera dokument med anpassningsbara alternativ. Oavsett om du arbetar med PDF-filer, Microsoft Office-dokument eller andra format, förenklar GroupDocs.Viewer processen för dokumentvisning, vilket förbättrar användarupplevelsen av dina applikationer.
## FAQ's
### Är GroupDocs.Viewer kompatibel med .NET Core?
Ja, GroupDocs.Viewer för .NET stöder .NET Core, vilket möjliggör plattformsoberoende kompatibilitet för dina applikationer.
### Kan jag anpassa utseendet på de renderade dokumenten?
Absolut! GroupDocs.Viewer erbjuder olika anpassningsalternativ inklusive zoomnivåer, sidrotation och mer för att skräddarsy visningsupplevelsen efter dina preferenser.
### Finns det en testversion tillgänglig för teständamål?
 Ja, du kan ladda ner en gratis testversion av GroupDocs.Viewer för .NET från[webbplatslänk](https://releases.groupdocs.com/viewer/net/) för att utvärdera dess funktioner innan du gör ett köp.
### Stöder GroupDocs.Viewer rendering av lösenordsskyddade dokument?
Ja, GroupDocs.Viewer har inbyggt stöd för att rendera lösenordsskyddade dokument, vilket säkerställer säker dokumentvisning i dina applikationer.
### Var kan jag hitta ytterligare support eller hjälp med GroupDocs.Viewer?
 För tekniska frågor eller hjälp kan du besöka GroupDocs.Viewer[forum](https://forum.groupdocs.com/c/viewer/9) eller kontakta deras supportteam för snabb hjälp och vägledning.