---
title: Enable Layered Rendering in PDF
linktitle: Enable Layered Rendering in PDF
second_title: GroupDocs.Viewer .NET API
description: Learn how to enable layered rendering in PDF documents using GroupDocs.Viewer for .NET. Enhance document viewing experience effortlessly.
weight: 15
url: /net/pdf-rendering-options/enable-layered-rendering-pdf/
---
## Introduction
In this tutorial, we'll delve into the process of enabling layered rendering in PDF documents using GroupDocs.Viewer for .NET. Layered rendering allows for enhanced document display and manipulation, providing users with a more interactive viewing experience.
## Prerequisites
Before we begin, ensure you have the following prerequisites:
1. GroupDocs.Viewer for .NET: Make sure you have installed the necessary package or library for using GroupDocs.Viewer for .NET in your project.
2. Visual Studio: You should have Visual Studio installed on your system for coding and executing the provided examples.
3. Basic Understanding of C#: This tutorial assumes familiarity with C# programming language syntax and concepts.

## Import Namespaces
Start by importing the required namespaces into your project:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Step 1: Define Output Directory
```csharp
string outputDirectory = "Your Document Directory";
```
Ensure to specify the directory path where you want the rendered output to be saved.
## Step 2: Define Page File Path Format
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
This step sets the format for the file paths of individual pages in the rendered output. `{0}` is a placeholder for the page number.
## Step 3: Enable Layered Rendering
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
Here, we create a `Viewer` object and specify the PDF document to be processed. We then configure `HtmlViewOptions` with the defined page file path format. By setting `EnableLayeredRendering` property to `true` in `PdfOptions`, we enable layered rendering for the PDF document.
## Step 4: Display Output Directory
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Finally, we print a message indicating the successful rendering of the source document and prompt the user to check the output in the specified directory.

## Conclusion
Enabling layered rendering in PDF documents using GroupDocs.Viewer for .NET enhances document viewing capabilities, providing users with a richer and more interactive experience. By following the steps outlined in this tutorial, you can seamlessly integrate this feature into your .NET applications.
## FAQ's
### What is layered rendering in PDF documents?
Layered rendering allows for the separation and manipulation of different components within a PDF document, enabling interactive viewing and enhanced user experience.
### Can I customize the output directory for rendered documents?
Yes, you can specify any directory path for the output as per your requirements.
### Does GroupDocs.Viewer support other file formats besides PDF?
Yes, GroupDocs.Viewer supports a wide range of document formats including Word, Excel, PowerPoint, and more.
### Is GroupDocs.Viewer compatible with .NET Core?
Yes, GroupDocs.Viewer is compatible with both .NET Framework and .NET Core environments.
### Where can I find additional support or assistance?
You can visit the GroupDocs.Viewer forum for any queries or assistance regarding the viewer library.
