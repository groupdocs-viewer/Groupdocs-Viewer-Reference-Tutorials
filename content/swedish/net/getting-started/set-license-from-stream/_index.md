---
title: Ställ in licens från Stream
linktitle: Ställ in licens från Stream
second_title: GroupDocs.Viewer .NET API
description: Förbättra dina .NET-applikationer med GroupDocs.Viewer för sömlös dokumentvisning. Följ vår steg-för-steg-guide och integrera kraftfulla dokumentvisningsmöjligheter utan ansträngning.
weight: 11
url: /sv/net/getting-started/set-license-from-stream/
---

# Ställ in licens från Stream

## Introduktion
Vill du ge dina .NET-applikationer avancerade dokumentvisningsmöjligheter? GroupDocs.Viewer för .NET erbjuder en heltäckande lösning för att sömlöst integrera dokumentvisningsfunktioner i dina projekt. I den här självstudien kommer vi att fördjupa oss i processen att utnyttja GroupDocs.Viewer för .NET för att berika dina applikationer med kraftfulla dokumentvisningsmöjligheter. 
## Förutsättningar
Innan vi dyker in i integrationsprocessen, se till att du har följande förutsättningar på plats:
1. Grundläggande kunskaper om .NET-utveckling: Bekantskap med C# och .NET framework är viktigt för att följa med i denna handledning.
   
2.  GroupDocs.Viewer for .NET-paketet: Se till att du har laddat ner och installerat GroupDocs.Viewer for .NET-paketet. Du kan få det från[nedladdningslänk](https://releases.groupdocs.com/viewer/net/).
3.  Tillgång till GroupDocs-dokumentation: Behåll[dokumentation](https://tutorials.groupdocs.com/viewer/net/) praktiskt som referens under integrationsprocessen.

## Importera namnområden
Till att börja med, importera de nödvändiga namnområdena till din .NET-applikation. Följ dessa steg:
### Steg 1: Öppna ditt .NET-projekt.
Se till att du har ditt .NET-projekt öppet i din föredragna utvecklingsmiljö.
### Steg 2: Lägg till GroupDocs.Viewer-namnutrymme.
Lägg till följande namnområde i din kodfil för att komma åt GroupDocs.Viewer-funktionerna:
```csharp
using System;
using System.IO;
```
## Ställ in licens från Stream
Nästa steg innebär att ställa in licensen från en stream. Följ dessa detaljerade steg:
### Steg 1: Definiera utdatakatalog.
Ställ in katalogen där dina dokument ska lagras genom att definiera utdatakatalogen:
```csharp
string outputDirectory = "Your Document Directory";
```
### Steg 2: Kontrollera licensfilens existens.
Kontrollera om licensfilen finns i din projektkatalog:
```csharp
if (File.Exists(Utils.LicensePath))
```
### Steg 3: Ställ in licens.
Om licensfilen finns, ställ in licensen med den medföljande strömmen:
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### Steg 4: Hantera licensfrånvaro.
Om licensfilen inte hittas, tillhandahåll instruktioner för att få en licens:
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
Grattis! Du har framgångsrikt lärt dig hur du integrerar GroupDocs.Viewer för .NET i dina applikationer. Med detta kraftfulla verktyg kan du nu enkelt se olika dokumentformat inom dina .NET-projekt, vilket förbättrar användarupplevelsen och produktiviteten.
## FAQ's
### Behöver jag en licens för att använda GroupDocs.Viewer för .NET?
Ja, du behöver en licens för att använda GroupDocs.Viewer för .NET. Du kan få antingen en tillfällig eller permanent licens från GroupDocs webbplats.
### Kan jag integrera GroupDocs.Viewer i min ASP.NET-applikation?
Absolut! GroupDocs.Viewer för .NET integreras sömlöst i både skrivbords- och webbapplikationer, inklusive ASP.NET.
### Vilka dokumentformat stöds av GroupDocs.Viewer?
GroupDocs.Viewer stöder ett brett utbud av dokumentformat, inklusive PDF, Microsoft Office (Word, Excel, PowerPoint), bilder och mer.
### Är GroupDocs.Viewer kompatibel med .NET Core?
Ja, GroupDocs.Viewer för .NET är kompatibel med både .NET Framework och .NET Core.
### Kan jag anpassa visningsgränssnittet efter programmets tema?
Ja, GroupDocs.Viewer erbjuder omfattande anpassningsalternativ, så att du kan skräddarsy visningsgränssnittet så att det matchar din applikations tema sömlöst.