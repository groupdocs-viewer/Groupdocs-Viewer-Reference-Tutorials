---
"description": "Erweitern Sie Ihre .NET-Anwendungen mit GroupDocs.Viewer für eine nahtlose Dokumentanzeige. Integrieren Sie problemlos Dokument-Rendering-Funktionen in Ihre Projekte."
"linktitle": "Gemessene Lizenz festlegen"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Gemessene Lizenz festlegen"
"url": "/de/net/getting-started/set-metered-license/"
"weight": 12
type: docs
---
# Gemessene Lizenz festlegen

## Einführung
In der .NET-Entwicklung ist die Integration leistungsstarker Dokumentanzeigefunktionen in Ihre Anwendungen unerlässlich, um Benutzerfreundlichkeit und Funktionalität zu verbessern. GroupDocs.Viewer für .NET bietet eine robuste Lösung für die nahtlose Integration von Dokumentanzeigefunktionen in Ihre .NET-Projekte. Ob Sie mit PDFs, Microsoft Office-Dokumenten oder verschiedenen Bildformaten arbeiten – GroupDocs.Viewer vereinfacht das Rendern und Anzeigen dieser Dokumente in Ihren Anwendungen.

![Legen Sie eine gebührenpflichtige Lizenz mit GroupDocs.Viewer für .NET fest](/viewer/getting-started/set-metered-license.png)

## Voraussetzungen
Bevor Sie mit der Implementierung von GroupDocs.Viewer für .NET beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
### 1. Installieren Sie GroupDocs.Viewer für .NET
Zunächst müssen Sie GroupDocs.Viewer für .NET herunterladen und installieren. Den Download-Link finden Sie hier [Hier](https://releases.groupdocs.com/viewer/net/). Befolgen Sie die bereitgestellten Installationsanweisungen, um die Bibliothek in Ihrer Entwicklungsumgebung einzurichten.
### 2. Erwerben Sie eine gebührenpflichtige Lizenz
Um GroupDocs.Viewer für .NET nutzen zu können, benötigen Sie eine mengengeregelte Lizenz. Mit dieser Lizenz können Sie Ihre API-Nutzung anhand vordefinierter Kontingente steuern und überwachen. Führen Sie die folgenden Schritte aus, um Ihre mengengeregelte Lizenz einzurichten:

## Namespaces importieren
Stellen Sie zunächst sicher, dass Sie die erforderlichen Namespaces importieren, um auf die von GroupDocs.Viewer für .NET bereitgestellte Funktionalität zuzugreifen:
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
Stellen Sie sicher, dass Sie `"YOUR_PUBLIC_KEY"` Und `"YOUR_PRIVATE_KEY"` mit Ihren tatsächlichen Schlüsseln.
## Schritt 2: Gemessene Lizenz festlegen
Überprüfen Sie, ob der öffentliche Schlüssel bereitgestellt wurde. Wenn nicht, fordern Sie den Benutzer auf, die Schlüssel festzulegen:
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://purchase.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## Schritt 3: Metered Object initialisieren und Lizenz festlegen
Initialisieren Sie das Metered-Objekt und legen Sie die gemessene Lizenz mit Ihrem öffentlichen und privaten Schlüssel fest:
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## Schritt 4: Bestätigungsnachricht
Zeigen Sie eine Bestätigungsmeldung an, die angibt, dass die Lizenz erfolgreich eingerichtet wurde:
```csharp
Console.WriteLine("License set successfully.");
```

## Abschluss
Zusammenfassend lässt sich sagen, dass GroupDocs.Viewer für .NET eine umfassende Lösung für die Integration von Dokumentanzeigefunktionen in Ihre .NET-Anwendungen bietet. Mit den beschriebenen Schritten können Sie ganz einfach eine gebührenpflichtige Lizenz einrichten und die Funktionen von GroupDocs.Viewer in Ihren Projekten nutzen.
## Häufig gestellte Fragen
### F: Wo finde ich Dokumentation für GroupDocs.Viewer für .NET?
Die Dokumentation finden Sie [Hier](https://tutorials.groupdocs.com/viewer/net/).
### F: Gibt es eine kostenlose Testversion für GroupDocs.Viewer für .NET?
Ja, Sie können auf die kostenlose Testversion zugreifen [Hier](https://releases.groupdocs.com/).
### F: Wie kann ich temporäre Lizenzen zu Testzwecken erhalten?
Temporäre Lizenzen können erworben werden [Hier](https://purchase.groupdocs.com/temporary-license/).
### F: Wo kann ich Unterstützung suchen oder Fragen zu GroupDocs.Viewer für .NET stellen?
Sie können im GroupDocs.Viewer-Forum Unterstützung suchen und Fragen stellen. [Hier](https://forum.groupdocs.com/c/viewer/9).
### F: Wo kann ich eine Lizenz für GroupDocs.Viewer für .NET erwerben?
Sie können eine Lizenz erwerben [Hier](https://purchase.groupdocs.com/buy).