---
date: '2026-02-05'
description: Erfahren Sie, wie Sie ViewInfo erhalten und Java‑Archivdateistrukturen
  mit GroupDocs.Viewer abrufen. Dieser Leitfaden behandelt die Einrichtung, Codebeispiele
  und Anwendungsfälle aus der Praxis.
keywords:
- GroupDocs.Viewer for Java
- retrieve archive structures
- Java document viewer
title: Wie man ViewInfo erhält und Archivstrukturen in Java abruft
type: docs
url: /de/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# Wie man ViewInfo abruft und Archivstrukturen in Java ermittelt

Die effektive Verwaltung von Archivdateien erfordert ein klares Verständnis ihrer Struktur. In diesem Tutorial lernen Sie **wie man viewinfo abruft** für jedes Archiv und sehen, wie es Ihnen bei der Arbeit mit dem **java archive file type** hilft. Wir führen Sie durch die Einrichtung von GroupDocs.Viewer, das Extrahieren von View‑Informationen und das rekursive Lesen von Ordnerhierarchien, damit Sie die Lösung in reale Projekte integrieren können.

![Archivstrukturen mit GroupDocs.Viewer für Java](/viewer/document-loading/archive-structures-java.png)

**Was Sie lernen werden**
- Einrichtung und Konfiguration von GroupDocs.Viewer für Java.  
- Methoden, um **viewinfo** aus Archiven zu erhalten.  
- Techniken zum Lesen und Anzeigen der Ordnerstruktur einer Archivdatei.  
- Praktische Anwendungsfälle und Performance‑Überlegungen bei der Verwendung von GroupDocs.Viewer in Java‑Projekten.

## Schnellantworten
- **Was liefert “viewinfo”?** Es gibt den Dateityp, die Seitenanzahl und die Auflistung der Archivordner zurück.  
- **Welche Archive werden unterstützt?** ZIP, RAR, TAR und andere gängige Formate.  
- **Benötige ich eine Lizenz?** Eine kostenlose Testversion reicht für die Evaluierung; für die Produktion ist eine kommerzielle Lizenz erforderlich.  
- **Kann ich große Archive verarbeiten?** Ja – verwenden Sie Streaming und eine geeignete Speicherverwaltung, wie später gezeigt.  
- **Ist Maven erforderlich?** Maven ist der empfohlene Weg, um die GroupDocs.Viewer‑Abhängigkeit zu verwalten.

## Was ist “how to get viewinfo”?
`getViewInfo` ist eine Methode in der GroupDocs.Viewer‑API, die Metadaten über ein Dokument oder Archiv extrahiert, ohne den gesamten Inhalt zu rendern. Für Archive enthüllt sie den internen Ordnerbaum, sodass Sie entscheiden können, welche Teile Sie rendern oder weiterverarbeiten möchten.

## Warum Java‑Archivdateityp‑Strukturen abrufen?
Das Verständnis des internen Layouts eines **java archive file type** (z. B. ZIP, RAR) ermöglicht Ihnen:
- Schnelles Auffinden benötigter Dateien, ohne alles zu entpacken.  
- Aufbau automatisierter Pipelines, die nur relevante Unterordner verarbeiten.  
- Integration der Archivnavigation in Content‑Management‑ oder Daten‑Ingestion‑Systeme.

## Voraussetzungen

- **Java Development Kit (JDK):** Version 8 oder neuer.  
- **Maven:** Für Abhängigkeitsverwaltung und Builds.  
- **Grundkenntnisse in Java:** Vertrautheit mit OOP‑Konzepten ist hilfreich, aber nicht zwingend erforderlich.

Sie benötigen außerdem Zugriff auf die GroupDocs.Viewer‑Bibliothek, die Sie Ihrem Maven‑Projekt wie unten gezeigt hinzufügen können.

## GroupDocs.Viewer für Java einrichten

### Maven‑Konfiguration

Fügen Sie das Repository und die Abhängigkeit zu Ihrer `pom.xml` hinzu.

**Repositories:**
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**Dependencies:**
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### Lizenzbeschaffung

- **Kostenlose Testversion:** Laden Sie eine Testversion von der GroupDocs‑Website herunter.  
- **Temporäre Lizenz:** Fordern Sie einen temporären Schlüssel für eine kurzfristige Evaluierung an.  
- **Vollständige Lizenz:** Kaufen Sie eine kommerzielle Lizenz für uneingeschränkten Produktionseinsatz.

Sobald die Bibliothek im Klassenpfad ist, können Sie mit dem Coden beginnen.

## Implementierungs‑Leitfaden

### Wie man ViewInfo für Archivdateien abruft

Dieser Abschnitt zeigt die genauen Schritte, um `getViewInfo` aufzurufen und die Ordnerhierarchie zu lesen.

