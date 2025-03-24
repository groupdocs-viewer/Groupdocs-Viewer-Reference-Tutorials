---
title: Adjust Image Quality in PDF
linktitle: Adjust Image Quality in PDF
second_title: GroupDocs.Viewer .NET API
description: Learn how to adjust image quality in PDF documents using GroupDocs.Viewer for .NET. Follow our step-by-step tutorial for seamless integration.
weight: 10
url: /net/pdf-rendering-options/adjust-image-quality-pdf/
---

# Adjust Image Quality in PDF

## Introduction
GroupDocs.Viewer for .NET is a powerful library that allows developers to integrate document rendering capabilities into their .NET applications effortlessly. One of the key features of this library is the ability to adjust image quality when rendering PDF documents. In this tutorial, we'll walk you through the process of adjusting image quality step by step using GroupDocs.Viewer for .NET.
## Prerequisites
Before we get started, ensure you have the following prerequisites:
1. Basic knowledge of C# programming.
2. Visual Studio installed on your system.
3. GroupDocs.Viewer for .NET library downloaded and installed. You can download it from [here](https://releases.groupdocs.com/viewer/net/).

## Import Namespaces
First, you need to import the necessary namespaces to work with GroupDocs.Viewer for .NET:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Step 1: Define Output Directory
```csharp
string outputDirectory = "Your Document Directory";
```
Replace `"Your Document Directory"` with the path where you want to save the rendered HTML pages.
## Step 2: Define Page File Path Format
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
This line defines the format for the file path of each rendered HTML page. `{0}` is a placeholder for the page number.
## Step 3: Adjust Image Quality
```csharp
using (Viewer viewer = new Viewer("Your PDF File Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.ImageQuality = ImageQuality.Medium;
    viewer.View(options);
}
```
Replace `"Your PDF File Path"` with the path to your PDF document.
## Step 4: Display Output Path
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
This line displays the path where the rendered HTML pages are saved.

## Conclusion
In this tutorial, we've learned how to adjust image quality when rendering PDF documents using GroupDocs.Viewer for .NET. By following the simple steps outlined above, you can easily customize the image quality according to your requirements.
## FAQ's
### Can I adjust image quality for other document formats besides PDF?
Yes, GroupDocs.Viewer for .NET supports various document formats, and you can adjust image quality for most of them.
### What are the available image quality options?
GroupDocs.Viewer for .NET provides options for Low, Medium, and High image quality.
### Is there a way to preview the document before rendering it with adjusted image quality?
Yes, you can use GroupDocs.Viewer for .NET to generate document previews with different image quality settings.
### Does GroupDocs.Viewer for .NET require a license for commercial use?
Yes, you need to obtain a license for commercial usage. You can purchase a license from [here](https://purchase.groupdocs.com/buy).
### Where can I get support for GroupDocs.Viewer for .NET?
You can get support from the GroupDocs.Viewer forum [here](https://forum.groupdocs.com/c/viewer/9).
