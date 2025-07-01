---
title: "Adjust Page Size for Email Rendering in .NET | GroupDocs.Viewer"
description: "Learn how to adjust the page size when rendering email messages to PDF in your .NET applications using GroupDocs.Viewer. Enhance your document viewing efficiency."
weight: 10
url: "/net/rendering-email-messages/adjust-page-size-email/"
keywords:
- adjust email page size .net
- groupdocs.viewer for .net
- .net email rendering
- render msg to pdf .net

---

## Introduction

In the realm of .NET development, **GroupDocs.Viewer** provides a comprehensive solution for rendering various document formats, including email messages. This tutorial focuses on adjusting the page size when rendering email messages to PDF format using GroupDocs.Viewer for .NET. By following the steps outlined in this guide, you will learn how to seamlessly manipulate the page size to meet your specific requirements.

## Prerequisites

Before you begin, ensure you have the following:
*   A working knowledge of C# and .NET development.
*   **.NET SDK:** Installed on your machine.
*   **GroupDocs.Viewer for .NET:** Download the library [here](https://releases.groupdocs.com/viewer/net/).
*   **IDE:** Visual Studio or any other .NET development environment.
*   **Sample Email File:** An MSG file for testing purposes.

## Import Namespaces

In your C# project, import the necessary namespaces to utilize GroupDocs.Viewer functionalities.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Step 1: Define Output Directory and File Path

First, define the directory where the output PDF file will be saved and the full path for the output file.

```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.pdf");
```
**Note:** Replace `"Your Document Directory"` with the actual path.

## Step 2: Initialize Viewer and Configure PDF View Options

Create an instance of the `Viewer` class and specify the email message file path. Then, instantiate `PdfViewOptions` and set the output file path.

```csharp
using (Viewer viewer = new Viewer("SAMPLE.msg"))
{
    PdfViewOptions options = new PdfViewOptions(outputFilePath);
    
    // The page size adjustment will go here
}
```
**Note:** Replace `"SAMPLE.msg"` with the path to your email file.

## Step 3: Adjust the Page Size

Modify the `PageSize` property in the `EmailOptions` of the `PdfViewOptions`.

```csharp
// Inside the using block
options.EmailOptions.PageSize = PageSize.A4;
```
In this example, we are setting the page size to A4. You can choose other predefined page sizes or specify custom dimensions.

## Step 4: Render the Document

Invoke the `View` method of the `Viewer` object, passing the configured `PdfViewOptions`.

```csharp
// Inside the using block
viewer.View(options);
```

## Step 5: Display Success Message

Finally, inform the user about the successful rendering and the output directory.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion

In conclusion, this tutorial has demonstrated how to adjust the page size when rendering email messages to PDF format using GroupDocs.Viewer for .NET. By following these step-by-step instructions, you can efficiently manipulate page sizes to meet your specific requirements, enhancing document viewing and management capabilities within your .NET applications.

## FAQs

### Is GroupDocs.Viewer compatible with different email message formats?
GroupDocs.Viewer supports rendering various email message formats, including MSG and EML.

### Can I customize the page size according to my preferences?
Yes, you can adjust the page size using GroupDocs.Viewer's `PdfViewOptions`, offering flexibility in document rendering.

### Does GroupDocs.Viewer provide support for other document formats?
Yes, GroupDocs.Viewer supports a wide range of document formats, including PDF, Microsoft Office, images, and more.

### Is GroupDocs.Viewer suitable for enterprise-level applications?
Absolutely, GroupDocs.Viewer offers robust functionalities suitable for both small-scale and enterprise-level applications, ensuring efficient document rendering and management.

### Where can I seek assistance or additional support for GroupDocs.Viewer?
You can visit the [GroupDocs.Viewer forum](https://forum.groupdocs.com/c/viewer/9) to seek assistance, ask questions, and engage with the community.