#### Viewer initialisieren

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### View‑Informationen abrufen

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### Ordnerstruktur anzeigen

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### Rekursives Ordnerlesen

```java
private static void readFolders(Viewer viewer, String folder) {
    ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
    viewInfoOptions.getArchiveOptions().setFolder(folder);
    
    ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(viewInfoOptions);
    
    for (String subFolder : viewInfo.getFolders()) {
        System.out.println(" - " + subFolder);
        readFolders(viewer, subFolder);
    }
}
```

### Feature 2: Archiv‑Ordnerstruktur abrufen

Dieses Feature konzentriert sich darauf, die Ordnerstruktur einer Archivdatei auszugeben. Es ist dem ersten Feature ähnlich, legt jedoch den Schwerpunkt auf die rekursive Erkundung.

#### View‑Info‑Optionen einrichten

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### Rekursive Erkundung

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## Praktische Anwendungsfälle

1. **Datenverwaltung:** Große Datensätze schnell organisieren, indem Sie Archivstrukturen verstehen.  
2. **Automatisierte Dateiverarbeitung:** Archivierte Dateien stapelweise verarbeiten, ohne sie vollständig zu entpacken.  
3. **CMS‑Integration:** Content‑Management‑Systeme mit On‑the‑Fly‑Archivnavigation erweitern.

## Performance‑Überlegungen

- **Speichernutzung optimieren:** Ordner jeweils eine Ebene nach der anderen verarbeiten und die `Viewer`‑Instanz zügig schließen.  
- **Auf dem neuesten Stand bleiben:** Verwenden Sie die aktuelle GroupDocs.Viewer‑Version und aktuelle JDK‑Releases für Leistungsverbesserungen.

## Häufige Probleme und Lösungen

| Problem | Warum es passiert | Lösung |
|-------|----------------|-----|
| `NullPointerException` beim Lesen von Ordnern | `viewInfo.getFolders()` liefert `null` für leere Verzeichnisse | Vor dem Durchlaufen auf `null` oder leere Liste prüfen. |
| Langsame Verarbeitung riesiger ZIP‑Dateien | Das gesamte Archiv wird in den Speicher geladen | Streaming‑Optionen der neueren GroupDocs‑Versionen nutzen. |
| Lizenz nicht gefunden | Pfad zur Lizenzdatei ist falsch | Lizenzdatei im Anwendungsverzeichnis ablegen oder `License.setLicense("path/to/license.json")` setzen. |

## Häufig gestellte Fragen

**F: Was ist GroupDocs.Viewer?**  
A: Eine leistungsstarke Java‑Bibliothek zum Rendern von Dokumenten, einschließlich Archiven, in Formate wie HTML, Bild und PDF.

**F: Kann ich GroupDocs.Viewer mit anderen Programmiersprachen verwenden?**  
A: Ja, GroupDocs bietet SDKs für mehrere Plattformen, aber dieses Tutorial konzentriert sich auf die Java‑Implementierung.

**F: Wie gehe ich mit großen Archivdateien um?**  
A: Effiziente Speicherverwaltung anwenden und bei Bedarf Archive in kleinere Teile aufteilen.

**F: Welche Archivformate unterstützt GroupDocs.Viewer?**  
A: Es unterstützt verschiedene Formate, darunter ZIP, RAR, TAR und weitere.

**F: Gibt es ein Limit für die Größe der verarbeitbaren Archive?**  
A: Die Grenzen hängen von den Ressourcen Ihres Systems ab. Testen Sie in Ihrer Zielumgebung, um praktische Grenzen zu bestimmen.

**F: Funktioniert “how to get viewinfo” bei passwortgeschützten Archiven?**  
A: Ja, Sie können das Passwort über `ArchiveOptions.setPassword("yourPassword")` setzen, bevor Sie `getViewInfo` aufrufen.

## Fazit

Durch Befolgen dieser Anleitung wissen Sie jetzt **wie man viewinfo abruft** für jedes unterstützte Archiv und wie Sie dessen Ordnerhierarchie mit GroupDocs.Viewer für Java durchlaufen. Diese Techniken ermöglichen Ihnen den Aufbau intelligenter Daten‑Verarbeitungspipelines, die Verbesserung von CMS‑Integrationen und den sicheren Umgang mit großen Sammlungen archivierter Dateien. Als Nächstes können Sie das Rendern einzelner Dateien aus dem Archiv oder die Konvertierung in PDF/HTML mithilfe weiterer Viewer‑Funktionen erkunden.

---

**Zuletzt aktualisiert:** 2026-02-05  
**Getestet mit:** GroupDocs.Viewer 25.2 für Java  
**Autor:** GroupDocs  

**Ressourcen**
- **Dokumentation:** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API‑Referenz:** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **GroupDocs.Viewer herunterladen:** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **Lizenz erwerben:** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **Kostenlose Testversion und temporäre Lizenz:** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)