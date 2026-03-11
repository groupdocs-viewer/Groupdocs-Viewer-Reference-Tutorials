---
date: '2026-01-15'
description: Erfahren Sie, wie Sie GroupDocs Viewer verwenden, um HTML aus Projektdokumenten
  innerhalb bestimmter Zeitintervalle zu generieren. Dieser Leitfaden behandelt Einrichtung,
  Code und Anwendungsbeispiele aus der Praxis.
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: Wie man GroupDocs Viewer verwendet, um Projektdokumente nach Zeitintervallen
  in Java zu rendern
type: docs
url: /de/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# Wie man GroupDocs Viewer verwendet, um Projektdokumente nach Zeitintervallen in Java zu rendern

Wenn Sie **wie man GroupDocs** verwendet, um Projektpläne in einem fokussierten Zeitfenster zu rendern, sind Sie hier genau richtig. In diesem Tutorial führen wir Sie durch den gesamten Prozess – von der Maven‑Einrichtung bis zur Generierung von HTML aus Projektdokumenten – damit Sie präzise Zeitstrahl‑Ansichten direkt in Ihre Anwendungen einbetten können.

![Render Project Documents by Time Intervals with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## Schnelle Antworten
- **Was macht die Funktion?** Sie rendert nur den Teil einer Microsoft‑Project‑Datei, der zwischen einem Start‑ und Enddatum liegt.  
- **Welches Ausgabeformat wird verwendet?** HTML mit eingebetteten Ressourcen, ideal für die Web‑Integration.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht für die Evaluierung; für die Produktion ist eine Voll‑Lizenz erforderlich.  
- **Kann ich den Datumsbereich zur Laufzeit ändern?** Ja – passen Sie die Werte `setStartDate` und `setEndDate` in den Rendering‑Optionen an.  
- **Wird das auf allen Java‑Versionen unterstützt?** Funktioniert mit Java 8+ solange Sie GroupDocs.Viewer 25.2 oder neuer verwenden.

## Was bedeutet „How to Use GroupDocs“ in diesem Kontext?
GroupDocs Viewer ist eine Java‑Bibliothek, die über 100 Dateiformate in web‑freundliche Darstellungen konvertiert. Wenn Sie **how to use GroupDocs** für Projektdaten verwenden, erhalten Sie die Möglichkeit, Zeitplandaten zu extrahieren, zu visualisieren und zu teilen, ohne dass Microsoft Project auf der Client‑Seite erforderlich ist.

## Warum Projektdokumente mit Zeitintervallen rendern?
- **Gezielte Analyse:** Zeigen Sie nur die Phase, die Sie interessiert (z. B. Q3 2024).  
- **Performance:** Kleinere HTML‑Ausgabe bedeutet schnellere Seitenladezeiten.  
- **Integration:** Betten Sie Zeitstrahl‑Ansichten in Dashboards, Reporting‑Portale oder benutzerdefinierte PM‑Tools ein.  

## Voraussetzungen

- **GroupDocs.Viewer for Java** Version 25.2 oder höher.  
- Java Development Kit (JDK) 8 oder neuer.  
- Eine IDE wie IntelliJ IDEA oder Eclipse.  
- Grundkenntnisse in Maven.  

## Einrichtung von GroupDocs.Viewer für Java

### Maven‑Abhängigkeit

Fügen Sie das Repository und die Abhängigkeit zu Ihrer `pom.xml` hinzu:

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

### Schritte zum Erwerb einer Lizenz

1. **Kostenlose Testversion** – Laden Sie eine Testversion von der [Download‑Seite von GroupDocs](https://releases.groupdocs.com/viewer/java/) herunter.  
2. **Temporäre Lizenz** – Erhalten Sie eine temporäre Lizenz für erweiterte Tests über [diesen Link](https://purchase.groupdocs.com/temporary-license/).  
3. **Kauf** – Für uneingeschränkte Produktion kaufen Sie eine Lizenz auf der [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

### Grundlegende Viewer‑Initialisierung

Das folgende Snippet zeigt, wie Sie eine `Viewer`‑Instanz erstellen, die auf eine Microsoft‑Project‑Datei (`.mpp`) verweist:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.mpp")) {
            // Your rendering code goes here
        }
    }
}
```

## Schritt‑für‑Schritt‑Implementierungs‑Leitfaden

### 1. Definieren Sie das Ausgabeverzeichnis

Erstellen Sie einen Ordner, in dem die generierten HTML‑Seiten gespeichert werden:

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*Warum?* Das strukturierte Ablegen gerenderter Dateien erleichtert das Bereitstellen von einem Web‑Server oder das Einbetten in eine Benutzeroberfläche.

### 2. Initialisieren Sie den Viewer mit Ihrer Projektdatei

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*Warum?* Das Laden des Dokuments bereitet den internen Parser vor und macht projektspezifische Metadaten zugänglich.

### 3. Abrufen von View‑Informationen für Projektdateien

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*Warum?* `ProjectManagementViewInfo` liefert Ihnen die Start‑ und Enddaten des Zeitplans, die Sie später verwenden, um den Rendering‑Umfang zu begrenzen.

### 4. Konfigurieren Sie die HTML‑Rendering‑Optionen (HTML aus Projekt generieren)

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*Warum?* Durch das Festlegen von `StartDate` und `EndDate` teilt man GroupDocs mit, **HTML aus dem Projekt**‑Daten nur innerhalb dieses Zeitfensters zu erzeugen.

### 5. Führen Sie den Rendering‑Prozess aus

```java
viewer.view(viewOptions);
```

*Warum?* Dieser Aufruf erzeugt eine Reihe von eigenständigen HTML‑Seiten, die den ausgewählten Zeitabschnitt Ihres Projektplans darstellen.

## Häufige Fallstricke & Fehlersuche

- **Falsche Dateipfade** – Stellen Sie sicher, dass sowohl die Quell‑`.mpp`‑Datei als auch das Ausgabeverzeichnis existieren.  
- **Nicht unterstützter Dateityp** – Vergewissern Sie sich, dass das Dokument ein unterstütztes Project‑Format ist (z. B. `.mpp`, `.mpt`).  
- **Lizenzfehler** – Eine Testlizenz kann Rendering‑Beschränkungen haben; wechseln Sie zu einer Voll‑Lizenz für uneingeschränkte Nutzung.  

## Praktische Anwendungsfälle

1. **Projekt‑Zeitstrahl‑Analyse** – Zeigen Sie Stakeholdern nur die aktuelle Phase.  
2. **Automatisiertes Reporting** – Generieren Sie zeitlich begrenzte HTML‑Berichte für wöchentliche Status‑Updates.  
3. **Integration in Dashboards** – Betten Sie die gerenderten Seiten in BI‑Tools oder benutzerdefinierte Portale ein.  
4. **Archivierung** – Speichern Sie einen web‑freundlichen Schnappschuss des Projektzeitplans für die Zukunft.  

## Performance‑Tipps

- Verwenden Sie die Option *embedded resources*, um jede HTML‑Seite eigenständig zu halten und HTTP‑Requests zu reduzieren.  
- Bei sehr großen Projekten sollten Sie das Rendering in kleineren Datums‑Chunks durchführen, um den Speicherverbrauch gering zu halten.  
- Löschen Sie temporäre Dateien nach der Bereitstellung, um Speicherplatz zu sparen.  

## Fazit

Sie wissen jetzt **wie man GroupDocs** Viewer verwendet, um Projektdokumente innerhalb eines bestimmten Zeitintervalls zu rendern und **HTML aus dem Projekt**‑Daten in Java zu erzeugen. Diese Fähigkeit vereinfacht Zeitstrahl‑Visualisierungen, verbessert die Reporting‑Effizienz und lässt sich nahtlos in moderne Web‑Anwendungen integrieren.

### Nächste Schritte
- Erkunden Sie weitere Viewer‑Funktionen wie Wasserzeichen, Passwortschutz oder benutzerdefiniertes CSS‑Styling.  
- Kombinieren Sie diese Rendering‑Pipeline mit einer REST‑API, um on‑demand Zeitstrahl‑Ansichten bereitzustellen.  

## Häufig gestellte Fragen

**F: Welche Dateiformate unterstützt GroupDocs.Viewer?**  
A: GroupDocs.Viewer unterstützt eine breite Palette von Formaten, darunter Microsoft Project (MPP), PDF, Word, Excel, PowerPoint und viele weitere.

**F: Wie starte ich mit einer kostenlosen Testversion von GroupDocs.Viewer?**  
A: Sie können die Testversion von [hier](https://releases.groupdocs.com/viewer/java/) herunterladen.

**F: Kann ich Dokumente rendern, ohne Ressourcen einzubetten?**  
A: Ja, Sie können eine andere HTML‑Ansichtsoption wählen, die externe Ressourcen referenziert statt sie einzubetten.

**F: Was, wenn mein Dokument zu groß zum Rendern ist?**  
A: Erwägen Sie, das Dokument in kleinere Abschnitte zu teilen oder nur den benötigten Datumsbereich zu rendern, wie oben gezeigt.

**F: Wie gehe ich mit Rendering‑Fehlern um?**  
A: Überprüfen Sie alle Konfigurationseinstellungen, stellen Sie sicher, dass Sie eine gültige Lizenz besitzen, und konsultieren Sie die GroupDocs‑Dokumentation für detaillierte Fehlermeldungen.

## Ressourcen
- **Dokumentation**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API‑Referenz**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Download**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)
- **Kauf**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Kostenlose Testversion**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)
- **Temporäre Lizenz**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Zuletzt aktualisiert:** 2026-01-15  
**Getestet mit:** GroupDocs.Viewer 25.2 for Java  
**Autor:** GroupDocs