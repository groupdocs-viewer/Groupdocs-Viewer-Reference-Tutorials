---
title: Reorder Pages in Document
linktitle: Reorder Pages in Document
second_title: GroupDocs.Viewer .NET API
description: Learn how to reorder pages in a document using GroupDocs.Viewer for .NET. Follow our step-by-step tutorial for seamless document management.
type: docs
weight: 19
url: /net/rendering-options/reorder-pages/
---
## Introduction
In the world of .NET development, managing and manipulating documents efficiently is crucial. GroupDocs.Viewer for .NET provides a powerful solution for viewing various document formats within your applications. One of the essential tasks developers often encounter is reordering pages within a document. Whether you're working with PDFs, Word documents, or other formats, being able to rearrange pages can streamline workflows and enhance user experience. In this tutorial, we'll delve into how to reorder pages in a document using GroupDocs.Viewer for .NET.
## Prerequisites
Before diving into the tutorial, make sure you have the following prerequisites set up:
### 1. Install GroupDocs.Viewer for .NET
Ensure you have GroupDocs.Viewer for .NET installed in your development environment. You can download it from [here](https://releases.groupdocs.com/viewer/net/) and follow the installation instructions provided in the documentation.
### 2. Set Up Your Development Environment
Make sure you have a working .NET development environment set up on your machine, including Visual Studio or any other preferred IDE.
### 3. Obtain Sample Documents
Have some sample documents ready for testing purposes. You can use any document format supported by GroupDocs.Viewer, such as PDF, DOCX, XLSX, etc.

## Import Namespaces
In your .NET application, import the necessary namespaces required for utilizing GroupDocs.Viewer functionality.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Step 1: Specify Output Directory
Define the directory where you want the reordered document to be saved.
```csharp
string outputDirectory = "Your Document Directory";
```
## Step 2: Define Output File Path
Combine the output directory with the desired file name for the reordered document.
```csharp
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
## Step 3: Instantiate Viewer Object
Create an instance of the Viewer class by providing the path to the input document.
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    // Code for reordering pages will go here
}
```
## Step 4: Set PDF View Options
Specify the options for rendering the document as PDF and define the output file path.
```csharp
PdfViewOptions options = new PdfViewOptions(outputFilePath);
```
## Step 5: Define Page Order
Pass the page numbers in the desired order for rendering.
```csharp
viewer.View(options, 2, 1);
```
## Step 6: Display Success Message
Inform the user that the document has been rendered successfully.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion
In conclusion, rearranging pages in a document is made simple with GroupDocs.Viewer for .NET. By following the steps outlined in this tutorial, you can efficiently manage document pages within your .NET applications, enhancing usability and productivity.
## FAQ's
### Can GroupDocs.Viewer for .NET handle multiple document formats?
Yes, GroupDocs.Viewer supports a wide range of document formats, including PDF, DOCX, XLSX, PPTX, and more.
### Is there a free trial available for GroupDocs.Viewer for .NET?
Yes, you can access a free trial of GroupDocs.Viewer from [here](https://releases.groupdocs.com/).
### Does GroupDocs.Viewer for .NET require a permanent license for development?
While a temporary license is available for testing and development, a permanent license is required for production use. You can obtain a temporary license [here](https://purchase.groupdocs.com/temporary-license/).
### Can I customize the appearance of the rendered document using GroupDocs.Viewer for .NET?
Yes, GroupDocs.Viewer provides various options for customizing the rendering output, including page rotation, watermarking, and more.
### Where can I find further assistance or support for GroupDocs.Viewer for .NET?
You can visit the GroupDocs.Viewer forum [here](https://forum.groupdocs.com/c/viewer/9) for any inquiries or support needs.
