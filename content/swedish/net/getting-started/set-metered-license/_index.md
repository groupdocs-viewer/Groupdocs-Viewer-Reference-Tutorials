---
title: Ställ in mätlicens
linktitle: Ställ in mätlicens
second_title: GroupDocs.Viewer .NET API
description: Förbättra dina .NET-applikationer med GroupDocs.Viewer för sömlös dokumentvisning. Integrera enkelt dokumentåtergivningsfunktioner i dina projekt.
type: docs
weight: 12
url: /sv/net/getting-started/set-metered-license/
---
## Introduktion
en värld av .NET-utveckling är det viktigt att integrera kraftfulla dokumentvisningsmöjligheter i dina applikationer för att förbättra användarupplevelsen och funktionaliteten. GroupDocs.Viewer för .NET erbjuder en robust lösning för att sömlöst integrera dokumentvisningsfunktioner i dina .NET-projekt. Oavsett om du arbetar med PDF-filer, Microsoft Office-dokument eller olika bildformat, förenklar GroupDocs.Viewer processen att rendera och visa dessa dokument i dina applikationer.
## Förutsättningar
Innan du går in i implementeringen av GroupDocs.Viewer för .NET, se till att du har följande förutsättningar på plats:
### 1. Installera GroupDocs.Viewer för .NET
 För att börja måste du ladda ner och installera GroupDocs.Viewer för .NET. Du hittar nedladdningslänken[här](https://releases.groupdocs.com/viewer/net/). Följ installationsinstruktionerna för att ställa in biblioteket i din utvecklingsmiljö.
### 2. Skaffa mätlicens
För att kunna använda GroupDocs.Viewer för .NET måste du skaffa en uppmätt licens. Denna licens låter dig kontrollera och övervaka din API-användning baserat på fördefinierade kvoter. Följ stegen nedan för att ställa in din mätlicens:

## Importera namnområden
Se först till att du importerar de nödvändiga namnområdena för att komma åt funktionen som tillhandahålls av GroupDocs.Viewer för .NET:
```csharp
using System;
```

Låt oss nu dela upp exempelkoden som tillhandahålls i flera steg:
## Steg 1: Deklarera offentliga och privata nycklar
Deklarera variabler för att lagra dina offentliga och privata nycklar:
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
 Se till att byta ut`"YOUR_PUBLIC_KEY"` och`"YOUR_PRIVATE_KEY"` med dina faktiska nycklar.
## Steg 2: Ställ in mätlicens
Kontrollera om den offentliga nyckeln tillhandahålls. Om inte, be användaren att ställa in nycklarna:
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://purchase.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## Steg 3: Initiera mätobjekt och ställ in licens
Initiera Metered-objektet och ställ in mätlicensen med dina offentliga och privata nycklar:
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## Steg 4: Bekräftelsemeddelande
Visa ett bekräftelsemeddelande som indikerar att licensen har ställts in:
```csharp
Console.WriteLine("License set successfully.");
```

## Slutsats
Sammanfattningsvis erbjuder GroupDocs.Viewer för .NET en heltäckande lösning för att integrera dokumentvisningsfunktioner i dina .NET-applikationer. Genom att följa de skisserade stegen kan du enkelt ställa in en mätlicens och börja utnyttja funktionerna i GroupDocs.Viewer i dina projekt.
## FAQ's
### F: Var kan jag hitta dokumentation för GroupDocs.Viewer för .NET?
 Du hittar dokumentationen[här](https://reference.groupdocs.com/viewer/net/).
### F: Finns det en gratis testversion tillgänglig för GroupDocs.Viewer för .NET?
 Ja, du kan komma åt den kostnadsfria provperioden[här](https://releases.groupdocs.com/).
### F: Hur kan jag få tillfälliga licenser för teständamål?
 Tillfälliga licenser kan erhållas[här](https://purchase.groupdocs.com/temporary-license/).
### F: Var kan jag söka support eller ställa frågor relaterade till GroupDocs.Viewer för .NET?
 Du kan söka support och ställa frågor på GroupDocs.Viewer-forumet[här](https://forum.groupdocs.com/c/viewer/9).
### F: Var kan jag köpa en licens för GroupDocs.Viewer för .NET?
 Du kan köpa en licens[här](https://purchase.groupdocs.com/buy).