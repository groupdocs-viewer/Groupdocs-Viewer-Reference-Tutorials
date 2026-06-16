---
title: "Generate HTML from PDF & Disable Grouping – GroupDocs Java"
description: "Learn how to generate HTML from PDF and disable character grouping using GroupDocs Viewer for Java for precise text representation."
date: "2026-03-22"
weight: 1
url: "/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/"
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
type: docs
---

# Generate HTML from PDF and Disable Grouping with GroupDocs Viewer for Java

In many projects you need to **generate HTML from PDF** while keeping every glyph exactly where it belongs. This is especially true for complex scripts, ancient languages, or legal documents where a single misplaced character can change meaning. In this tutorial we’ll walk you through the complete process of rendering PDFs to HTML with GroupDocs Viewer for Java and show you **how to disable grouping** so each character is treated as an independent element.

![Precise Rendering Techniques with GroupDocs.Viewer for Java](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## Quick Answers
- **What does “disable grouping” do?** It forces the renderer to treat each character as an independent element, preserving exact layout.  
- **Which API option controls this?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **Do I need a license?** A trial works for testing, but a full license is required for production.  
- **Can I generate HTML from PDF at the same time?** Yes—use `HtmlViewOptions` to create HTML output while disabling grouping.  
- **Is this feature limited to PDFs?** It’s primarily for PDFs, but the viewer supports many other formats.

## Introduction

When working with PDF documents, precision in rendering is crucial—especially when dealing with complex text structures like hieroglyphics or languages that require precise character representation. The "Character Grouping" feature often causes issues by grouping characters incorrectly, leading to misinterpretation of the document content. This can be particularly problematic for users needing exact replication of their documents' text layout.

### Prerequisites

Before diving into code implementation, ensure that you meet the following requirements:
- **Libraries & Dependencies**: You'll need GroupDocs.Viewer for Java version 25.2 or later.  
- **Environment Setup**: Make sure you have a Java Development Kit (JDK) installed and your IDE set up to work with Maven projects.  
- **Knowledge Prerequisites**: Basic understanding of Java programming, especially handling file paths and using external libraries.

## How to generate HTML from PDF with GroupDocs Viewer

Generating HTML from PDF is a two‑step process: configure the viewer, then render the document. The key is to turn off character grouping before rendering so the HTML output mirrors the original PDF layout character‑by‑character.

### Setting Up GroupDocs.Viewer for Java

#### Installation via Maven

First, integrate the necessary library into your project. Add the following configuration in your `pom.xml`:

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

#### License Acquisition

To fully utilize GroupDocs.Viewer, consider acquiring a license:
- **Free Trial**: Start with the free trial to test features.  
- **Temporary License**: Apply for a temporary license if you need more time.  
- **Purchase**: For long‑term projects, purchasing a license is advisable.

#### Basic Initialization and Setup

Below is a ready‑to‑run snippet that shows the full workflow—from setting the output folder to rendering the PDF as HTML while disabling character grouping:

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

### Implementation Guide

#### Feature: Disable Characters Grouping

Below we break down each line of the example so you can understand **why** we do it and **how** it contributes to generating HTML from PDF without unwanted character merging.

##### Step 1: Define Output Directory  

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**Why?** This ensures your rendered HTML files are stored in a dedicated folder, making it easy to locate and manage them later.

##### Step 2: Configure File Path Format  

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Why?** Using a placeholder (`{0}`) lets the viewer create a separate HTML file for each PDF page, keeping the output organized.

##### Step 3: Initialize HTML View Options  

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**Why?** Embedded resources bundle images, fonts, and CSS directly with each HTML page, which is ideal for web‑based viewers or e‑learning platforms.

##### Step 4: Disable Character Grouping  

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**Why?** This is the crucial line that tells the rendering engine **not** to merge adjacent characters, guaranteeing that the generated HTML reflects the exact glyph placement from the source PDF.

##### Step 5: Render the Document  

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**Why?** Wrapping the `Viewer` in a try‑with‑resources block guarantees that all native resources are released automatically, preventing memory leaks in long‑running applications.

### Generating Java HTML from PDF without Grouping

The `HtmlViewOptions` class lets you produce **generate html from pdf** while keeping each character separate. This is especially handy when you need to embed the rendered pages into a web portal or an e‑learning platform where exact glyph placement matters.

### Common Issues and Solutions

- **FileNotFoundException** – Double‑check the path you pass to `new Viewer(...)`. Use absolute paths or `Path.of(...)` for clarity.  
- **Write Permissions** – Make sure the output directory is writable by the Java process; on Linux you may need to adjust folder permissions (`chmod 775`).  
- **Version Mismatch** – The `setDisableCharsGrouping` option is available starting with version 25.2. Verify your `pom.xml` reflects the correct version.  

### Practical Applications

1. **Language Preservation** – Ideal for rendering documents in Chinese, Japanese, Arabic, or ancient scripts where character spacing carries meaning.  
2. **Legal & Financial Documents** – Guarantees exact text replication for compliance‑heavy paperwork.  
3. **Educational Resources** – Perfect for textbooks that include complex diagrams, annotations, or multilingual content.

### Performance Considerations

- **Optimize Resource Usage** – Large PDFs can consume significant memory. Consider processing pages in batches and disposing of `Viewer` instances promptly.  
- **Java Memory Management** – Tune the JVM heap (`-Xmx2g` or higher) if you anticipate processing multi‑hundred‑page PDFs.  
- **Parallel Rendering** – For bulk conversions, spawn separate threads each with its own `Viewer` instance to leverage multi‑core CPUs.

## Frequently Asked Questions

**Q:** *Why would I need to disable character grouping at all?*  
**A:** Disabling grouping prevents the renderer from merging characters that belong to distinct glyphs, which is essential for scripts where spacing and ordering convey meaning.

**Q:** *Is the `setDisableCharsGrouping` setting applicable to HTML output only?*  
**A:** No, it affects the underlying PDF rendering engine, so any output format (HTML, PNG, JPEG, etc.) will reflect the change.

**Q:** *Can I combine this setting with custom fonts?*  
**A:** Yes—load your custom fonts before initializing `Viewer`, and the grouping rule will still apply.

**Q:** *Does disabling grouping impact performance?*  
**A:** Slightly, because the engine processes each character individually, but the impact is minimal for most documents.

**Q:** *Is there a way to toggle grouping on a per‑page basis?*  
**A:** Currently the option is global per `PdfOptions` instance; you would need separate `Viewer` instances for different pages if you require mixed behavior.

## Resources

- [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [Purchase License](https://purchase.groupdocs.com/buy)
- [Free Trial Version](https://releases.groupdocs.com/viewer/java/)
- [Temporary License Application](https://purchase.groupdocs.com/temporary-license/)
- [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-03-22  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs