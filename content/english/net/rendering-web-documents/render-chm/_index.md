---
title: "Render CHM Files in .NET | GroupDocs.Viewer"
description: "Learn how to render CHM (Compiled HTML Help) files to HTML, JPG, PNG, and PDF in your .NET applications using GroupDocs.Viewer."
weight: 10
url: "/net/rendering-web-documents/render-chm/"
keywords:
- render chm files .net
- groupdocs.viewer for .net
- .net chm to html
- .net chm to pdf

---

## Introduction

In this tutorial, we will explore how to render CHM (Compiled HTML Help) files using **GroupDocs.Viewer for .NET**. GroupDocs.Viewer for .NET is a powerful document rendering API that allows developers to display over 170 document types within their .NET applications without requiring any external software installations.

## Prerequisites

Before we begin, ensure you have the following:
*   A working knowledge of C# and .NET development.
*   **.NET SDK:** Installed on your machine.
*   **GroupDocs.Viewer for .NET:** Download the library [here](https://releases.groupdocs.com/viewer/net/).
*   **IDE:** Visual Studio or any other .NET development environment.
*   **Sample CHM File:** A CHM file for testing purposes.

## Import Namespaces

Make sure to import the necessary namespaces into your project:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Now, let's break down the rendering process into multiple steps.

## Step 1: Define Output Directory

First, define the directory where you want the rendered files to be saved.

```csharp
string outputDirectory = "Your Document Directory";
```
**Note:** Replace `"Your Document Directory"` with the actual path.

## Step 2: Render to HTML

To render a CHM file to a single HTML page, use the following code.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.html");

using (Viewer viewer = new Viewer("YOUR_SAMPLE_FILE.chm"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // Render all content to a single page
    
    viewer.View(options);
}
```
**Note:** Replace `"YOUR_SAMPLE_FILE.chm"` with the path to your CHM file.

## Step 3: Render to JPG

To render a CHM file to JPG images, use the following code. You can specify which pages to render.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("YOUR_SAMPLE_FILE.chm"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    // Render the first three pages
    viewer.View(options, 1, 2, 3);
}
```

## Step 4: Render to PNG

To render a CHM file to PNG images, use the following code.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("YOUR_SAMPLE_FILE.chm"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options, 1, 2, 3);
}
```

## Step 5: Render to PDF

To render a CHM file to a PDF document, use the following code.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("YOUR_SAMPLE_FILE.chm"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## Step 6: Check Output

Once the rendering process is complete, you can check the specified output directory for the rendered files.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion

Rendering CHM files using GroupDocs.Viewer for .NET is a straightforward process. By following the steps outlined in this tutorial, you can efficiently convert CHM documents into various formats such as HTML, images (JPG, PNG), and PDF within your .NET applications.

## FAQs

### Can GroupDocs.Viewer render other document formats besides CHM?
Yes, GroupDocs.Viewer supports rendering over 170 document formats, including PDF, DOCX, XLSX, PPTX, and more.

### Is GroupDocs.Viewer compatible with .NET Core?
Yes, GroupDocs.Viewer supports .NET Core in addition to the traditional .NET Framework.

### Can I customize the rendering options for different output formats?
Yes, GroupDocs.Viewer provides various options for customizing the rendering process, such as specifying page numbers, setting image quality, and configuring output paths.

### Does GroupDocs.Viewer require any external dependencies for rendering documents?
No, GroupDocs.Viewer is a standalone library and does not require any external dependencies or third-party software installations.

### Is there a free trial available for GroupDocs.Viewer?
Yes, you can get a [free trial](https://releases.groupdocs.com/) of GroupDocs.Viewer from the official website.
