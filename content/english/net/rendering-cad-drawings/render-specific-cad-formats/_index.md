---
title: Render Specific CAD Formats (CF2)
linktitle: Render Specific CAD Formats (CF2)
second_title: GroupDocs.Viewer .NET API
description: Learn how to render specific CAD formats like CF2 to HTML, JPG, PNG, and PDF using Groupdocs.Viewer for .NET.
weight: 12
url: /net/rendering-cad-drawings/render-specific-cad-formats/
---

# Render Specific CAD Formats (CF2)

## Introduction
In this tutorial, we'll explore how to render specific CAD formats using Groupdocs.Viewer for .NET. Groupdocs.Viewer is a powerful document viewer API that allows developers to display over 170 document types in their applications without requiring any external software installations. Specifically, we'll focus on rendering CAD formats such as CF2 to various output formats like HTML, JPG, PNG, and PDF.
## Prerequisites
Before we dive into the tutorial, ensure you have the following prerequisites:
- Visual Studio installed on your system.
- Groupdocs.Viewer for .NET SDK. You can download it from [here](https://releases.groupdocs.com/viewer/net/).
- Basic knowledge of C# programming language.
## Import Namespaces
First, let's import the necessary namespaces required for rendering CAD formats.
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Now, let's break down each example into multiple steps:
## Render CF2 to HTML
### Step 1: Define the output directory where the rendered HTML will be saved.
```csharp
string outputDirectory = "Your Document Directory";
```
### Step 2: Define the file path format for the HTML output.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.html");
```
### Step 3: Initialize the Viewer object and specify the input CF2 file.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // Set additional rendering options if required
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Render CF2 to JPG
### Step 1: Define the file path format for the JPG output.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.jpg");
```
### Step 2: Initialize the Viewer object and specify the input CF2 file.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // Set additional rendering options if required
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Render CF2 to PNG

### Step 1: Define the file path format for the PNG output.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.png");
```
### Step 2: Initialize the Viewer object and specify the input CF2 file.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // Set additional rendering options if required
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```
## Render CF2 to PDF
### Step 1: Define the file path format for the PDF output.
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "CF2_result.pdf");
```
### Step 2: Initialize the Viewer object and specify the input CF2 file.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CF2))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // Set additional rendering options if required
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    viewer.View(options);
}
```

## Conclusion
In this tutorial, we've learned how to render specific CAD formats such as CF2 using Groupdocs.Viewer for .NET. By following the step-by-step guide, you can easily integrate document rendering capabilities into your .NET applications.
## FAQ's
### Can Groupdocs.Viewer render other CAD formats apart from CF2?
Yes, Groupdocs.Viewer supports a wide range of CAD formats, including DWG, DXF, DGN, and more.
### Is Groupdocs.Viewer suitable for rendering documents in web applications?
Absolutely, Groupdocs.Viewer can be seamlessly integrated into web applications for rendering documents directly in the browser.
### Does Groupdocs.Viewer require any external dependencies for rendering?
No, Groupdocs.Viewer is a standalone API and does not require any external dependencies or software installations.
### Can I customize the rendering options according to my requirements?
Yes, Groupdocs.Viewer provides various rendering options that can be customized to meet your specific needs.
### Is there a trial version available for Groupdocs.Viewer?
Yes, you can get a free trial version of Groupdocs.Viewer from [here](https://releases.groupdocs.com/).
