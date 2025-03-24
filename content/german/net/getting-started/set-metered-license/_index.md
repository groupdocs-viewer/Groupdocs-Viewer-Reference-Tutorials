---
title: Legen Sie die gemessene Lizenz fest
linktitle: Legen Sie die gemessene Lizenz fest
second_title: GroupDocs.Viewer .NET-API
description: Erweitern Sie Ihre .NET-Anwendungen mit GroupDocs.Viewer für eine nahtlose Dokumentenanzeige. Integrieren Sie Funktionen zum Rendern von Dokumenten ganz einfach in Ihre Projekte.
weight: 12
url: /de/net/getting-started/set-metered-license/
---

# Legen Sie die gemessene Lizenz fest

## Einführung
In der Welt der .NET-Entwicklung ist die Integration leistungsstarker Dokumentanzeigefunktionen in Ihre Anwendungen für die Verbesserung des Benutzererlebnisses und der Funktionalität von entscheidender Bedeutung. GroupDocs.Viewer für .NET bietet eine robuste Lösung für die nahtlose Integration von Dokumentanzeigefunktionen in Ihre .NET-Projekte. Ganz gleich, ob Sie mit PDFs, Microsoft Office-Dokumenten oder verschiedenen Bildformaten arbeiten, GroupDocs.Viewer vereinfacht den Prozess des Renderns und Anzeigens dieser Dokumente in Ihren Anwendungen.
## Voraussetzungen
Bevor Sie mit der Implementierung von GroupDocs.Viewer für .NET beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
### 1. Installieren Sie GroupDocs.Viewer für .NET
 Zunächst müssen Sie GroupDocs.Viewer für .NET herunterladen und installieren. Den Download-Link finden Sie hier[Hier](https://releases.groupdocs.com/viewer/net/). Befolgen Sie die bereitgestellten Installationsanweisungen, um die Bibliothek in Ihrer Entwicklungsumgebung einzurichten.
### 2. Besorgen Sie sich eine Metered-Lizenz
Um GroupDocs.Viewer für .NET nutzen zu können, müssen Sie eine kostenpflichtige Lizenz erwerben. Mit dieser Lizenz können Sie Ihre API-Nutzung basierend auf vordefinierten Kontingenten steuern und überwachen. Führen Sie die folgenden Schritte aus, um Ihre getaktete Lizenz einzurichten:

## Namespaces importieren
Stellen Sie zunächst sicher, dass Sie die erforderlichen Namespaces importieren, um auf die von GroupDocs.Viewer für .NET bereitgestellten Funktionen zuzugreifen:
```csharp
using System;
```

Lassen Sie uns nun den bereitgestellten Beispielcode in mehrere Schritte aufteilen:
## Schritt 1: Öffentliche und private Schlüssel deklarieren
Deklarieren Sie Variablen zum Speichern Ihrer öffentlichen und privaten Schlüssel:
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
 Stellen Sie sicher, dass Sie es ersetzen`"YOUR_PUBLIC_KEY"` Und`"YOUR_PRIVATE_KEY"` mit Ihren tatsächlichen Schlüsseln.
## Schritt 2: Festlegen der gemessenen Lizenz
Überprüfen Sie, ob der öffentliche Schlüssel bereitgestellt wird. Wenn nicht, fordern Sie den Benutzer auf, die Schlüssel festzulegen:
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://Purchase.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## Schritt 3: Messobjekt initialisieren und Lizenz festlegen
Initialisieren Sie das Metered-Objekt und legen Sie die Metered-Lizenz mit Ihren öffentlichen und privaten Schlüsseln fest:
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## Schritt 4: Bestätigungsnachricht
Zeigt eine Bestätigungsmeldung an, die angibt, dass die Lizenz erfolgreich eingerichtet wurde:
```csharp
Console.WriteLine("License set successfully.");
```

## Abschluss
Zusammenfassend bietet GroupDocs.Viewer für .NET eine umfassende Lösung für die Integration von Dokumentanzeigefunktionen in Ihre .NET-Anwendungen. Indem Sie die beschriebenen Schritte befolgen, können Sie ganz einfach eine getaktete Lizenz einrichten und damit beginnen, die Funktionen von GroupDocs.Viewer in Ihren Projekten zu nutzen.
## FAQs
### F: Wo finde ich Dokumentation für GroupDocs.Viewer für .NET?
 Die Dokumentation finden Sie hier[Hier](https://tutorials.groupdocs.com/viewer/net/).
### F: Gibt es eine kostenlose Testversion für GroupDocs.Viewer für .NET?
 Ja, Sie können auf die kostenlose Testversion zugreifen[Hier](https://releases.groupdocs.com/).
### F: Wie kann ich temporäre Lizenzen zu Testzwecken erhalten?
 Es können befristete Lizenzen erworben werden[Hier](https://purchase.groupdocs.com/temporary-license/).
### F: Wo kann ich Unterstützung suchen oder Fragen zu GroupDocs.Viewer für .NET stellen?
 Im GroupDocs.Viewer-Forum können Sie Unterstützung suchen und Fragen stellen[Hier](https://forum.groupdocs.com/c/viewer/9).
### F: Wo kann ich eine Lizenz für GroupDocs.Viewer für .NET erwerben?
 Sie können eine Lizenz erwerben[Hier](https://purchase.groupdocs.com/buy).