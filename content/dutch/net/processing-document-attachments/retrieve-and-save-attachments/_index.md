---
"description": "Beheer documentbijlagen efficiënt in .NET-applicaties met GroupDocs.Viewer. Haal bijlagen probleemloos op en sla ze op."
"linktitle": "Documentbijlagen ophalen en opslaan"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Documentbijlagen ophalen en opslaan"
"url": "/nl/net/processing-document-attachments/retrieve-and-save-attachments/"
"weight": 12
---

# Documentbijlagen ophalen en opslaan

## Invoering
In het digitale tijdperk is efficiënte documentverwerking cruciaal voor zowel bedrijven als particulieren. Of het nu gaat om het beheren van e-mails, het bekijken van contracten of het raadplegen van rapporten, een betrouwbare tool voor documentvisualisatie is essentieel. GroupDocs.Viewer voor .NET is een robuuste oplossing waarmee gebruikers moeiteloos verschillende documentformaten kunnen bekijken en ermee kunnen werken, rechtstreeks vanuit hun .NET-applicaties.

![Documentbijlagen ophalen en opslaan met GroupDocs.Viewer .NET](/viewer/processing-document-attachments/retrieve-and-save-document-attachments.png)

## Vereisten
Voordat u GroupDocs.Viewer voor .NET gaat gebruiken voor het ophalen en opslaan van documentbijlagen, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. Operationele omgeving: Een werkomgeving ingericht met .NET Framework.
2. Installatie: GroupDocs.Viewer voor .NET-bibliotheek gedownload en geïnstalleerd. U kunt de bibliotheek openen via de [downloadlink](https://releases.groupdocs.com/viewer/net/).
3. Basiskennis: Kennis van de programmeertaal C#.
4. Bron van het document: Toegang tot een voorbeelddocument met bijlagen voor demonstratiedoeleinden.

## Naamruimten importeren
Om GroupDocs.Viewer voor .NET te kunnen gebruiken voor het ophalen en opslaan van documentbijlagen, importeert u de benodigde naamruimten:
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Results;
```

## Stap 1: Definieer de uitvoermap
```csharp
string outputDirectory = "Your Document Directory";
```
Definieer de map waarin u de bijlagen uit het document wilt opslaan.
## Stap 2: Viewerobject instantiëren
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
Maak een exemplaar van het Viewer-object met het pad naar het document met bijlagen.
## Stap 3: Bijlagen ophalen
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
Haal een lijst op met de bijlagen die bij het document aanwezig zijn.
## Stap 4: Bijlagen opslaan
```csharp
foreach(Attachment attachment in attachments)
{
    string filePath = Path.Combine(outputDirectory, attachment.FileName);  
    viewer.SaveAttachment(attachment, File.OpenWrite(filePath)); 
}
```
Loop door elke bijlage, definieer het bestandspad en sla de bijlage op in de opgegeven map.
## Stap 5: Succesbericht weergeven
```csharp
Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
```
Geef een succesbericht weer waarin staat dat de bijlagen succesvol zijn opgeslagen, samen met het pad naar de map.

## Conclusie
Door GroupDocs.Viewer voor .NET te integreren in uw workflows voor documentverwerking, stroomlijnt u het beheer van bijlagen en biedt u efficiëntie en gemak. Door de bovenstaande stapsgewijze handleiding te volgen, kunnen gebruikers naadloos documentbijlagen ophalen en opslaan in hun .NET-applicaties.
## Veelgestelde vragen
### Kan GroupDocs.Viewer voor .NET verschillende documentformaten verwerken?
Ja, GroupDocs.Viewer ondersteunt een breed scala aan documentformaten, waaronder PDF, Microsoft Office-documenten, afbeeldingen en meer.
### Is er een gratis proefversie beschikbaar voor GroupDocs.Viewer voor .NET?
Ja, u kunt de gratis proefperiode gebruiken vanaf [hier](https://releases.groupdocs.com/).
### Hoe kan ik tijdelijke licenties voor GroupDocs.Viewer voor .NET verkrijgen?
Tijdelijke licenties kunnen worden verkregen bij [deze link](https://purchase.groupdocs.com/temporary-license/).
### Waar kan ik documentatie vinden voor GroupDocs.Viewer voor .NET?
Er is uitgebreide documentatie beschikbaar [hier](https://tutorials.groupdocs.com/viewer/net/).
### Welke ondersteuningsopties zijn beschikbaar voor GroupDocs.Viewer voor .NET?
U kunt hulp krijgen via het communityforum [hier](https://forum.groupdocs.com/c/viewer/9).