---
date: '2026-08-25'
description: Learn how to render hidden pages java with GroupDocs.Viewer, configure
  the API, and integrate it into Java applications for full document visibility.
images:
- /java/advanced-rendering/java-render-hidden-pages-groupdocs-viewer/og-image.png
keywords:
- render hidden pages java
- groupdocs viewer hidden slides
- java document rendering
- groupdocs viewer integration
lastmod: '2026-08-25'
og_description: Render hidden pages java using GroupDocs.Viewer. This step‑by‑step
  tutorial shows you how to enable hidden slide rendering, configure options, and
  handle performance in Java.
og_image_alt: 'Developer guide: render hidden pages java using GroupDocs.Viewer'
og_title: Render hidden pages java with GroupDocs.Viewer – Complete guide
schemas:
- author: GroupDocs
  dateModified: '2026-08-25'
  description: Learn how to render hidden pages java with GroupDocs.Viewer, configure
    the API, and integrate it into Java applications for full document visibility.
  headline: 'Render hidden pages java: How to use GroupDocs.Viewer'
  type: TechArticle
- description: Learn how to render hidden pages java with GroupDocs.Viewer, configure
    the API, and integrate it into Java applications for full document visibility.
  name: 'Render hidden pages java: How to use GroupDocs.Viewer'
  steps:
  - name: Define output directory and file‑path format
    text: 'Set up where the rendered HTML files will be saved: - **`outputDirectory`**
      – the folder that will contain the generated HTML pages. - **`pageFilePathFormat`**
      – naming pattern for each page file, using placeholders such as `{0}` for the
      page number.'
  - name: Configure HtmlViewOptions
    text: 'Create an `HtmlViewOptions` instance and enable embedded resources: HtmlViewOptions
      defines rendering settings for HTML output. - **`forEmbeddedResources`** – bundles
      CSS, JavaScript, and images directly inside the HTML output. - **`setRenderHiddenPages(true)`**
      – activates rendering of hidden slide'
  - name: Render the document
    text: 'Invoke the `Viewer` object with the configured options: - **`Viewer`**
      – loads and processes the source file. - **`view(viewOptions)`** – performs
      the rendering based on the supplied `HtmlViewOptions`. **Troubleshooting tip:**
      Verify that the document path is correct and that the Java process has wr'
  type: HowTo
- questions:
  - answer: It supports more than 30 popular formats, including PDF, DOCX, XLSX, PPTX,
      HTML, and common image types.
    question: What formats does GroupDocs.Viewer support?
  - answer: Yes – a commercial license is required for production deployments.
    question: Can I use GroupDocs.Viewer in a commercial application?
  - answer: Optimize memory usage by increasing the JVM heap, render pages in batches,
      and consider load‑balancing across multiple instances.
    question: How do I handle large documents with GroupDocs.Viewer?
  - answer: Absolutely. You can render to HTML, PNG, JPEG, or PDF by selecting the
      appropriate `ViewOptions` class.
    question: Is it possible to customize the output format?
  - answer: Double‑check your `pom.xml` dependencies, confirm the license file is
      correctly placed, and verify all file paths.
    question: What should I do if I encounter errors during setup?
  type: FAQPage
tags:
- render hidden pages
- groupdocs viewer
- java rendering
- document processing
title: 'Render hidden pages java: How to use GroupDocs.Viewer'
type: docs
url: /java/advanced-rendering/java-render-hidden-pages-groupdocs-viewer/
weight: 1
---

# Render hidden pages java: How to use GroupDocs.Viewer

In this tutorial you’ll learn **how to render hidden pages java** with GroupDocs.Viewer, why the feature matters for compliance and user experience, and exactly which API calls you need to enable hidden slide or section rendering. Whether you work with PowerPoint decks, Word documents, or PDFs, the steps below let you expose every hidden element in your Java applications.

![Render Hidden Pages with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-hidden-pages-java.png)
[Render Hidden Pages with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-hidden-pages-java.png)

## Quick answers
- **Can GroupDocs.Viewer show hidden PowerPoint slides?** Yes – call `setRenderHiddenPages(true)` on the view options.
- **Do I need a license for hidden page rendering?** A valid GroupDocs license is required for production deployments.
- **Which Java version is supported?** Java 8+ and any newer JDK.
- **Is Maven the only way to add the library?** Maven is recommended, but Gradle or manual JAR inclusion also work.
- **Will rendering affect performance?** Rendering hidden pages adds a modest overhead; see the performance‑tuning tips later in this guide.

## What is render hidden pages java?

Render hidden pages java tells GroupDocs.Viewer to treat hidden slides, hidden sections, or any content marked as invisible in the source document as regular pages during rendering. This guarantees that no information is omitted when you generate HTML, images, or PDFs from the source file.

## Why use GroupDocs.Viewer for rendering hidden content?

GroupDocs.Viewer can process **over 30 input and output formats** – including PPTX, DOCX, PDF, XLSX, and many image types – without loading the entire file into memory. Enabling hidden page rendering ensures a **100 % audit‑ready output**, which is essential for legal compliance, board‑room presentations, and archival workflows.

## Prerequisites

- **GroupDocs.Viewer for Java** version 25.2 or later.  
- **JDK 8+** installed on your development machine.  
- An IDE such as **IntelliJ IDEA** or **Eclipse**.  
- **Maven** (or Gradle) for dependency management.

### Required libraries, versions, and dependencies
- GroupDocs.Viewer for Java 25.2+  
- Java Development Kit (JDK) 8 or newer  

