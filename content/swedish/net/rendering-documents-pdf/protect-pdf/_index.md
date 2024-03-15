---
title: Skydda renderad PDF med lösenord
linktitle: Skydda renderad PDF med lösenord
second_title: GroupDocs.Viewer .NET API
description: Skydda dina återgivna PDF-filer med lösenord enkelt med Groupdocs.Viewer för .NET. Håll dina dokument säkra och konfidentiella.
type: docs
weight: 12
url: /sv/net/rendering-documents-pdf/protect-pdf/
---
## Introduktion
den här handledningen får du lära dig hur du använder Groupdocs.Viewer för .NET för att skydda en renderad PDF med ett lösenord. Genom att lägga till säkerhetsåtgärder kan du kontrollera åtkomsten till dina PDF-dokument, vilket säkerställer konfidentialitet och integritet.
## Förutsättningar
Innan du börjar, se till att du har följande:
1.  Groupdocs.Viewer för .NET Library: Ladda ner och installera biblioteket från[hemsida](https://releases.groupdocs.com/viewer/net/).
2. Utvecklingsmiljö: Se till att du har en fungerande utvecklingsmiljö inrättad för .NET-utveckling.

## Importera namnområden
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Steg 1: Definiera utdatakatalog och filsökväg
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## Steg 2: Initiera Viewer Object och Ange säkerhetsalternativ
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    Security security = new Security
    {
        DocumentOpenPassword = "o123",
        PermissionsPassword = "p123",
        Permissions = Permissions.AllowAll ^ Permissions.DenyPrinting
    };
```
## Steg 3: Ställ in PDF-vyalternativ
```csharp
    PdfViewOptions options = new PdfViewOptions(filePath)
    {
        Security = security
    };
```
## Steg 4: Återge dokument med säkerhetsalternativ
```csharp
    viewer.View(options);
}
```
## Steg 5: Kontrollera det renderade dokumentet
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Genom att följa dessa steg kan du skydda en renderad PDF med ett lösenord med Groupdocs.Viewer för .NET. Detta säkerställer att dina dokument förblir säkra och tillgängliga endast för behöriga användare.

## Slutsats
Att säkra PDF-dokument är viktigt för att upprätthålla konfidentialitet och integritet. Med Groupdocs.Viewer för .NET kan du enkelt skydda renderade PDF-filer med lösenord och kontrollera åtkomsten till känslig information.

## FAQ's
### Kan jag skydda PDF-filer med olika behörighetsnivåer?
Ja, du kan ange olika behörigheter för visning, utskrift, kopiering och mer samtidigt som du skyddar PDF-filer med lösenord.
### Är Groupdocs.Viewer kompatibel med olika filformat?
Absolut! Groupdocs.Viewer stöder rendering av ett brett utbud av filformat, inklusive DOCX, XLSX, PPTX, PDF och mer.
### Kan jag integrera Groupdocs.Viewer i min befintliga .NET-applikation?
Säkert! Groupdocs.Viewer tillhandahåller API:er för sömlös integrering i .NET-applikationer, och erbjuder robusta dokumentvisningsmöjligheter.
### Erbjuder Groupdocs.Viewer stöd för molnlagringstjänster?
Ja, Groupdocs.Viewer stöder integration med populära molnlagringstjänster som Dropbox, Google Drive och Amazon S3, så att du kan rendera dokument lagrade i molnet.
### Finns det en testversion tillgänglig för Groupdocs.Viewer?
 Ja, du kan komma igång med Groupdocs.Viewer genom att komma åt den kostnadsfria testversionen från[hemsida](https://releases.groupdocs.com/).