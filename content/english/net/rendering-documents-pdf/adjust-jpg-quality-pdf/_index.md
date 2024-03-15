---
title: Adjust JPG Image Quality in Rendered PDF
linktitle: Adjust JPG Image Quality in Rendered PDF
second_title: GroupDocs.Viewer .NET API
description: Learn how to adjust JPG image quality in rendered PDF documents using GroupDocs.Viewer for .NET. Enhance your document viewing experience.
type: docs
weight: 11
url: /net/rendering-documents-pdf/adjust-jpg-quality-pdf/
---
## Introduction
In this tutorial, we'll learn how to adjust the quality of JPG images when rendering a PDF using GroupDocs.Viewer for .NET. This powerful library allows you to view and manipulate various document formats in your .NET applications seamlessly.
## Prerequisites
Before diving into this tutorial, ensure you have the following prerequisites:
1. GroupDocs.Viewer for .NET Library: Make sure you have downloaded and installed the GroupDocs.Viewer for .NET library. You can download it from [here](https://releases.groupdocs.com/viewer/net/).
2. Development Environment: Have a working development environment set up with .NET framework installed.

## Import Namespaces
Firstly, you need to import the necessary namespaces to your C# code. This allows your application to access the functionalities provided by GroupDocs.Viewer for .NET.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Step 1: Define Output Directory and File Path
Set the output directory where the rendered PDF will be saved and define the file path for the output PDF file.
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## Step 2: Render PDF with Adjusted JPG Image Quality
Instantiate the Viewer class and pass the path of the document containing JPG images. Then, configure the PDF rendering options to adjust the JPG image quality.
```csharp
using (Viewer viewer = new Viewer(TestFiles.JPG_IMAGE_PPTX))
{               
    PdfViewOptions options = new PdfViewOptions(filePath);
    viewer.View(options);
}
```
## Step 3: Display Success Message
After rendering the PDF successfully, display a message to notify the user about the completion and the location of the output file.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion
In this tutorial, we've explored how to adjust the JPG image quality when rendering a PDF using GroupDocs.Viewer for .NET. By following these steps, you can effectively control the quality of images in your rendered PDF documents, ensuring optimal visual representation.
## FAQ's
### Can I adjust the image quality for other formats besides JPG?
Yes, GroupDocs.Viewer for .NET supports various image formats, and you can adjust the quality for PNG, TIFF, and other formats as well.
### Is GroupDocs.Viewer for .NET compatible with all versions of .NET framework?
GroupDocs.Viewer for .NET is compatible with multiple versions of the .NET framework, including .NET Core and .NET Standard.
### Can I render documents asynchronously using GroupDocs.Viewer for .NET?
Yes, GroupDocs.Viewer for .NET provides asynchronous rendering capabilities, allowing you to enhance the performance of your applications.
### Is there a trial version available for GroupDocs.Viewer for .NET?
Yes, you can access a free trial version of GroupDocs.Viewer for .NET from [here](https://releases.groupdocs.com/).
### How can I get support or assistance with GroupDocs.Viewer for .NET?
You can visit the GroupDocs.Viewer for .NET forum [here](https://forum.groupdocs.com/c/viewer/9) to get help, ask questions, and interact with other users and developers.