### Environment setup requirements
- IntelliJ IDEA or Eclipse for coding and debugging.  
- Maven (or Gradle) to pull the GroupDocs artifacts.

### Knowledge prerequisites
- Basic Java programming skills.  
- Familiarity with Maven’s `pom.xml` file structure.

## Setting up GroupDocs.Viewer for Java

### Maven setup

Add the following dependency to your `pom.xml` file to include GroupDocs.Viewer:

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

### License acquisition steps
- **Free trial** – start with a trial to explore all features.  
- **Temporary license** – obtain a short‑term license for extended testing without functional limits.  
- **Purchase** – buy a commercial license for production use and receive priority support.

### Basic initialization and setup

Ensure you import the required classes in your Java source file:

The `Viewer` class is the core component that loads and renders documents.
```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import java.nio.file.Paths;
```

Create a `Viewer` instance to begin working with documents.

## Implementation guide

### Rendering hidden pages

Below is a step‑by‑step walkthrough of the **render hidden pages java** process.

#### Step 1: Define output directory and file‑path format

Set up where the rendered HTML files will be saved:

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

- **`outputDirectory`** – the folder that will contain the generated HTML pages.  
- **`pageFilePathFormat`** – naming pattern for each page file, using placeholders such as `{0}` for the page number.

#### Step 2: Configure HtmlViewOptions

Create an `HtmlViewOptions` instance and enable embedded resources:

HtmlViewOptions defines rendering settings for HTML output.
```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.setRenderHiddenPages(true); // Enable rendering of hidden pages
```

- **`forEmbeddedResources`** – bundles CSS, JavaScript, and images directly inside the HTML output.  
- **`setRenderHiddenPages(true)`** – activates rendering of hidden slides or sections, ensuring they appear in the final result.

#### Step 3: Render the document

Invoke the `Viewer` object with the configured options:

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PPTX_HIDDEN_PAGE")) {
    viewer.view(viewOptions);
}
```

- **`Viewer`** – loads and processes the source file.  
- **`view(viewOptions)`** – performs the rendering based on the supplied `HtmlViewOptions`.

**Troubleshooting tip:** Verify that the document path is correct and that the Java process has write permission for the output directory to avoid “access denied” errors.

## Practical applications

1. **Corporate presentations** – Include every hidden slide for board‑room reviews, guaranteeing no confidential content is missed.  
2. **Document archiving** – Preserve every page of legal contracts or policy manuals, even those hidden for internal use.  
3. **Educational materials** – Deliver full lecture decks, including instructor notes that were hidden in the original file.  
4. **Interactive reports** – Allow analysts to explore supplemental charts or tables that were hidden in the source.  
5. **Software documentation** – Expose optional configuration sections that developers may need during troubleshooting.

## Performance considerations

- **Resource management** – Monitor JVM heap size (`-Xmx`) when rendering large PPTX files with many hidden slides.  
- **Load balancing** – Distribute rendering jobs across multiple server instances to handle high‑volume workloads.  
- **Efficient file handling** – Use Java NIO streams and avoid unnecessary file copies to keep latency low.

## Common issues and solutions

| Issue | Cause | Solution |
|-------|-------|----------|
| No output files generated | Incorrect `outputDirectory` path or missing write permission | Verify the directory exists and grant write access to the Java process |
| Hidden pages still missing | `setRenderHiddenPages(true)` not called | Ensure the option is set before invoking `viewer.view()` |
| Out‑of‑Memory errors | Rendering very large PPTX files with many hidden slides | Increase JVM heap (`-Xmx`) or split the document into smaller chunks before rendering |

## Frequently asked questions

**Q: What formats does GroupDocs.Viewer support?**  
A: It supports more than 30 popular formats, including PDF, DOCX, XLSX, PPTX, HTML, and common image types.

**Q: Can I use GroupDocs.Viewer in a commercial application?**  
A: Yes – a commercial license is required for production deployments.

**Q: How do I handle large documents with GroupDocs.Viewer?**  
A: Optimize memory usage by increasing the JVM heap, render pages in batches, and consider load‑balancing across multiple instances.

**Q: Is it possible to customize the output format?**  
A: Absolutely. You can render to HTML, PNG, JPEG, or PDF by selecting the appropriate `ViewOptions` class.

**Q: What should I do if I encounter errors during setup?**  
A: Double‑check your `pom.xml` dependencies, confirm the license file is correctly placed, and verify all file paths.

## Conclusion

You now have a complete, production‑ready guide for **render hidden pages java** using GroupDocs.Viewer. By enabling `setRenderHiddenPages(true)`, you guarantee that every piece of content—visible or hidden—is rendered for your users. Explore additional Viewer capabilities such as watermarking, custom CSS, or PDF conversion to extend the solution further.

---

**Last Updated:** 2026-08-25  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs  

## Resources

- **Documentation**: [GroupDocs.Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API reference**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **Download**: [GroupDocs Viewer Download](https://releases.groupdocs.com/viewer/java/)
- **Purchase**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **Free trial**: [Start a Free Trial](https://releases.groupdocs.com/viewer/java/)
- **Temporary license**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **Support**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

## Related Tutorials

- [Java Guide: render selected pages java with GroupDocs.Viewer](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)
- [How to Convert Excel to HTML and Render Hidden Rows & Columns in Java with GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [Load Document from URL in Java – GroupDocs.Viewer Tutorial](/viewer/java/document-loading/)