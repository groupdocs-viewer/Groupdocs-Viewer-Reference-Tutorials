---
title: "Render Apple Numbers Spreadsheets in .NET | GroupDocs.Viewer"
description: "Learn how to render Apple Numbers spreadsheets to HTML, JPG, PNG, and PDF in your .NET applications using GroupDocs.Viewer. A step-by-step guide."
weight: 15
url: "/net/spreadsheet-rendering-options/rendering-numbers/"
keywords:
- render numbers files .net
- groupdocs.viewer for .net
- .net numbers to html
- .net numbers to pdf

---

## Introduction

Welcome to this step-by-step tutorial on rendering Apple Numbers files using **GroupDocs.Viewer for .NET**. Whether you are a seasoned developer or just starting, this guide will walk you through the process of converting Numbers documents into various formats like HTML, JPG, PNG, and PDF. GroupDocs.Viewer for .NET is a powerful API that allows you to seamlessly integrate document viewing capabilities into your .NET applications.

## Prerequisites

Before you begin, ensure you have the following:
*   A working knowledge of C# and .NET development.
*   **.NET SDK:** Installed on your machine.
*   **GroupDocs.Viewer for .NET:** Download the library [here](https://releases.groupdocs.com/viewer/net/).
*   **IDE:** Visual Studio or any other .NET development environment.

## Import Namespaces

In your C# project, make sure to import the necessary namespaces to use the GroupDocs.Viewer library:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Step 1: Set Up Output Directory

First, define the directory where the rendered files will be saved. Replace `"Your Document Directory"` with the actual path.

```csharp
string outputDirectory = "Your Document Directory";
```

## Step 2: Render to Multi-Page HTML

Use the following code to convert the Numbers file to a multi-page HTML document with embedded resources.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "numbers_result.html");

using (Viewer viewer = new Viewer("YOUR_SAMPLE_FILE.numbers"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
**Note:** Replace `"YOUR_SAMPLE_FILE.numbers"` with the path to your Numbers file.

## Step 3: Render to JPG

Convert the Numbers file to a JPG image with the following code.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "numbers_result.jpg");

using (Viewer viewer = new Viewer("YOUR_SAMPLE_FILE.numbers"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## Step 4: Render to PNG

Transform the Numbers file into a PNG image using the following code.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "numbers_result.png");

using (Viewer viewer = new Viewer("YOUR_SAMPLE_FILE.numbers"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## Step 5: Render to PDF

Finally, convert the Numbers file to a PDF document using the following code.

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "numbers_result.pdf");

using (Viewer viewer = new Viewer("YOUR_SAMPLE_FILE.numbers"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

Congratulations! You have successfully rendered an Apple Numbers file into various formats using GroupDocs.Viewer for .NET.

## Conclusion

In this tutorial, we covered the basics of rendering Numbers files using GroupDocs.Viewer for .NET. This powerful library provides seamless integration for viewing and converting a wide range of document formats within your .NET applications.

## FAQs

### Can I use GroupDocs.Viewer for .NET with other document types?
Yes, GroupDocs.Viewer supports a wide range of document formats, including Microsoft Office, PDF, images, and more.

### Is a temporary license available for testing?
Yes, you can obtain a temporary license for testing purposes from the [GroupDocs website](https://purchase.groupdocs.com/temporary-license/).

### Where can I find support for GroupDocs.Viewer for .NET?
Visit the [GroupDocs.Viewer Forum](https://forum.groupdocs.com/c/viewer/9) for assistance and community discussions.

### How do I purchase the full version of GroupDocs.Viewer for .NET?
You can purchase the full version from the [GroupDocs purchase page](https://purchase.groupdocs.com/buy).

### Is there a free trial available?
Yes, you can explore the features of GroupDocs.Viewer with a free trial available for download [here](https://releases.groupdocs.com/).
