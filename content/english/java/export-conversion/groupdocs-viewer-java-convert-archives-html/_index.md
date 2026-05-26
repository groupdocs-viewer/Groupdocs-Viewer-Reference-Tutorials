---
title: "Set Items Per Page: Convert Archives to HTML with GroupDocs.Viewer Java"
description: "Learn how to set items per page, embed resources HTML, and batch convert archives to single or multi‑page HTML using GroupDocs.Viewer Java."
date: "2026-02-23"
weight: 1
url: "/java/export-conversion/groupdocs-viewer-java-convert-archives-html/"
keywords:
- convert archives to HTML Java
- GroupDocs.Viewer Java tutorial
- render ZIP RAR to HTML
type: docs
---

# Set Items Per Page: Convert Archives to HTML with GroupDocs.Viewer Java

Converting archive files such as ZIP or RAR into web‑friendly HTML is a frequent need when you want to share or review documents directly in a browser. In this guide you’ll learn **how to set items per page** while rendering archives, how to embed resources HTML for a self‑contained output, and how to batch convert archives efficiently with GroupDocs.Viewer Java.

![Convert Archives to HTML with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## Quick Answers
- **What does “set items per page” control?** It determines how many files or folders from an archive appear on each generated HTML page.  
- **Can I embed images and CSS directly in the HTML?** Yes – use the `forEmbeddedResources` option to embed resources HTML.  
- **Is batch conversion possible?** Absolutely; you can loop over a collection of archives and render each one with the same settings.  
- **Do I need Maven to use GroupDocs.Viewer?** Yes, add the `maven groupdocs viewer` dependency as shown below.  
- **Which output formats are supported?** Single‑page HTML Java and multi‑page HTML Java are both available.

## What is “set items per page” in GroupDocs.Viewer?
The **set items per page** setting belongs to the archive rendering options. It tells the viewer how many archive entries (files or folders) should be displayed on each HTML page when you generate a multi‑page HTML document. Adjusting this value helps you balance page size and navigation speed, especially for large archives.

## Why embed resources HTML?
Embedding resources (images, CSS, fonts) directly inside the HTML file creates a single, portable document that can be opened without external files. This is ideal for email attachments, offline viewing, or embedding the output into other web pages.

## Prerequisites

- **Required Libraries:** Include GroupDocs.Viewer version 25.2 or later.  
- **Environment:** Java Development Kit (JDK) installed and configured.  
- **Knowledge:** Basic Java and Maven dependency management.  

## Maven GroupDocs Viewer Setup

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

### License Acquisition
GroupDocs.Viewer offers a **free trial link**, a temporary license, or a full purchase option. Choose the one that fits your project timeline.

### Basic Initialization
After the Maven setup, bring the viewer into your code:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## How to Render Archives to Single‑Page HTML

### Step 1: Define Output Directory
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Step 2: Set File Name for Single‑Page Output
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### Step 3: Initialize the Viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### Step 4: Configure Rendering Options (embed resources HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Step 5: Render as a Single Page
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## How to Render Archives to Multi‑Page HTML and Set Items Per Page

### Step 1: Reuse the Output Directory
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### Step 2: Define File Name Format for Multiple Pages
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### Step 3: Initialize the Viewer Again
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### Step 4: Configure Multi‑Page Options (embed resources HTML)
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### Step 5: Set Items Per Page (primary keyword in action)
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## Practical Applications

- **Document Management Systems:** Add archive preview functionality without installing extra viewers.  
- **Web Portals:** Offer users a quick, no‑download way to explore bundled documents.  
- **Collaboration Tools:** Let teams inspect shared archives directly in the browser.

## Performance Considerations

- **Resource Management:** Keep an eye on memory usage; consider tuning the JVM’s garbage‑collector for large batches.  
- **Batch Convert Archives:** Loop through a list of archive files and call the same rendering logic to maximize throughput.  
- **Caching Strategy:** Store rendered HTML in a cache if the same archive is accessed frequently.

## Frequently Asked Questions

**Q: What is GroupDocs.Viewer Java?**  
A: A versatile library for rendering documents—including archives—into formats such as HTML, PDF, and images.

**Q: How can I obtain a free trial of GroupDocs.Viewer?**  
A: Visit the [free trial link](https://releases.groupdocs.com/viewer/java/) to download and test.

**Q: Can I convert other document types besides archives?**  
A: Yes, the viewer supports PDFs, Word, Excel, and many more formats.

**Q: What should I do if rendering is slow?**  
A: Reduce the number of items per page, enable streaming, or process archives in smaller batches.

**Q: Where can I get help or support?**  
A: Reach out via the [support forum](https://forum.groupdocs.com/c/viewer/9).

**Q: Is it possible to embed CSS and images directly in the HTML?**  
A: Absolutely—use `HtmlViewOptions.forEmbeddedResources` as shown in the examples.

**Q: How do I batch convert a folder of archives?**  
A: Iterate over each file with a `for` loop, applying the same `Viewer` and `HtmlViewOptions` configuration for each iteration.

## Resources

- **Documentation:** Dive deeper into functionality with the [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/).  
- **API Reference:** Explore the full API at the [GroupDocs API](https://reference.groupdocs.com/viewer/java/).  
- **Download:** Get the latest binaries from the [download page](https://releases.groupdocs.com/viewer/java/).  
- **Purchase and Licensing:** Review options on the [purchase page](https://purchase.groupdocs.com/buy).  
- **Support and Community:** Join discussions on the [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9).

---

**Last Updated:** 2026-02-23  
**Tested With:** GroupDocs.Viewer 25.2  
**Author:** GroupDocs