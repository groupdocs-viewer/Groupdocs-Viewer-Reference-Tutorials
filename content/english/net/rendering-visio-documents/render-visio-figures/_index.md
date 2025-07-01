---
title: "Render Visio Figures in .NET | GroupDocs.Viewer"
description: "Learn how to render Visio figures to HTML, JPG, PNG, and PDF in your .NET applications using GroupDocs.Viewer. Enhance your document viewing capabilities."
weight: 10
url: "/net/rendering-visio-documents/render-visio-figures/"
keywords:
- render visio figures .net
- groupdocs.viewer for .net
- .net visio rendering
- view visio diagrams .net

---

## Introduction

In today's digital age, document rendering plays a crucial role in various applications. Whether it is displaying documents on a website or converting them into different formats, efficient rendering is essential. **GroupDocs.Viewer for .NET** provides a robust solution for viewing and manipulating documents within .NET applications. In this tutorial, we will delve into rendering Visio figures using GroupDocs.Viewer for .NET, breaking down the process into simple steps.

## Prerequisites

Before you begin, ensure you have the following:
*   A working knowledge of C# and .NET development.
*   **.NET SDK:** Installed on your machine.
*   **GroupDocs.Viewer for .NET:** Download the library [here](https://releases.groupdocs.com/viewer/net/).
*   **IDE:** Visual Studio or any other .NET development environment.
*   **Sample Visio Document:** A Visio file (e.g., `SAMPLE.VSDX`) for rendering.

## Import Namespaces

In your C# project, start by importing the necessary namespaces:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Step 1: Rendering to HTML

To render Visio figures to HTML, follow these steps.

### 1.1. Define Output Directory and File Path Format

```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.html");
```
**Note:** Replace `"Your Document Directory"` with the actual path.

### 1.2. Initialize Viewer and Configure HTML View Options

```csharp
using (Viewer viewer = new Viewer("SAMPLE.VSDX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    
    viewer.View(options);
}
```
**Note:** Replace `"SAMPLE.VSDX"` with the path to your Visio file. The `RenderFiguresOnly` option ensures that only the figures in the Visio document are rendered.

## Step 2: Rendering to JPG

To render Visio figures to a JPG image, use the following code.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.jpg");

using (Viewer viewer = new Viewer("SAMPLE.VSDX"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    
    viewer.View(options);
}
```

## Step 3: Rendering to PNG

To render Visio figures to a PNG image, use this code.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.png");

using (Viewer viewer = new Viewer("SAMPLE.VSDX"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    
    viewer.View(options);
}
```

## Step 4: Rendering to PDF

To render Visio figures to a PDF document, use the following code.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.pdf");

using (Viewer viewer = new Viewer("SAMPLE.VSDX"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    
    viewer.View(options);
}
```

## Conclusion

In this tutorial, we have explored how to render Visio figures using GroupDocs.Viewer for .NET. By following the step-by-step guide, you can seamlessly integrate document rendering capabilities into your .NET applications, enhancing user experience and productivity.

## FAQs

### Can I customize the rendering options for Visio figures?
Yes, GroupDocs.Viewer for .NET provides extensive options for customizing rendering, including figure width, rendering only figures, and more.

### Is GroupDocs.Viewer for .NET suitable for large-scale document rendering?
Absolutely, GroupDocs.Viewer for .NET is optimized for handling large-scale document rendering efficiently.

### Does GroupDocs.Viewer support other document formats besides Visio?
Yes, GroupDocs.Viewer supports a wide range of document formats, including PDF, Microsoft Office, AutoCAD, and more.

### Can I integrate GroupDocs.Viewer into web applications?
Yes, GroupDocs.Viewer can be seamlessly integrated into web applications for document viewing and manipulation.

### Is there a trial version available for testing before purchasing?
Yes, you can get a [free trial](https://releases.groupdocs.com/) from the official website to test the capabilities of GroupDocs.Viewer for .NET.
