---
date: '2025-12-21'
description: Erfahren Sie, wie Sie die Gruppierung in PDFs mit GroupDocs.Viewer für
  Java deaktivieren, indem Sie Java‑HTML aus den PDF‑Renderoptionen verwenden, um
  eine präzise Textdarstellung zu gewährleisten.
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
title: Wie man die Gruppierung in PDFs mit GroupDocs.Viewer für Java deaktiviert
type: docs
url: /de/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# So deaktivieren Sie die Gruppierung in PDFs mit GroupDocs.Viewer für Java

Wenn Sie **wie man die Gruppierung deaktiviert** beim Rendern von PDFs benötigen, insbesondere für komplexe Schriften oder alte Sprachen, wird eine präzise Zeichenplatzierung unerlässlich. Die standardmäßige *Character Grouping*-Funktion kann Zeichen fälschlicherweise zusammenführen, was zu Fehlinterpretationen des Inhalts führt. In diesem Leitfaden zeigen wir Ihnen Schritt für Schritt, wie Sie die Gruppierung mit GroupDocs.Viewer für Java deaktivieren, sodass jedes Glyph exakt dort bleibt, wo es hingehört.

![Präzise Rendering-Techniken mit GroupDocs.Viewer für Java](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## Schnelle Antworten
- **Was bewirkt das „Deaktivieren der Gruppierung“?** Es zwingt den Renderer, jedes Zeichen als unabhängiges Element zu behandeln und bewahrt das genaue Layout.  
- **Welche API‑Option steuert das?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **Benötige ich eine Lizenz?** Eine Testversion funktioniert zum Testen, aber für den Produktionseinsatz ist eine Voll‑Lizenz erforderlich.  
- **Kann ich gleichzeitig Java‑HTML aus PDF erzeugen?** Ja — verwenden Sie `HtmlViewOptions`, um HTML‑Ausgabe zu erstellen, während die Gruppierung deaktiviert ist.  
- **Ist diese Funktion nur auf PDFs beschränkt?** Sie ist primär für PDFs gedacht, aber der Viewer unterstützt viele weitere Formate.

## Einführung

Beim Arbeiten mit PDF‑Dokumenten ist Präzision beim Rendern entscheidend — insbesondere bei komplexen Textstrukturen wie Hieroglyphen oder Sprachen, die eine genaue Zeichenrepräsentation erfordern. Die „Character Grouping“-Funktion verursacht häufig Probleme, indem sie Zeichen fälschlicherweise gruppiert, was zu Fehlinterpretationen des Dokumenteninhalts führt. Dies kann besonders problematisch für Nutzer sein, die eine exakte Replikation des Textlayouts ihrer Dokumente benötigen.

### Voraussetzungen

Bevor Sie mit der Code‑Implementierung beginnen, stellen Sie sicher, dass Sie die folgenden Anforderungen erfüllen:
- **Bibliotheken & Abhängigkeiten**: Sie benötigen GroupDocs.Viewer für Java Version 25.2 oder höher.  
- **Umgebungseinrichtung**: Stellen Sie sicher, dass ein Java Development Kit (JDK) installiert ist und Ihre IDE für Maven‑Projekte konfiguriert ist.  
- **Vorkenntnisse**: Grundlegendes Verständnis von Java‑Programmierung, insbesondere im Umgang mit Dateipfaden und externen Bibliotheken.

## So deaktivieren Sie die Gruppierung beim PDF-Rendering

### Einrichtung von GroupDocs.Viewer für Java

#### Installation über Maven

Zuerst integrieren Sie die benötigte Bibliothek in Ihr Projekt. Fügen Sie die folgende Konfiguration in Ihre `pom.xml` ein:

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

#### Lizenzbeschaffung

Um GroupDocs.Viewer vollständig nutzen zu können, sollten Sie eine Lizenz erwerben:
- **Kostenlose Testversion**: Beginnen Sie mit der kostenlosen Testversion, um Funktionen zu testen.  
- **Temporäre Lizenz**: Beantragen Sie eine temporäre Lizenz, wenn Sie mehr Zeit benötigen.  
- **Kauf**: Für langfristige Projekte ist der Kauf einer Lizenz empfehlenswert.

#### Grundlegende Initialisierung und Einrichtung

Beginnen Sie mit der Einrichtung Ihrer Projektumgebung:

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

// Initialize the GroupDocs Viewer
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getPdfOptions().setDisableCharsGrouping(true);

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

### Implementierungsleitfaden

#### Feature: Deaktivieren der Zeichen­gruppierung

##### Schritt 1: Ausgabeverzeichnis definieren

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**Warum?** Dies stellt sicher, dass Ihre Ausgaben organisiert und leicht zugänglich sind.

##### Schritt 2: Dateipfadformat konfigurieren

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Warum?** Es hilft, die Seiten des PDF‑Dokuments systematisch zu organisieren.

##### Schritt 3: HTML-View-Optionen initialisieren

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**Warum?** Eingebettete Ressourcen stellen sicher, dass alle notwendigen Assets in jeder HTML‑Datei der Seite enthalten sind.

##### Schritt 4: Zeichen­gruppierung deaktivieren

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**Warum?** Dadurch werden Zeichen einzeln gerendert, wodurch ihr beabsichtigtes Layout und ihre Bedeutung erhalten bleiben.

##### Schritt 5: Dokument rendern

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**Warum?** So wird sichergestellt, dass alle Ressourcen ordnungsgemäß geschlossen werden und Speicherlecks vermieden werden.

### Java-HTML aus PDF ohne Gruppierung erzeugen

Die Klasse `HtmlViewOptions` ermöglicht es Ihnen, **java html from pdf** zu erzeugen, während jedes Zeichen separat bleibt. Das ist besonders praktisch, wenn Sie die gerenderten Seiten in ein Web‑Portal oder eine E‑Learning‑Plattform einbetten müssen, wo die exakte Glyph‑Platzierung entscheidend ist.

### Tipps zur Fehlerbehebung

- Stellen Sie sicher, dass Ihr Dokumentpfad korrekt ist, um `FileNotFoundException` zu vermeiden.  
- Prüfen Sie, ob das Ausgabeverzeichnis Schreibrechte besitzt.  
- Vergewissern Sie sich, dass Sie eine kompatible Version von GroupDocs.Viewer für Java verwenden.

## Praktische Anwendungen

1. **Sprachbewahrung**: Ideal für das Rendern von Dokumenten in Sprachen wie Chinesisch, Japanisch oder alten Schriften, bei denen Zeichenpräzision wichtig ist.  
2. **Rechtliche und finanzielle Dokumente**: Gewährleistet Genauigkeit in Dokumenten, die eine präzise Textdarstellung für die Einhaltung von Vorschriften erfordern.  
3. **Bildungsressourcen**: Perfekt für Lehrbücher und wissenschaftliche Arbeiten, die komplexe Diagramme oder Anmerkungen enthalten.

## Leistungsüberlegungen

- **Ressourcennutzung optimieren**: Stellen Sie sicher, dass Ihr Server über ausreichende Ressourcen verfügt, um große PDF‑Dateien zu verarbeiten.  
- **Java‑Speichermanagement**: Verwenden Sie effiziente Datenstrukturen und Garbage‑Collection‑Praktiken, um den Speicher effektiv zu verwalten.  
- **Batch‑Verarbeitung**: Beim Rendern mehrerer Dokumente sollten Sie diese in Stapeln verarbeiten, um den Durchsatz zu erhöhen.

## Fazit

Sie haben nun gelernt, **wie man die Gruppierung** beim PDF‑Rendering mit GroupDocs.Viewer für Java deaktiviert. Diese Fähigkeit ist entscheidend für Anwendungen, die eine präzise Textdarstellung erfordern. Um weiter zu experimentieren, versuchen Sie, diese Funktion in andere Dokumenten‑Management‑Systeme zu integrieren oder mit zusätzlichen Rendering‑Optionen zu spielen.

Nächste Schritte umfassen das Erkunden weiterer fortgeschrittener Funktionen von GroupDocs.Viewer und das Fein‑Tuning der Leistung für groß angelegte Deployments.

## Häufig gestellte Fragen

**F:** *Warum sollte ich überhaupt die Zeichen­gruppierung deaktivieren?*  
**A:** Das Deaktivieren verhindert, dass der Renderer Zeichen zusammenführt, die zu unterschiedlichen Glyphen gehören, was für Schriften, bei denen Abstand und Reihenfolge Bedeutung tragen, unerlässlich ist.

**F:** *Ist die Einstellung `setDisableCharsGrouping` nur für HTML‑Ausgabe gültig?*  
**A:** Nein, sie wirkt sich auf die zugrunde liegende PDF‑Render‑Engine aus, sodass jedes Ausgabeformat (HTML, PNG usw.) die Änderung widerspiegelt.

**F:** *Kann ich diese Einstellung mit benutzerdefinierten Schriften kombinieren?*  
**A:** Ja — laden Sie einfach Ihre benutzerdefinierten Schriften, bevor Sie `Viewer` initialisieren, und die Gruppierungsregel bleibt aktiv.

**F:** *Beeinflusst das Deaktivieren der Gruppierung die Leistung?*  
**A:** Leicht, da der Engine jedes Zeichen einzeln verarbeitet, aber der Einfluss ist für die meisten Dokumente minimal.

**F:** *Gibt es eine Möglichkeit, die Gruppierung pro Seite zu steuern?*  
**A:** Derzeit ist die Option global pro `PdfOptions`‑Instanz; für unterschiedliche Seiten müssten Sie separate `Viewer`‑Instanzen erstellen.

## Ressourcen

- [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/)  
- [API Reference](https://reference.groupdocs.com/viewer/java/)  
- [Download GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)  
- [Purchase License](https://purchase.groupdocs.com/buy)  
- [Free Trial Version](https://releases.groupdocs.com/viewer/java/)  
- [Temporary License Application](https://purchase.groupdocs.com/temporary-license/)  
- [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Zuletzt aktualisiert:** 2025-12-21  
**Getestet mit:** GroupDocs.Viewer 25.2 für Java  
**Autor:** GroupDocs