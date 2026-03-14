---
date: '2026-02-23'
description: Erfahren Sie, wie Sie die Elemente pro Seite festlegen, HTML‑Ressourcen
  einbetten und Archive stapelweise in ein‑ oder mehrseitiges HTML mit GroupDocs.Viewer
  Java konvertieren.
keywords:
- convert archives to HTML Java
- GroupDocs.Viewer Java tutorial
- render ZIP RAR to HTML
title: 'Elemente pro Seite festlegen: Archive mit GroupDocs.Viewer Java in HTML konvertieren'
type: docs
url: /de/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# Elemente pro Seite festlegen: Archive mit GroupDocs.Viewer Java in HTML konvertieren

Das Konvertieren von Archivdateien wie ZIP oder RAR in web‑freundliches HTML ist ein häufiger Bedarf, wenn Sie Dokumente direkt im Browser teilen oder prüfen möchten. In diesem Leitfaden lernen Sie **wie man Elemente pro Seite festlegt** beim Rendern von Archiven, wie man Ressourcen‑HTML für eine eigenständige Ausgabe einbettet und wie man Archive effizient stapelweise konvertiert mit GroupDocs.Viewer Java.

![Archive mit GroupDocs.Viewer für Java in HTML konvertieren](/viewer/export-conversion/convert-archives-to-html-java.png)

## Schnellantworten
- **Was steuert “set items per page”?** Es bestimmt, wie viele Dateien oder Ordner aus einem Archiv auf jeder erzeugten HTML‑Seite angezeigt werden.  
- **Kann ich Bilder und CSS direkt in das HTML einbetten?** Ja – verwenden Sie die Option `forEmbeddedResources`, um Ressourcen‑HTML einzubetten.  
- **Ist eine Stapelkonvertierung möglich?** Absolut; Sie können über eine Sammlung von Archiven iterieren und jedes mit denselben Einstellungen rendern.  
- **Benötige ich Maven, um GroupDocs.Viewer zu verwenden?** Ja, fügen Sie die `maven groupdocs viewer`‑Abhängigkeit wie unten gezeigt hinzu.  
- **Welche Ausgabeformate werden unterstützt?** Single‑Page HTML Java und Multi‑Page HTML Java sind beide verfügbar.

## Was bedeutet “set items per page” in GroupDocs.Viewer?
Die **set items per page**‑Einstellung gehört zu den Archiv‑Renderoptionen. Sie gibt dem Viewer an, wie viele Archiveinträge (Dateien oder Ordner) auf jeder HTML‑Seite angezeigt werden sollen, wenn Sie ein mehrseitiges HTML‑Dokument erzeugen. Das Anpassen dieses Werts hilft, die Seitengröße und die Navigationsgeschwindigkeit auszubalancieren, insbesondere bei großen Archiven.

## Warum Ressourcen‑HTML einbetten?
Das Einbetten von Ressourcen (Bilder, CSS, Schriftarten) direkt in die HTML‑Datei erzeugt ein einziges, portables Dokument, das ohne externe Dateien geöffnet werden kann. Das ist ideal für E‑Mail‑Anhänge, Offline‑Betrachtung oder das Einbetten der Ausgabe in andere Webseiten.

## Voraussetzungen

- **Erforderliche Bibliotheken:** GroupDocs.Viewer Version 25.2 oder höher einbinden.  
- **Umgebung:** Java Development Kit (JDK) installiert und konfiguriert.  
- **Kenntnisse:** Grundlegendes Java und Maven‑Abhängigkeitsverwaltung.  

## Maven GroupDocs Viewer Einrichtung

Fügen Sie das GroupDocs‑Repository und die Viewer‑Abhängigkeit zu Ihrer `pom.xml` hinzu:

