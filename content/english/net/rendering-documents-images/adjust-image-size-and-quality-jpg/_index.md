---
title: "Adjust Image Size and Quality (JPG) in .NET | GroupDocs.Viewer"
description: "Learn how to adjust the size and quality of JPG images when rendering documents in your .NET applications using GroupDocs.Viewer. Optimize your document viewing experience."
weight: 11
url: "/net/rendering-documents-images/adjust-image-size-and-quality-jpg/"
keywords:
- adjust jpg size quality .net
- groupdocs.viewer for .net
- .net image rendering
- optimize jpg rendering

---

## Introduction

**GroupDocs.Viewer for .NET** is a powerful library that enables developers to seamlessly integrate document viewing functionality into their .NET applications. One common requirement in document viewing applications is the ability to adjust the size and quality of images, particularly when dealing with JPEG (JPG) images. In this tutorial, we will walk you through the process of adjusting image size and quality using GroupDocs.Viewer for .NET.

## Prerequisites

Before you begin, ensure you have the following:
*   A basic understanding of C# programming.
*   **Visual Studio:** Installed on your system.
*   **GroupDocs.Viewer for .NET:** Download the library [here](https://releases.groupdocs.com/viewer/net/).
*   **Sample Document:** A document file (e.g., DOCX, PDF) for testing.

## Import Namespaces

First, you need to import the necessary namespaces into your C# code. These namespaces provide access to the classes and methods required for working with GroupDocs.Viewer.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Now, let's break down the example code into multiple steps for a better understanding.

## Step 1: Define Output Directory and Page File Path Format

Specify the directory where the rendered images will be saved and define the format for the file path of each page image.

```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
**Note:** Replace `"Your Document Directory"` with the actual path.

## Step 2: Initialize Viewer and Configure JPG View Options

Initialize the `Viewer` object with the path to the document to be viewed. Then, create an instance of `JpgViewOptions` and set the desired width and height for the JPEG images.

```csharp
using (Viewer viewer = new Viewer("SAMPLE.docx"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    
    // The rendering process will go here
}
```
**Note:** Replace `"SAMPLE.docx"` with the path to your document.

## Step 3: Render the Source Document

Finally, call the `View` method of the `Viewer` object, passing the configured `JpgViewOptions`.

```csharp
// Inside the using block
viewer.View(options);
```

## Step 4: Display the Output Path

Print a message indicating the successful rendering of the source document and the location where the output images are saved.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion

In this tutorial, we have learned how to adjust the size and quality of JPEG images using GroupDocs.Viewer for .NET. By following the steps outlined above, you can easily incorporate this functionality into your .NET applications, providing users with an optimized image viewing experience.

## FAQs

### Can I adjust the image quality as well?
Yes, you can adjust the image quality by setting the `Quality` property in the `JpgViewOptions`. The value is an integer between 0 and 100.

### What document formats are supported by GroupDocs.Viewer for .NET?
GroupDocs.Viewer for .NET supports a wide range of document formats, including DOCX, PDF, PPTX, XLSX, and more.

### Is GroupDocs.Viewer for .NET compatible with .NET Core?
Yes, GroupDocs.Viewer for .NET is compatible with .NET Core along with the traditional .NET Framework.

### Can I customize the output file naming format?
Yes, you can customize the output file naming format by modifying the `pageFilePathFormat` variable in the code.

### Does GroupDocs.Viewer for .NET support document annotations?
Yes, GroupDocs.Viewer for .NET provides comprehensive support for document annotations, including text highlighting, underlining, and commenting.
