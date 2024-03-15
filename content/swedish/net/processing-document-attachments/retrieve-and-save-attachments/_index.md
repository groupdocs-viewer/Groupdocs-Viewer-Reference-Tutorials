---
title: Hämta och spara dokumentbilagor
linktitle: Hämta och spara dokumentbilagor
second_title: GroupDocs.Viewer .NET API
description: Hantera dokumentbilagor effektivt i .NET-applikationer med GroupDocs.Viewer. Hämta och spara bilagor problemfritt.
type: docs
weight: 12
url: /sv/net/processing-document-attachments/retrieve-and-save-attachments/
---
## Introduktion
I den digitala eran är effektiv dokumenthantering avgörande för både företag och privatpersoner. Oavsett om det handlar om att hantera e-postmeddelanden, visa kontrakt eller få tillgång till rapporter är det viktigt att ha ett tillförlitligt verktyg för dokumentvisualisering. GroupDocs.Viewer för .NET framstår som en robust lösning som ger användarna möjlighet att enkelt se och interagera med olika dokumentformat direkt i sina .NET-applikationer.
## Förutsättningar
Innan du fördjupar dig i att använda GroupDocs.Viewer för .NET för att hämta och spara dokumentbilagor, se till att du har följande förutsättningar:
1. Driftmiljö: En arbetsmiljö som är inrättad med .NET-ramverk.
2.  Installation: GroupDocs.Viewer för .NET-biblioteket laddades ner och installerades. Du kan komma åt biblioteket från[nedladdningslänk](https://releases.groupdocs.com/viewer/net/).
3. Grundläggande förståelse: Kännedom om programmeringsspråket C#.
4. Dokumentkälla: Tillgång till ett exempeldokument med bilagor för demonstrationsändamål.

## Importera namnområden
För att börja använda GroupDocs.Viewer för .NET för att hämta och spara dokumentbilagor, importera nödvändiga namnområden:
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Results;
```

## Steg 1: Definiera utdatakatalog
```csharp
string outputDirectory = "Your Document Directory";
```
Definiera katalogen där du vill spara de bilagor som hämtats från dokumentet.
## Steg 2: Instantiera Viewer Object
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
Instantiera Viewer-objektet med sökvägen till dokumentet som innehåller bilagor.
## Steg 3: Hämta bilagor
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
Hämta en lista över bilagor som finns i dokumentet.
## Steg 4: Spara bilagor
```csharp
foreach(Attachment attachment in attachments)
{
    string filePath = Path.Combine(outputDirectory, attachment.FileName);  
    viewer.SaveAttachment(attachment, File.OpenWrite(filePath)); 
}
```
Iterera genom varje bilaga, definiera filsökvägen och spara bilagan i den angivna katalogen.
## Steg 5: Visa framgångsmeddelande
```csharp
Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
```
Visa ett lyckat meddelande som indikerar att bilagor har sparats tillsammans med katalogsökvägen.

## Slutsats
Att integrera GroupDocs.Viewer för .NET i dina dokumenthanteringsarbetsflöden effektiviserar processen för att hantera bilagor, vilket ger effektivitet och bekvämlighet. Genom att följa den steg-för-steg-guide som beskrivs ovan kan användare sömlöst hämta och spara dokumentbilagor i sina .NET-applikationer.
## FAQ's
### Kan GroupDocs.Viewer för .NET hantera olika dokumentformat?
Ja, GroupDocs.Viewer stöder ett brett utbud av dokumentformat, inklusive PDF, Microsoft Office-dokument, bilder och mer.
### Finns det en gratis testversion tillgänglig för GroupDocs.Viewer för .NET?
 Ja, du kan komma åt den kostnadsfria provperioden från[här](https://releases.groupdocs.com/).
### Hur kan jag få tillfälliga licenser för GroupDocs.Viewer för .NET?
 Tillfälliga licenser kan erhållas från[den här länken](https://purchase.groupdocs.com/temporary-license/).
### Var kan jag hitta dokumentation för GroupDocs.Viewer för .NET?
 Omfattande dokumentation finns tillgänglig[här](https://reference.groupdocs.com/viewer/net/).
### Vilka supportalternativ finns tillgängliga för GroupDocs.Viewer för .NET?
 Du kan söka hjälp från communityforumet[här](https://forum.groupdocs.com/c/viewer/9).