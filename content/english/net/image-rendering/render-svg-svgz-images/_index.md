---
title: Render SVG and SVGZ Images
linktitle: Render SVG and SVGZ Images
second_title: GroupDocs.Viewer .NET API
description: Learn how to render SVG and SVGZ images using GroupDocs.Viewer for .NET. Convert vector graphics into HTML, JPG, PNG, and PDF effortlessly.
type: docs
weight: 16
url: /net/image-rendering/render-svg-svgz-images/
---
## Introduction
In this tutorial, we will guide you through the process of rendering SVG and SVGZ images using GroupDocs.Viewer for .NET. GroupDocs.Viewer for .NET is a powerful document rendering API that enables developers to render various document formats in their .NET applications. SVG and SVGZ are popular image formats used for vector graphics, and with GroupDocs.Viewer for .NET, you can easily render them into different output formats such as HTML, JPG, PNG, and PDF.
## Prerequisites
Before we begin, make sure you have the following prerequisites installed and set up:
1. GroupDocs.Viewer for .NET: Download and install GroupDocs.Viewer for .NET from [here](https://releases.groupdocs.com/viewer/net/).
2. Development Environment: Ensure you have a working development environment for .NET development, such as Visual Studio.
3. Sample SVGZ File: Have a sample SVGZ file ready for testing.

## Import Namespaces
Before we dive into the code, let's import the necessary namespaces:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## Step 1: Render SVGZ to HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## Step 2: Render SVGZ to JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## Step 3: Render SVGZ to PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Step 4: Render SVGZ to PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## Conclusion
In this tutorial, we have learned how to render SVG and SVGZ images using GroupDocs.Viewer for .NET. With just a few simple steps, you can convert SVGZ images into various output formats like HTML, JPG, PNG, and PDF, making them accessible and viewable in different environments.
## FAQ's
### Can GroupDocs.Viewer render other image formats?
Yes, GroupDocs.Viewer supports rendering various image formats including PNG, JPEG, BMP, TIFF, GIF, and more.
### Is GroupDocs.Viewer compatible with .NET Core?
Yes, GroupDocs.Viewer is compatible with both .NET Framework and .NET Core.
### Can I customize the rendering options?
Yes, GroupDocs.Viewer provides extensive rendering options allowing you to customize the output according to your requirements.
### Does GroupDocs.Viewer require any third-party dependencies?
No, GroupDocs.Viewer is a standalone API and does not require any third-party dependencies for rendering documents.
### Is there a trial version available for testing?
Yes, you can download a free trial version of GroupDocs.Viewer from [here](https://releases.groupdocs.com/) to evaluate its features before making a purchase.
