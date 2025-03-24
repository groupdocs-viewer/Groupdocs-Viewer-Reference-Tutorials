---
title: Render CHM Files
linktitle: Render CHM Files
second_title: GroupDocs.Viewer .NET API
description: Learn how to render CHM files in .NET using GroupDocs.Viewer. Convert CHM to HTML, JPG, PNG, and PDF formats effortlessly.
weight: 10
url: /net/rendering-web-documents/render-chm/
---
## Introduction
In this tutorial, we'll explore how to render CHM (Compiled HTML Help) files using GroupDocs.Viewer for .NET. GroupDocs.Viewer for .NET is a powerful document rendering API that allows developers to display over 170 document types within their .NET applications without requiring any external software installations.

## Prerequisites

Before we dive into rendering CHM files, ensure you have the following prerequisites:

### Installing GroupDocs.Viewer for .NET

To get started, you need to install GroupDocs.Viewer for .NET. You can download the library from the [GroupDocs website](https://releases.groupdocs.com/viewer/net/) or install it via NuGet Package Manager by running the following command in the Package Manager Console:

```bash
Install-Package GroupDocs.Viewer
```

## Importing Namespaces

Make sure to import the necessary namespaces into your project:

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

Now let's break down the rendering process into multiple steps:

## Step 1: Define Output Directory

Define the directory where you want the rendered files to be saved:

```csharp
string outputDirectory = "Your Document Directory";
```

## Step 2: Render to HTML

To render CHM files to HTML, use the following code snippet:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // Set to true to convert all CHM content to a single page

    viewer.View(options); // Convert all pages
}
```

## Step 3: Render to JPG

To render CHM files to JPG images, use the following code snippet:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Convert only pages 1, 2, 3
}
```

## Step 4: Render to PNG

To render CHM files to PNG images, use the following code snippet:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // Convert only pages 1, 2, 3
}
```

## Step 5: Render to PDF

To render CHM files to a PDF document, use the following code snippet:

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); // Convert all pages
}
```

## Step 6: Check Output

Once the rendering process is complete, check the specified output directory for the rendered files:

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion

Rendering CHM files using GroupDocs.Viewer for .NET is a straightforward process. By following the steps outlined in this tutorial, you can efficiently convert CHM documents into various formats such as HTML, images (JPG, PNG), and PDF within your .NET applications.

## FAQ's

### Q1: Can GroupDocs.Viewer render other document formats apart from CHM?

A1: Yes, GroupDocs.Viewer supports rendering over 170 document formats including PDF, DOCX, XLSX, PPTX, and more.

### Q2: Is GroupDocs.Viewer compatible with .NET Core?

A2: Yes, GroupDocs.Viewer supports .NET Core in addition to the traditional .NET Framework.

### Q3: Can I customize the rendering options for different output formats?

A3: Yes, GroupDocs.Viewer provides various options for customizing the rendering process, such as specifying page numbers, setting image quality, and configuring output paths.

### Q4: Does GroupDocs.Viewer require any external dependencies for rendering documents?

A4: No, GroupDocs.Viewer is a standalone library and does not require any external dependencies or third-party software installations.

### Q5: Is there a free trial available for GroupDocs.Viewer?

A5: Yes, you can avail of a free trial of GroupDocs.Viewer by visiting the [website](https://releases.groupdocs.com/).
