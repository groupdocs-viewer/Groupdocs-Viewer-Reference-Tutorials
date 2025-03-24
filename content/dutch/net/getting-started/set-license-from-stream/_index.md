---
title: Licentie instellen vanuit Stream
linktitle: Licentie instellen vanuit Stream
second_title: GroupDocs.Viewer .NET-API
description: Verbeter uw .NET-toepassingen met GroupDocs.Viewer voor naadloze documentweergave. Volg onze stapsgewijze handleiding en integreer moeiteloos krachtige documentweergavemogelijkheden.
weight: 11
url: /nl/net/getting-started/set-license-from-stream/
---

# Licentie instellen vanuit Stream

## Invoering
Wilt u uw .NET-applicaties uitrusten met geavanceerde mogelijkheden voor documentweergave? GroupDocs.Viewer voor .NET biedt een uitgebreide oplossing om de functionaliteit voor het bekijken van documenten naadloos in uw projecten te integreren. In deze zelfstudie verdiepen we ons in het proces van het gebruik van GroupDocs.Viewer voor .NET om uw toepassingen te verrijken met krachtige documentweergavemogelijkheden. 
## Vereisten
Voordat we ingaan op het integratieproces, moet je ervoor zorgen dat je aan de volgende vereisten voldoet:
1. Basiskennis van .NET-ontwikkeling: Bekendheid met C# en .NET-framework is essentieel om samen met deze tutorial te volgen.
   
2.  GroupDocs.Viewer voor .NET-pakket: Zorg ervoor dat u het GroupDocs.Viewer voor .NET-pakket hebt gedownload en geïnstalleerd. U kunt deze verkrijgen bij de[download link](https://releases.groupdocs.com/viewer/net/).
3.  Toegang tot GroupDocs-documentatie: Bewaar de[documentatie](https://tutorials.groupdocs.com/viewer/net/) handig als referentie tijdens het integratieproces.

## Naamruimten importeren
Importeer om te beginnen de benodigde naamruimten in uw .NET-applicatie. Volg deze stappen:
### Stap 1: Open uw .NET-project.
Zorg ervoor dat uw .NET-project is geopend in de ontwikkelomgeving van uw voorkeur.
### Stap 2: Voeg GroupDocs.Viewer-naamruimte toe.
Voeg in uw codebestand de volgende naamruimte toe om toegang te krijgen tot de GroupDocs.Viewer-functionaliteiten:
```csharp
using System;
using System.IO;
```
## Licentie instellen vanuit Stream
De volgende stap omvat het instellen van de licentie van een stream. Volg deze gedetailleerde stappen:
### Stap 1: Definieer de uitvoerdirectory.
Stel de map in waar uw documenten worden opgeslagen door de uitvoermap te definiëren:
```csharp
string outputDirectory = "Your Document Directory";
```
### Stap 2: Controleer het bestaan van licentiebestanden.
Controleer of het licentiebestand in uw projectmap bestaat:
```csharp
if (File.Exists(Utils.LicensePath))
```
### Stap 3: Licentie instellen.
Als het licentiebestand bestaat, stelt u de licentie in met behulp van de meegeleverde stream:
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### Stap 4: Afhandeling van licentieafwezigheid.
Als het licentiebestand niet wordt gevonden, geef dan instructies om een licentie te verkrijgen:
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://Purchase.groupdocs.com/faqs/licensing. " +
                      "\nLearn how to request a temporary license at https://aankoop.groupdocs.com/tijdelijke-licentie.");
}
```

## Conclusie
Gefeliciteerd! U heeft met succes geleerd hoe u GroupDocs.Viewer voor .NET in uw toepassingen kunt integreren. Met deze krachtige tool kunt u nu moeiteloos verschillende documentformaten binnen uw .NET-projecten bekijken, waardoor de gebruikerservaring en productiviteit worden verbeterd.
## Veelgestelde vragen
### Heb ik een licentie nodig om GroupDocs.Viewer voor .NET te gebruiken?
Ja, u heeft een licentie nodig om GroupDocs.Viewer voor .NET te gebruiken. U kunt een tijdelijke of permanente licentie verkrijgen via de GroupDocs-website.
### Kan ik GroupDocs.Viewer integreren in mijn ASP.NET-applicatie?
Absoluut! GroupDocs.Viewer voor .NET kan naadloos worden geïntegreerd in zowel desktop- als webapplicaties, inclusief ASP.NET.
### Welke documentformaten worden ondersteund door GroupDocs.Viewer?
GroupDocs.Viewer ondersteunt een breed scala aan documentformaten, waaronder PDF, Microsoft Office (Word, Excel, PowerPoint), afbeeldingen en meer.
### Is GroupDocs.Viewer compatibel met .NET Core?
Ja, GroupDocs.Viewer voor .NET is compatibel met zowel .NET Framework als .NET Core.
### Kan ik de viewerinterface aanpassen aan het thema van mijn toepassing?
Ja, GroupDocs.Viewer biedt uitgebreide aanpassingsmogelijkheden, waardoor u de viewerinterface naadloos kunt afstemmen op het thema van uw toepassing.