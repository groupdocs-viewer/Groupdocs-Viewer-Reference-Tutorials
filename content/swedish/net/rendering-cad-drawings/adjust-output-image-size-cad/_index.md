---
"description": "Lär dig hur du justerar bildstorleken för CAD-ritningar med GroupDocs.Viewer för .NET. Förbättra synligheten och användbarheten utan ansträngning."
"linktitle": "Justera utdatabildens storlek för CAD-ritningar"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Justera utdatabildens storlek för CAD-ritningar"
"url": "/sv/net/rendering-cad-drawings/adjust-output-image-size-cad/"
"weight": 15
---

# Justera utdatabildens storlek för CAD-ritningar

## Introduktion
CAD-ritningar kräver ofta specifika justeringar för optimal visning och presentation. GroupDocs.Viewer för .NET tillhandahåller en kraftfull verktygsuppsättning för att hantera och anpassa utdata från CAD-ritningar. I den här handledningen guidar vi dig genom processen att justera bildstorleken för CAD-ritningar steg för steg.
## Förkunskapskrav
Innan du börjar, se till att du har följande förutsättningar:
1. GroupDocs.Viewer för .NET: Ladda ner och installera GroupDocs.Viewer för .NET från [här](https://releases.groupdocs.com/viewer/net/).
2. Dokumentkatalog: Förbered katalogen där ditt dokument finns.
3. Grundläggande förståelse: Bekanta dig med grundläggande koncept inom .NET-programmering.

## Importera namnrymder
Se först till att importera de namnrymder som krävs för att komma åt GroupDocs.Viewer-funktionerna:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Steg 1: Ställ in utdatakatalog
Definiera katalogen där du vill lagra utdatabilderna från CAD-ritningar:
```csharp
string outputDirectory = "Your Document Directory";
```
## Steg 2: Definiera format för sidfilens sökväg
Ställ in formatet för sökvägar till sidor. Detta format kommer att användas för att namnge och spara enskilda sidor som HTML-filer:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Steg 3: Justera bildstorleken
Inuti ett using-block för Viewer-objektet, justera bildstorleken för CAD-ritningar genom att ange lämpliga alternativ:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## Steg 4: Visa utdatakatalogen
När dokumentet har renderats, visa ett meddelande som anger att renderingen har lyckats och ange platsen för utdatakatalogen:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Slutsats
Att justera bildstorleken för CAD-ritningar är avgörande för att förbättra deras synlighet och användbarhet. Med GroupDocs.Viewer för .NET blir denna process strömlinjeformad och effektiv, så att du kan anpassa resultatet efter dina specifika behov.
## Vanliga frågor
### Kan jag justera bildstorleken för andra typer av dokument än CAD-ritningar?
Ja, GroupDocs.Viewer för .NET stöder olika dokumenttyper, och du kan justera bildstorleken för de flesta dokumentformat.
### Är GroupDocs.Viewer för .NET kompatibel med olika versioner av .NET-ramverket?
Ja, GroupDocs.Viewer för .NET är kompatibelt med flera versioner av .NET-ramverket, vilket säkerställer flexibilitet och användbarhet i olika miljöer.
### Finns det några licensalternativ tillgängliga för GroupDocs.Viewer för .NET?
Ja, du kan utforska olika licensalternativ, inklusive tillfälliga licenser och kommersiella licenser, för att passa dina behov.
### Kan jag anpassa utdataformatet för renderade dokument?
Absolut, GroupDocs.Viewer för .NET erbjuder olika anpassningsalternativ, så att du kan skräddarsy utdataformatet efter dina handledningar.
### Var kan jag hitta ytterligare support eller hjälp med GroupDocs.Viewer för .NET?
Du kan besöka GroupDocs.Viewer-forumet [här](https://forum.groupdocs.com/c/viewer/9) för att få stöd, ställa frågor och engagera sig i samhället.