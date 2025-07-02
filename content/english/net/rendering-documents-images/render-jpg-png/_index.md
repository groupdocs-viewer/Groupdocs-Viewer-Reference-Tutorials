---
title: "Render Documents to JPG or PNG Images in .NET | GroupDocs.Viewer"
description: "Learn how to render documents to JPG or PNG images in your .NET applications using GroupDocs.Viewer. Enhance your document viewing experience."
weight: 10
url: "/net/rendering-documents-images/render-jpg-png/"
keywords:
  - render document to jpg .net
  - render document to png .net
  - groupdocs.viewer for .net
  - .net document rendering
---

## Introduction

In the world of .NET development, handling documents efficiently is essential for various applications. Whether you are building a document management system, an e-commerce platform, or a content-rich application, the ability to view documents seamlessly is crucial. This is where **GroupDocs.Viewer for .NET** comes into play, offering a comprehensive solution for rendering documents to various formats such as JPG and PNG.

![Render Document to JPG PNG with GroupDocs.Viewer .NET](/viewer/rendering-documents-images/render-document-to-jpg-png.png)

## Prerequisites

Before you begin, ensure you have the following:

- A working knowledge of C# and .NET development.
- **.NET SDK:** Installed on your machine.
- **GroupDocs.Viewer for .NET:** Download the library [here](https://releases.groupdocs.com/viewer/net/).
- **IDE:** Visual Studio or any other .NET development environment.
- **Document Files:** Have the document files ready that you want to render (e.g., DOCX, PDF, PPT).

## Import Namespaces

To get started with rendering documents using GroupDocs.Viewer for .NET, you need to import the necessary namespaces into your project. This allows you to access the functionalities provided by the library.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Rendering a document to JPG or PNG format is a straightforward process with GroupDocs.Viewer for .NET. Below is a step-by-step guide to help you achieve this.

## Step 1: Define Output Directory and Page File Path Format

First, define the directory where you want the rendered pages to be saved and the format for the file paths of each rendered page.

```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```

**Note:** Replace `"Your Document Directory"` with the actual path.

## Step 2: Initialize Viewer and Configure Rendering Options

Create an instance of the `Viewer` class by providing the path to the document file you want to render. Then, specify the rendering options. For JPG rendering, use `JpgViewOptions`.

```csharp
using (Viewer viewer = new Viewer("SAMPLE.docx"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    // The rendering process will go here
}
```

**Note:** Replace `"SAMPLE.docx"` with the path to your document.

## Step 3: Render the Document

Invoke the `View` method of the `Viewer` object and pass the rendering options created earlier.

```csharp
// Inside the using block
viewer.View(options);
```

## Step 4: Display Output Results

Once the rendering process is complete, you can inform the user about the successful rendering and provide the directory where the rendered pages are saved.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

To render to PNG, simply replace `JpgViewOptions` with `PngViewOptions` and change the file extension in the `pageFilePathFormat`.

```csharp
string pngPageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
PngViewOptions pngOptions = new PngViewOptions(pngPageFilePathFormat);
viewer.View(pngOptions);
```

## Conclusion

In conclusion, GroupDocs.Viewer for .NET offers a powerful solution for rendering documents to various formats, including JPG and PNG. By following the steps outlined in this tutorial, you can seamlessly integrate document rendering functionality into your .NET applications, enhancing user experience and productivity.

## FAQs

### Can I render documents other than DOCX using GroupDocs.Viewer for .NET?

Yes, GroupDocs.Viewer supports a wide range of document formats, including PDF, PPT, XLS, and more.

### Is there a free trial available for GroupDocs.Viewer for .NET?

Yes, you can download a [free trial](https://releases.groupdocs.com/) from the official website.

### How can I obtain a temporary license for evaluation purposes?

You can request a [temporary license](https://purchase.groupdocs.com/temporary-license/) from the GroupDocs website.

### Where can I find documentation for GroupDocs.Viewer for .NET?

Detailed documentation is available [here](https://reference.groupdocs.com/viewer/net/).

### Where can I get support or ask questions related to GroupDocs.Viewer for .NET?

You can visit the [support forum](https://forum.groupdocs.com/c/viewer/9) for assistance.