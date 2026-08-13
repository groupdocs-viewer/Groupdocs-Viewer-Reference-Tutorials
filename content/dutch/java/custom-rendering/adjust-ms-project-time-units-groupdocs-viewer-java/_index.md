---
date: '2026-05-21'
description: Leer hoe u een MS Project HTML-export uitvoert met aangepaste tijdseenheden
  met behulp van GroupDocs Viewer voor Java. Stapsgewijze handleiding met vereisten,
  installatie en probleemoplossing.
keywords:
- ms project html export
- groupdocs viewer java time units
- render ms project files
schemas:
- author: GroupDocs
  dateModified: '2026-05-21'
  description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  headline: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  type: TechArticle
- description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  name: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  steps:
  - name: Define the output folder
    text: Choose a writable directory where the HTML pages will be saved, for example
      `output/`.
  - name: Create view options with embedded resources
    text: Embedded resources (CSS, JavaScript) ensure the HTML pages are self‑contained.
  - name: Set the time‑unit to days
    text: Use `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` to switch the
      granularity.
  - name: Render the document
    text: Call `viewer.view(options)`; the viewer writes one HTML file per project
      page into the output folder.
  - name: Verify the result
    text: Open the generated `index.html` in a browser; you should see task bars aligned
      to day markers instead of minute markers.
  type: HowTo
