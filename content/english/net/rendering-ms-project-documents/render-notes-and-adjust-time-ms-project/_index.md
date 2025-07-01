---
title: "Render Notes & Adjust Time Units in MS Project with .NET"
description: "Learn how to render MS Project documents with notes and adjust time units to various formats like HTML, JPG, PNG, and PDF in your .NET applications using GroupDocs.Viewer."
weight: 11
url: "/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/"
keywords:
- render ms project notes .net
- groupdocs.viewer for .net
- .net ms project rendering
- adjust project time units .net

---

## Introduction

**GroupDocs.Viewer for .NET** is a powerful document rendering API that allows developers to view and manipulate various document formats within their .NET applications. In this tutorial, we will focus on rendering notes and adjusting time units specifically for MS Project documents.

## Prerequisites

Before we begin, make sure you have the following:
*   A working knowledge of C# and .NET development.
*   **.NET SDK:** Installed on your machine.
*   **GroupDocs.Viewer for .NET:** Download the library [here](https://releases.groupdocs.com/viewer/net/).
*   **IDE:** Visual Studio or any other .NET development environment.
*   **MS Project Document:** A sample MPP file for testing.

## Import Namespaces

First, let's import the necessary namespaces to get started with rendering MS Project documents.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Now, let's break down each example into multiple steps for a comprehensive understanding.

## Rendering MS Project Document to HTML

To render an MS Project document to HTML format with notes included, follow these steps.

### Step 1: Define Output Directory and File Path Format

```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
**Note:** Replace `"Your Document Directory"` with the actual path.

### Step 2: Initialize Viewer and Configure HTML View Options

```csharp
using (Viewer viewer = new Viewer("SAMPLE.mpp"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
    
    viewer.View(options);
}
```
**Note:** Replace `"SAMPLE.mpp"` with the path to your MS Project file.

## Rendering MS Project Document to Image Formats

You can also render MS Project documents to image formats like JPG and PNG.

### Step 1: Define Output Directory and File Path Format for JPG

```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.jpg");
```

### Step 2: Initialize Viewer and Configure JPG View Options

```csharp
using (Viewer viewer = new Viewer("SAMPLE.mpp"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
    
    viewer.View(options);
}
```

You can follow similar steps to render to PNG by using `PngViewOptions`.

## Rendering MS Project Document to PDF

To render an MS Project document to PDF format, proceed as follows.

### Step 1: Define Output Directory and File Path Format for PDF

```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```

### Step 2: Initialize Viewer and Configure PDF View Options

```csharp
using (Viewer viewer = new Viewer("SAMPLE.mpp"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
    
    viewer.View(options);
}
```

## Conclusion

Congratulations! You have successfully learned how to render MS Project documents with notes and adjust time units using GroupDocs.Viewer for .NET. Incorporate this knowledge into your projects to enhance your document viewing capabilities.

## FAQs

### Can I render MS Project documents to other formats apart from HTML, images, and PDF?
Yes, GroupDocs.Viewer for .NET supports rendering to various formats such as DOCX, XLSX, PPTX, and more.

### Is there a trial version available for GroupDocs.Viewer for .NET?
Yes, you can get a [free trial](https://releases.groupdocs.com/) from the official website.

### How can I get a temporary license for GroupDocs.Viewer for .NET?
Visit [this link](https://purchase.groupdocs.com/temporary-license/) to obtain a temporary license.

### Where can I find the documentation for GroupDocs.Viewer for .NET?
Refer to the [documentation](https://reference.groupdocs.com/viewer/net/) for detailed information.

### Where can I seek support or ask questions related to GroupDocs.Viewer for .NET?
You can visit the [support forum](https://forum.groupdocs.com/c/viewer/9) for assistance.
