---
title: Load Documents from Local Disk
linktitle: Load Documents from Local Disk
second_title: GroupDocs.Viewer .NET API
description: Learn how to seamlessly render documents from your local disk using Groupdocs.Viewer for .NET. Enhance your .NET applications with efficient document.
type: docs
weight: 10
url: /net/loading-documents/loading-document-local-disk/
---
## Introduction
In today's digital age, efficient document rendering is essential for various applications. Groupdocs.Viewer for .NET offers a powerful solution for rendering documents directly from your local disk. In this tutorial, we'll guide you through the process of loading documents from your local disk using Groupdocs.Viewer for .NET. Whether you're a seasoned developer or just starting, this step-by-step guide will help you seamlessly integrate document rendering into your .NET applications.
## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites:
1. Groupdocs.Viewer for .NET: Download and install the latest version from [here](https://releases.groupdocs.com/viewer/net/).
2. .NET Development Environment: Make sure you have a working .NET development environment set up on your system.
3. Local Documents: Have the documents you want to render stored locally on your disk.

## Import Namespaces
Firstly, let's import the necessary namespaces to access the functionalities of Groupdocs.Viewer for .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Step 1: Load Documents from Local Disk
Begin by setting up the output directory where the rendered HTML pages will be saved.
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Step 2: Initialize Viewer and Render Documents
Initialize the Viewer object with the document's path and render it using HTML view options.
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## Step 3: Display Output
Once rendering is complete, display a message indicating the successful rendering of the source document and the location of the output files.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion
Congratulations! You've successfully learned how to load documents from your local disk using Groupdocs.Viewer for .NET. This powerful tool opens up a world of possibilities for document rendering within your .NET applications.
## FAQ's
### Can I render documents of different formats using Groupdocs.Viewer for .NET?
Yes, Groupdocs.Viewer for .NET supports a wide range of document formats including DOCX, PDF, XLSX, PPTX, and more.
### Is Groupdocs.Viewer for .NET compatible with all .NET frameworks?
Groupdocs.Viewer for .NET is compatible with most .NET frameworks including .NET Core, .NET Framework, and .NET Standard.
### Can I customize the rendering options for my documents?
Absolutely! Groupdocs.Viewer for .NET provides extensive customization options allowing you to tailor the rendering process to your specific requirements.
### Is there a trial version available for Groupdocs.Viewer for .NET?
Yes, you can download a free trial version from [here](https://releases.groupdocs.com/).
### Where can I find support or additional resources for Groupdocs.Viewer for .NET?
For support and additional resources, visit the Groupdocs.Viewer for .NET [forum](https://forum.groupdocs.com/c/viewer/9).
