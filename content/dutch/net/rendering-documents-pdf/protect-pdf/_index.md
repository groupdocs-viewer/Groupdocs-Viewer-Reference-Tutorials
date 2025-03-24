---
title: Bescherm gerenderde PDF met wachtwoord
linktitle: Bescherm gerenderde PDF met wachtwoord
second_title: GroupDocs.Viewer .NET-API
description: Bescherm uw weergegeven PDF's eenvoudig met wachtwoorden met Groupdocs.Viewer voor .NET. Houd uw documenten veilig en vertrouwelijk.
weight: 12
url: /nl/net/rendering-documents-pdf/protect-pdf/
---

# Bescherm gerenderde PDF met wachtwoord

## Invoering
In deze zelfstudie leert u hoe u Groupdocs.Viewer voor .NET kunt gebruiken om een weergegeven PDF met een wachtwoord te beveiligen. Door beveiligingsmaatregelen toe te voegen, kunt u de toegang tot uw PDF-documenten controleren, waardoor de vertrouwelijkheid en integriteit wordt gewaarborgd.
## Vereisten
Zorg ervoor dat u over het volgende beschikt voordat u begint:
1.  Groupdocs.Viewer voor .NET-bibliotheek: Download en installeer de bibliotheek vanaf de .NET-bibliotheek[website](https://releases.groupdocs.com/viewer/net/).
2. Ontwikkelomgeving: Zorg ervoor dat u een werkende ontwikkelomgeving hebt ingesteld voor .NET-ontwikkeling.

## Naamruimten importeren
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Stap 1: Definieer de uitvoermap en het bestandspad
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## Stap 2: Initialiseer het Viewer-object en stel beveiligingsopties in
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
## Stap 3: Stel de PDF-weergaveopties in
```csharp
    PdfViewOptions options = new PdfViewOptions(filePath)
    {
        Security = security
    };
```
## Stap 4: Geef het document weer met beveiligingsopties
```csharp
    viewer.View(options);
}
```
## Stap 5: Controleer het weergegeven document
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Door deze stappen te volgen, kunt u een gerenderde PDF met een wachtwoord beveiligen met Groupdocs.Viewer voor .NET. Dit zorgt ervoor dat uw documenten veilig blijven en alleen toegankelijk zijn voor geautoriseerde gebruikers.

## Conclusie
Het beveiligen van PDF-documenten is essentieel voor het behoud van de vertrouwelijkheid en integriteit. Met Groupdocs.Viewer voor .NET kunt u gerenderde PDF's eenvoudig beveiligen met wachtwoorden, waardoor u de toegang tot gevoelige informatie beheert.

## Veelgestelde vragen
### Kan ik PDF's beveiligen met verschillende machtigingsniveaus?
Ja, u kunt verschillende machtigingen opgeven voor het bekijken, afdrukken, kopiëren en meer, terwijl u PDF's met wachtwoorden beschermt.
### Is Groupdocs.Viewer compatibel met verschillende bestandsformaten?
Absoluut! Groupdocs.Viewer ondersteunt het weergeven van een breed scala aan bestandsindelingen, waaronder DOCX, XLSX, PPTX, PDF en meer.
### Kan ik Groupdocs.Viewer integreren in mijn bestaande .NET-applicatie?
Zeker! Groupdocs.Viewer biedt API's voor naadloze integratie in .NET-applicaties en biedt robuuste mogelijkheden voor het bekijken van documenten.
### Biedt Groupdocs.Viewer ondersteuning voor cloudopslagdiensten?
Ja, Groupdocs.Viewer ondersteunt integratie met populaire cloudopslagdiensten zoals Dropbox, Google Drive en Amazon S3, waardoor u documenten kunt weergeven die zijn opgeslagen in de cloud.
### Is er een proefversie beschikbaar voor Groupdocs.Viewer?
 Ja, u kunt aan de slag met Groupdocs.Viewer door de gratis proefversie te openen via de[website](https://releases.groupdocs.com/).