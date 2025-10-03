---
"description": "Integrieren Sie GroupDocs.Viewer für .NET nahtlos in Ihre Anwendungen und profitieren Sie von leistungsstarken Funktionen zur Dokumentanzeige. Verbessern Sie das Benutzererlebnis mit anpassbaren Optionen."
"linktitle": "Datums./Uhrzeitformat und Zeitzonenverschiebung festlegen (E-Mail)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Datums./Uhrzeitformat und Zeitzonenverschiebung festlegen (E-Mail)"
"url": "/de/net/rendering-email-messages/set-date-time-format-offset-email/"
"weight": 11
type: docs
---
# Datums./Uhrzeitformat und Zeitzonenverschiebung festlegen (E-Mail)


## Einführung
GroupDocs.Viewer für .NET ist ein leistungsstarkes Tool, mit dem Entwickler die Dokumentanzeige nahtlos in ihre .NET-Anwendungen integrieren können. Mit GroupDocs.Viewer können Sie eine Vielzahl von Dokumentformaten, darunter PDFs, Microsoft Office-Dokumente, Bilder und mehr, direkt in Ihrer Anwendung anzeigen, ohne dass externe Plug-Ins oder Viewer erforderlich sind. In diesem umfassenden Tutorial führen wir Sie durch die Einrichtung von GroupDocs.Viewer für .NET, stellen Ihnen seine Funktionen vor und zeigen Ihnen, wie Sie ihn effektiv nutzen können, um die Dokumentanzeige Ihrer Anwendung zu verbessern.
## Voraussetzungen
Bevor Sie mit diesem Tutorial beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllt haben:
1. Visual Studio: Stellen Sie sicher, dass Visual Studio auf Ihrem System installiert ist. GroupDocs.Viewer für .NET ist vollständig mit Visual Studio kompatibel und ermöglicht eine nahtlose Integration in Ihre .NET-Projekte.
2. GroupDocs.Viewer für .NET: Laden Sie GroupDocs.Viewer für .NET herunter und installieren Sie es von der [Download-Link](https://releases.groupdocs.com/viewer/net/). Befolgen Sie die bereitgestellten Installationsanweisungen, um die Bibliothek in Ihrer Entwicklungsumgebung einzurichten.
3. .NET Framework: Stellen Sie sicher, dass Sie die entsprechende Version des .NET Frameworks installiert haben. GroupDocs.Viewer für .NET unterstützt verschiedene Versionen des .NET Frameworks, einschließlich .NET Core und .NET Standard.

## Namespaces importieren
Um GroupDocs.Viewer für .NET effektiv nutzen zu können, müssen Sie die erforderlichen Namespaces in Ihr Projekt importieren. Führen Sie die folgenden Schritte aus, um die erforderlichen Namespaces zu importieren:

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
In diesem Schritt definieren wir das Ausgabeverzeichnis, in dem das gerenderte Dokument gespeichert wird, und geben den Dateipfad für die HTML-Ausgabedatei an.
## Schritt 2: Viewer-Objekt instanziieren
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
Hier erstellen wir eine neue Instanz des `Viewer` Klasse und übergibt den Pfad des anzuzeigenden Dokuments (in diesem Fall eine Beispiel-EML-Datei) als Parameter.
## Schritt 3: HTML-Ansichtsoptionen definieren
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
In diesem Schritt konfigurieren wir die HTML-Ansichtsoptionen für die Dokumentwiedergabe und geben den Ausgabedateipfad für das gerenderte HTML-Dokument an.
## Schritt 4: Datums./Uhrzeitformat und Zeitzonen-Offset festlegen
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Hier passen wir das Datums- und Zeitformat für E-Mail-Nachrichten an und legen den Zeitzonen-Offset entsprechend der gewünschten Zeitzone fest.
## Schritt 5: Dokument rendern
```csharp
viewer.View(options);
```
Schließlich nennen wir die `View` Methode der `Viewer` Objekt, das die konfigurierten HTML-Ansichtsoptionen übergibt, um das Dokument im HTML-Format darzustellen.
## Schritt 6: Ausgabeverzeichnis anzeigen
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
In diesem Schritt wird lediglich eine Meldung angezeigt, die die erfolgreiche Darstellung des Dokuments bestätigt, und der Pfad zum Ausgabeverzeichnis bereitgestellt, in dem sich das gerenderte HTML-Dokument befindet.

## Abschluss
GroupDocs.Viewer für .NET bietet eine robuste Lösung zur Integration von Dokumentanzeigefunktionen in Ihre .NET-Anwendungen. Mit den in diesem Tutorial beschriebenen Schritten können Sie GroupDocs.Viewer ganz einfach einrichten, die erforderlichen Namespaces importieren und seine Funktionen nutzen, um Dokumente mit anpassbaren Optionen darzustellen. Ob Sie mit PDFs, Microsoft Office-Dokumenten oder anderen Formaten arbeiten – GroupDocs.Viewer vereinfacht die Dokumentanzeige und verbessert das Benutzererlebnis Ihrer Anwendungen.
## Häufig gestellte Fragen
### Ist GroupDocs.Viewer mit .NET Core kompatibel?
Ja, GroupDocs.Viewer für .NET unterstützt .NET Core und ermöglicht plattformübergreifende Kompatibilität für Ihre Anwendungen.
### Kann ich das Erscheinungsbild der gerenderten Dokumente anpassen?
Absolut! GroupDocs.Viewer bietet verschiedene Anpassungsoptionen, darunter Zoomstufen, Seitendrehung und mehr, um das Anzeigeerlebnis an Ihre Bedürfnisse anzupassen.
### Gibt es eine Testversion zum Testen?
Ja, Sie können eine kostenlose Testversion von GroupDocs.Viewer für .NET herunterladen von der [Website-Link](https://releases.groupdocs.com/viewer/net/) um die Funktionen vor dem Kauf zu bewerten.
### Unterstützt GroupDocs.Viewer das Rendern passwortgeschützter Dokumente?
Ja, GroupDocs.Viewer verfügt über integrierte Unterstützung für die Darstellung passwortgeschützter Dokumente und gewährleistet so die sichere Anzeige von Dokumenten in Ihren Anwendungen.
### Wo finde ich zusätzlichen Support oder Hilfe zu GroupDocs.Viewer?
Bei technischen Fragen oder Unterstützung können Sie den GroupDocs.Viewer besuchen [Forum](https://forum.groupdocs.com/c/viewer/9) oder wenden Sie sich an das Support-Team, um umgehend Hilfe und Anleitung zu erhalten.