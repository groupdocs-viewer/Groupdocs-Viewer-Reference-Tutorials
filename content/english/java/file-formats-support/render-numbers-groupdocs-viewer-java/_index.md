---
date: '2026-08-25'
description: Learn how to convert numbers with GroupDocs.Viewer for Java, turning
  Apple Numbers files into PDF, HTML, JPG, or PNG. Includes setup, java document conversion
  steps, and web display tips.
images:
- /java/file-formats-support/render-numbers-groupdocs-viewer-java/og-image.png
keywords:
- how to convert numbers
- java document conversion
- display numbers web
- java spreadsheet pdf
lastmod: '2026-08-25'
og_description: Learn how to convert numbers with GroupDocs.Viewer for Java, turning
  Apple Numbers files into PDF, HTML, JPG, or PNG. Includes setup, java document conversion
  steps, and web display tips.
og_image_alt: 'Developer guide: Convert Numbers to PDF, HTML, JPG, PNG using GroupDocs.Viewer
  for Java'
og_title: How to convert numbers with GroupDocs.Viewer for Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-25'
  description: Learn how to convert numbers with GroupDocs.Viewer for Java, turning
    Apple Numbers files into PDF, HTML, JPG, or PNG. Includes setup, java document
    conversion steps, and web display tips.
  headline: How to convert numbers with GroupDocs.Viewer for Java
  type: TechArticle
- questions:
  - answer: Over 100 formats, including DOCX, XLSX, PDF, HTML, and Apple Numbers,
      with full rendering capabilities for each.
    question: What file formats does GroupDocs.Viewer support?
  - answer: Stream the conversion page‑by‑page, use `options.setPageCount()` to limit
      memory usage, and consider compressing the output PDF.
    question: How do I handle large Numbers files efficiently?
  - answer: Yes—purchase a commercial license to remove trial limitations and obtain
      production‑grade support.
    question: Can GroupDocs.Viewer be used in a commercial project?
  - answer: Absolutely. Adjust `JpgViewOptions.setQuality(int)` or `PngViewOptions.setResolution(int)`
      to meet your size‑quality requirements.
    question: Is it possible to customize the output quality of images?
  - answer: Visit the [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)
      for deep‑dive guides, sample projects, and API reference details.
    question: Where can I find more advanced usage examples?
  type: FAQPage
tags:
- convert numbers
- GroupDocs.Viewer
- Java document processing
title: How to convert numbers with GroupDocs.Viewer for Java
type: docs
url: /java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# How to convert numbers with GroupDocs.Viewer for Java

Displaying Apple Numbers spreadsheets on the web or inside a desktop client can feel like a puzzle, especially when you need to **convert numbers to PDF** or embed them as images for reports. In this tutorial you’ll learn exactly **how to convert numbers** to PDF, HTML, JPG, and PNG using **GroupDocs.Viewer for Java**. We’ll walk through project setup, code‑level rendering, and real‑world scenarios so you can build robust preview or archiving pipelines in minutes.

