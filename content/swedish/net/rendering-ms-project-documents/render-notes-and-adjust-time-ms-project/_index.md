---
"description": "Bemästra rendering av MS Project-dokument med GroupDocs.Viewer för .NET. Rendera anteckningar, justera tidsenheter och utforska olika utdataformat utan ansträngning."
"linktitle": "Rendera anteckningar och justera tidsenheter (MS Project)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Rendera anteckningar och justera tidsenheter (MS Project)"
"url": "/sv/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/"
"weight": 11
---

# Rendera anteckningar och justera tidsenheter (MS Project)

## Introduktion
GroupDocs.Viewer för .NET är ett kraftfullt API för dokumentrendering som låter utvecklare visa och manipulera olika dokumentformat i sina .NET-applikationer. I den här handledningen kommer vi att fokusera på att rendera anteckningar och justera tidsenheter specifikt för MS Project-dokument.
## Förkunskapskrav
Innan vi börjar, se till att du har följande förutsättningar:
1. GroupDocs.Viewer för .NET: Se till att du har laddat ner och installerat GroupDocs.Viewer för .NET-biblioteket. Du kan ladda ner det från [här](https://releases.groupdocs.com/viewer/net/).
2. Utvecklingsmiljö: Konfigurera din föredragna utvecklingsmiljö med .NET-stöd.
3. MS Project-dokument: Ha ett exempel på ett MS Project-dokument redo för testning.
## Importera namnrymder
Låt oss först importera de namnrymder som behövs för att komma igång med att rendera MS Project-dokument:
## Steg 1: Importera namnrymder
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Nu när vi har importerat de namnrymder som krävs, låt oss dela upp varje exempel i flera steg för en heltäckande förståelse.
## Rendera MS Project-dokument till HTML
För att rendera ett MS Project-dokument till HTML-format med anteckningar, följ dessa steg:
### Steg 2: Ställ in utdatakatalog och filformat
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### Steg 3: Initiera visningsobjektet och ange alternativ
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### Steg 4: Rendera dokument till HTML
```csharp
viewer.View(options);
```
## Rendera MS Project-dokument till bildformat
Du kan också rendera MS Project-dokument till bildformat som JPG och PNG. Så här gör du:
### Steg 5: Ställ in utdatakatalog och filformat för JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### Steg 6: Initiera visningsobjektet och ange JPG-alternativ
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Steg 7: Rendera dokument till JPG
```csharp
viewer.View(options);
```
Upprepa liknande steg för rendering till PNG och andra bildformat.
## Rendera MS Project-dokument till PDF
För att rendera ett MS Project-dokument till PDF-format, gör så här:
### Steg 8: Ställ in utdatakatalog och filformat för PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### Steg 9: Initiera visningsobjektet och ange PDF-alternativ
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Steg 10: Rendera dokument till PDF
```csharp
viewer.View(options);
```

## Slutsats
Grattis! Du har nu lärt dig hur man renderar MS Project-dokument och justerar tidsenheter med GroupDocs.Viewer för .NET. Integrera denna kunskap i dina projekt för att förbättra dokumentvisningsfunktionerna.
## Vanliga frågor
### Kan jag rendera MS Project-dokument till andra format än HTML, bilder och PDF?
Ja, GroupDocs.Viewer för .NET stöder rendering till olika format som DOCX, XLSX, PPTX med flera.
### Finns det en testversion tillgänglig för GroupDocs.Viewer för .NET?
Ja, du kan få en gratis provperiod från [här](https://releases.groupdocs.com/).
### Hur kan jag få tillfällig licens för GroupDocs.Viewer för .NET?
Besök [den här länken](https://purchase.groupdocs.com/temporary-license/) att få en tillfällig licens.
### Var kan jag hitta dokumentation för GroupDocs.Viewer för .NET?
Se dokumentationen [här](https://tutorials.groupdocs.com/viewer/net/).
### Var kan jag söka support eller ställa frågor relaterade till GroupDocs.Viewer för .NET?
Du kan besöka supportforumet [här](https://forum.groupdocs.com/c/viewer/9).