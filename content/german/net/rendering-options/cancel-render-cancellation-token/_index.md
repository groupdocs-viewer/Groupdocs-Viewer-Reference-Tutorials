---
"description": "Integrieren Sie Groupdocs.Viewer für .NET nahtlos in Ihre .NET-Projekte für eine effiziente Dokumentanzeige."
"linktitle": "Rendern mit Abbruchtoken abbrechen"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Rendern mit Abbruchtoken abbrechen"
"url": "/de/net/rendering-options/cancel-render-cancellation-token/"
"weight": 11
type: docs
---
# Rendern mit Abbruchtoken abbrechen

## Einführung
Groupdocs.Viewer für .NET ist ein leistungsstarkes Tool zur Vereinfachung der Dokumentanzeige und -verarbeitung in .NET-Anwendungen. Ob PDFs, Microsoft Office-Dokumente oder andere gängige Formate – diese Bibliothek bietet robuste Funktionen zur nahtlosen Integration von Dokumentanzeigefunktionen in Ihre .NET-Projekte.
## Voraussetzungen
Bevor Sie mit der Integration von Groupdocs.Viewer für .NET beginnen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1. Installation: Laden Sie die Bibliothek Groupdocs.Viewer für .NET von der bereitgestellten [Download-Link](https://releases.groupdocs.com/viewer/net/).
   
2. Lizenz: Erhalten Sie eine Lizenz von [Gruppendokumente](https://purchase.groupdocs.com/buy) um das volle Potenzial der Bibliothek auszuschöpfen. Alternativ können Sie mit einer kostenlosen Testversion beginnen, indem Sie [vorläufige Lizenz](https://purchase.groupdocs.com/temporary-license/).
   
3. Entwicklungsumgebung: Stellen Sie sicher, dass Sie eine kompatible Entwicklungsumgebung eingerichtet haben, einschließlich Visual Studio oder einer anderen .NET-IDE Ihrer Wahl.

## Namespaces importieren
Um Groupdocs.Viewer für .NET effektiv nutzen zu können, müssen Sie die erforderlichen Namespaces in Ihr Projekt importieren. Gehen Sie dazu folgendermaßen vor:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Lassen Sie uns nun das bereitgestellte Beispiel zum besseren Verständnis und zur besseren Implementierung in mehrere Schritte unterteilen:
## Schritt 1: Ausgabeverzeichnis definieren
```csharp
string outputDirectory = "Your Document Directory";
```
In diesem Schritt wird das Verzeichnis festgelegt, in dem die gerenderten Dokumentseiten gespeichert werden.
## Schritt 2: Definieren Sie das Auslagerungsdateipfadformat
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Hier definieren wir das Format für die Dateipfade einzelner Dokumentseiten.
## Schritt 3: Initialisieren von CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource wird zum Generieren von CancellationToken-Instanzen verwendet, die zum Abbrechen asynchroner Vorgänge verwendet werden können.
## Schritt 4: Abrufen des CancellationTokens
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
In diesem Schritt wird das Token aus der CancellationTokenSource abgerufen, das zum Abbrechen des Renderingvorgangs verwendet wird.
## Schritt 5: Dokumentseiten rendern
```csharp
Task.Run(() =>
{
    using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX, new ViewerSettings(new GroupDocs.Viewer.Logging.ConsoleLogger())))
    {
        HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
        options.RenderComments = true;
        viewer.View(options, cancellationToken);
    }
}, cancellationToken);
```
Hier starten wir das Rendering von Dokumentseiten asynchron mit Task.Run(). Die Viewer-Instanz wird mit der angegebenen Dokumentdatei (SAMPLE_DOCX) erstellt und die Rendering-Optionen konfiguriert. Der Rendering-Prozess wird anschließend mit der View-Methode der Viewer-Klasse gestartet.
## Schritt 6: Render-Timeout festlegen
```csharp
cancellationTokenSource.CancelAfter(10);
```
Dieser Schritt legt für den Rendervorgang ein Timeout von 10 Millisekunden fest. Wenn der Vorgang dieses Timeout überschreitet, wird er automatisch abgebrochen.
## Schritt 7: Erfolgsmeldung anzeigen
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Abschließend wird eine Erfolgsmeldung angezeigt, die angibt, dass das Dokument erfolgreich gerendert wurde.

## Abschluss
In diesem Tutorial haben wir die Grundlagen der Integration von Groupdocs.Viewer für .NET in Ihre Projekte behandelt. Mit den oben beschriebenen Schritten können Sie die Dokumentanzeigefunktionen nahtlos in Ihre .NET-Anwendungen integrieren und so Benutzerfreundlichkeit und Produktivität steigern.
## Häufig gestellte Fragen
### Ist Groupdocs.Viewer für .NET mit allen Dokumentformaten kompatibel?
Groupdocs.Viewer für .NET unterstützt eine Vielzahl von Dokumentformaten, darunter PDF, Microsoft Office-Dokumente, Bilder und mehr.
### Kann ich das Erscheinungsbild der gerenderten Dokumentseiten anpassen?
Ja, Sie können verschiedene Aspekte des Rendering-Prozesses anpassen, einschließlich Seitengröße, Qualität, Wasserzeichen und mehr.
### Benötigt Groupdocs.Viewer für .NET eine Internetverbindung?
Nein, Groupdocs.Viewer für .NET wird lokal in Ihrer .NET-Umgebung ausgeführt und erfordert keine Internetverbindung zum Anzeigen von Dokumenten.
### Ist technischer Support für Groupdocs.Viewer für .NET verfügbar?
Ja, technischer Support ist verfügbar über die [Groupdocs-Forum](https://forum.groupdocs.com/c/viewer/9), wo Sie Fragen stellen, Probleme melden und mit der Community interagieren können.
### Kann ich Groupdocs.Viewer für .NET vor dem Kauf testen?
Ja, Sie können mit einer kostenlosen Testversion beginnen, indem Sie die bereitgestellte [Testversion](https://releases.groupdocs.com/).