---
title: Gemeten licentie instellen
linktitle: Gemeten licentie instellen
second_title: GroupDocs.Viewer .NET-API
description: Verbeter uw .NET-toepassingen met GroupDocs.Viewer voor naadloze documentweergave. Integreer eenvoudig functionaliteiten voor documentweergave in uw projecten.
weight: 12
url: /nl/net/getting-started/set-metered-license/
---
## Invoering
In de wereld van .NET-ontwikkeling is het integreren van krachtige documentweergavemogelijkheden in uw applicaties essentieel voor het verbeteren van de gebruikerservaring en functionaliteit. GroupDocs.Viewer voor .NET biedt een robuuste oplossing voor het naadloos integreren van documentweergavefunctionaliteiten in uw .NET-projecten. Of u nu werkt met PDF's, Microsoft Office-documenten of verschillende afbeeldingsformaten, GroupDocs.Viewer vereenvoudigt het proces van het weergeven en weergeven van deze documenten in uw toepassingen.
## Vereisten
Voordat u ingaat op de implementatie van GroupDocs.Viewer voor .NET, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
### 1. Installeer GroupDocs.Viewer voor .NET
 Om te beginnen moet u GroupDocs.Viewer voor .NET downloaden en installeren. Je kunt de downloadlink vinden[hier](https://releases.groupdocs.com/viewer/net/). Volg de meegeleverde installatie-instructies om de bibliotheek in uw ontwikkelomgeving in te stellen.
### 2. Verkrijg een gemeten licentie
Om GroupDocs.Viewer voor .NET te kunnen gebruiken, heeft u een gemeten licentie nodig. Met deze licentie kunt u uw API-gebruik controleren en monitoren op basis van vooraf gedefinieerde quota. Volg de onderstaande stappen om uw gemeten licentie in te stellen:

## Naamruimten importeren
Zorg er eerst voor dat u de benodigde naamruimten importeert om toegang te krijgen tot de functionaliteit van GroupDocs.Viewer voor .NET:
```csharp
using System;
```

Laten we nu de voorbeeldcode in meerdere stappen opsplitsen:
## Stap 1: Declareer publieke en private sleutels
Declareer variabelen om uw openbare en privésleutels op te slaan:
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
 Zorg ervoor dat u deze vervangt`"YOUR_PUBLIC_KEY"` En`"YOUR_PRIVATE_KEY"` met uw echte sleutels.
## Stap 2: Stel de gemeten licentie in
Controleer of de publieke sleutel aanwezig is. Als dit niet het geval is, vraagt u de gebruiker de sleutels in te stellen:
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://aankoop.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## Stap 3: Initialiseer het gemeten object en stel de licentie in
Initialiseer het Gemeten object en stel de gemeten licentie in met behulp van uw openbare en privésleutels:
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## Stap 4: Bevestigingsbericht
Geef een bevestigingsbericht weer dat aangeeft dat de licentie succesvol is ingesteld:
```csharp
Console.WriteLine("License set successfully.");
```

## Conclusie
Concluderend biedt GroupDocs.Viewer voor .NET een uitgebreide oplossing voor het integreren van functionaliteit voor het bekijken van documenten in uw .NET-toepassingen. Door de beschreven stappen te volgen, kunt u eenvoudig een gemeten licentie instellen en de mogelijkheden van GroupDocs.Viewer binnen uw projecten gaan benutten.
## Veelgestelde vragen
### Vraag: Waar kan ik documentatie vinden voor GroupDocs.Viewer voor .NET?
 U kunt de documentatie vinden[hier](https://tutorials.groupdocs.com/viewer/net/).
### Vraag: Is er een gratis proefversie beschikbaar voor GroupDocs.Viewer voor .NET?
 Ja, u heeft toegang tot de gratis proefperiode[hier](https://releases.groupdocs.com/).
### Vraag: Hoe kan ik tijdelijke licenties verkrijgen voor testdoeleinden?
 Er kunnen tijdelijke licenties worden verkregen[hier](https://purchase.groupdocs.com/temporary-license/).
### Vraag: Waar kan ik ondersteuning zoeken of vragen stellen met betrekking tot GroupDocs.Viewer voor .NET?
 U kunt ondersteuning zoeken en vragen stellen op het GroupDocs.Viewer-forum[hier](https://forum.groupdocs.com/c/viewer/9).
### Vraag: Waar kan ik een licentie kopen voor GroupDocs.Viewer voor .NET?
 U kunt een licentie kopen[hier](https://purchase.groupdocs.com/buy).