---
date: '2026-08-08'
description: Learn how to convert IGS to PDF, HTML, JPG, and PNG using GroupDocs.Viewer
  for Java. Step‑by‑step guide, prerequisites, and troubleshooting for Java developers.
images:
- /java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/og-image.png
keywords:
- convert igs to pdf
- convert cad to image
- convert igs to jpg
- java cad to pdf
lastmod: '2026-08-08'
og_description: Convert IGS to PDF, HTML, JPG, and PNG using GroupDocs.Viewer for
  Java. Detailed setup, code snippets, and troubleshooting for Java developers.
og_image_alt: 'Developer guide: convert IGS files to PDF, HTML, JPG, PNG with GroupDocs.Viewer
  Java'
og_title: Convert IGS to PDF, HTML, JPG & PNG with GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-08'
  description: Learn how to convert IGS to PDF, HTML, JPG, and PNG using GroupDocs.Viewer
    for Java. Step‑by‑step guide, prerequisites, and troubleshooting for Java developers.
  headline: Convert IGS to PDF, HTML, JPG & PNG with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: Yes. Iterate over a collection of file paths and invoke the appropriate
      `view` method for each file within the same `Viewer` instance.
    question: Can I convert multiple IGS files in a single run?
  - answer: Absolutely. `PdfViewOptions` offers `setPageSize(PageSize.A4)`, `PageSize.Letter`,
      and custom dimensions via `setCustomSize(width, height)`.
    question: Is it possible to customize the PDF page size?
  - answer: No. A single GroupDocs.Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: The library reliably processes files up to **500 MB**; for models larger
      than 200 MB, allocate additional JVM memory and consider rendering in batches.
    question: How large can an IGS file be before performance degrades?
  - answer: GroupDocs.Viewer renders the default orientation defined in the IGS file.
      For custom views, preprocess the file with a CAD tool or adjust the model before
      conversion.
    question: Can I render only a specific view or orientation?
  type: FAQPage
tags:
- convert igs
- groupdocs.viewer
- java cad conversion
- pdf generation java
title: Convert IGS to PDF, HTML, JPG & PNG with GroupDocs.Viewer Java
type: docs
url: /java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# Convert IGS to PDF, HTML, JPG & PNG with GroupDocs.Viewer Java

If you need to **convert IGS to PDF** (or to HTML, JPG, PNG) directly from a Java application, you’ve come to the right place. In this tutorial we’ll walk through everything you need—from installing the library to rendering the 3‑D model in the format that fits your project. You’ll understand why GroupDocs.Viewer is a solid choice for fast, reliable conversions and you’ll get ready‑to‑run code snippets you can drop into your own solution.

