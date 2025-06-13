---
title: Render EMZ and EMF Images
linktitle: Render EMZ and EMF Images
second_title: GroupDocs.Viewer .NET API
description: Learn how to render EMZ and EMF images to various formats using GroupDocs.Viewer for .NET. Easy-to-follow tutorial for developers.
weight: 14
url: /net/image-rendering/render-emz-emf-images/
---

# Render EMZ and EMF Images

## Introduction

GroupDocs.Viewer for .NET is a powerful document rendering API that allows developers to display various document types, including EMZ (Enhanced Windows Metafile) and EMF (Enhanced Metafile) images, in their .NET applications. In this tutorial, we will explore how to render EMZ and EMF images to different formats such as HTML, JPG, PNG, and PDF using GroupDocs.Viewer for .NET.

![Render EMZ and EMF Images with GroupDocs.Viewer for .NET](/viewer/image-rendering/render-emz-and-emf-images.png)

## Prerequisites

Before we begin, make sure you have the following prerequisites:

1. GroupDocs.Viewer for .NET: You can download the library from [here](https://releases.groupdocs.com/viewer/net/).
2. Development Environment: Ensure you have a compatible development environment set up for .NET development.
3. Sample EMZ/EMF Images: Have sample EMZ and EMF images available for rendering.

## Import Namespaces

Before diving into the code, let's import the necessary namespaces:

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

Now, let's break down each example into multiple steps in a step-by-step guide format:

## Rendering EMZ/EMF Images to HTML

### Step 1: Set Output Directory:
```csharp
string outputDirectory = "Your Document Directory";
```
Replace `"Your Document Directory"` with the path where you want to save the rendered HTML file.

### Step 2: Define Page File Path Format:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
This will specify the file path format for the rendered HTML file.

### Step 3: Render to HTML:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
This code initializes the `Viewer` object with the sample EMZ image and renders it to HTML format using specified options.

## Rendering EMZ/EMF Images to JPG, PNG, and PDF

Repeat the following steps for rendering to JPG, PNG, and PDF formats:

### Step 1: Define Page File Path Format:
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
Adjust the file name and extension according to the desired output format (`jpg`, `png`, or `pdf`).

### Step 2: Render to Respective Format:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    // Adjust options according to the output format (Jpg, Png, Pdf)
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
Replace `JpgViewOptions` with `PngViewOptions` or `PdfViewOptions` based on the desired output format.

## Conclusion

In conclusion, GroupDocs.Viewer for .NET provides a seamless solution for rendering EMZ and EMF images to various formats in .NET applications. By following the steps outlined in this tutorial, developers can effortlessly integrate document rendering capabilities into their applications.

## FAQ's

### Q: Can GroupDocs.Viewer render other document formats apart from EMZ and EMF images?
A: Yes, GroupDocs.Viewer supports a wide range of document formats including PDF, DOCX, PPTX, XLSX, and more.

### Q: Is there a free trial available for GroupDocs.Viewer for .NET?
A: Yes, you can access the free trial [here](https://releases.groupdocs.com/).

### Q: Does GroupDocs.Viewer offer support for developers?
A: Yes, GroupDocs provides support through its [forum](https://forum.groupdocs.com/c/viewer/9) where developers can ask questions and seek assistance.

### Q: Can I purchase a temporary license for GroupDocs.Viewer for .NET?
A: Yes, temporary licenses are available for purchase [here](https://purchase.groupdocs.com/temporary-license/).

### Q: Where can I find detailed documentation for GroupDocs.Viewer for .NET?
A: You can refer to the documentation [here](https://tutorials.groupdocs.com/viewer/net/) for comprehensive guidance on using the API.