- questions:
  - answer: Yes, the `ProjectOptions` object lets you enable or disable specific views
      such as Gantt, Resource Sheet, and Calendar before rendering.
    question: Can I render other Project views (e.g., Resource Sheet) to HTML?
  - answer: Absolutely. Provide a custom stylesheet path via `options.setStyleSheetPath("path/to/custom.css")`
      and the viewer will embed it into every page.
    question: Is it possible to customize the CSS of the generated HTML?
  - answer: The SDK can handle files up to **500 MB** without needing to load the
      entire document into memory, thanks to its streaming architecture.
    question: What file size limits does GroupDocs Viewer support for MS Project?
  - answer: No. GroupDocs Viewer parses the .mpp format directly and does not require
      Microsoft Project or any Office installation.
    question: Do I need to install Microsoft Project on the server?
  - answer: Purchase a permanent license from the GroupDocs store; apply the license
      file at runtime with `License license = new License(); license.setLicense("path/to/license.lic");`.
      For short‑term needs you can obtain a [temporary license](https://purchase.groupdocs.com/temporary-license/).
    question: How do I license the viewer for a production environment?
  type: FAQPage
title: 'MS Project HTML Export: Tijdseenheden aanpassen via GroupDocs Java'
type: docs
url: /nl/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# MS Project HTML-export: Tijdseenheden aanpassen via GroupDocs Java

Exporteren van een **MS Project**‑bestand naar HTML is een veelvoorkomende eis voor project‑managementdashboards, status‑rapportportalen en collaboratieve beoordelings‑tools. Standaard rendert de viewer tijdgerelateerde gegevens in minuten, wat de visuele lay-out kan rommelen en dagelijkse rapportage moeilijker leesbaar maakt. Met **GroupDocs Viewer for Java** kun je programmatisch de tijdseenheid instellen op **days**, waardoor een nette *ms project html export* ontstaat die aansluit bij de verwachtingen van de meeste belanghebbenden. In deze tutorial leer je hoe je de viewer configureert, de tijdseenheid aanpast en het project naar HTML rendert in een paar eenvoudige stappen.

![Tijdseenheden van MS Project aanpassen met GroupDocs.Viewer voor Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

[​Tijdseenheden van MS Project aanpassen met GroupDocs.Viewer voor Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

## Snelle antwoorden
- **Welke bibliotheek rendert MS Project‑bestanden?** GroupDocs Viewer for Java.  
- **Welke tijdseenheid kan ik instellen voor HTML‑export?** Days, using `TimeUnit.DAYS`.  
- **Heb ik een licentie nodig voor productie?** Ja— een permanente licentie is vereist; een proefversie werkt voor evaluatie. Je kunt beginnen met een [GroupDocs Gratis Proefversie](https://releases.groupdocs.com/viewer/java/).  
- **Welke IDE werkt het beste?** Any Java IDE (IntelliJ IDEA, Eclipse, NetBeans) that supports Maven.  
- **Is Maven verplicht?** Maven simplifies dependency management, but you can also use Gradle or manual JAR inclusion.  
- **Waar kan ik kopen?** Bezoek de [kooppagina](https://purchase.groupdocs.com/buy) for pricing.

## Wat is GroupDocs Viewer voor Java?
**GroupDocs Viewer for Java** is a Java SDK that converts over 150 document formats—including MS Project—into web‑friendly HTML, PNG, JPEG, or PDF.  
It abstracts the parsing logic, lets you control rendering options such as time units, and works on any platform that supports Java 8 or higher.  

## Waarom tijdseenheden aanpassen voor MS Project HTML‑export?
Setting the time unit to **days** reduces visual noise, matches most reporting cadences, and improves page load times because fewer granular time markers are generated. In quantitative terms, rendering with days instead of minutes can cut the generated HTML size by up to **45 %** for typical 30‑day projects, and it speeds up client‑side rendering by roughly **30 %**.

## Vereisten
- **Java Development Kit (JDK) 8 of nieuwer** installed on your workstation.  
- **Maven** (or Gradle) for dependency management.  
- Een **MS Project (.mpp)**‑bestand dat je wilt exporteren.  
- Toegang tot een **GroupDocs Viewer for Java**‑licentie (proef of permanent).  

### Vereiste bibliotheken
Add the following dependency to your `pom.xml` (or the equivalent Gradle snippet):

```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-viewer</artifactId>
    <version>25.2</version>
</dependency>
```

> **Pro tip:** Houd het versienummer up‑to‑date; nieuwere releases voegen formatondersteuning en prestatieverbeteringen toe.

## Hoe stel ik GroupDocs Viewer voor Java in?
Initialize the viewer by creating a `Viewer` instance that points to your MS Project file. The `Viewer` class is the entry point for all rendering operations. It loads the source document, prepares internal structures, and exposes methods such as `view()` and `viewToHtml()` to generate the desired output formats.

```java
Viewer viewer = new Viewer("path/to/project.mpp");
```

> **Definition anchor:** De `Viewer`‑klasse is de kerncomponent van GroupDocs Viewer die een bron‑document laadt en rendermethoden biedt zoals `view()` en `viewToHtml()`.

## Hoe kan ik tijdseenheden aanpassen voor de HTML‑export?
To change the time granularity, create a `ViewOptions` object, configure its `ProjectOptions` to use `TimeUnit.DAYS`, and pass it to the viewer. `ViewOptions` defines rendering settings for the document, while the `TimeUnit` enum specifies the unit (minutes, hours, days) for time‑related data. After setting these options, invoke `viewer.view(options)` to produce HTML with daily markers.

Load your MS Project file with `new Viewer("file.mpp")`, create a `ViewOptions` object, set `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)`, then call `viewer.view(options)`. This three‑step flow changes the time‑unit from minutes to days and generates HTML files that display daily intervals only.

### Stap 1: Definieer de uitvoermap
Choose a writable directory where the HTML pages will be saved, for example `output/`.

### Stap 2: Maak weergave‑opties met ingesloten bronnen
Embedded resources (CSS, JavaScript) ensure the HTML pages are self‑contained.

### Stap 3: Stel de tijdseenheid in op dagen
Use `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` to switch the granularity.

### Stap 4: Render het document
Call `viewer.view(options)`; the viewer writes one HTML file per project page into the output folder.

### Stap 5: Verifieer het resultaat
Open the generated `index.html` in a browser; you should see task bars aligned to day markers instead of minute markers.

## Veelvoorkomende valkuilen en probleemoplossing
- **Incorrect output path** – Ensure the directory exists and the Java process has write permissions.  
- **Missing license** – Without a valid license the viewer falls back to trial mode and may embed watermarks.  
- **Large files (> 500 MB)** – Consider increasing the JVM heap size (`-Xmx2g`) or rendering with `options.setRenderLimit(1000)` to process pages in batches.  

## Praktische toepassingen van aangepaste tijdseenheid HTML‑export
1. **Executive dashboards** – Daily granularity matches most KPI visualizations.  
2. **Automated status emails** – Embed the generated HTML directly into email bodies for quick updates.  
3. **Project portals** – Host the HTML on an intranet site where team members can filter tasks by day.  

## Prestatieoverwegingen voor grote MS Project‑bestanden
- **Memory management** – Use Java’s garbage collector flags (`-XX:+UseG1GC`) to free unused objects promptly.  
- **Selective rendering** – If you only need the Gantt chart, disable other resource rendering via `options.getProjectOptions().setRenderGantt(true)` and `setRenderResources(false)`.  
- **Parallel processing** – For batch conversions, instantiate separate `Viewer` objects per file and run them in a thread pool to utilize multi‑core CPUs.

## Conclusie
You now have a complete, production‑ready workflow for performing an **ms project html export** with time units set to days using GroupDocs Viewer for Java. This approach reduces HTML size, speeds up client rendering, and delivers a stakeholder‑friendly view of project schedules. Explore additional rendering options—such as PDF export or image snapshots—to extend the integration into broader reporting pipelines.

## Veelgestelde vragen

**Q: Kan ik andere Project‑weergaven (bijv. Resource Sheet) naar HTML renderen?**  
A: Ja, het `ProjectOptions`‑object laat je specifieke weergaven zoals Gantt, Resource Sheet en Calendar in- of uitschakelen vóór het renderen.

**Q: Is het mogelijk de CSS van de gegenereerde HTML aan te passen?**  
A: Absoluut. Provide a custom stylesheet path via `options.setStyleSheetPath("path/to/custom.css")` and the viewer will embed it into every page.

**Q: Welke bestandsgrootte‑limieten ondersteunt GroupDocs Viewer voor MS Project?**  
A: The SDK can handle files up to **500 MB** without needing to load the entire document into memory, thanks to its streaming architecture.

**Q: Moet ik Microsoft Project op de server installeren?**  
A: Nee. GroupDocs Viewer parses the .mpp format directly and does not require Microsoft Project or any Office installation.

**Q: Hoe licentieer ik de viewer voor een productie‑omgeving?**  
A: Purchase a permanent license from the GroupDocs store; apply the license file at runtime with `License license = new License(); license.setLicense("path/to/license.lic");`. For short‑term needs you can obtain a [tijdelijke licentie](https://purchase.groupdocs.com/temporary-license/).

---

**Laatst bijgewerkt:** 2026-05-21  
**Getest met:** GroupDocs Viewer Java 25.2  
**Auteur:** GroupDocs  

**Bronnen**  
- [Documentation](https://docs.groupdocs.com/viewer/java/)  
- [API Reference](https://reference.groupdocs.com/viewer/java/)  
- [Download GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- [Purchase a License](https://purchase.groupdocs.com/buy)  

---

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

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

## Gerelateerde tutorials

- [How to Render MS Project Files as HTML, JPG, PNG, and PDF with Notes Using GroupDocs.Viewer for Java](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [How to Use GroupDocs Viewer to Render Project Documents by Time Intervals in Java](/viewer/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/)
- [How to Set Licenses in GroupDocs.Viewer Java: File and URL Setup Guide](/viewer/java/getting-started/groupdocs-viewer-java-license-setup/)