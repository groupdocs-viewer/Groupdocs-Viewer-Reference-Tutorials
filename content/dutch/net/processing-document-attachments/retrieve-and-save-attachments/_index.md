---
title: Documentbijlagen ophalen en opslaan
linktitle: Documentbijlagen ophalen en opslaan
second_title: GroupDocs.Viewer .NET-API
description: Beheer documentbijlagen efficiënt binnen .NET-applicaties met GroupDocs.Viewer. Haal bijlagen probleemloos op en sla ze op.
weight: 12
url: /nl/net/processing-document-attachments/retrieve-and-save-attachments/
---

# Documentbijlagen ophalen en opslaan

## Invoering
In het digitale tijdperk is efficiënte documentverwerking cruciaal voor zowel bedrijven als particulieren. Of het nu gaat om het beheren van e-mails, het bekijken van contracten of het openen van rapporten: het hebben van een betrouwbare tool voor documentvisualisatie is essentieel. GroupDocs.Viewer voor .NET komt naar voren als een robuuste oplossing, waarmee gebruikers moeiteloos verschillende documentformaten kunnen bekijken en ermee kunnen communiceren, rechtstreeks binnen hun .NET-applicaties.
## Vereisten
Voordat u GroupDocs.Viewer voor .NET gaat gebruiken voor het ophalen en opslaan van documentbijlagen, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. Bedrijfsomgeving: een werkomgeving die is opgezet met het .NET-framework.
2.  Installatie: GroupDocs.Viewer voor .NET-bibliotheek gedownload en geïnstalleerd. U kunt de bibliotheek bereiken via de[download link](https://releases.groupdocs.com/viewer/net/).
3. Basiskennis: Bekendheid met de programmeertaal C#.
4. Documentbron: toegang tot een voorbeelddocument met bijlagen voor demonstratiedoeleinden.

## Naamruimten importeren
Om GroupDocs.Viewer voor .NET te gaan gebruiken voor het ophalen en opslaan van documentbijlagen, importeert u de benodigde naamruimten:
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Results;
```

## Stap 1: Definieer de uitvoerdirectory
```csharp
string outputDirectory = "Your Document Directory";
```
Definieer de map waarin u de bijlagen wilt opslaan die u uit het document hebt opgehaald.
## Stap 2: Instantie van Viewer-object
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
Instantieer het Viewer-object met het pad naar het document met bijlagen.
## Stap 3: bijlagen ophalen
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
Haal een lijst op met bijlagen in het document.
## Stap 4: Bijlagen opslaan
```csharp
foreach(Attachment attachment in attachments)
{
    string filePath = Path.Combine(outputDirectory, attachment.FileName);  
    viewer.SaveAttachment(attachment, File.OpenWrite(filePath)); 
}
```
Doorloop elke bijlage, definieer het bestandspad en sla de bijlage op in de opgegeven map.
## Stap 5: Succesbericht weergeven
```csharp
Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
```
Geef een succesbericht weer dat aangeeft dat de bijlagen succesvol zijn opgeslagen, samen met het mappad.

## Conclusie
Door GroupDocs.Viewer voor .NET op te nemen in uw documentverwerkingsworkflows wordt het proces van het beheren van bijlagen gestroomlijnd, wat efficiëntie en gemak oplevert. Door de hierboven beschreven stapsgewijze handleiding te volgen, kunnen gebruikers naadloos documentbijlagen ophalen en opslaan binnen hun .NET-applicaties.
## Veelgestelde vragen
### Kan GroupDocs.Viewer voor .NET verschillende documentformaten verwerken?
Ja, GroupDocs.Viewer ondersteunt een breed scala aan documentformaten, waaronder PDF, Microsoft Office-documenten, afbeeldingen en meer.
### Is er een gratis proefversie beschikbaar voor GroupDocs.Viewer voor .NET?
 Ja, u kunt toegang krijgen tot de gratis proefperiode vanaf[hier](https://releases.groupdocs.com/).
### Hoe kan ik tijdelijke licenties verkrijgen voor GroupDocs.Viewer voor .NET?
 Tijdelijke licenties kunnen worden verkregen via[deze link](https://purchase.groupdocs.com/temporary-license/).
### Waar kan ik documentatie vinden voor GroupDocs.Viewer voor .NET?
 Er is uitgebreide documentatie beschikbaar[hier](https://tutorials.groupdocs.com/viewer/net/).
### Welke ondersteuningsopties zijn beschikbaar voor GroupDocs.Viewer voor .NET?
 U kunt hulp zoeken op het communityforum[hier](https://forum.groupdocs.com/c/viewer/9).