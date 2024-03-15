---
title: Återge anteckningar och justera tidsenheter (MS Project)
linktitle: Återge anteckningar och justera tidsenheter (MS Project)
second_title: GroupDocs.Viewer .NET API
description: Masterrendering av MS Project-dokument med GroupDocs.Viewer för .NET. Gör anteckningar, justera tidsenheter och utforska olika utdataformat utan ansträngning.
type: docs
weight: 11
url: /sv/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/
---
## Introduktion
GroupDocs.Viewer för .NET är ett kraftfullt dokumentåtergivnings-API som låter utvecklare se och manipulera olika dokumentformat i sina .NET-applikationer. I den här handledningen kommer vi att fokusera på att rendera anteckningar och justera tidsenheter specifikt för MS Project-dokument.
## Förutsättningar
Innan vi börjar, se till att du har följande förutsättningar:
1. GroupDocs.Viewer for .NET: Se till att du har laddat ner och installerat GroupDocs.Viewer for .NET-biblioteket. Du kan ladda ner den från[här](https://releases.groupdocs.com/viewer/net/).
2. Utvecklingsmiljö: Konfigurera din föredragna utvecklingsmiljö med .NET-stöd.
3. MS Project Document: Ha ett exempel på MS Project-dokument redo för testning.
## Importera namnområden
Låt oss först importera de nödvändiga namnrymden för att komma igång med att rendera MS Project-dokument:
## Steg 1: Importera namnområden
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Nu när vi har importerat de nödvändiga namnområdena, låt oss dela upp varje exempel i flera steg för en heltäckande förståelse.
## Rendera MS Project Document till HTML
För att rendera ett MS Project-dokument till HTML-format med anteckningar, följ dessa steg:
### Steg 2: Ställ in utdatakatalog och filformat
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### Steg 3: Initiera Viewer Object och Ange alternativ
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
## Återge MS Project-dokument till bildformat
Du kan också rendera MS Project-dokument till bildformat som JPG och PNG. Här är hur:
### Steg 5: Ställ in utdatakatalog och filformat för JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### Steg 6: Initiera Viewer Object och Ange JPG-alternativ
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Steg 7: Gör dokumentet till JPG
```csharp
viewer.View(options);
```
Upprepa liknande steg för rendering till PNG och andra bildformat.
## Rendera MS Project Document till PDF
Gör så här för att återge ett MS Project-dokument till PDF-format:
### Steg 8: Ställ in utdatakatalog och filformat för PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### Steg 9: Initiera Viewer Object och Ange PDF-alternativ
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Steg 10: Gör dokumentet till PDF
```csharp
viewer.View(options);
```

## Slutsats
Grattis! Du har framgångsrikt lärt dig hur du renderar MS Project-dokument och justerar tidsenheter med GroupDocs.Viewer för .NET. Införliva denna kunskap i dina projekt för att förbättra dokumentvisningskapaciteten.
## FAQ's
### Kan jag återge MS Project-dokument till andra format förutom HTML, bilder och PDF?
Ja, GroupDocs.Viewer för .NET stöder rendering till olika format som DOCX, XLSX, PPTX och mer.
### Finns det en testversion tillgänglig för GroupDocs.Viewer för .NET?
 Ja, du kan få en gratis provperiod från[här](https://releases.groupdocs.com/).
### Hur kan jag få tillfällig licens för GroupDocs.Viewer för .NET?
 Besök[den här länken](https://purchase.groupdocs.com/temporary-license/) för att få en tillfällig licens.
### Var kan jag hitta dokumentation för GroupDocs.Viewer för .NET?
 Se dokumentationen[här](https://reference.groupdocs.com/viewer/net/).
### Var kan jag söka support eller ställa frågor relaterade till GroupDocs.Viewer för .NET?
 Du kan besöka supportforumet[här](https://forum.groupdocs.com/c/viewer/9).