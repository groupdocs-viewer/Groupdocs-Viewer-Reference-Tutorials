---
title: "Reorder Pages in Documents with .NET | GroupDocs.Viewer"
description: "Learn how to reorder pages in a document when rendering to PDF in your .NET applications using GroupDocs.Viewer. A step-by-step tutorial for seamless document management."
weight: 19
url: "/net/rendering-options/reorder-pages/"
keywords:
  - reorder pages .net
  - groupdocs.viewer for .net
  - .net document management
  - rearrange pdf pages .net
---

## Introduction

In the world of .NET development, managing and manipulating documents efficiently is crucial. **GroupDocs.Viewer for .NET** provides a powerful solution for viewing various document formats within your applications. One of the essential tasks developers often encounter is reordering pages within a document. Whether you are working with PDFs, Word documents, or other formats, being able to rearrange pages can streamline workflows and enhance user experience. In this tutorial, we will delve into how to reorder pages in a document using GroupDocs.Viewer for .NET.

## Prerequisites

Before you begin, ensure you have the following:

- A working knowledge of C# and .NET development.
- **.NET SDK:** Installed on your machine.
- **GroupDocs.Viewer for .NET:** Download the library [here](https://releases.groupdocs.com/viewer/net/).
- **IDE:** Visual Studio or any other .NET development environment.
- **Sample Document:** A document file (e.g., PDF, DOCX) for testing purposes.

## Import Namespaces

In your .NET application, import the necessary namespaces required for utilizing GroupDocs.Viewer functionality.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Step 1: Define Output Directory and File Path

First, define the directory where you want the reordered document to be saved and the full path for the output file.

```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```

**Note:** Replace `"Your Document Directory"` with the actual path.

## Step 2: Initialize Viewer and Configure PDF View Options

Instantiate the `Viewer` class with the path to your input document. Then, specify the `PdfViewOptions` for rendering the document as a PDF.

```csharp
using (Viewer viewer = new Viewer("YOUR_SAMPLE_FILE.pdf"))
{
    PdfViewOptions options = new PdfViewOptions(outputFilePath);
    
    // The reordering logic will go here
}
```

**Note:** Replace `"YOUR_SAMPLE_FILE.pdf"` with the path to your document.

## Step 3: Define Page Order and Render

Pass the page numbers in the desired order to the `View` method. For example, to swap the first and second pages, you would pass `2, 1`.

```csharp
// Inside the using block
viewer.View(options, 2, 1);
```

## Step 4: Display Success Message

Finally, inform the user that the document has been rendered successfully.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion

In conclusion, rearranging pages in a document is made simple with GroupDocs.Viewer for .NET. By following the steps outlined in this tutorial, you can efficiently manage document pages within your .NET applications, enhancing usability and productivity.

## FAQs

### Can GroupDocs.Viewer for .NET handle multiple document formats?

Yes, GroupDocs.Viewer supports a wide range of document formats, including PDF, DOCX, XLSX, PPTX, and more.

### Is there a free trial available for GroupDocs.Viewer for .NET?

Yes, you can access a [free trial](https://releases.groupdocs.com/) of GroupDocs.Viewer from the official website.

### Does GroupDocs.Viewer for .NET require a permanent license for development?

While a [temporary license](https://purchase.groupdocs.com/temporary-license/) is available for testing and development, a permanent license is required for production use.

### Can I customize the appearance of the rendered document using GroupDocs.Viewer for .NET?

Yes, GroupDocs.Viewer provides various options for customizing the rendering output, including page rotation, watermarking, and more.

### Where can I find further assistance or support for GroupDocs.Viewer for .NET?

You can visit the [GroupDocs.Viewer forum](https://forum.groupdocs.com/c/viewer/9) for any inquiries or support needs.