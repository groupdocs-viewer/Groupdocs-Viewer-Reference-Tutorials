---
"description": "Förbättra dina .NET-applikationer med GroupDocs.Viewer för sömlös dokumentvisning. Följ vår steg-för-steg-guide och integrera kraftfulla dokumentvisningsfunktioner utan ansträngning."
"linktitle": "Ange licens från ström"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Ange licens från ström"
"url": "/sv/net/getting-started/set-license-from-stream/"
"weight": 11
type: docs
---
# Ange licens från ström

## Introduktion
Vill du utöka dina .NET-applikationer med avancerade dokumentvisningsfunktioner? GroupDocs.Viewer för .NET erbjuder en omfattande lösning för att sömlöst integrera dokumentvisningsfunktioner i dina projekt. I den här handledningen går vi in på hur man använder GroupDocs.Viewer för .NET för att berika dina applikationer med kraftfulla dokumentvisningsfunktioner. 

![Ställ in licens från Stream med GroupDocs.Viewer för .NET](/viewer/getting-started/set-license-from-stream.png)

## Förkunskapskrav
Innan vi går in i integrationsprocessen, se till att du har följande förutsättningar på plats:
1. Grundläggande kunskaper om .NET-utveckling: Bekantskap med C# och .NET Framework är avgörande för att följa den här handledningen.
   
2. GroupDocs.Viewer för .NET-paketet: Se till att du har laddat ner och installerat GroupDocs.Viewer för .NET-paketet. Du kan hämta det från [nedladdningslänk](https://releases.groupdocs.com/viewer/net/).
3. Åtkomst till GroupDocs-dokumentation: Behåll [dokumentation](https://tutorials.groupdocs.com/viewer/net/) praktiskt för handledningar under integrationsprocessen.

## Importera namnrymder
Börja med att importera de nödvändiga namnrymderna till din .NET-applikation. Följ dessa steg:
### Steg 1: Öppna ditt .NET-projekt.
Se till att du har ditt .NET-projekt öppet i din föredragna utvecklingsmiljö.
### Steg 2: Lägg till namnrymden GroupDocs.Viewer.
I din kodfil lägger du till följande namnrymd för att komma åt GroupDocs.Viewer-funktionerna:
```csharp
using System;
using System.IO;
```
## Ange licens från ström
Nästa steg innebär att ställa in licensen från en ström. Följ dessa detaljerade steg:
### Steg 1: Definiera utdatakatalog.
Ange katalogen där dina dokument ska lagras genom att definiera utdatakatalogen:
```csharp
string outputDirectory = "Your Document Directory";
```
### Steg 2: Kontrollera att licensfilen finns.
Kontrollera om licensfilen finns i din projektkatalog:
```csharp
if (File.Exists(Utils.LicensePath))
```
### Steg 3: Ställ in licens.
Om licensfilen finns, ställ in licensen med hjälp av den angivna strömmen:
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### Steg 4: Hantera frånvaro av licens.
Om licensfilen inte hittas, ge instruktioner för att erhålla en licens:
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://purchase.groupdocs.com/faqs/licensing. " +
                      "\nLearn how to request a temporary license at https://purchase.groupdocs.com/temporary-license.");
}
```

## Slutsats
Grattis! Du har nu lärt dig hur du integrerar GroupDocs.Viewer för .NET i dina applikationer. Med det här kraftfulla verktyget kan du nu enkelt visa olika dokumentformat i dina .NET-projekt, vilket förbättrar användarupplevelsen och produktiviteten.
## Vanliga frågor
### Behöver jag en licens för att använda GroupDocs.Viewer för .NET?
Ja, du behöver en licens för att använda GroupDocs.Viewer för .NET. Du kan få antingen en tillfällig eller permanent licens från GroupDocs webbplats.
### Kan jag integrera GroupDocs.Viewer i mitt ASP.NET-program?
Absolut! GroupDocs.Viewer för .NET integreras sömlöst i både skrivbords- och webbapplikationer, inklusive ASP.NET.
### Vilka dokumentformat stöds av GroupDocs.Viewer?
GroupDocs.Viewer stöder en mängd olika dokumentformat, inklusive PDF, Microsoft Office (Word, Excel, PowerPoint), bilder och mer.
### Är GroupDocs.Viewer kompatibel med .NET Core?
Ja, GroupDocs.Viewer för .NET är kompatibel med både .NET Framework och .NET Core.
### Kan jag anpassa visningsgränssnittet efter programmets tema?
Ja, GroupDocs.Viewer erbjuder omfattande anpassningsalternativ, vilket gör att du kan skräddarsy visningsgränssnittet så att det matchar ditt programs tema sömlöst.