---
"description": "Verbeter uw .NET-applicaties met GroupDocs.Viewer voor naadloze documentweergave. Integreer eenvoudig documentweergavefuncties in uw projecten."
"linktitle": "Metered-licentie instellen"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Metered-licentie instellen"
"url": "/nl/net/getting-started/set-metered-license/"
"weight": 12
type: docs
---
# Metered-licentie instellen

## Invoering
In de wereld van .NET-ontwikkeling is het integreren van krachtige documentweergavemogelijkheden in uw applicaties essentieel voor het verbeteren van de gebruikerservaring en functionaliteit. GroupDocs.Viewer voor .NET biedt een robuuste oplossing voor het naadloos integreren van documentweergavefuncties in uw .NET-projecten. Of u nu werkt met PDF's, Microsoft Office-documenten of verschillende afbeeldingsformaten, GroupDocs.Viewer vereenvoudigt het proces van het renderen en weergeven van deze documenten in uw applicaties.

![Stel een gemeten licentie in met GroupDocs.Viewer voor .NET](/viewer/getting-started/set-metered-license.png)

## Vereisten
Voordat u begint met de implementatie van GroupDocs.Viewer voor .NET, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
### 1. GroupDocs.Viewer voor .NET installeren
Om te beginnen moet u GroupDocs.Viewer voor .NET downloaden en installeren. U vindt de downloadlink hier. [hier](https://releases.groupdocs.com/viewer/net/)Volg de installatie-instructies om de bibliotheek in uw ontwikkelomgeving in te stellen.
### 2. Verkrijg een meterlicentie
Om GroupDocs.Viewer voor .NET te kunnen gebruiken, hebt u een gedoseerde licentie nodig. Met deze licentie kunt u uw API-gebruik beheren en monitoren op basis van vooraf gedefinieerde quota. Volg de onderstaande stappen om uw gedoseerde licentie in te stellen:

## Naamruimten importeren
Zorg er eerst voor dat u de benodigde naamruimten importeert om toegang te krijgen tot de functionaliteit die GroupDocs.Viewer voor .NET biedt:
```csharp
using System;
```

Laten we de voorbeeldcode nu opsplitsen in meerdere stappen:
## Stap 1: Publieke en privésleutels declareren
Declareer variabelen om uw openbare en persoonlijke sleutels op te slaan:
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
Zorg ervoor dat u deze vervangt `"YOUR_PUBLIC_KEY"` En `"YOUR_PRIVATE_KEY"` met uw eigen sleutels.
## Stap 2: Stel een gemeten licentie in
Controleer of de openbare sleutel beschikbaar is. Zo niet, vraag de gebruiker dan om de sleutels in te stellen:
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://purchase.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## Stap 3: Initialiseer het gemeten object en stel de licentie in
Initialiseer het Metered-object en stel de gemeten licentie in met behulp van uw openbare en persoonlijke sleutels:
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## Stap 4: Bevestigingsbericht
Geef een bevestigingsbericht weer waarin staat dat de licentie succesvol is ingesteld:
```csharp
Console.WriteLine("License set successfully.");
```

## Conclusie
Kortom, GroupDocs.Viewer voor .NET biedt een complete oplossing voor het integreren van documentweergavefunctionaliteit in uw .NET-applicaties. Door de beschreven stappen te volgen, kunt u eenvoudig een gelicentieerde licentie instellen en de mogelijkheden van GroupDocs.Viewer binnen uw projecten benutten.
## Veelgestelde vragen
### V: Waar kan ik documentatie vinden voor GroupDocs.Viewer voor .NET?
De documentatie vindt u hier [hier](https://tutorials.groupdocs.com/viewer/net/).
### V: Is er een gratis proefversie beschikbaar voor GroupDocs.Viewer voor .NET?
Ja, u kunt deelnemen aan de gratis proefperiode [hier](https://releases.groupdocs.com/).
### V: Hoe kan ik tijdelijke licenties voor testdoeleinden verkrijgen?
Tijdelijke vergunningen kunnen worden verkregen [hier](https://purchase.groupdocs.com/temporary-license/).
### V: Waar kan ik ondersteuning krijgen of vragen stellen over GroupDocs.Viewer voor .NET?
U kunt ondersteuning zoeken en vragen stellen op het GroupDocs.Viewer-forum [hier](https://forum.groupdocs.com/c/viewer/9).
### V: Waar kan ik een licentie voor GroupDocs.Viewer voor .NET kopen?
U kunt een licentie kopen [hier](https://purchase.groupdocs.com/buy).