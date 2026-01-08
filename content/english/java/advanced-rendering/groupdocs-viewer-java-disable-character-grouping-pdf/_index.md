---
title: "How to Disable Grouping in PDFs with GroupDocs.Viewer for Java"
description: "Learn how to disable grouping in PDFs with GroupDocs.Viewer for Java, using java html from pdf rendering options to ensure precise text representation."
date: "2025-12-21"
weight: 1
url: "/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/"
keywords:
- disable character grouping PDFs
- GroupDocs Viewer Java configuration
- precise text representation in PDFs
type: docs
---

# How to Disable Grouping in PDFs with GroupDocs.Viewer for Java

When you need **how to disable grouping** while rendering PDFs, especially for complex scripts or ancient languages, precise character placement becomes essential. The default *Character Grouping* feature can merge characters incorrectly, causing misinterpretation of the content. In this guide we’ll show you step‑by‑step how to disable grouping using GroupDocs.Viewer for Java, so every glyph stays exactly where it belongs.

![Precise Rendering Techniques with GroupDocs.Viewer for Java](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## Quick Answers
- **What does “disable grouping” do?** It forces the renderer to treat each character as an independent element, preserving exact layout.  
- **Which API option controls this?** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.  
- **Do I need a license?** A trial works for testing, but a full license is required for production.  
- **Can I generate Java HTML from PDF at the same time?** Yes—use `HtmlViewOptions` to create HTML output while disabling grouping.  
- **Is this feature limited to PDFs?** It’s primarily for PDFs, but the viewer supports many other formats.

## Introduction

When working with PDF documents, precision in rendering is crucial—especially when dealing with complex text structures like hieroglyphics or languages that require precise character representation. The "Character Grouping" feature often causes issues by grouping characters incorrectly, leading to misinterpretation of the document content. This can be particularly problematic for users needing exact replication of their documents' text layout.

### Prerequisites

Before diving into code implementation, ensure that you meet the following requirements:
- **Libraries & Dependencies**: You'll need GroupDocs.Viewer for Java version 25.2 or later.
- **Environment Setup**: Make sure you have a Java Development Kit (JDK) installed and your IDE set up to work with Maven projects.
- **Knowledge Prerequisites**: Basic understanding of Java programming, especially handling file paths and using external libraries.

## How to Disable Grouping in PDF Rendering

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

Begin by setting up your project environment:

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

##### Step 1: Define Output Directory

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**Why?** This ensures your output is organized and easily accessible.

##### Step 2: Configure File Path Format

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**Why?** It helps in systematically organizing the pages of the PDF document.

##### Step 3: Initialize HTML View Options

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**Why?** Embedded resources ensure all necessary assets are included within each page's HTML file.

##### Step 4: Disable Character Grouping

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**Why?** This ensures characters are rendered individually, preserving their intended layout and meaning.

##### Step 5: Render the Document

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**Why?** This ensures that all resources are closed appropriately, preventing memory leaks.

### Generating Java HTML from PDF without Grouping

The `HtmlViewOptions` class lets you produce **java html from pdf** while keeping each character separate. This is especially handy when you need to embed the rendered pages into a web portal or an e‑learning platform where exact glyph placement matters.

### Troubleshooting Tips

- Ensure your document path is correct to avoid `FileNotFoundException`.  
- Verify that the output directory has write permissions.  
- Double‑check that you're using a compatible version of GroupDocs.Viewer for Java.

## Practical Applications

1. **Language Preservation**: Ideal for rendering documents in languages like Chinese, Japanese, or ancient scripts where character precision matters.  
2. **Legal and Financial Documents**: Guarantees accuracy in documents requiring precise text representation for compliance.  
3. **Educational Resources**: Perfect for textbooks and academic papers that include complex diagrams or annotations.

## Performance Considerations

- **Optimize Resource Usage**: Ensure your server has adequate resources to handle large PDF files.  
- **Java Memory Management**: Use efficient data structures and garbage‑collection practices to manage memory effectively.  
- **Batch Processing**: When rendering multiple documents, process them in batches to improve throughput.

## Conclusion

You've now mastered **how to disable grouping** during PDF rendering with GroupDocs.Viewer for Java. This capability is crucial for applications that demand precise text representation. To further explore, try integrating this feature with other document management systems or experiment with additional rendering options.

Next steps include exploring more advanced features of GroupDocs.Viewer and fine‑tuning performance for large‑scale deployments.

## FAQ Section

1. **What does disabling character grouping achieve?**  
   - It ensures characters are rendered individually, preserving their original layout.  
2. **Can I use this feature with other document types?**  
   - Yes, while the focus here is PDFs, GroupDocs.Viewer supports many formats.  
3. **How do I handle large documents efficiently?**  
   - Use batch processing and optimize your server resources.  
4. **What should I do if the output directory is not writable?**  
   - Check permissions or select a different directory with proper access rights.  
5. **Are there licensing limits for GroupDocs.Viewer?**  
   - A free trial is available, but long‑term use requires a purchased license.

## Frequently Asked Questions

**Q:** *Why would I need to disable character grouping at all?*  
**A:** Disabling grouping prevents the renderer from merging characters that belong to distinct glyphs, which is essential for scripts where spacing and ordering convey meaning.

**Q:** *Is the `setDisableCharsGrouping` setting applicable to HTML output only?*  
**A:** No, it affects the underlying PDF rendering engine, so any output format (HTML, PNG, etc.) will reflect the change.

**Q:** *Can I combine this setting with custom fonts?*  
**A:** Yes—simply load your custom fonts before initializing `Viewer`, and the grouping rule will still apply.

**Q:** *Does disabling grouping impact performance?*  
**A:** Slightly, because the engine processes each character individually, but the impact is minimal for most documents.

**Q:** *Is there a way to toggle grouping on a per‑page basis?*  
**A:** Currently the option is global per `PdfOptions` instance; you would need to create separate `Viewer` instances for different pages.

## Resources

- [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [Purchase License](https://purchase.groupdocs.com/buy)
- [Free Trial Version](https://releases.groupdocs.com/viewer/java/)
- [Temporary License Application](https://purchase.groupdocs.com/temporary-license/)
- [GroupDocs Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2025-12-21  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs