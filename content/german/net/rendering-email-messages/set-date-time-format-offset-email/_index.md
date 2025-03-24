---
title: Datum/Uhrzeit-Format und Zeitzonenversatz festlegen (E-Mail)
linktitle: Datum/Uhrzeit-Format und Zeitzonenversatz festlegen (E-Mail)
second_title: GroupDocs.Viewer .NET-API
description: Integrieren Sie GroupDocs.Viewer für .NET nahtlos in Ihre Anwendungen, um leistungsstarke Funktionen zur Dokumentenanzeige zu erhalten. Verbessern Sie das Benutzererlebnis mit anpassbaren Optionen.
weight: 11
url: /de/net/rendering-email-messages/set-date-time-format-offset-email/
---

# Datum/Uhrzeit-Format und Zeitzonenversatz festlegen (E-Mail)


## Einführung
GroupDocs.Viewer für .NET ist ein leistungsstarkes Tool, mit dem Entwickler Funktionen zur Dokumentenanzeige nahtlos in ihre .NET-Anwendungen integrieren können. Mit GroupDocs.Viewer können Sie eine Vielzahl von Dokumentformaten, darunter PDFs, Microsoft Office-Dokumente, Bilder und mehr, direkt in Ihrer Anwendung anzeigen, ohne dass externe Plugins oder Viewer erforderlich sind. In diesem umfassenden Tutorial führen wir Sie durch den Prozess der Einrichtung von GroupDocs.Viewer für .NET, erkunden seine Funktionen und zeigen, wie Sie es effektiv nutzen können, um die Dokumentanzeigefunktionen Ihrer Anwendung zu verbessern.
## Voraussetzungen
Bevor Sie mit diesem Tutorial beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1. Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem System installiert ist. GroupDocs.Viewer für .NET ist vollständig kompatibel mit Visual Studio und ermöglicht so eine nahtlose Integration in Ihre .NET-Projekte.
2.  GroupDocs.Viewer für .NET: Laden Sie GroupDocs.Viewer für .NET von herunter und installieren Sie es[Download-Link](https://releases.groupdocs.com/viewer/net/). Befolgen Sie die bereitgestellten Installationsanweisungen, um die Bibliothek in Ihrer Entwicklungsumgebung einzurichten.
3. .NET Framework: Stellen Sie sicher, dass Sie die entsprechende Version von .NET Framework installiert haben. GroupDocs.Viewer für .NET unterstützt verschiedene Versionen des .NET Frameworks, einschließlich .NET Core und .NET Standard.

## Namespaces importieren
Um GroupDocs.Viewer für .NET effektiv nutzen zu können, müssen Sie die erforderlichen Namespaces in Ihr Projekt importieren. Befolgen Sie diese Schritte, um die erforderlichen Namespaces zu importieren:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


Lassen Sie uns das bereitgestellte Beispiel in mehrere Schritte unterteilen, um jede Komponente und ihre Funktionalität zu verstehen.
## Schritt 1: Ausgabeverzeichnis und Dateipfad festlegen
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
In diesem Schritt definieren wir das Ausgabeverzeichnis, in dem das gerenderte Dokument gespeichert wird, und geben den Dateipfad für die Ausgabe-HTML-Datei an.
## Schritt 2: Viewer-Objekt instanziieren
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
 Hier erstellen wir eine neue Instanz von`Viewer` Klasse, wobei der Pfad des anzuzeigenden Dokuments (in diesem Fall eine EML-Beispieldatei) als Parameter übergeben wird.
## Schritt 3: Definieren Sie die HTML-Ansichtsoptionen
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
In diesem Schritt konfigurieren wir die HTML-Ansichtsoptionen für die Dokumentwiedergabe und geben den Ausgabedateipfad für das gerenderte HTML-Dokument an.
## Schritt 4: Legen Sie das Datum/Uhrzeit-Format und den Zeitzonenversatz fest
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Hier passen wir das Datums- und Uhrzeitformat für E-Mail-Nachrichten an und stellen den Zeitzonenversatz entsprechend der gewünschten Zeitzone ein.
## Schritt 5: Dokument rendern
```csharp
viewer.View(options);
```
 Abschließend nennen wir die`View` Methode der`Viewer` -Objekt und übergibt die konfigurierten HTML-Ansichtsoptionen, um das Dokument im HTML-Format darzustellen.
## Schritt 6: Ausgabeverzeichnis anzeigen
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Dieser Schritt zeigt lediglich eine Meldung an, die das erfolgreiche Rendern des Dokuments angibt, und stellt den Pfad zum Ausgabeverzeichnis bereit, in dem sich das gerenderte HTML-Dokument befindet.

## Abschluss
GroupDocs.Viewer für .NET bietet eine robuste Lösung für die Integration von Dokumentanzeigefunktionen in Ihre .NET-Anwendungen. Wenn Sie die in diesem Tutorial beschriebenen Schritte befolgen, können Sie GroupDocs.Viewer ganz einfach einrichten, die erforderlichen Namespaces importieren und seine Funktionen zum Rendern von Dokumenten mit anpassbaren Optionen nutzen. Ganz gleich, ob Sie mit PDFs, Microsoft Office-Dokumenten oder anderen Formaten arbeiten, GroupDocs.Viewer vereinfacht die Dokumentenanzeige und verbessert das Benutzererlebnis Ihrer Anwendungen.
## FAQs
### Ist GroupDocs.Viewer mit .NET Core kompatibel?
Ja, GroupDocs.Viewer für .NET unterstützt .NET Core und ermöglicht so plattformübergreifende Kompatibilität für Ihre Anwendungen.
### Kann ich das Erscheinungsbild der gerenderten Dokumente anpassen?
Absolut! GroupDocs.Viewer bietet verschiedene Anpassungsoptionen, darunter Zoomstufen, Seitendrehung und mehr, um das Anzeigeerlebnis an Ihre Vorlieben anzupassen.
### Gibt es zu Testzwecken eine Testversion?
 Ja, Sie können eine kostenlose Testversion von GroupDocs.Viewer für .NET herunterladen[Website-Link](https://releases.groupdocs.com/viewer/net/) um die Funktionen vor dem Kauf zu bewerten.
### Unterstützt GroupDocs.Viewer das Rendern passwortgeschützter Dokumente?
Ja, GroupDocs.Viewer verfügt über integrierte Unterstützung für die Darstellung passwortgeschützter Dokumente und gewährleistet so eine sichere Dokumentenanzeige in Ihren Anwendungen.
### Wo finde ich zusätzliche Unterstützung oder Hilfe zu GroupDocs.Viewer?
 Bei technischen Fragen oder Hilfe können Sie den GroupDocs.Viewer besuchen[Forum](https://forum.groupdocs.com/c/viewer/9) Oder wenden Sie sich an ihr Support-Team, um umgehend Hilfe und Anleitung zu erhalten.