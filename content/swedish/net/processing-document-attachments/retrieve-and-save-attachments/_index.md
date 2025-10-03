---
"description": "Hantera dokumentbilagor effektivt i .NET-applikationer med GroupDocs.Viewer. Hämta och spara bilagor problemfritt."
"linktitle": "Hämta och spara dokumentbilagor"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Hämta och spara dokumentbilagor"
"url": "/sv/net/processing-document-attachments/retrieve-and-save-attachments/"
"weight": 12
type: docs
---
# Hämta och spara dokumentbilagor

## Introduktion
I den digitala eran är effektiv dokumenthantering avgörande för både företag och privatpersoner. Oavsett om det gäller att hantera e-post, visa avtal eller komma åt rapporter är det viktigt att ha ett pålitligt verktyg för dokumentvisualisering. GroupDocs.Viewer för .NET framstår som en robust lösning som gör det möjligt för användare att enkelt visa och interagera med olika dokumentformat direkt i sina .NET-applikationer.

![Hämta och spara dokumentbilagor med GroupDocs.Viewer .NET](/viewer/processing-document-attachments/retrieve-and-save-document-attachments.png)

## Förkunskapskrav
Innan du börjar använda GroupDocs.Viewer för .NET för att hämta och spara dokumentbilagor, se till att du har följande förutsättningar:
1. Driftmiljö: En arbetsmiljö konfigurerad med .NET Framework.
2. Installation: GroupDocs.Viewer för .NET-biblioteket har laddats ner och installerats. Du kan komma åt biblioteket från [nedladdningslänk](https://releases.groupdocs.com/viewer/net/).
3. Grundläggande förståelse: Bekantskap med programmeringsspråket C#.
4. Dokumentkälla: Åtkomst till ett exempeldokument med bilagor för demonstrationsändamål.

## Importera namnrymder
För att börja använda GroupDocs.Viewer för .NET för att hämta och spara dokumentbilagor, importera nödvändiga namnrymder:
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
## Steg 2: Instansiera Viewer-objekt
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
Instansiera Viewer-objektet med sökvägen till dokumentet som innehåller bilagor.
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
Gå igenom varje bilaga, definiera sökvägen och spara den bifogade filen i den angivna katalogen.
## Steg 5: Visa meddelande om framgång
```csharp
Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
```
Visa ett meddelande som anger att bilagorna har sparats tillsammans med sökvägen till katalogen.

## Slutsats
Att integrera GroupDocs.Viewer för .NET i dina dokumenthanteringsarbetsflöden effektiviserar processen att hantera bilagor, vilket ger effektivitet och bekvämlighet. Genom att följa steg-för-steg-guiden som beskrivs ovan kan användare smidigt hämta och spara dokumentbilagor i sina .NET-applikationer.
## Vanliga frågor
### Kan GroupDocs.Viewer för .NET hantera olika dokumentformat?
Ja, GroupDocs.Viewer stöder en mängd olika dokumentformat, inklusive PDF, Microsoft Office-dokument, bilder och mer.
### Finns det en gratis testversion av GroupDocs.Viewer för .NET?
Ja, du kan få tillgång till gratis provperioden från [här](https://releases.groupdocs.com/).
### Hur kan jag få tillfälliga licenser för GroupDocs.Viewer för .NET?
Tillfälliga licenser kan erhållas från [den här länken](https://purchase.groupdocs.com/temporary-license/).
### Var kan jag hitta dokumentation för GroupDocs.Viewer för .NET?
Omfattande dokumentation finns tillgänglig [här](https://tutorials.groupdocs.com/viewer/net/).
### Vilka supportalternativ finns tillgängliga för GroupDocs.Viewer för .NET?
Du kan söka hjälp från communityforumet [här](https://forum.groupdocs.com/c/viewer/9).