---
"description": "Förbättra dina .NET-applikationer med GroupDocs.Viewer för sömlös dokumentvisning. Integrera enkelt dokumentrenderingsfunktioner i dina projekt."
"linktitle": "Ställ in uppmätt licens"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Ställ in uppmätt licens"
"url": "/sv/net/getting-started/set-metered-license/"
"weight": 12
---

# Ställ in uppmätt licens

## Introduktion
.NET-utvecklingens värld är det viktigt att integrera kraftfulla dokumentvisningsfunktioner i dina applikationer för att förbättra användarupplevelsen och funktionaliteten. GroupDocs.Viewer för .NET erbjuder en robust lösning för att sömlöst integrera dokumentvisningsfunktioner i dina .NET-projekt. Oavsett om du arbetar med PDF-filer, Microsoft Office-dokument eller olika bildformat förenklar GroupDocs.Viewer processen att rendera och visa dessa dokument i dina applikationer.

![Ställ in en uppmätt licens med GroupDocs.Viewer för .NET](/viewer/getting-started/set-metered-license.png)

## Förkunskapskrav
Innan du börjar implementera GroupDocs.Viewer för .NET, se till att du har följande förutsättningar på plats:
### 1. Installera GroupDocs.Viewer för .NET
För att börja måste du ladda ner och installera GroupDocs.Viewer för .NET. Du hittar nedladdningslänken [här](https://releases.groupdocs.com/viewer/net/)Följ installationsanvisningarna för att konfigurera biblioteket i din utvecklingsmiljö.
### 2. Skaffa mätarlicens
För att kunna använda GroupDocs.Viewer för .NET behöver du skaffa en mätad licens. Denna licens låter dig kontrollera och övervaka din API-användning baserat på fördefinierade kvoter. Följ stegen nedan för att konfigurera din mätade licens:

## Importera namnrymder
Se först till att du importerar de namnrymder som krävs för att komma åt funktionerna som tillhandahålls av GroupDocs.Viewer för .NET:
```csharp
using System;
```

Nu ska vi dela upp exempelkoden i flera steg:
## Steg 1: Deklarera offentliga och privata nycklar
Deklarera variabler för att lagra dina publika och privata nycklar:
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
Se till att byta ut `"YOUR_PUBLIC_KEY"` och `"YOUR_PRIVATE_KEY"` med dina riktiga nycklar.
## Steg 2: Ställ in licensmätning
Kontrollera om den publika nyckeln har angetts. Om inte, uppmana användaren att ange nycklarna:
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://purchase.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## Steg 3: Initiera mätobjekt och ange licens
Initiera det mätta objektet och ange den mätta licensen med dina publika och privata nycklar:
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## Steg 4: Bekräftelsemeddelande
Visa ett bekräftelsemeddelande som anger att licensen har konfigurerats:
```csharp
Console.WriteLine("License set successfully.");
```

## Slutsats
Sammanfattningsvis erbjuder GroupDocs.Viewer för .NET en omfattande lösning för att integrera dokumentvisningsfunktioner i dina .NET-applikationer. Genom att följa de beskrivna stegen kan du enkelt konfigurera en licens med uppmätt avgift och börja utnyttja GroupDocs.Viewers funktioner i dina projekt.
## Vanliga frågor
### F: Var kan jag hitta dokumentation för GroupDocs.Viewer för .NET?
Du kan hitta dokumentationen [här](https://tutorials.groupdocs.com/viewer/net/).
### F: Finns det en gratis testversion av GroupDocs.Viewer för .NET?
Ja, du kan få tillgång till gratis provperioden [här](https://releases.groupdocs.com/).
### F: Hur kan jag få tillfälliga licenser för teständamål?
Tillfälliga licenser kan erhållas [här](https://purchase.groupdocs.com/temporary-license/).
### F: Var kan jag söka support eller ställa frågor relaterade till GroupDocs.Viewer för .NET?
Du kan söka support och ställa frågor på GroupDocs.Viewer-forumet. [här](https://forum.groupdocs.com/c/viewer/9).
### F: Var kan jag köpa en licens för GroupDocs.Viewer för .NET?
Du kan köpa en licens [här](https://purchase.groupdocs.com/buy).