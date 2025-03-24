---
title: Render Visio Figures
linktitle: Render Visio Figures
second_title: GroupDocs.Viewer .NET API
description: Learn how to render Visio figures using GroupDocs.Viewer for .NET with this comprehensive. Enhance document viewing capabilities in your .NET applications.
weight: 10
url: /net/rendering-visio-documents/render-visio-figures/
---

# Render Visio Figures

## Introduction
In today's digital age, document rendering plays a crucial role in various applications. Whether it's displaying documents on a website or converting them into different formats, efficient rendering is essential. GroupDocs.Viewer for .NET provides a robust solution for viewing and manipulating documents within .NET applications. In this tutorial, we'll delve into rendering Visio figures using GroupDocs.Viewer for .NET, breaking down the process into simple steps.
## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites:
1. Environment Setup: Make sure you have a working environment for .NET development.
2. GroupDocs.Viewer for .NET: Download and install GroupDocs.Viewer for .NET from the [download link](https://releases.groupdocs.com/viewer/net/).
3. Basic Understanding of C#: Familiarize yourself with C# programming language fundamentals.
4. Sample Visio Document: Have a sample Visio document ready for rendering.

## Import Namespaces
In your C# project, start by importing the necessary namespaces:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1. Rendering to HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "result_page.html");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Output Directory: Define the directory where the rendered HTML will be saved.
- Page File Path Format: Specify the path format for the HTML page.
- Viewer Initialization: Initialize the Viewer object with the path to the Visio document.
- HTML View Options: Configure options for rendering HTML.
- Visio Rendering Options: Set options specific to Visio rendering, such as rendering only figures and figure width.
## 2. Rendering to JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.jpg");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Similar to rendering to HTML, configure options for rendering to JPG format.
## 3. Rendering to PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.png");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- Configuration for rendering to PNG format follows a similar pattern as JPG rendering.
## 4. Rendering to PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.pdf");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- For rendering to PDF, configure options specific to PDF format.

## Conclusion
In this tutorial, we've explored how to render Visio figures using GroupDocs.Viewer for .NET. By following the step-by-step guide, you can seamlessly integrate document rendering capabilities into your .NET applications, enhancing user experience and productivity.
## FAQ's
### Can I customize the rendering options for Visio figures?
Yes, GroupDocs.Viewer for .NET provides extensive options for customizing rendering, including figure width, rendering only figures, and more.
### Is GroupDocs.Viewer for .NET suitable for large-scale document rendering?
Absolutely, GroupDocs.Viewer for .NET is optimized for handling large-scale document rendering efficiently.
### Does GroupDocs.Viewer support other document formats apart from Visio?
Yes, GroupDocs.Viewer supports a wide range of document formats, including PDF, Microsoft Office, AutoCAD, and more.
### Can I integrate GroupDocs.Viewer into web applications?
Yes, GroupDocs.Viewer can be seamlessly integrated into web applications for document viewing and manipulation.
### Is there a trial version available for testing before purchasing?
Yes, you can avail of a free trial from the [website](https://releases.groupdocs.com/) to test the capabilities of GroupDocs.Viewer for .NET.
