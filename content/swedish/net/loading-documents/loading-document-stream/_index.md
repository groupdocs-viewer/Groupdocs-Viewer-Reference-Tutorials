---
"description": "Lär dig hur du sömlöst laddar dokument från strömmar med GroupDocs.Viewer för .NET. Förbättra dina .NET-applikationer med kraftfulla dokumentvisningsfunktioner."
"linktitle": "Läs in dokument från strömmen"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Läs in dokument från strömmen"
"url": "/sv/net/loading-documents/loading-document-stream/"
"weight": 12
---

# Läs in dokument från strömmen

## Introduktion
Inom .NET-utveckling är det av yttersta vikt att hantera och visa dokument effektivt. Med tillkomsten av avancerade verktyg och bibliotek har uppgifter som en gång verkade skrämmande nu förenklats. Bland dessa verktyg utmärker sig GroupDocs.Viewer för .NET som en mångsidig lösning för att smidigt hantera olika dokumentformat. I den här omfattande guiden fördjupar vi oss i hur det är att använda GroupDocs.Viewer för .NET för att ladda dokument från en ström. Oavsett om du är en erfaren utvecklare eller precis har börjat, kommer den här handledningen att ge dig kunskapen för att effektivt utnyttja kraften i GroupDocs.Viewer.

![Läs in dokument från Stream med GroupDocs.Viewer .NET](/viewer/loading-documents/load-documents-from-stream.png)

## Förkunskapskrav
Innan du börjar med handledningen, se till att du har följande förutsättningar på plats:
1. Grundläggande förståelse för C# och .NET Framework: Bekantskap med programmeringsspråket C# och .NET Framework hjälper till att förstå de koncept som diskuteras.
   
2. Installation av GroupDocs.Viewer för .NET: Ladda ner och installera GroupDocs.Viewer för .NET från [webbplats](https://releases.groupdocs.com/viewer/net/).
3. IDE: Ha en integrerad utvecklingsmiljö (IDE) som Visual Studio installerad för kodning och testning.
4. Dokumentström: Förbered en dokumentström för laddning. Detta kan vara en filström eller någon annan kompatibel strömkälla.

## Importera namnrymder
Innan du implementerar koden för att läsa in dokument från en ström, se till att importera nödvändiga namnrymder:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Steg 1: Definiera utdatakatalog
```csharp
string outputDirectory = "Your Document Directory";
```
Ange sökvägen till katalogen där det renderade dokumentet ska sparas.
## Steg 2: Definiera format för sidfilens sökväg
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Definiera formatet för filsökvägen för varje sida. Här kommer "{0}" att ersättas med sidnumret.
## Steg 3: Hämta dokumentströmmen
```csharp
Stream stream = GetFileStream();
```
Hämta dokumentströmmen från önskad källa. Detta kan vara en filström, minnesström eller någon annan kompatibel ström.
## Steg 4: Ladda dokument med hjälp av visningsprogrammet
```csharp
using (Viewer viewer = new Viewer(stream)) 
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
Initiera en ny instans av Viewer-klassen med dokumentströmmen. Konfigurera sedan HTML-visningsalternativen och rendera dokumentet.
## Steg 5: Visa utdatakatalogen
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Informera användaren om att dokumentet har renderats och ange platsen där utdata sparas.

## Slutsats
Sammanfattningsvis erbjuder GroupDocs.Viewer för .NET en robust lösning för att enkelt ladda och visa dokument från strömmar. Genom att följa stegen som beskrivs i den här handledningen kan du sömlöst integrera dokumentvisningsfunktioner i dina .NET-applikationer, vilket förbättrar användarupplevelsen och produktiviteten.
## Vanliga frågor
### Kan GroupDocs.Viewer för .NET hantera olika dokumentformat?
Ja, GroupDocs.Viewer stöder ett brett utbud av dokumentformat, inklusive PDF, DOCX, XLSX, PPTX och mer.
### Är GroupDocs.Viewer för .NET lämplig för både webb- och skrivbordsapplikationer?
Absolut! GroupDocs.Viewer kan integreras sömlöst i både webb- och skrivbordsapplikationer som utvecklats med .NET.
### Erbjuder GroupDocs.Viewer anpassningsalternativ för dokumentrendering?
Ja, du kan anpassa olika aspekter av dokumentrendering, till exempel vattenstämpel, sidrotation och zoomnivå, efter dina behov.
### Kan jag använda GroupDocs.Viewer för .NET i kommersiella projekt?
Ja, GroupDocs.Viewer erbjuder licensalternativ som är lämpliga för kommersiella projekt. Du kan köpa licenser från den officiella [webbplats](https://purchase.groupdocs.com/temporary-license/).
### Finns teknisk support tillgänglig för GroupDocs.Viewer för .NET?
Ja, du kan söka teknisk hjälp och vägledning från det dedikerade supportforumet som tillhandahålls av [Gruppdokument.Visare](https://forum.groupdocs.com/c/viewer/9).