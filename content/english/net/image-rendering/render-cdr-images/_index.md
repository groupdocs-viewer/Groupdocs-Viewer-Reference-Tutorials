---
title: Render CDR Images
linktitle: Render CDR Images
second_title: GroupDocs.Viewer .NET API
description: Learn how to render CDR images to HTML, JPG, PNG, and PDF using GroupDocs.Viewer for .NET. Easily convert CorelDRAW files with this tutorial.
type: docs
weight: 12
url: /net/image-rendering/render-cdr-images/
---
## Introduction
In this tutorial, we will guide you through the process of rendering CDR (CorelDRAW) images using GroupDocs.Viewer for .NET. CDR is a file format primarily associated with CorelDRAW, a vector graphics editor. With GroupDocs.Viewer, you can easily convert CDR files into various formats like HTML, JPG, PNG, and PDF.
## Prerequisites
Before you begin, ensure that you have the following prerequisites:
1. GroupDocs.Viewer for .NET: Make sure you have installed GroupDocs.Viewer for .NET. You can download it from [here](https://releases.groupdocs.com/viewer/net/).
2. Document Directory: Prepare a directory where you want to save the rendered images.
3. Basic Knowledge of C#: Familiarity with C# programming language is necessary to understand the code examples.
## Import Namespaces
Before diving into the code examples, import the necessary namespaces in your C# file:
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Now, let's break down each example into multiple steps:
## Rendering to HTML
1. Define the output directory where you want to save the rendered HTML files:
```csharp
string outputDirectory = "Your Document Directory";
```
2. Specify the file path format for HTML files:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. Use the Viewer class to render the CDR file to HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Rendering to JPG
1. Define the file path format for JPG files:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. Use the Viewer class to render the CDR file to JPG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Rendering to PNG
1. Define the file path format for PNG files:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. Use the Viewer class to render the CDR file to PNG:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## Rendering to PDF
1. Define the file path format for PDF:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. Use the Viewer class to render the CDR file to PDF:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3. Optionally, you can specify rendering options or render specific pages by passing additional parameters to the `viewer.View()` method.
## Conclusion
Rendering CDR images to various formats like HTML, JPG, PNG, and PDF using GroupDocs.Viewer for .NET is a straightforward process. By following the steps outlined in this tutorial, you can efficiently convert CDR files into different formats based on your requirements.
## FAQ's
### Is GroupDocs.Viewer for .NET compatible with all versions of CDR files?
GroupDocs.Viewer for .NET supports rendering of CDR files created by different versions of CorelDRAW.
### Can I customize the output of rendered files?
Yes, GroupDocs.Viewer for .NET provides various options to customize the output, such as adjusting image quality, setting watermark, etc.
### Does GroupDocs.Viewer for .NET require any external dependencies?
No, GroupDocs.Viewer for .NET is a standalone library and does not require any external dependencies for rendering documents.
### Is there a trial version available for GroupDocs.Viewer for .NET?
Yes, you can download a free trial version of GroupDocs.Viewer for .NET from [here](https://releases.groupdocs.com/).
### Where can I get support for GroupDocs.Viewer for .NET?
You can get support from the GroupDocs.Viewer community forum [here](https://forum.groupdocs.com/c/viewer/9).
