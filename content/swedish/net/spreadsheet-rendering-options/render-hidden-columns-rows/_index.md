---
title: Gör dolda kolumner och rader
linktitle: Gör dolda kolumner och rader
second_title: GroupDocs.Viewer .NET API
description: Lås upp dolda data i kalkylblad utan ansträngning med GroupDocs.Viewer för .NET. Följ vår steg-för-steg-guide för att avslöja dolda kolumner och rader.
weight: 13
url: /sv/net/spreadsheet-rendering-options/render-hidden-columns-rows/
---

# Gör dolda kolumner och rader

## Introduktion
När det gäller dokumentvisualisering står GroupDocs.Viewer för .NET högt som ett robust verktyg som underlättar sömlös rendering av olika dokumentformat. En spännande förmåga är möjligheten att avslöja dolda kolumner och rader i kalkylblad. I den här handledningen kommer vi att fördjupa oss i stegen för att låsa upp den här funktionen och frigöra potentialen i din data.
## Förutsättningar
Innan du ger dig ut på denna resa, se till att du har följande förutsättningar på plats:
- GroupDocs.Viewer för .NET: Se till att du har den senaste versionen installerad. Om inte kan du ladda ner den från[officiell hemsida](https://releases.groupdocs.com/viewer/net/).
- Dokumentfil: Förbered ett exempeldokument i ett kalkylbladsformat (t.ex. SAMPLE.XLSX) för att experimentera med dolda kolumner och rader.
- Utvecklingsmiljö: Skapa en arbetsmiljö, helst med Visual Studio eller någon annan lämplig IDE för .NET-utveckling.
## Importera namnområden
I ditt .NET-projekt importerar du nödvändiga namnområden för att effektivt utnyttja GroupDocs.Viewer-funktionerna:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Steg 1: Konfigurera utdatakatalog
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Definiera utdatakatalogen där de renderade HTML-sidorna ska lagras. Justera filsökvägsformatet därefter.
## Steg 2: Initiera Viewer och konfigurera alternativ
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHiddenColumns = true;
    options.SpreadsheetOptions.RenderHiddenRows = true;
```
Skapa en Viewer-instans genom att ange sökvägen till ditt kalkylarksdokument. Konfigurera HTML-vyalternativ för att bädda in resurser och aktivera rendering av dolda kolumner och rader.
## Steg 3: Utför renderingsprocessen
```csharp
    viewer.View(options);
}
```
Anropa View-metoden på visningsobjektet och skicka de konfigurerade alternativen. Detta initierar renderingsprocessen.
## Steg 4: Kontrollera utdata
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Verifiera att renderingen av källdokumentet lyckades och lokalisera utdata i den angivna katalogen.
## Slutsats
Att låsa upp dolda kolumner och rader i dina kalkylblad blir en bris med GroupDocs.Viewer för .NET. Den här handledningen har utrustat dig med de grundläggande stegen för att avslöja dolda data, vilket ger en mer heltäckande bild av dina dokument.
## Vanliga frågor
### Kan jag återge dolda kolumner och rader i andra dokumentformat än kalkylblad?
Ja, GroupDocs.Viewer stöder olika dokumentformat, inklusive Word, PDF och PowerPoint, förutom kalkylblad.
### Finns det en gräns för antalet dolda kolumner och rader som kan renderas?
GroupDocs.Viewer hanterar effektivt rendering för ett stort antal dolda kolumner och rader. Men extrema fall med en stor mängd dolda data kan påverka prestandan.
### Kan jag anpassa utdataformatet för de renderade data?
Absolut! GroupDocs.Viewer erbjuder flexibla alternativ för att anpassa utdata, så att du kan skräddarsy den renderade informationen efter dina specifika behov.
### Finns det några licensöverväganden för att använda GroupDocs.Viewer?
 Ja, se till att du har rätt licens för din användning. Utforska licensalternativ på[GroupDocs köp](https://purchase.groupdocs.com/buy) eller skaffa en[tillfällig licens](https://purchase.groupdocs.com/temporary-license/) för provning.
### Var kan jag söka hjälp eller få kontakt med GroupDocs-communityt för stöd?
 Besök[GroupDocs.Viewer-forum](https://forum.groupdocs.com/c/viewer/9) för stöd, diskussioner och gemenskapsinteraktion.