---
title: Rendering Numbers
linktitle: Rendering Numbers
second_title: GroupDocs.Viewer .NET API
description: Explore the power of Groupdocs.Viewer for .NET in rendering Numbers files seamlessly. Convert to HTML, JPG, PNG, and PDF effortlessly.
weight: 15
url: /net/spreadsheet-rendering-options/rendering-numbers/
---
## Introduction
Welcome to this step-by-step tutorial on rendering Numbers files using Groupdocs.Viewer for .NET. Whether you're a seasoned developer or a beginner, this guide will walk you through the process of converting Numbers documents into various formats. Groupdocs.Viewer for .NET is a powerful tool that allows you to seamlessly integrate document viewing capabilities into your .NET applications.
## Prerequisites
Before diving into the tutorial, make sure you have the following prerequisites in place:
- A working knowledge of C# and .NET development.
- Groupdocs.Viewer for .NET library installed. You can download it [here](https://releases.groupdocs.com/viewer/net/).
- Your document directory path where the output files will be saved.
## Import Namespaces
In your C# project, ensure you import the necessary namespaces to use the Groupdocs.Viewer library:
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Step 1: Set Up Output Directory
Before you start rendering, define the output directory where the converted files will be saved. Replace "Your Document Directory" with the actual path:
```csharp
string outputDirectory = "Your Document Directory";
```
## Step 2: Render to Multi-Pages HTML
Use the following code to convert the Numbers file to multi-pages HTML:
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## Step 3: Render to JPG
Convert the Numbers file to JPG format with the following code:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Step 4: Render to PNG
Transform the Numbers file into PNG format using the following code:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## Step 5: Render to PDF
Lastly, convert the Numbers file to PDF format using the following code:
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
Congratulations! You've successfully rendered Numbers files into various formats using Groupdocs.Viewer for .NET.
## Conclusion
In this tutorial, we covered the basics of rendering Numbers files using Groupdocs.Viewer for .NET. This powerful library provides seamless integration for viewing and converting documents in your .NET applications.
## FAQs
### Can I use Groupdocs.Viewer for .NET with other document types?
Yes, Groupdocs.Viewer supports a wide range of document formats, including Word, Excel, PDF, and more.
### Is a temporary license available for testing purposes?
Yes, you can obtain a temporary license [here](https://purchase.groupdocs.com/temporary-license/) for testing.
### Where can I find support for Groupdocs.Viewer for .NET?
Visit the [Groupdocs.Viewer Forum](https://forum.groupdocs.com/c/viewer/9) for assistance and discussions.
### How do I purchase the full version of Groupdocs.Viewer for .NET?
You can purchase the full version [here](https://purchase.groupdocs.com/buy).
### Is there a free trial version available?
Yes, you can explore the free trial version [here](https://releases.groupdocs.com/).
