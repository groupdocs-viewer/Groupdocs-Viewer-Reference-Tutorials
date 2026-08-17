---
date: '2026-08-03'
description: Learn how to convert zip to html using GroupDocs.Viewer Java, set items
  per page, embed resources html, and batch convert archives efficiently.
images:
- /java/export-conversion/groupdocs-viewer-java-convert-archives-html/og-image.png
keywords:
- convert zip to html
- how to batch convert
- embed resources html
- batch convert archives
- how to convert archives
lastmod: '2026-08-03'
og_description: Learn how to convert zip to html using GroupDocs.Viewer Java, set
  items per page, embed resources html, and batch convert archives efficiently. Follow
  step‑by‑step code and performance tips.
og_image_alt: 'Guide: convert zip to html with GroupDocs.Viewer Java, showing pagination
  and embedded resources'
og_title: Convert zip to html and set items per page with GroupDocs.Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-08-03'
  description: Learn how to convert zip to html using GroupDocs.Viewer Java, set items
    per page, embed resources html, and batch convert archives efficiently.
  headline: Convert zip to html and set items per page with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: GroupDocs.Viewer Java is a server‑side library that renders over 50 document
      and archive formats—including ZIP and RAR—into HTML, PDF, or image files without
      requiring external applications.
    question: What is GroupDocs.Viewer Java?
  - answer: Visit the [free trial link](https://releases.groupdocs.com/viewer/java/)
      to download and test.
    question: How can I obtain a free trial of GroupDocs.Viewer?
  - answer: Yes, the viewer supports PDFs, Word, Excel, PowerPoint, and 35+ additional
      formats.
    question: Can I convert other document types besides archives?
  - answer: Reduce the number of items per page, enable streaming, or process archives
      in smaller batches to improve speed.
    question: What should I do if rendering is slow?
  - answer: Reach out via the [support forum](https://forum.groupdocs.com/c/viewer/9).
    question: Where can I get help or support?
  type: FAQPage
tags:
- convert zip
- GroupDocs.Viewer
- Java archive conversion
- html rendering
- batch conversion
title: Convert zip to html and set items per page with GroupDocs.Viewer Java
type: docs
url: /java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# Convert zip to html and set items per page with GroupDocs.Viewer Java

In many web applications you need to show the contents of a ZIP or RAR archive directly in a browser. With GroupDocs.Viewer for Java you can **convert zip to html** in a single step, control how many archive entries appear on each page, embed all supporting images and CSS, and even batch‑process dozens of archives. This tutorial walks you through the complete workflow, from Maven setup to multi‑page rendering, and explains why each setting matters for performance and usability.

![Convert Archives to HTML with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Quick answers
- **What does “set items per page” control?** It determines how many files or folders from an archive appear on each generated HTML page.  
- **Can I embed images and CSS directly in the HTML?** Yes – use the `forEmbeddedResources` option to embed resources HTML.  
- **Is batch conversion possible?** Absolutely; you can loop over a collection of archives and render each one with the same settings.  
- **Do I need Maven to use GroupDocs.Viewer?** Yes, add the `groupdocs-viewer` Maven dependency as shown below.  
- **Which output formats are supported?** Single‑page HTML and multi‑page HTML are both available, and the library supports 50+ input archive types.

## What is “set items per page” in GroupDocs.Viewer?
The **set items per page** setting belongs to the archive rendering options. It tells the viewer how many archive entries (files or folders) should be displayed on each HTML page when you generate a multi‑page HTML document. Adjusting this value helps you balance page size and navigation speed, especially for large archives.

## Why embed resources html?
Embedding resources (images, CSS, fonts) directly inside the HTML file creates a single, portable document that can be opened without external files. This is ideal for email attachments, offline viewing, or embedding the output into other web pages. This approach also simplifies deployment because no external asset paths need to be managed.

## Prerequisites

- **Required libraries:** Include GroupDocs.Viewer version 25.2 or later.  
- **Environment:** Java Development Kit (JDK) installed and configured.  
- **Knowledge:** Basic Java and Maven dependency management.  

## Maven GroupDocs Viewer setup

Add the GroupDocs repository and the viewer dependency to your `pom.xml`:

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
GroupDocs.Viewer offers a **free trial link**, a temporary license, or a full purchase option. Choose the one that fits your project timeline.

### Basic initialization
After the Maven setup, bring the viewer into your code:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## How to render archives to single‑page html
Viewer is the core class that loads a document or archive for rendering.

To generate a single HTML file that contains the entire archive, create a `Viewer` instance for the ZIP file and use `HtmlViewOptions.forEmbeddedResources()` to embed all images, CSS, and fonts. Rendering the archive with these options produces one self‑contained page suitable for email or offline use.

### Step 1: Define output directory
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Step 2: Set file name for single‑page output
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Step 3: Initialize the viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Step 4: Configure rendering options (embed resources html)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Step 5: Render as a single page
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## How to render archives to multi‑page html and set items per page
`HtmlViewOptions` configures how the viewer renders HTML output, including pagination and resource embedding.

To split an archive into multiple pages, create `HtmlViewOptions.forEmbeddedResources()` and set the desired page size with `options.setItemsPerPage(20)`. The viewer will generate separate HTML files, each showing up to the specified number of entries, which improves navigation for large archives and ensures faster loading.

### Step 1: Reuse the output directory
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Step 2: Define file name format for multiple pages
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Step 3: Initialize the viewer again
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Step 4: Configure multi‑page options (embed resources html)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Step 5: Set items per page (primary keyword in action)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Practical applications

- **Document management systems:** Add archive preview functionality without installing extra viewers.  
- **Web portals:** Offer users a quick, no‑download way to explore bundled documents.  
- **Collaboration tools:** Let teams inspect shared archives directly in the browser.

## Performance considerations

- **Resource management:** Keep memory usage low by processing archives in streams; the viewer can handle archives up to 500 MB without loading the entire file into memory.  
- **Batch convert archives:** Loop through a list of archive files and call the same rendering logic to maximize throughput.  
- **Caching strategy:** Store rendered HTML in a cache if the same archive is accessed frequently, reducing repeat processing time by up to 70 %.

## Frequently asked questions

**Q: What is GroupDocs.Viewer Java?**  
A: GroupDocs.Viewer Java is a server‑side library that renders over 50 document and archive formats—including ZIP and RAR—into HTML, PDF, or image files without requiring external applications.

**Q: How can I obtain a free trial of GroupDocs.Viewer?**  
A: Visit the [free trial link](https://releases.groupdocs.com/viewer/java/) to download and test.

**Q: Can I convert other document types besides archives?**  
A: Yes, the viewer supports PDFs, Word, Excel, PowerPoint, and 35+ additional formats.

**Q: What should I do if rendering is slow?**  
A: Reduce the number of items per page, enable streaming, or process archives in smaller batches to improve speed.

**Q: Where can I get help or support?**  
A: Reach out via the [support forum](https://forum.groupdocs.com/c/viewer/9).

**Q: Is it possible to embed CSS and images directly in the HTML?**  
A: Absolutely—use `HtmlViewOptions.forEmbeddedResources` as shown in the examples.

**Q: How do I batch convert a folder of archives?**  
A: Iterate over each file with a `for` loop, applying the same `Viewer` and `HtmlViewOptions` configuration for each iteration.

## Resources

- **Documentation:** Dive deeper into functionality with the [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/).  
- **API reference:** Explore the full API at the [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Download:** Get the latest binaries from the [download page](https://releases.groupdocs.com/viewer/java/).  
- **Purchase and licensing:** Review options on the [purchase page](https://purchase.groupdocs.com/buy).  
- **Support and community:** Join discussions on the [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9).

---

**Last Updated:** 2026-08-03  
**Tested With:** GroupDocs.Viewer 25.2  
**Author:** GroupDocs

## Related Tutorials

- [How to convert zip to HTML and render zip folders in Java with GroupDocs.Viewer](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [convert zip to pdf with GroupDocs.Viewer Java - Custom Filenames](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [How to Convert DOCX to HTML Using GroupDocs.Viewer for Java: A Step‑By‑Step Guide](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)