```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>

<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Lizenzbeschaffung
GroupDocs.Viewer bietet einen **Free‑Trial‑Link**, eine temporäre Lizenz oder eine Vollkauf‑Option. Wählen Sie das passende Angebot für Ihren Projektzeitplan.

### Grundlegende Initialisierung
Nach der Maven‑Einrichtung bringen Sie den Viewer in Ihren Code:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## Wie man Archive in Single‑Page HTML rendert

### Schritt 1: Ausgabeverzeichnis festlegen
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Schritt 2: Dateinamen für Single‑Page‑Ausgabe festlegen
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Schritt 3: Viewer initialisieren
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Schritt 4: Render‑Optionen konfigurieren (Ressourcen‑HTML einbetten)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Schritt 5: Als einzelne Seite rendern
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## Wie man Archive in Multi‑Page HTML rendert und Elemente pro Seite festlegt

### Schritt 1: Ausgabeverzeichnis wiederverwenden
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Schritt 2: Dateinamenformat für mehrere Seiten definieren
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Schritt 3: Viewer erneut initialisieren
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Schritt 4: Multi‑Page‑Optionen konfigurieren (Ressourcen‑HTML einbetten)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Schritt 5: Elemente pro Seite festlegen (primäres Schlüsselwort in Aktion)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Praktische Anwendungsfälle

- **Document Management Systems:** Archiv‑Vorschaufunktion hinzufügen, ohne zusätzliche Viewer zu installieren.  
- **Web‑Portale:** Nutzern eine schnelle, download‑freie Möglichkeit bieten, gebündelte Dokumente zu erkunden.  
- **Collaboration Tools:** Teams erlauben, geteilte Archive direkt im Browser zu prüfen.

## Leistungsüberlegungen

- **Ressourcenverwaltung:** Speicherverbrauch im Auge behalten; für große Stapel die JVM‑Garbage‑Collector‑Einstellungen anpassen.  
- **Batch‑Convert Archives:** Durchlaufen Sie eine Liste von Archivdateien und rufen Sie dieselbe Render‑Logik auf, um den Durchsatz zu maximieren.  
- **Caching‑Strategie:** Rendered HTML in einem Cache speichern, wenn dasselbe Archiv häufig aufgerufen wird.

## Häufig gestellte Fragen

**F: Was ist GroupDocs.Viewer Java?**  
A: Eine vielseitige Bibliothek zum Rendern von Dokumenten — einschließlich Archiven — in Formate wie HTML, PDF und Bilder.

**F: Wie kann ich eine kostenlose Testversion von GroupDocs.Viewer erhalten?**  
A: Besuchen Sie den [free trial link](https://releases.groupdocs.com/viewer/java/), um herunterzuladen und zu testen.

**F: Kann ich andere Dokumenttypen außer Archiven konvertieren?**  
A: Ja, der Viewer unterstützt PDFs, Word, Excel und viele weitere Formate.

**F: Was soll ich tun, wenn das Rendern langsam ist?**  
A: Reduzieren Sie die Anzahl der Elemente pro Seite, aktivieren Sie Streaming oder verarbeiten Sie Archive in kleineren Stapeln.

**F: Wo finde ich Hilfe oder Support?**  
A: Wenden Sie sich im [support forum](https://forum.groupdocs.com/c/viewer/9) an.

**F: Ist es möglich, CSS und Bilder direkt in das HTML einzubetten?**  
A: Absolut — verwenden Sie `HtmlViewOptions.forEmbeddedResources` wie in den Beispielen gezeigt.

**F: Wie konvertiere ich einen Ordner voller Archive stapelweise?**  
A: Iterieren Sie über jede Datei mit einer `for`‑Schleife und wenden Sie dieselbe `Viewer`‑ und `HtmlViewOptions`‑Konfiguration für jede Iteration an.

## Ressourcen

- **Documentation:** Vertiefen Sie sich in die Funktionalität mit der [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/).  
- **API Reference:** Erkunden Sie die vollständige API unter [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Download:** Laden Sie die neuesten Binärdateien von der [download page](https://releases.groupdocs.com/viewer/java/).  
- **Purchase and Licensing:** Prüfen Sie die Optionen auf der [purchase page](https://purchase.groupdocs.com/buy).  
- **Support and Community:** Nehmen Sie an Diskussionen im [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9) teil.

---

**Zuletzt aktualisiert:** 2026-02-23  
**Getestet mit:** GroupDocs.Viewer 25.2  
**Autor:** GroupDocs