---
"description": "Lär dig hur du inaktiverar textmarkering i PDF med GroupDocs.Viewer för .NET. Följ vår steg-för-steg-guide för sömlös integration."
"linktitle": "Inaktivera textmarkering i PDF"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Inaktivera textmarkering i PDF"
"url": "/sv/net/pdf-rendering-options/disable-text-selection-pdf/"
"weight": 13
type: docs
---
# Inaktivera textmarkering i PDF

## Introduktion
GroupDocs.Viewer för .NET är ett kraftfullt API för dokumentrendering som gör det möjligt för utvecklare att enkelt integrera dokumentvisningsfunktioner i sina .NET-applikationer. En av de viktigaste funktionerna i GroupDocs.Viewer är möjligheten att inaktivera textmarkering i PDF-dokument. Den här funktionen är särskilt användbar i scenarier där du behöver förhindra att användare kopierar text från känsliga dokument, vilket säkerställer dokumentsäkerhet och integritet.

![Inaktivera textmarkering i PDF med GroupDocs.Viewer .NET](/viewer/pdf-rendering-options/disable-text-selection-in-pdf.png)

## Förkunskapskrav
Innan vi går in på steg-för-steg-guiden om hur man inaktiverar textmarkering i PDF med GroupDocs.Viewer för .NET, se till att du har följande förutsättningar på plats:
1. Installation av GroupDocs.Viewer för .NET: Se till att du har laddat ner och installerat GroupDocs.Viewer för .NET från [nedladdningslänk](https://releases.groupdocs.com/viewer/net/).
2. Dokumentkatalog: Förbered en katalog där dina dokument ska lagras. Du måste ange den här katalogen i kodavsnittet för att rendera PDF-dokumentet.

## Importera namnrymder
Först måste du importera de namnrymder som behövs för att komma åt funktionerna som tillhandahålls av GroupDocs.Viewer för .NET. Så här gör du:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Nu ska vi dela upp processen för att inaktivera textmarkering i ett PDF-dokument med GroupDocs.Viewer för .NET i flera steg:
## Steg 1: Ange utdatakatalog
```csharp
string outputDirectory = "Your Document Directory";
```
I det här steget, byt ut `"Your Document Directory"` med katalogsökvägen där ditt PDF-dokument finns.
## Steg 2: Definiera format för sidfilens sökväg
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Det här steget definierar formatet för sökvägarna till de renderade HTML-sidorna. Varje sida i PDF-dokumentet konverteras till en HTML-fil med ett sekventiellt sidnummer.
## Steg 3: Rendera PDF-dokument med textmarkering inaktiverad
```csharp
using (Viewer viewer = new Viewer("Path to Your PDF Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.RenderTextAsImage = true;
    viewer.View(options);
}
```
Ersätta `"Path to Your PDF Document"` med den faktiska sökvägen till din PDF-fil. Detta kodavsnitt initierar en `Viewer` objekt, konfigurerar HTML-visningsalternativ för att bädda in resurser och inaktiverar textmarkering genom att ställa in `RenderTextAsImage` egendom till `true`.
## Steg 4: Visa meddelande om framgång
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Efter att PDF-dokumentet har renderats visar det här steget ett meddelande om att det lyckades tillsammans med katalogen där de renderade HTML-sidorna lagras.

## Slutsats
I den här handledningen har vi lärt oss hur man inaktiverar textmarkering i PDF-dokument med GroupDocs.Viewer för .NET. Genom att följa steg-för-steg-guiden kan du sömlöst integrera den här funktionen i dina .NET-applikationer, vilket säkerställer dokumentsäkerhet och förbättrar användarupplevelsen.
## Vanliga frågor
### Kan jag anpassa utdatakatalogen för renderade HTML-sidor?
Ja, du kan ange vilken katalogsökväg som helst där du vill att de renderade HTML-sidorna ska lagras.
### Är GroupDocs.Viewer för .NET kompatibel med olika versioner av .NET framework?
Ja, GroupDocs.Viewer för .NET är kompatibel med olika versioner av .NET Framework, inklusive .NET Core och .NET Framework.
### Påverkar inaktivering av textmarkering andra funktioner i PDF-dokumentet?
Nej, att inaktivera textmarkering hindrar bara användare från att markera och kopiera text från dokumentet. Andra funktioner förblir intakta.
### Kan jag aktivera textmarkering igen efter att dokumentet har renderats?
Ja, du kan aktivera textval genom att helt enkelt ställa in `RenderTextAsImage` egendom till `false` i HTML-vyalternativen.
### Finns det en testversion tillgänglig för GroupDocs.Viewer för .NET?
Ja, du kan få tillgång till en gratis provversion av GroupDocs.Viewer för .NET från [webbplats](https://releases.groupdocs.com/).