![Convert IGS Files to HTML, JPG, PNG, and PDF with GroupDocs.Viewer for Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## Quick answers
- **Can I convert IGS to PDF with Java?** Yes, use `PdfViewOptions` together with the `Viewer` API.  
- **Which output formats are supported?** HTML, JPG, PNG, and PDF are all natively handled.  
- **Do I need a license for production?** A commercial license is required; a free trial lets you test the core features.  
- **What Java version is required?** JDK 8 or higher; the library also runs on Java 11, 17, and later.  
- **Is Maven the only way to add the library?** No, you can also use Gradle or manually add the JAR files to your classpath.

## What is convert IGS to PDF?
Converting IGS to PDF means turning a neutral 3‑D CAD file into a static, universally viewable document. This enables you to share design visuals with stakeholders who lack CAD tools, embed the rendering in reports, or archive the model for compliance purposes.

## Why use GroupDocs.Viewer for IGS conversions?
GroupDocs.Viewer processes IGS files without requiring any external CAD software. It supports **50+ input and output formats**, can render assemblies containing **hundreds of parts** while keeping memory usage under **200 MB**, and delivers results in under **2 seconds** for typical models on a standard server. These quantified benefits make it a high‑performance, cost‑effective choice for enterprise pipelines.

## Prerequisites
- **GroupDocs.Viewer for Java** ≥ 25.2 (the latest stable release).  
- **JDK 8+** installed and configured in your IDE (IntelliJ IDEA, Eclipse, NetBeans, etc.).  
- Basic Maven knowledge (optional but recommended for dependency management).  

## Setting up GroupDocs.Viewer for Java

### Maven dependency
Add the GroupDocs repository and the Viewer dependency to your `pom.xml`:

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
GroupDocs.Viewer offers three licensing options:
- **Free trial** – limited usage, perfect for quick proof‑of‑concept tests.  
- **Temporary license** – full feature set for a short evaluation period, ideal for pilot projects.  
- **Commercial license** – unrestricted production use, includes priority support and updates.

### Basic viewer initialization
The `Viewer` class is the entry point for all rendering operations. It loads the source file, parses the format, and exposes methods to produce the desired output.

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## Rendering IGS to HTML

### How to convert IGS to HTML?
Load the IGS file with a `Viewer` instance and pass an `HtmlViewOptions` object that embeds all required assets. The call returns a single HTML file that contains the full 3‑D view, making it easy to embed in web pages. You can also customize the rendering by setting options such as page size, background color, and whether to include interactive controls.  
HtmlViewOptions configures how the HTML output is generated, including resource embedding and page layout.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToHtml {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Rendering IGS to JPG

### How to convert IGS to JPG?
Create a `JpgViewOptions` object, configure the desired resolution and compression quality, and let the `Viewer` generate raster images for each page of the model. The generated JPG files can be saved to a specified directory, and you may adjust the quality parameter to balance file size against visual fidelity, which is useful for thumbnails or high‑resolution prints.  
JpgViewOptions specifies settings for JPG image generation such as resolution, quality, and output directory.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToJpg {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Rendering IGS to PNG

### How to convert IGS to PNG?
The `PngViewOptions` class lets you produce lossless images with optional transparency. This format is ideal for overlaying the model on colored backgrounds in marketing material. You can also define the resolution and background color to match your brand guidelines, ensuring consistent appearance across all generated assets.  
PngViewOptions defines parameters for PNG rendering, including resolution, transparency, and background color.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPng {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Rendering IGS to PDF

### How to convert IGS to PDF?
Use `PdfViewOptions` to produce a paginated PDF that preserves the visual layout of the 3‑D model. You can also embed fonts and control page size to meet corporate branding guidelines. Additional settings allow you to specify image quality, compression level, and whether to include a table of contents for multi‑page assemblies.  
PdfViewOptions controls PDF creation, allowing page size, image quality, and font embedding configuration.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPdf {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## Practical applications
- **Web portals** – embed HTML‑rendered models directly into product configurators, allowing customers to rotate and zoom without installing plugins.  
- **Marketing assets** – generate high‑resolution JPG/PNG images for brochures, slide decks, and social media posts.  
- **Technical documentation** – include PDF renderings of CAD models in user manuals, ensuring that engineers can view designs offline.  
- **Quality assurance** – automate thumbnail creation for thousands of IGS files, speeding up visual inspection workflows.

## Common issues & solutions

| Issue | Solution |
|-------|----------|
| **Output folder not found** | Verify the path passed to `Path outputDirectory` and ensure the Java process has write permissions on the target directory. |
| **Blank pages in PDF** | Confirm the source IGS file is not corrupted; open it in a native CAD viewer first. |
| **Slow rendering for large assemblies** | Increase JVM heap (`-Xmx2g` or more) and consider rendering page‑by‑page using `viewer.getPageCount()` to process chunks. |
| **Missing fonts in PDF** | Use `PdfViewOptions` to embed required fonts or install the missing fonts on the server hosting the conversion service. |

## Frequently asked questions

**Q: Can I convert multiple IGS files in a single run?**  
A: Yes. Iterate over a collection of file paths and invoke the appropriate `view` method for each file within the same `Viewer` instance.

**Q: Is it possible to customize the PDF page size?**  
A: Absolutely. `PdfViewOptions` offers `setPageSize(PageSize.A4)`, `PageSize.Letter`, and custom dimensions via `setCustomSize(width, height)`.

**Q: Do I need a separate license for each output format?**  
A: No. A single GroupDocs.Viewer license covers all supported formats, including HTML, JPG, PNG, and PDF.

**Q: How large can an IGS file be before performance degrades?**  
A: The library reliably processes files up to **500 MB**; for models larger than 200 MB, allocate additional JVM memory and consider rendering in batches.

**Q: Can I render only a specific view or orientation?**  
A: GroupDocs.Viewer renders the default orientation defined in the IGS file. For custom views, preprocess the file with a CAD tool or adjust the model before conversion.

---

**Last updated:** 2026-08-08  
**Tested with:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs

## Related Tutorials

- [convert cdr to html, jpg, png, pdf with GroupDocs.Viewer Java](/viewer/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/)
- [How to convert pdf to html and optimize image quality in Java with GroupDocs.Viewer](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)