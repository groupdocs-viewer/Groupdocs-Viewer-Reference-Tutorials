---
"description": "Integrera GroupDocs.Viewer för .NET sömlöst i dina applikationer för kraftfulla dokumentvisningsfunktioner. Förbättra användarupplevelsen med anpassningsbara alternativ."
"linktitle": "Ställ in datum- och tidsformat och tidszonsförskjutning (e-post)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Ställ in datum- och tidsformat och tidszonsförskjutning (e-post)"
"url": "/sv/net/rendering-email-messages/set-date-time-format-offset-email/"
"weight": 11
---

# Ställ in datum- och tidsformat och tidszonsförskjutning (e-post)


## Introduktion
GroupDocs.Viewer för .NET är ett kraftfullt verktyg som gör det möjligt för utvecklare att sömlöst integrera dokumentvisningsfunktioner i sina .NET-applikationer. Med GroupDocs.Viewer kan du visa en mängd olika dokumentformat, inklusive PDF-filer, Microsoft Office-dokument, bilder och mer direkt i din applikation, utan behov av externa plugin-program eller visningsprogram. I den här omfattande handledningen guidar vi dig genom processen att konfigurera GroupDocs.Viewer för .NET, utforskar dess funktioner och demonstrerar hur du använder det effektivt för att förbättra din applikations dokumentvisningsfunktioner.
## Förkunskapskrav
Innan du börjar med den här handledningen, se till att du har följande förutsättningar konfigurerade:
1. Visual Studio: Se till att du har Visual Studio installerat på ditt system. GroupDocs.Viewer för .NET är helt kompatibelt med Visual Studio, vilket möjliggör sömlös integration i dina .NET-projekt.
2. GroupDocs.Viewer för .NET: Ladda ner och installera GroupDocs.Viewer för .NET från [nedladdningslänk](https://releases.groupdocs.com/viewer/net/)Följ installationsanvisningarna för att konfigurera biblioteket i din utvecklingsmiljö.
3. .NET Framework: Se till att du har rätt version av .NET Framework installerad. GroupDocs.Viewer för .NET stöder olika versioner av .NET Framework, inklusive .NET Core och .NET Standard.

## Importera namnrymder
För att kunna använda GroupDocs.Viewer för .NET effektivt måste du importera de nödvändiga namnrymderna till ditt projekt. Följ dessa steg för att importera de nödvändiga namnrymderna:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


Låt oss dela upp det givna exemplet i flera steg för att förstå varje komponent och dess funktionalitet.
## Steg 1: Ange utdatakatalog och filsökväg
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
I det här steget definierar vi utdatakatalogen där det renderade dokumentet ska sparas och anger sökvägen för HTML-utdatafilen.
## Steg 2: Instansiera Viewer-objekt
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
Här skapar vi en ny instans av `Viewer` klass, och skickar sökvägen till det dokument som ska visas (i det här fallet en exempel-EML-fil) som en parameter.
## Steg 3: Definiera HTML-visningsalternativ
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
I det här steget konfigurerar vi HTML-visningsalternativen för dokumentrenderingen och anger sökvägen till utdatafilen för det renderade HTML-dokumentet.
## Steg 4: Ställ in datum- och tidsformat och tidszonsförskjutning
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Här anpassar vi datum- och tidsformatet för e-postmeddelanden och ställer in tidszonsförskjutningen enligt önskad tidszon.
## Steg 5: Rendera dokument
```csharp
viewer.View(options);
```
Slutligen kallar vi `View` metod för `Viewer` objektet och skickar de konfigurerade HTML-visningsalternativen för att rendera dokumentet i HTML-format.
## Steg 6: Visa utdatakatalogen
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Det här steget visar helt enkelt ett meddelande som anger att dokumentet har renderats och anger sökvägen till utdatakatalogen där det renderade HTML-dokumentet finns.

## Slutsats
GroupDocs.Viewer för .NET erbjuder en robust lösning för att integrera dokumentvisningsfunktioner i dina .NET-applikationer. Genom att följa stegen som beskrivs i den här handledningen kan du enkelt konfigurera GroupDocs.Viewer, importera nödvändiga namnrymder och använda dess funktioner för att rendera dokument med anpassningsbara alternativ. Oavsett om du arbetar med PDF-filer, Microsoft Office-dokument eller andra format förenklar GroupDocs.Viewer processen för dokumentvisning och förbättrar användarupplevelsen i dina applikationer.
## Vanliga frågor
### Är GroupDocs.Viewer kompatibel med .NET Core?
Ja, GroupDocs.Viewer för .NET stöder .NET Core, vilket möjliggör plattformsoberoende kompatibilitet för dina applikationer.
### Kan jag anpassa utseendet på de renderade dokumenten?
Absolut! GroupDocs.Viewer erbjuder olika anpassningsalternativ, inklusive zoomnivåer, sidrotation och mer, för att skräddarsy visningsupplevelsen efter dina handledningar.
### Finns det en testversion tillgänglig för teständamål?
Ja, du kan ladda ner en gratis testversion av GroupDocs.Viewer för .NET från [webbplatslänk](https://releases.groupdocs.com/viewer/net/) att utvärdera dess funktioner innan man gör ett köp.
### Har GroupDocs.Viewer stöd för rendering av lösenordsskyddade dokument?
Ja, GroupDocs.Viewer har inbyggt stöd för att rendera lösenordsskyddade dokument, vilket säkerställer säker dokumentvisning i dina applikationer.
### Var kan jag hitta ytterligare support eller hjälp med GroupDocs.Viewer?
För tekniska frågor eller hjälp kan du besöka GroupDocs.Viewer. [forum](https://forum.groupdocs.com/c/viewer/9) eller kontakta deras supportteam för snabb hjälp och vägledning.