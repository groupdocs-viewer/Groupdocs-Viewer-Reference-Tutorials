---
title: Justera bildstorleken för CAD-ritningar
linktitle: Justera bildstorleken för CAD-ritningar
second_title: GroupDocs.Viewer .NET API
description: Lär dig hur du justerar storleken på utdatabilden för CAD-ritningar med GroupDocs.Viewer för .NET. Förbättra synligheten och användbarheten utan ansträngning.
weight: 15
url: /sv/net/rendering-cad-drawings/adjust-output-image-size-cad/
---
## Introduktion
CAD-ritningar kräver ofta specifika justeringar för optimal visning och presentation. GroupDocs.Viewer för .NET tillhandahåller en kraftfull verktygsuppsättning för att hantera och anpassa CAD-ritningar. I den här handledningen kommer vi att guida dig genom processen att justera utdatabildstorleken för CAD-ritningar steg för steg.
## Förutsättningar
Innan du börjar, se till att du har följande förutsättningar:
1.  GroupDocs.Viewer för .NET: Ladda ner och installera GroupDocs.Viewer för .NET från[här](https://releases.groupdocs.com/viewer/net/).
2. Dokumentkatalog: Förbered katalogen där ditt dokument finns.
3. Grundläggande förståelse: Bekanta dig med grundläggande begrepp för .NET-programmering.

## Importera namnområden
Se först till att importera de nödvändiga namnområdena för att få åtkomst till GroupDocs.Viewer-funktioner:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Steg 1: Ställ in utdatakatalog
Definiera katalogen där du vill lagra utdatabilder av CAD-ritningar:
```csharp
string outputDirectory = "Your Document Directory";
```
## Steg 2: Definiera sidfilssökvägsformat
Ställ in formatet för sökvägar för sidfil. Detta format kommer att användas för att namnge och spara enskilda sidor som HTML-filer:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Steg 3: Justera bildstorleken
Justera bildstorleken för CAD-ritningar i ett block för Viewer-objektet genom att ställa in lämpliga alternativ:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## Steg 4: Visa utdatakatalog
När du har renderat dokumentet, visa ett meddelande som indikerar den lyckade renderingen och ange platsen för utdatakatalogen:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Slutsats
Att justera storleken på utdatabilden för CAD-ritningar är avgörande för att förbättra deras synlighet och användbarhet. Med GroupDocs.Viewer för .NET blir denna process strömlinjeformad och effektiv, så att du kan anpassa utdata efter dina specifika krav.
## FAQ's
### Kan jag justera storleken på utdatabilden för andra typer av dokument förutom CAD-ritningar?
Ja, GroupDocs.Viewer för .NET stöder olika dokumenttyper, och du kan justera storleken på utdatabilden för de flesta dokumentformat.
### Är GroupDocs.Viewer för .NET kompatibel med olika versioner av .NET-ramverket?
Ja, GroupDocs.Viewer för .NET är kompatibel med flera versioner av .NET-ramverket, vilket säkerställer flexibilitet och användbarhet i olika miljöer.
### Finns det några licensalternativ för GroupDocs.Viewer för .NET?
Ja, du kan utforska olika licensalternativ, inklusive tillfälliga licenser och kommersiella licenser, för att passa dina behov.
### Kan jag anpassa utdataformatet för renderade dokument?
Absolut, GroupDocs.Viewer för .NET erbjuder olika anpassningsalternativ, så att du kan skräddarsy utdataformatet efter dina preferenser.
### Var kan jag hitta ytterligare support eller hjälp med GroupDocs.Viewer för .NET?
 Du kan besöka forumet GroupDocs.Viewer[här](https://forum.groupdocs.com/c/viewer/9) att få stöd, ställa frågor och engagera sig i samhället.