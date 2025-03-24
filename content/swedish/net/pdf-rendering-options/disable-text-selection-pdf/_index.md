---
title: Inaktivera textval i PDF
linktitle: Inaktivera textval i PDF
second_title: GroupDocs.Viewer .NET API
description: Lär dig hur du inaktiverar textval i PDF med GroupDocs.Viewer för .NET. Följ vår steg-för-steg-guide för sömlös integration.
weight: 13
url: /sv/net/pdf-rendering-options/disable-text-selection-pdf/
---
## Introduktion
GroupDocs.Viewer för .NET är ett kraftfullt dokumentåtergivnings-API som tillåter utvecklare att integrera dokumentvisningsmöjligheter i sina .NET-applikationer utan ansträngning. En av nyckelfunktionerna som tillhandahålls av GroupDocs.Viewer är möjligheten att inaktivera textval i PDF-dokument. Den här funktionen är särskilt användbar i scenarier där du behöver förhindra användare från att kopiera text från känsliga dokument, vilket säkerställer dokumentsäkerhet och integritet.
## Förutsättningar
Innan vi dyker in i steg-för-steg-guiden om hur du inaktiverar textval i PDF med GroupDocs.Viewer för .NET, se till att du har följande förutsättningar:
1.  Installation av GroupDocs.Viewer för .NET: Se till att du har laddat ner och installerat GroupDocs.Viewer för .NET från[nedladdningslänk](https://releases.groupdocs.com/viewer/net/).
2. Dokumentkatalog: Förbered en katalog där dina dokument kommer att lagras. Du måste ange den här katalogen i kodavsnittet för att rendera PDF-dokumentet.

## Importera namnområden
Först måste du importera de nödvändiga namnområdena för att komma åt funktionerna som tillhandahålls av GroupDocs.Viewer för .NET. Så här kan du göra det:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Låt oss nu dela upp processen att inaktivera textval i ett PDF-dokument med GroupDocs.Viewer för .NET i flera steg:
## Steg 1: Ange utdatakatalog
```csharp
string outputDirectory = "Your Document Directory";
```
 I detta steg, byt ut`"Your Document Directory"` med katalogsökvägen där ditt PDF-dokument finns.
## Steg 2: Definiera sidfilssökvägsformat
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Det här steget definierar formatet för filsökvägarna för de renderade HTML-sidorna. Varje sida i PDF-dokumentet kommer att konverteras till en HTML-fil med ett sekventiellt sidnummer.
## Steg 3: Återge PDF-dokument med textval inaktiverat
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
 Byta ut`"Path to Your PDF Document"` med den faktiska sökvägen till din PDF-fil. Det här kodavsnittet initierar en`Viewer` objekt, konfigurerar HTML-vyalternativ för att bädda in resurser och inaktiverar textval genom inställning`RenderTextAsImage` egendom till`true`.
## Steg 4: Visa framgångsmeddelande
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Efter att PDF-dokumentet har renderats visar det här steget ett framgångsmeddelande tillsammans med katalogen där de renderade HTML-sidorna lagras.

## Slutsats
I den här handledningen har vi lärt oss hur du inaktiverar textval i PDF-dokument med GroupDocs.Viewer för .NET. Genom att följa steg-för-steg-guiden kan du sömlöst integrera den här funktionen i dina .NET-applikationer, vilket säkerställer dokumentsäkerhet och förbättrar användarupplevelsen.
## FAQ's
### Kan jag anpassa utdatakatalogen för renderade HTML-sidor?
Ja, du kan ange vilken katalogsökväg som helst där du vill att de renderade HTML-sidorna ska lagras.
### Är GroupDocs.Viewer för .NET kompatibel med olika versioner av .NET framework?
Ja, GroupDocs.Viewer för .NET är kompatibel med olika versioner av .NET-ramverket, inklusive .NET Core och .NET Framework.
### Påverkar inaktivering av textval andra funktioner i PDF-dokumentet?
Nej, om du inaktiverar texturval förhindras bara användare från att markera och kopiera text från dokumentet. Övriga funktioner förblir intakta.
### Kan jag aktivera textval igen efter att ha renderat dokumentet?
 Ja, du kan aktivera textval genom att helt enkelt ställa in`RenderTextAsImage` egendom till`false` i HTML-vyalternativen.
### Finns det en testversion tillgänglig för GroupDocs.Viewer för .NET?
 Ja, du kan få tillgång till en gratis provversion av GroupDocs.Viewer för .NET från[hemsida](https://releases.groupdocs.com/).