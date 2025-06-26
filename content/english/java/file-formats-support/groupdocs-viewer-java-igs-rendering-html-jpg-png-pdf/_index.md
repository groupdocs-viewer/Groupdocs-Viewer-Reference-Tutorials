---
title: "Mastering GroupDocs.Viewer Java&#58; Convert IGS Files to HTML, JPG, PNG, and PDF"
description: "Learn how to convert IGS files into various formats using GroupDocs.Viewer for Java. Follow this step-by-step guide to render 3D models in HTML, JPG, PNG, or PDF."
date: "2025-04-24"
weight: 1
url: "/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/"
keywords:
- GroupDocs.Viewer Java
- Convert IGS Files
- Render IGS Documents

---


# Mastering GroupDocs.Viewer Java: Convert IGS Files to Multiple Formats

## Introduction

Are you looking to convert complex IGS files into accessible formats like HTML, JPG, PNG, or PDF using Java? This comprehensive guide will help you master the GroupDocs.Viewer for Java library. Whether you're a seasoned developer or just starting out, this tutorial will enable you to render IGS documents effortlessly.

![Convert IGS Files to HTML, JPG, PNG, and PDF with GroupDocs.Viewer for Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

**What You'll Learn:**
- How to set up and configure GroupDocs.Viewer for Java.
- Step-by-step instructions on rendering IGS files into HTML, JPG, PNG, and PDF formats.
- Key configuration options and troubleshooting tips.
- Practical applications of these conversions in real-world scenarios.

Let's begin by covering the prerequisites!

## Prerequisites

To follow this tutorial effectively, ensure you have the following:

### Required Libraries and Dependencies
- **GroupDocs.Viewer for Java**: Version 25.2 or later is recommended.
- **Java Development Kit (JDK)**: Ensure JDK 8 or higher is installed on your system.

### Environment Setup Requirements
- A suitable Integrated Development Environment (IDE) like IntelliJ IDEA, Eclipse, or NetBeans.
- Basic understanding of Java programming concepts and file I/O operations.

### Knowledge Prerequisites
Familiarity with Maven for dependency management would be beneficial but not mandatory. We'll cover everything step-by-step!

## Setting Up GroupDocs.Viewer for Java

To get started with rendering IGS files, first set up the GroupDocs.Viewer library in your project.

**Maven Setup**
Add the following configuration to your `pom.xml` file:

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
GroupDocs.Viewer offers a free trial, temporary licenses for testing, and purchase options for full access:
- **Free Trial**: Access core features with limited usage.
- **Temporary License**: Evaluate the library without restrictions for a short period.
- **Purchase**: Buy a license for long-term use.

Once set up, initialize GroupDocs.Viewer in your Java application as follows:

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

## Implementation Guide

Now, let's break down the process of converting IGS files into various formats using GroupDocs.Viewer for Java.

### Rendering IGS to HTML

**Overview:**
Convert an IGS file into an interactive HTML page with embedded resources. This format is excellent for web applications where users need to view 3D models directly in their browsers.

#### Step-by-Step Implementation:
1. **Set Output Directory and File Path:**
   Define the directory where your rendered files will be saved, along with specifying the output file name.

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

2. **Understand Parameters:**
   - `HtmlViewOptions.forEmbeddedResources()` specifies that resources (like images) should be embedded within the HTML file, making it a standalone document.

3. **Troubleshooting Tips:**
   - Ensure your output directory path is correct.
   - Verify file permissions to write in the specified directory.

### Rendering IGS to JPG

**Overview:**
Convert your IGS files into high-quality JPG images, which can be used for thumbnails or previews of 3D models.

#### Step-by-Step Implementation:
1. **Set Output Directory and File Path:**
   Similar setup as HTML conversion but with JPG-specific options.

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

2. **Key Configurations:**
   - `JpgViewOptions` allows you to define the resolution and quality of the output image.

3. **Troubleshooting Tips:**
   - Check if your IGS file is correctly referenced.
   - Adjust JPG options for optimal quality based on your needs.

### Rendering IGS to PNG

**Overview:**
Generate transparent or non-transparent images from your IGS files in PNG format, ideal for detailed visualizations.

#### Step-by-Step Implementation:
1. **Set Output Directory and File Path:**

    ```java
    import com.groupdocs.viewer.Viewer;
    import com.groupdocs.viewer.options.PngViewOptions;
    import java.nio.file.Path;
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

2. **Configuration Options:**
   - `PngViewOptions` can be used to specify image quality and transparency.

3. **Troubleshooting Tips:**
   - Ensure your IGS file path is correctly set.
   - Experiment with different PNG options for best results.

### Rendering IGS to PDF

**Overview:**
Convert IGS documents into universally accessible PDF files, perfect for sharing detailed 3D models in a standardized format.

#### Step-by-Step Implementation:
1. **Set Output Directory and File Path:**

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

2. **Key Features:**
   - `PdfViewOptions` allows customization of PDF settings like layout and quality.

3. **Troubleshooting Tips:**
   - Verify that the output directory is writable.
   - Check for any errors in the IGS file format.

## Practical Applications

Rendering IGS files into various formats opens up numerous possibilities:
1. **Web Integration**: Embed HTML-rendered 3D models directly in web applications.
2. **Document Sharing**: Share detailed visualizations via PDFs or image previews (JPG/PNG).
3. **Product Visualization**: Use high-quality images for product catalogs and marketing materials.

This guide equips you with the knowledge to effectively utilize GroupDocs.Viewer for Java, transforming IGS files into a variety of formats.
