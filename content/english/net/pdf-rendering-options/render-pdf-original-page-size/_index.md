---
title: Render PDF with Original Page Size
linktitle: Render PDF with Original Page Size
second_title: GroupDocs.Viewer .NET API
description: Learn how to render PDFs with original page sizes using GroupDocs.Viewer for .NET. Follow our step-by-step guide and seamlessly integrate this functionality.
type: docs
weight: 17
url: /net/pdf-rendering-options/render-pdf-original-page-size/
---
## Introduction
In the realm of .NET development, GroupDocs.Viewer stands out as a powerful tool for rendering various document formats, including PDFs. One common requirement in document handling is to render PDFs while preserving their original page sizes. Achieving this task seamlessly requires a comprehensive understanding of GroupDocs.Viewer for .NET and its functionalities.
## Prerequisites
Before diving into rendering PDFs with original page sizes using GroupDocs.Viewer for .NET, ensure you have the following prerequisites in place:
### 1. Install GroupDocs.Viewer for .NET
Begin by downloading the GroupDocs.Viewer library from the website. You can obtain the library from the provided [download link](https://releases.groupdocs.com/viewer/net/). Follow the installation instructions provided in the documentation to integrate it into your .NET project effectively.
### 2. Set Up Development Environment
Ensure you have a development environment set up for .NET development. This includes having a compatible IDE installed, such as Visual Studio, and a basic understanding of C# programming.
### 3. Obtain a PDF Document
You'll need a sample PDF document to render with GroupDocs.Viewer. You can use any PDF document for testing purposes. If you don't have one, you can download a sample PDF from various online sources.

## Import Namespaces
Before proceeding with rendering PDFs, it's essential to import the necessary namespaces into your C# project. This step allows you to access the required classes and methods from the GroupDocs.Viewer library.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Now that you have the prerequisites in place and the necessary namespaces imported, let's break down the process of rendering PDFs with original page sizes using GroupDocs.Viewer for .NET into simple steps:
## Step 1: Define Output Directory
```csharp
string outputDirectory = "Your Document Directory";
```
Ensure you specify the directory where you want the rendered pages to be saved. Replace `"Your Document Directory"` with the path of your desired directory.
## Step 2: Define Page File Path Format
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
Set up the format for naming the rendered page files. In this example, the pages will be saved as PNG images with filenames in the format `"page_1.png"`, `"page_2.png"`, and so on.
## Step 3: Render PDF with Original Page Size
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
Instantiate a `Viewer` object with the path to your PDF file. Then, create `PngViewOptions` with the specified page file path format. Set `RenderOriginalPageSize` property to `true` to preserve the original page sizes while rendering.
## Step 4: Display Rendered Document Location
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Print a message indicating successful rendering and provide the directory where the rendered pages are saved.

## Conclusion
Rendering PDFs with original page sizes using GroupDocs.Viewer for .NET is a straightforward process when you follow the steps outlined in this tutorial. By importing the necessary namespaces and following the step-by-step guide, you can seamlessly integrate this functionality into your .NET applications.
## FAQ's
### Can GroupDocs.Viewer render other document formats besides PDF?
Yes, GroupDocs.Viewer supports rendering various document formats, including Word, Excel, PowerPoint, and more.
### Is GroupDocs.Viewer compatible with .NET Core?
Yes, GroupDocs.Viewer is compatible with both .NET Framework and .NET Core environments.
### Can I customize the output format of rendered pages?
Yes, you can customize the output format by adjusting the options provided by GroupDocs.Viewer, such as setting different image formats or specifying custom rendering options.
### Does GroupDocs.Viewer offer support for cloud-based document rendering?
Yes, GroupDocs.Viewer provides APIs for cloud-based document rendering, allowing you to render documents directly from cloud storage providers.
### Is there a free trial available for GroupDocs.Viewer?
Yes, you can explore GroupDocs.Viewer with a free trial by visiting the provided [link](https://releases.groupdocs.com/).
