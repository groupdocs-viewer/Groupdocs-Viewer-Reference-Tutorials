---
title: Render FODG and ODG Images
linktitle: Render FODG and ODG Images
second_title: GroupDocs.Viewer .NET API
description: Learn how to render FODG and ODG images to HTML, JPG, PNG, and PDF using GroupDocs.Viewer for .NET. Enhance your document handling.
weight: 15
url: /net/image-rendering/render-fodg-odg-images/
---

# Render FODG and ODG Images

## Introduction
In the world of software development, efficient handling of document formats is paramount. GroupDocs.Viewer for .NET is a powerful tool designed to simplify the process of rendering FODG and ODG images within .NET applications. This tutorial will walk you through the steps required to render these images into various formats, such as HTML, JPG, PNG, and PDF, using GroupDocs.Viewer for .NET.
## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites:
1. GroupDocs.Viewer for .NET: Download and install GroupDocs.Viewer for .NET from [here](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework: Make sure you have .NET Framework installed on your system.
3. Basic knowledge of C#: Familiarity with C# programming language will be helpful.

## Import Namespaces
Before starting with the implementation, import the necessary namespaces:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Step 1: Set Output Directory
```csharp
string outputDirectory = "Your Document Directory";
```
Replace `"Your Document Directory"` with the directory path where you want to save the rendered images.
## Step 2: Render to HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
This step renders the FODG image to HTML format.
## Step 3: Render to JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Here, the FODG image is rendered to JPG format.
## Step 4: Render to PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
This step converts the FODG image to PNG format.
## Step 5: Render to PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
Finally, the FODG image is rendered to PDF format.

## Conclusion
In this tutorial, we've explored how to render FODG and ODG images into various formats using GroupDocs.Viewer for .NET. By following these steps, you can seamlessly integrate document rendering capabilities into your .NET applications.
## FAQ's
### Is GroupDocs.Viewer for .NET compatible with all versions of .NET Framework?
GroupDocs.Viewer for .NET is compatible with a wide range of .NET Framework versions, including the latest ones.
### Can I render documents asynchronously with GroupDocs.Viewer for .NET?
Yes, GroupDocs.Viewer for .NET provides asynchronous rendering capabilities for improved performance.
### Does GroupDocs.Viewer for .NET support rendering encrypted documents?
Yes, GroupDocs.Viewer for .NET supports rendering encrypted documents with appropriate decryption keys.
### Is it possible to customize the rendering output with GroupDocs.Viewer for .NET?
Absolutely, GroupDocs.Viewer for .NET offers various customization options to tailor the rendering output according to your requirements.
### Can I render documents from remote storage locations using GroupDocs.Viewer for .NET?
Yes, GroupDocs.Viewer for .NET supports rendering documents from both local and remote storage locations.
