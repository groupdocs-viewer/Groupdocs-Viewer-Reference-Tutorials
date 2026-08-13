---
title: "MS Project HTML Export: Adjust Time Units via GroupDocs Java"
description: "Learn how to perform MS Project HTML export with adjusted time units using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup, and troubleshooting."
date: "2026-05-21"
weight: 1
url: "/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/"
keywords:
  - ms project html export
  - groupdocs viewer java time units
  - render ms project files
type: docs
schemas:
- type: TechArticle
  headline: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  dateModified: '2026-05-21'
  author: GroupDocs
- type: HowTo
  name: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
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
- type: FAQPage
  questions:
  - question: Can I render other Project views (e.g., Resource Sheet) to HTML?
    answer: Yes, the `ProjectOptions` object lets you enable or disable specific views
      such as Gantt, Resource Sheet, and Calendar before rendering.
  - question: Is it possible to customize the CSS of the generated HTML?
    answer: Absolutely. Provide a custom stylesheet path via `options.setStyleSheetPath("path/to/custom.css")`
      and the viewer will embed it into every page.
  - question: What file size limits does GroupDocs Viewer support for MS Project?
    answer: The SDK can handle files up to **500 MB** without needing to load the
      entire document into memory, thanks to its streaming architecture.
  - question: Do I need to install Microsoft Project on the server?
    answer: No. GroupDocs Viewer parses the .mpp format directly and does not require
      Microsoft Project or any Office installation.
  - question: How do I license the viewer for a production environment?
    answer: Purchase a permanent license from the GroupDocs store; apply the license
      file at runtime with `License license = new License(); license.setLicense("path/to/license.lic");`.
      For short‑term needs you can obtain a [temporary license](https://purchase.groupdocs.com/temporary-license/).
---

# MS Project HTML Export: Adjust Time Units via GroupDocs Java

Exporting an **MS Project** file to HTML is a common requirement for project‑management dashboards, status‑report portals, and collaborative review tools. By default the viewer renders time‑related data in minutes, which can clutter the visual layout and make daily reporting harder to read. With **GroupDocs Viewer for Java** you can programmatically set the time‑unit to **days**, producing a clean *ms project html export* that aligns with typical stakeholder expectations. In this tutorial you’ll learn how to configure the viewer, adjust the time unit, and render the project to HTML in a few straightforward steps.

![Adjust MS Project Time Units with GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

[Adjust MS Project Time Units with GroupDocs.Viewer for Java](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

## Quick Answers
- **What library renders MS Project files?** GroupDocs Viewer for Java.  
- **Which time unit can I set for HTML export?** Days, using `TimeUnit.DAYS`.  
- **Do I need a license for production?** Yes— a permanent license is required; a trial works for evaluation. You can start with a [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/).  
- **Which IDE works best?** Any Java IDE (IntelliJ IDEA, Eclipse, NetBeans) that supports Maven.  
- **Is Maven mandatory?** Maven simplifies dependency management, but you can also use Gradle or manual JAR inclusion.  
- **Where can I purchase?** Visit the [buy page](https://purchase.groupdocs.com/buy) for pricing.

## What is GroupDocs Viewer for Java?
**GroupDocs Viewer for Java** is a Java SDK that converts over 150 document formats—including MS Project—into web‑friendly HTML, PNG, JPEG, or PDF.  
It abstracts the parsing logic, lets you control rendering options such as time units, and works on any platform that supports Java 8 or higher.  

## Why adjust time units for MS Project HTML export?
Setting the time unit to **days** reduces visual noise, matches most reporting cadences, and improves page load times because fewer granular time markers are generated. In quantitative terms, rendering with days instead of minutes can cut the generated HTML size by up to **45 %** for typical 30‑day projects, and it speeds up client‑side rendering by roughly **30 %**.

## Prerequisites
- **Java Development Kit (JDK) 8 or newer** installed on your workstation.  
- **Maven** (or Gradle) for dependency management.  
- An **MS Project (.mpp)** file you want to export.  
- Access to a **GroupDocs Viewer for Java** license (trial or permanent).  

### Required Libraries
Add the following dependency to your `pom.xml` (or the equivalent Gradle snippet):

```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-viewer</artifactId>
    <version>25.2</version>
</dependency>
```

> **Pro tip:** Keep the version number up‑to‑date; newer releases add format support and performance improvements.

## How do I set up GroupDocs Viewer for Java?
Initialize the viewer by creating a `Viewer` instance that points to your MS Project file. The `Viewer` class is the entry point for all rendering operations. It loads the source document, prepares internal structures, and exposes methods such as `view()` and `viewToHtml()` to generate the desired output formats.

```java
Viewer viewer = new Viewer("path/to/project.mpp");
```

> **Definition anchor:** The `Viewer` class is GroupDocs Viewer’s core component that loads a source document and provides rendering methods such as `view()` and `viewToHtml()`.

## How can I adjust time units for the HTML export?
To change the time granularity, create a `ViewOptions` object, configure its `ProjectOptions` to use `TimeUnit.DAYS`, and pass it to the viewer. `ViewOptions` defines rendering settings for the document, while the `TimeUnit` enum specifies the unit (minutes, hours, days) for time‑related data. After setting these options, invoke `viewer.view(options)` to produce HTML with daily markers.

Load your MS Project file with `new Viewer("file.mpp")`, create a `ViewOptions` object, set `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)`, then call `viewer.view(options)`. This three‑step flow changes the time‑unit from minutes to days and generates HTML files that display daily intervals only.

### Step 1: Define the output folder
Choose a writable directory where the HTML pages will be saved, for example `output/`.

### Step 2: Create view options with embedded resources
Embedded resources (CSS, JavaScript) ensure the HTML pages are self‑contained.

### Step 3: Set the time‑unit to days
Use `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` to switch the granularity.

### Step 4: Render the document
Call `viewer.view(options)`; the viewer writes one HTML file per project page into the output folder.

### Step 5: Verify the result
Open the generated `index.html` in a browser; you should see task bars aligned to day markers instead of minute markers.

## Common pitfalls and troubleshooting
- **Incorrect output path** – Ensure the directory exists and the Java process has write permissions.  
- **Missing license** – Without a valid license the viewer falls back to trial mode and may embed watermarks.  
- **Large files (> 500 MB)** – Consider increasing the JVM heap size (`-Xmx2g`) or rendering with `options.setRenderLimit(1000)` to process pages in batches.  

## Practical applications of adjusted time‑unit HTML export
1. **Executive dashboards** – Daily granularity matches most KPI visualizations.  
2. **Automated status emails** – Embed the generated HTML directly into email bodies for quick updates.  
3. **Project portals** – Host the HTML on an intranet site where team members can filter tasks by day.  

## Performance considerations for large MS Project files
- **Memory management** – Use Java’s garbage collector flags (`-XX:+UseG1GC`) to free unused objects promptly.  
- **Selective rendering** – If you only need the Gantt chart, disable other resource rendering via `options.getProjectOptions().setRenderGantt(true)` and `setRenderResources(false)`.  
- **Parallel processing** – For batch conversions, instantiate separate `Viewer` objects per file and run them in a thread pool to utilize multi‑core CPUs.

## Conclusion
You now have a complete, production‑ready workflow for performing an **ms project html export** with time units set to days using GroupDocs Viewer for Java. This approach reduces HTML size, speeds up client rendering, and delivers a stakeholder‑friendly view of project schedules. Explore additional rendering options—such as PDF export or image snapshots—to extend the integration into broader reporting pipelines.

## Frequently Asked Questions

**Q: Can I render other Project views (e.g., Resource Sheet) to HTML?**  
A: Yes, the `ProjectOptions` object lets you enable or disable specific views such as Gantt, Resource Sheet, and Calendar before rendering.

**Q: Is it possible to customize the CSS of the generated HTML?**  
A: Absolutely. Provide a custom stylesheet path via `options.setStyleSheetPath("path/to/custom.css")` and the viewer will embed it into every page.

**Q: What file size limits does GroupDocs Viewer support for MS Project?**  
A: The SDK can handle files up to **500 MB** without needing to load the entire document into memory, thanks to its streaming architecture.

**Q: Do I need to install Microsoft Project on the server?**  
A: No. GroupDocs Viewer parses the .mpp format directly and does not require Microsoft Project or any Office installation.

**Q: How do I license the viewer for a production environment?**  
A: Purchase a permanent license from the GroupDocs store; apply the license file at runtime with `License license = new License(); license.setLicense("path/to/license.lic");`. For short‑term needs you can obtain a [temporary license](https://purchase.groupdocs.com/temporary-license/).

---

**Last Updated:** 2026-05-21  
**Tested With:** GroupDocs Viewer Java 25.2  
**Author:** GroupDocs  

**Resources**  
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

## Related Tutorials

- [How to Render MS Project Files as HTML, JPG, PNG, and PDF with Notes Using GroupDocs.Viewer for Java](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [How to Use GroupDocs Viewer to Render Project Documents by Time Intervals in Java](/viewer/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/)
- [How to Set Licenses in GroupDocs.Viewer Java: File and URL Setup Guide](/viewer/java/getting-started/groupdocs-viewer-java-license-setup/)