![Render Apple Numbers Documents with GroupDocs.Viewer for Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

[Render Apple Numbers Documents with GroupDocs.Viewer for Java](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### What you’ll learn
- How to add GroupDocs.Viewer to a Maven‑based Java project.  
- Step‑by‑step code to **convert numbers to pdf**, **convert numbers to html**, **convert numbers to jpg**, and **convert numbers to png**.  
- When to choose each output format for web portals, email workflows, or document management systems.  

## Quick answers
- **Can I convert Numbers to PDF with Java?** Yes – instantiate `Viewer` and call `PdfViewOptions` to get a ready‑to‑store PDF.  
- **Which format gives the richest web preview?** HTML, because it keeps tables, formulas, and styling interactive.  
- **Do I need a license for production?** A commercial license is required for any non‑trial deployment.  
- **Is image conversion supported?** Absolutely – use `JpgViewOptions` or `PngViewOptions` for high‑quality snapshots.  
- **What Java version is required?** Java 8+ and Maven for dependency management.

## Prerequisites
- Java Development Kit (JDK) 8 or later installed on your machine.  
- Maven for handling dependencies and building the project.  
- Basic familiarity with Java file I/O, paths, and exception handling.  

## Setting up GroupDocs.Viewer for Java

### Installation with Maven
Add the GroupDocs repository and the Viewer dependency to your `pom.xml`. This block must stay exactly as shown:

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

### License acquisition
- **Free trial:** Full feature set, no credit‑card required.  
- **Temporary license:** Request a time‑limited key for extended testing.  
- **Full purchase:** Obtain a perpetual license for commercial use.

## What is the Viewer class?
The `Viewer` class is GroupDocs.Viewer’s core engine that loads a document and renders it into the requested output format. It abstracts file‑type handling so you can focus on business logic instead of parsing spreadsheet internals.

## How to convert Numbers to HTML with GroupDocs.Viewer for Java?

`HtmlViewOptions` specifies settings for HTML rendering, such as embedding resources or linking external files.  
Load the Numbers file, configure HTML options, and call `viewer.view()`. The `HtmlViewOptions.forEmbeddedResources()` method bundles CSS and images directly into the HTML, which makes the result ideal for embedding in a web page without additional assets.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    viewer.view(options);
}
```

- **Why this matters:** Embedded resources keep the preview self‑contained, eliminating broken image links and simplifying CDN deployment.

## How to convert Numbers to JPG with GroupDocs.Viewer for Java?

`JpgViewOptions` configures JPEG output, allowing quality and size adjustments for each rendered page.  
You can turn each spreadsheet page into a JPEG snapshot. Adjust the `quality` setting to balance file size and visual fidelity, which is useful when you need lightweight images for social media or email newsletters.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Tip:** For faster processing of large workbooks, lower the quality to 70 % – the visual impact is minimal while the file size drops dramatically.

## How to convert Numbers to PNG with GroupDocs.Viewer for Java?

`PngViewOptions` configures PNG output, supporting lossless compression and resolution settings for high‑quality images.  
PNG offers lossless compression, preserving every pixel exactly as rendered. Use the `resolution` property to increase DPI when you need print‑ready graphics for reports or PDFs.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Pro tip:** Set `options.setResolution(300)` for high‑resolution output that looks crisp on printed pages.

## How to convert Numbers to PDF with GroupDocs.Viewer for Java?

`PdfViewOptions` defines PDF rendering options, including font embedding, compression, and page size control.  
The `PdfViewOptions` object lets you embed fonts, control page size, and preserve the original layout of the Numbers workbook. The conversion runs in a single call, producing a searchable, non‑editable PDF that’s perfect for archiving or compliance.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Key configuration:** Enable `options.setCompress(true)` to shrink the PDF size without sacrificing quality, which is essential for large‑scale document warehouses.

## Why use GroupDocs.Viewer for Java?

GroupDocs.Viewer supports **over 100 file formats**, including Apple Numbers, and can render multi‑hundred‑page spreadsheets without loading the entire file into memory. Benchmarks show that a 250‑page Numbers file is converted to PDF in under 8 seconds on a standard 2.5 GHz CPU, delivering both speed and reliability for enterprise pipelines.

## Practical applications
- **Web integration:** Render to HTML for an interactive spreadsheet viewer that works across browsers without plugins.  
- **Content sharing:** Convert to JPG/PNG for quick image embeds in newsletters, chat apps, or social feeds.  
- **Enterprise DMS:** Use **how to convert numbers** to PDF to store a non‑editable, searchable version of the spreadsheet for compliance and audit trails.  

## Performance considerations
- **Resource management:** Always instantiate `Viewer` inside a try‑with‑resources block (as shown) so native resources are released promptly.  
- **Large workbooks:** Process page‑by‑page and stream the output to keep memory usage under 100 MB, even for 500‑page files.  
- **Thread safety:** Create a separate `Viewer` instance per thread; the class is not thread‑safe, so sharing a single instance can cause race conditions.

## Common pitfalls and troubleshooting

- **Missing fonts:** If the generated PDF looks different, ensure the required fonts are available on the server or embed them using `PdfViewOptions.setEmbedFonts(true)`.  
- **Blank pages:** Verify that the Numbers file isn’t password‑protected; GroupDocs.Viewer currently does not decrypt protected workbooks.  
- **Out‑of‑memory errors:** For extremely large files, enable `options.setPageCount(1)` to render one page at a time and combine the results later.

## Frequently asked questions

**Q: What file formats does GroupDocs.Viewer support?**  
A: Over 100 formats, including DOCX, XLSX, PDF, HTML, and Apple Numbers, with full rendering capabilities for each.

**Q: How do I handle large Numbers files efficiently?**  
A: Stream the conversion page‑by‑page, use `options.setPageCount()` to limit memory usage, and consider compressing the output PDF.

**Q: Can GroupDocs.Viewer be used in a commercial project?**  
A: Yes—purchase a commercial license to remove trial limitations and obtain production‑grade support.

**Q: Is it possible to customize the output quality of images?**  
A: Absolutely. Adjust `JpgViewOptions.setQuality(int)` or `PngViewOptions.setResolution(int)` to meet your size‑quality requirements.

**Q: Where can I find more advanced usage examples?**  
A: Visit the [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/) for deep‑dive guides, sample projects, and API reference details.

## Next steps
Experiment with the options shown above, then explore additional customization such as watermarking PDFs, adding password protection, or integrating the viewer into a Spring Boot REST service. The [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/) provides a full catalog of features you can mix and match.

## Resources
- **Documentation:** [GroupDocs.Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)  
- **GroupDocs documentation:** [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)  
- **API reference:** [API reference](https://reference.groupdocs.com/viewer/java/)  
- **API reference:** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **Download:** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- **Purchase license:** [Buy a License](https://purchase.groupdocs.com/buy)  
- **Free trial:** [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **Temporary license:** [Request Here](https://purchase.groupdocs.com/temporary-license/)  
- **Support forum:** [Join the Discussion](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-08-25  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs

## Related Tutorials

- [How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/)
- [How to Convert Excel to HTML and Render Hidden Rows & Columns in Java with GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)
- [Java Document Rendering Tutorial - Convert Files to HTML, PDF & Images](/viewer/java/rendering-basics/)