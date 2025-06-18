---
"description": "Lär dig hur du anger filtyp när du laddar dokument med GroupDocs.Viewer för .NET. Rendera olika format korrekt i dina .NET-applikationer."
"linktitle": "Ange filtyp när du laddar dokument"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Ange filtyp när du laddar dokument"
"url": "/sv/net/advanced-loading/specify-file-type/"
"weight": 10
---

# Ange filtyp när du laddar dokument

## Introduktion
GroupDocs.Viewer för .NET är ett mångsidigt API för dokumentrendering som stöder en mängd olika filformat, inklusive DOCX, PDF, PPTX med flera. Genom att ange filtypen när du laddar dokument kan du säkerställa korrekt rendering och en smidig visningsupplevelse för dina användare.

![Ange filtyp när du laddar dokument i GroupDocs.Viewer för .NET](/viewer/advanced-loading/specify-file-type-when-loading-documents-img.png)

## Förkunskapskrav
Innan du börjar, se till att du har följande förutsättningar:
- Grundläggande kunskaper i C# och .NET framework.
- Visual Studio installerat på ditt system.
- GroupDocs.Viewer för .NET installerat i ditt projekt. Du kan ladda ner det från [här](https://releases.groupdocs.com/viewer/net/).
##
## Importera namnrymder
Först måste du importera de nödvändiga namnrymderna till din C#-kod. Dessa namnrymder ger åtkomst till de klasser och metoder som krävs för dokumentrendering.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Steg 1: Konfigurera utdatakatalogen
Definiera katalogen där du vill spara de renderade dokumentsidorna.
```csharp
string outputDirectory = "Your Document Directory";
```
## Steg 2: Definiera format för sidfilens sökväg
Ange formatet för namngivning av HTML-filerna för varje sida i dokumentet.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Steg 3: Ange laddningsalternativ
Skapa en instans av `LoadOptions` klassen och ange önskad filtyp.
```csharp
LoadOptions loadOptions = new LoadOptions
{
    FileType = FileType.DOCX
};
```
## Steg 4: Ladda dokument och rendera
Använd `Viewer` klassen för att ladda dokumentet och rendera det i HTML-format.
```csharp
using (Viewer viewer = new Viewer("YourDocument.docx", loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Steg 5: Visa meddelande om framgång
Informera användaren om att dokumentet har renderats och ange platsen för utdatafilerna.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Slutsats
den här handledningen har vi lärt oss hur man använder GroupDocs.Viewer för .NET för att ange filtypen när dokument laddas. Genom att följa dessa enkla steg kan du säkerställa korrekt rendering av olika dokumentformat i dina .NET-applikationer.
## Vanliga frågor
### Kan jag rendera andra dokument än DOCX med GroupDocs.Viewer för .NET?
Ja, GroupDocs.Viewer stöder ett brett utbud av filformat, inklusive PDF, PPTX, XLSX och mer.
### Är GroupDocs.Viewer för .NET kompatibel med .NET Core?
Ja, GroupDocs.Viewer för .NET är kompatibel med både .NET Framework och .NET Core.
### Kan jag anpassa HTML-utdatafilerna som genereras av GroupDocs.Viewer?
Ja, du kan anpassa HTML-utdata med hjälp av olika alternativ som tillhandahålls av API:et.
### Kräver GroupDocs.Viewer för .NET några externa beroenden?
Nej, GroupDocs.Viewer för .NET är ett fristående bibliotek och kräver inga externa beroenden.
### Finns det en testversion tillgänglig för GroupDocs.Viewer för .NET?
Ja, du kan ladda ner en gratis testversion från [här](https://releases.groupdocs.com/viewer/net/).