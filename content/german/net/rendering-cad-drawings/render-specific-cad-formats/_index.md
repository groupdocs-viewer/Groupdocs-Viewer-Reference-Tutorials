---
"description": "Erfahren Sie, wie Sie mit Groupdocs.Viewer für .NET bestimmte CAD-Formate wie CF2 in HTML, JPG, PNG und PDF rendern."
"linktitle": "Renderspezifische CAD-Formate (CF2)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "Renderspezifische CAD-Formate (CF2)"
"url": "/de/net/rendering-cad-drawings/render-specific-cad-formats/"
"weight": 12
---

# Renderspezifische CAD-Formate (CF2)

## Einführung
In diesem Tutorial erfahren Sie, wie Sie bestimmte CAD-Formate mit Groupdocs.Viewer für .NET rendern. Groupdocs.Viewer ist eine leistungsstarke Dokumentanzeige-API, mit der Entwickler über 170 Dokumenttypen in ihren Anwendungen anzeigen können, ohne externe Software installieren zu müssen. Wir konzentrieren uns insbesondere auf die Konvertierung von CAD-Formaten wie CF2 in verschiedene Ausgabeformate wie HTML, JPG, PNG und PDF.
## Voraussetzungen
Bevor wir mit dem Lernprogramm beginnen, stellen Sie sicher, dass Sie die folgenden Voraussetzungen erfüllen:
- Visual Studio ist auf Ihrem System installiert.
- Groupdocs.Viewer für .NET SDK. Sie können es herunterladen von [Hier](https://releases.groupdocs.com/viewer/net/).
- Grundkenntnisse der Programmiersprache C#.
## Namespaces importieren
Importieren wir zunächst die erforderlichen Namespaces, die zum Rendern von CAD-Formaten erforderlich sind.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Lassen Sie uns nun jedes Beispiel in mehrere Schritte unterteilen:
## Rendern Sie CF2 in HTML
### Schritt 1: Definieren Sie das Ausgabeverzeichnis, in dem das gerenderte HTML gespeichert wird.
```csharp
string outputDirectory = "Your Document Directory";
```
### Schritt 2: Definieren Sie das Dateipfadformat für die HTML-Ausgabe.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### Schritt 3: Initialisieren Sie das Viewer-Objekt und geben Sie die CF2-Eingabedatei an.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // Legen Sie bei Bedarf zusätzliche Rendering-Optionen fest
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2 in JPG rendern
### Schritt 1: Definieren Sie das Dateipfadformat für die JPG-Ausgabe.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### Schritt 2: Initialisieren Sie das Viewer-Objekt und geben Sie die CF2-Eingabedatei an.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // Legen Sie bei Bedarf zusätzliche Rendering-Optionen fest
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Rendern Sie CF2 in PNG

### Schritt 1: Definieren Sie das Dateipfadformat für die PNG-Ausgabe.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### Schritt 2: Initialisieren Sie das Viewer-Objekt und geben Sie die CF2-Eingabedatei an.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // Legen Sie bei Bedarf zusätzliche Rendering-Optionen fest
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## CF2 in PDF rendern
### Schritt 1: Definieren Sie das Dateipfadformat für die PDF-Ausgabe.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### Schritt 2: Initialisieren Sie das Viewer-Objekt und geben Sie die CF2-Eingabedatei an.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // Legen Sie bei Bedarf zusätzliche Rendering-Optionen fest
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## Abschluss
In diesem Tutorial haben wir gelernt, wie Sie bestimmte CAD-Formate wie CF2 mit Groupdocs.Viewer für .NET rendern. Mit der Schritt-für-Schritt-Anleitung können Sie Dokumentrendering-Funktionen problemlos in Ihre .NET-Anwendungen integrieren.
## Häufig gestellte Fragen
### Kann Groupdocs.Viewer außer CF2 auch andere CAD-Formate rendern?
Ja, Groupdocs.Viewer unterstützt eine Vielzahl von CAD-Formaten, darunter DWG, DXF, DGN und mehr.
### Ist Groupdocs.Viewer zum Rendern von Dokumenten in Webanwendungen geeignet?
Absolut, Groupdocs.Viewer kann nahtlos in Webanwendungen integriert werden, um Dokumente direkt im Browser darzustellen.
### Benötigt Groupdocs.Viewer externe Abhängigkeiten zum Rendern?
Nein, Groupdocs.Viewer ist eine eigenständige API und erfordert keine externen Abhängigkeiten oder Softwareinstallationen.
### Kann ich die Rendering-Optionen meinen Anforderungen entsprechend anpassen?
Ja, Groupdocs.Viewer bietet verschiedene Rendering-Optionen, die an Ihre spezifischen Anforderungen angepasst werden können.
### Gibt es eine Testversion für Groupdocs.Viewer?
Ja, Sie können eine kostenlose Testversion von Groupdocs.Viewer erhalten von [Hier](https://releases.groupdocs.com/).