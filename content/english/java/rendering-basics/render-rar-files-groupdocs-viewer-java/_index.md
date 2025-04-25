---
title: "Render RAR Files to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer for Java"
description: "Learn how to transform RAR files into accessible formats like HTML, JPG, PNG, and PDF using GroupDocs.Viewer for Java. This step-by-step guide covers everything from setup to rendering specific folders."
date: "2025-04-24"
weight: 1
url: "/java/rendering-basics/render-rar-files-groupdocs-viewer-java/"
keywords:
- render RAR files
- GroupDocs.Viewer for Java
- convert RAR to HTML
- convert RAR to JPG
- convert RAR to PNG
- convert RAR to PDF

---


# Render RAR Files to Various Formats Using GroupDocs.Viewer for Java

Unlock the potential of your RAR archives by transforming them into accessible formats like HTML, JPG, PNG, and PDF with GroupDocs.Viewer for Java. This tutorial will guide you through each step, enabling seamless document management and presentation.

## What You'll Learn
- Render RAR files into multiple formats using GroupDocs.Viewer for Java.
- Step-by-step code examples for converting RARs to HTML, JPG, PNG, and PDF.
- Retrieve view information from a RAR archive.
- Render specific folders within a RAR file.

Let's dive in!

### Prerequisites
Before we begin, ensure you have the following:

1. **Java Development Kit (JDK)**: Version 8 or higher is required.
2. **Maven**: This tutorial uses Maven for dependency management.
3. **GroupDocs.Viewer for Java Library**: We'll be using version 25.2.

#### Environment Setup
- Make sure your development environment is set up with JDK and Maven installed.
- Familiarity with basic Java programming concepts will help you follow along more easily.

### Setting Up GroupDocs.Viewer for Java
To integrate GroupDocs.Viewer into your project, add the following dependencies in your `pom.xml` file:

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
- **Free Trial**: Download a free trial from the [GroupDocs website](https://releases.groupdocs.com/viewer/java/).
- **Temporary License**: Obtain a temporary license for extended features at [GroupDocs License Page](https://purchase.groupdocs.com/temporary-license/).
- **Purchase**: For long-term use, purchase a license through the [GroupDocs Purchase Page](https://purchase.groupdocs.com/buy).

#### Basic Initialization
After setting up your environment and dependencies, initialize GroupDocs.Viewer like so:

```java
import com.groupdocs.viewer.Viewer;

public class ViewerInitialization {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/file.rar")) {
            // Your rendering code here
        }
    }
}
```

### Implementation Guide
We'll explore how to render RAR files into different formats, each with its own set of configurations.

#### Rendering RAR to HTML
**Overview**: Convert a RAR file into an HTML document for web viewing.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import java.nio.file.Paths;

public class RenderRarToHtml {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderingRar");
        Path pageFilePathFormat = outputDirectory.resolve("RAR_result_{0}.html");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options); // Renders the RAR file to HTML format
        }
    }
}
```
- **Explanation**: The `HtmlViewOptions` class is used with embedded resources, allowing for a complete web page render including CSS and images.

#### Rendering RAR to JPG
**Overview**: Transform RAR files into JPEG images, ideal for thumbnail previews.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;

public class RenderRarToJpg {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderingRar");
        Path pageFilePathFormat = outputDirectory.resolve("RAR_result_{0}.jpg");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options); // Converts the RAR file to JPG format
        }
    }
}
```
- **Explanation**: `JpgViewOptions` specifies the output path and handles image rendering.

#### Rendering RAR to PNG
**Overview**: Convert RAR archives into PNG images for high-quality previews.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;

public class RenderRarToPng {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderingRar");
        Path pageFilePathFormat = outputDirectory.resolve("RAR_result_{0}.png");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options); // Renders the RAR file to PNG format
        }
    }
}
```
- **Explanation**: Similar to JPG, `PngViewOptions` is used for rendering each page of the RAR as a PNG image.

#### Rendering RAR to PDF
**Overview**: Generate PDF documents from RAR files for easy sharing and printing.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;

public class RenderRarToPdf {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderingRar");
        Path pageFilePathFormat = outputDirectory.resolve("RAR_result.pdf");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options); // Converts the RAR file to PDF format
        }
    }
}
```
- **Explanation**: `PdfViewOptions` configures the output path for the PDF document.

#### Getting View Info for RAR
**Overview**: Retrieve metadata and structure information from a RAR archive.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ArchiveViewInfo;

public class GetViewInfoForRar {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            ViewInfo info = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
            System.out.println("File type: " + info.getFileType());
            System.out.println("Pages count: " + info.getPages().size());

            readFolders(viewer, "");
        }
    }

    private static void readFolders(Viewer viewer, String folder) {
        ViewInfoOptions options = ViewInfoOptions.forHtmlView();
        options.getArchiveOptions().setFolder(folder);

        ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(options);
        for (String subFolder : viewInfo.getFolders()) {
            System.out.println(" - " + subFolder);
            readFolders(viewer, subFolder);
        }
    }
}
```
- **Explanation**: This code retrieves and prints the file type and number of pages in a RAR archive.

#### Rendering Specific Folder of RAR Archive
**Overview**: Focus on rendering specific folders within a RAR file to HTML format.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class RenderSpecificArchiveFolder {
    public static void main(String[] args) {
        Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY", "RenderSpecificArchiveFolder");
        Path pageFilePathFormat = outputDirectory.resolve("archive_folder_page_{0}.html");

        try (Viewer viewer = new Viewer(Paths.get("YOUR_DOCUMENT_DIRECTORY", "SAMPLE_RAR_WITH_FOLDERS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            options.getArchiveOptions().setFolder("TargetFolderName"); // Specify the folder you want to render
            viewer.view(options); // Renders specified folder content to HTML
        }
    }
}
```
- **Explanation**: Use `HtmlViewOptions` with specific folder settings to target and render individual folders within a RAR archive.

By following these steps, you can effectively use GroupDocs.Viewer for Java to manage and convert your RAR files into various formats.
