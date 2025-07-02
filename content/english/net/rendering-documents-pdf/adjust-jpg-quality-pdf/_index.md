---
title: "Adjust JPG Image Quality in Rendered PDF with .NET | GroupDocs.Viewer"
description: "Learn how to adjust the quality of JPG images when rendering documents to PDF in your .NET applications using GroupDocs.Viewer. Enhance your document viewing experience."
weight: 11
url: "/net/rendering-documents-pdf/adjust-jpg-quality-pdf/"
keywords:
  - adjust jpg quality pdf .net
  - groupdocs.viewer for .net
  - .net pdf rendering
  - image quality pdf .net
---

## Introduction

In this tutorial, we will learn how to adjust the quality of JPG images when rendering a document to PDF using **GroupDocs.Viewer for .NET**. This powerful library allows you to view and manipulate various document formats in your .NET applications seamlessly.

![Adjust JPG Image Quality in Rendered PDF with GroupDocs.Viewer .NET](/viewer/rendering-documents-pdf/adjust-jpg-image-quality-in-rendered-pdf.png)

## Prerequisites

Before you begin, ensure you have the following:

- A working knowledge of C# and .NET development.
- **.NET SDK:** Installed on your machine.
- **GroupDocs.Viewer for .NET:** Download the library [here](https://releases.groupdocs.com/viewer/net/).
- **IDE:** Visual Studio or any other .NET development environment.
- **Sample Document:** A document file (e.g., PPTX, DOCX) containing JPG images.

## Import Namespaces

First, you need to import the necessary namespaces into your C# code. This allows your application to access the functionalities provided by GroupDocs.Viewer for .NET.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Step 1: Define Output Directory and File Path

Set the output directory where the rendered PDF will be saved and define the full path for the output PDF file.

```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output_jpg_quality.pdf");
```

**Note:** Replace `"Your Document Directory"` with the actual path.

## Step 2: Initialize Viewer and Configure PDF View Options

Instantiate the `Viewer` class with the path of the document containing JPG images. Then, configure the `PdfViewOptions` to adjust the JPG image quality.

```csharp
using (Viewer viewer = new Viewer("SAMPLE.pptx"))
{
    PdfViewOptions options = new PdfViewOptions(outputFilePath);
    options.JpgQuality = 50; // Set JPG quality to 50%
    
    // The rendering process will go here
}
```

**Note:** Replace `"SAMPLE.pptx"` with the path to your document. The `JpgQuality` property is an integer value between 0 and 100, where 100 is the best quality.

## Step 3: Render the Document with Adjusted JPG Quality

Invoke the `View` method of the `Viewer` object, passing the configured `PdfViewOptions`.

```csharp
// Inside the using block
viewer.View(options);
```

## Step 4: Display Success Message

After rendering the PDF successfully, display a message to notify the user about the completion and the location of the output file.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion

In this tutorial, we have explored how to adjust the JPG image quality when rendering a document to PDF using GroupDocs.Viewer for .NET. By following these steps, you can effectively control the quality of images in your rendered PDF documents, ensuring an optimal visual representation.

## FAQs

### Can I adjust the image quality for other formats besides JPG?

Yes, GroupDocs.Viewer for .NET supports various image formats, and you can adjust the quality for PNG, TIFF, and other formats as well.

### Is GroupDocs.Viewer for .NET compatible with all versions of the .NET framework?

GroupDocs.Viewer for .NET is compatible with multiple versions of the .NET framework, including .NET Core and .NET Standard.

### Can I render documents asynchronously using GroupDocs.Viewer for .NET?

Yes, GroupDocs.Viewer for .NET provides asynchronous rendering capabilities, allowing you to enhance the performance of your applications.

### Is there a trial version available for GroupDocs.Viewer for .NET?

Yes, you can access a [free trial](https://releases.groupdocs.com/) of GroupDocs.Viewer for .NET from the official website.

### How can I get support or assistance with GroupDocs.Viewer for .NET?

You can visit the [GroupDocs.Viewer forum](https://forum.groupdocs.com/c/viewer/9) to get help, ask questions, and interact with other users and developers.