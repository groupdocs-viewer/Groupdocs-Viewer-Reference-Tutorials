---
title: Rendervorgang mit Abbruchtoken abbrechen
linktitle: Rendervorgang mit Abbruchtoken abbrechen
second_title: GroupDocs.Viewer .NET-API
description: Integrieren Sie Groupdocs.Viewer für .NET nahtlos in Ihre .NET-Projekte für eine effiziente Dokumentenanzeige.
weight: 11
url: /de/net/rendering-options/cancel-render-cancellation-token/
---
## Einführung
Groupdocs.Viewer für .NET ist ein leistungsstarkes Tool, das die Anzeige und Verarbeitung von Dokumenten in .NET-Anwendungen vereinfacht. Unabhängig davon, ob Sie mit PDFs, Microsoft Office-Dokumenten oder anderen gängigen Formaten arbeiten, bietet diese Bibliothek robuste Funktionen zur nahtlosen Integration von Dokumentanzeigefunktionen in Ihre .NET-Projekte.
## Voraussetzungen
Bevor Sie sich mit der Integration von Groupdocs.Viewer für .NET befassen, stellen Sie sicher, dass die folgenden Voraussetzungen erfüllt sind:
1.  Installation: Laden Sie die Groupdocs.Viewer für .NET-Bibliothek von der bereitgestellten Website herunter und installieren Sie sie[Download-Link](https://releases.groupdocs.com/viewer/net/).
   
2.  Lizenz: Besorgen Sie sich eine Lizenz von[Gruppendokumente](https://purchase.groupdocs.com/buy) um das volle Potenzial der Bibliothek auszuschöpfen. Alternativ können Sie mit einer kostenlosen Testversion beginnen[temporäre Lizenz](https://purchase.groupdocs.com/temporary-license/).
   
3. Entwicklungsumgebung: Stellen Sie sicher, dass Sie eine kompatible Entwicklungsumgebung eingerichtet haben, einschließlich Visual Studio oder einer anderen .NET-IDE Ihrer Wahl.

## Namespaces importieren
Um Groupdocs.Viewer für .NET effektiv nutzen zu können, müssen Sie die erforderlichen Namespaces in Ihr Projekt importieren. Folge diesen Schritten:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Lassen Sie uns nun das bereitgestellte Beispiel zum besseren Verständnis und zur besseren Implementierung in mehrere Schritte aufteilen:
## Schritt 1: Ausgabeverzeichnis definieren
```csharp
string outputDirectory = "Your Document Directory";
```
Dieser Schritt legt das Verzeichnis fest, in dem die gerenderten Dokumentseiten gespeichert werden.
## Schritt 2: Definieren Sie das Format des Seitendateipfads
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Hier legen wir das Format für die Dateipfade einzelner Dokumentseiten fest.
## Schritt 3: CancellationTokenSource initialisieren
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource wird zum Generieren von CancellationToken-Instanzen verwendet, die zum Abbrechen asynchroner Vorgänge verwendet werden können.
## Schritt 4: Erhalten Sie den CancellationToken
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
Dieser Schritt ruft das Token aus der CancellationTokenSource ab, das zum Abbrechen des Rendervorgangs verwendet wird.
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
Hier initiieren wir das asynchrone Rendern von Dokumentseiten mithilfe von Task.Run(). Die Viewer-Instanz wird mit der angegebenen Dokumentdatei (SAMPLE_DOCX) erstellt und die Rendering-Optionen werden konfiguriert. Anschließend wird der Rendervorgang mit der View-Methode der Viewer-Klasse gestartet.
## Schritt 6: Render-Timeout festlegen
```csharp
cancellationTokenSource.CancelAfter(10);
```
Dieser Schritt legt ein Timeout von 10 Millisekunden für den Rendervorgang fest. Wenn der Vorgang dieses Timeout überschreitet, wird er automatisch abgebrochen.
## Schritt 7: Erfolgsmeldung anzeigen
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Abschließend wird eine Erfolgsmeldung angezeigt, die angibt, dass das Dokument erfolgreich gerendert wurde.

## Abschluss
In diesem Tutorial haben wir die Grundlagen der Integration von Groupdocs.Viewer für .NET in Ihre Projekte behandelt. Wenn Sie die oben beschriebenen Schritte befolgen, können Sie Funktionen zur Dokumentenanzeige nahtlos in Ihre .NET-Anwendungen integrieren und so die Benutzererfahrung und Produktivität verbessern.
## FAQs
### Ist Groupdocs.Viewer für .NET mit allen Dokumentformaten kompatibel?
Groupdocs.Viewer für .NET unterstützt eine Vielzahl von Dokumentformaten, darunter PDF, Microsoft Office-Dokumente, Bilder und mehr.
### Kann ich das Erscheinungsbild der gerenderten Dokumentseiten anpassen?
Ja, Sie können verschiedene Aspekte des Rendering-Prozesses anpassen, einschließlich Seitengröße, Qualität, Wasserzeichen und mehr.
### Benötigt Groupdocs.Viewer für .NET eine Internetverbindung?
Nein, Groupdocs.Viewer für .NET wird lokal in Ihrer .NET-Umgebung ausgeführt und erfordert keine Internetverbindung zum Anzeigen von Dokumenten.
### Ist technischer Support für Groupdocs.Viewer für .NET verfügbar?
 Ja, technischer Support ist über verfügbar[Groupdocs-Forum](https://forum.groupdocs.com/c/viewer/9), wo Sie Fragen stellen, Probleme melden und mit der Community interagieren können.
### Kann ich Groupdocs.Viewer für .NET vor dem Kauf testen?
 Ja, Sie können mit der bereitgestellten kostenlosen Testversion beginnen[Probeversion](https://releases.groupdocs.com/).