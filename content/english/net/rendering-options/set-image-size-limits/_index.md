---
title: "Set Image Size Limits in .NET | GroupDocs.Viewer"
description: "Learn how to set image size limits when rendering documents to JPG in your .NET applications using GroupDocs.Viewer, enhancing document viewing experiences."
weight: 21
url: "/net/rendering-options/set-image-size-limits/"
keywords:
- set image size limits .net
- groupdocs.viewer for .net
- .net document rendering
- limit image width .net

---

## Introduction

**GroupDocs.Viewer for .NET** is a powerful tool designed to facilitate seamless document viewing within .NET applications. With its robust features and intuitive interface, developers can effortlessly integrate document viewing capabilities into their projects, enhancing user experience and productivity. In this tutorial, we will explore how to set image size limits using GroupDocs.Viewer for .NET, ensuring optimal display of documents while maintaining performance and efficiency.

## Prerequisites

Before you begin, ensure you have the following:
*   A working knowledge of C# and .NET development.
*   **.NET SDK:** Installed on your machine.
*   **GroupDocs.Viewer for .NET:** Download the library [here](https://releases.groupdocs.com/viewer/net/).
*   **IDE:** Visual Studio or any other .NET development environment.
*   **Sample Document:** A document file (e.g., DOCX, PDF) for testing.

## Import Namespaces

Before proceeding with the implementation, it is essential to import the required namespaces to access the functionalities of GroupDocs.Viewer for .NET effectively.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Step 1: Define Output Directory and File Path

First, define the directory where you want the rendered image to be saved and the full path for the output file.

```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "result_image_size_limit.jpg");
```
**Note:** Replace `"Your Document Directory"` with the actual path.

## Step 2: Initialize Viewer and Configure JPG View Options

Initialize a `Viewer` object with the path to your document. Then, configure the `JpgViewOptions` to set the maximum width for the rendered image.

```csharp
using (Viewer viewer = new Viewer("SAMPLE.DOCX"))
{
    JpgViewOptions options = new JpgViewOptions(outputFilePath);
    options.MaxWidth = 400;
    
    // The rendering process will go here
}
```
**Note:** Replace `"SAMPLE.DOCX"` with the path to your document. The `MaxWidth` property ensures that the rendered image does not exceed the specified width, maintaining an optimal display.

## Step 3: Render the Document with Specified Options

This line of code triggers the rendering process, generating the output image with the defined size limits.

```csharp
// Inside the using block
viewer.View(options);
```

## Step 4: Display Success Message

Upon successful rendering, a message indicating the completion and the output directory path is displayed.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion

In conclusion, mastering the art of setting image size limits using GroupDocs.Viewer for .NET can significantly enhance document viewing experiences within your .NET applications. By following the step-by-step guide outlined in this tutorial, you can effortlessly optimize image display while ensuring performance and efficiency.

## FAQs

### Can I set both maximum width and height for the rendered images?
Yes, you can set both `MaxWidth` and `MaxHeight` properties in the view options to control the dimensions of the rendered image.

### What document formats are supported by GroupDocs.Viewer for .NET?
GroupDocs.Viewer for .NET supports a wide range of document formats, including DOCX, PDF, PPT, XLS, and more.

### Is GroupDocs.Viewer for .NET compatible with .NET Core?
Yes, GroupDocs.Viewer for .NET offers compatibility with .NET Core, allowing seamless integration into modern .NET applications.

### Can I customize the output image format to something other than JPEG?
Yes, GroupDocs.Viewer for .NET provides support for various output formats, including PNG, TIFF, and PDF.

### Is there a trial version available for testing before purchasing?
Yes, you can get a [free trial](https://releases.groupdocs.com/) from the official website to explore the features and functionalities of GroupDocs.Viewer for .NET before making a purchase.
