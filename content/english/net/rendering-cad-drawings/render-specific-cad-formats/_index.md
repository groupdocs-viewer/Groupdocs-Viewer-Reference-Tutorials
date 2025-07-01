---
title: "Render Specific CAD Formats (CF2) in .NET | GroupDocs.Viewer"
description: "Learn how to render specific CAD formats like CF2 to HTML, JPG, PNG, and PDF in your .NET applications using GroupDocs.Viewer."
weight: 12
url: "/net/rendering-cad-drawings/render-specific-cad-formats/"
keywords:
- render cf2 .net
- groupdocs.viewer for .net
- .net cad rendering
- view cf2 files .net

---

## Introduction

In this tutorial, we will explore how to render specific CAD formats, such as CF2, using **GroupDocs.Viewer for .NET**. GroupDocs.Viewer is a powerful document viewer API that allows developers to display over 170 document types in their applications without requiring any external software installations. Specifically, we will focus on rendering CF2 files to various output formats like HTML, JPG, PNG, and PDF.

## Prerequisites

Before you begin, ensure you have the following:
*   **Visual Studio:** Installed on your system.
*   **GroupDocs.Viewer for .NET SDK:** Download it from [here](https://releases.groupdocs.com/viewer/net/).
*   **Basic Knowledge of C#:** Familiarity with the C# programming language.

## Import Namespaces

First, let's import the necessary namespaces required for rendering CAD formats.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Now, let's break down each example into multiple steps.

## Render CF2 to HTML

### Step 1: Define Output Directory and File Path Format

Define the directory where the rendered HTML will be saved and the format for the HTML file path.

```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cf2_result.html");
```
**Note:** Replace `"Your Document Directory"` with the actual path.

### Step 2: Initialize Viewer and Configure HTML View Options

Initialize the `Viewer` object with the input CF2 file and configure the `HtmlViewOptions`.

```csharp
using (Viewer viewer = new Viewer("SAMPLE.cf2"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // Set additional rendering options if required
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    
    viewer.View(options);
}
```
**Note:** Replace `"SAMPLE.cf2"` with the path to your CF2 file.

## Render CF2 to JPG

### Step 1: Define Output Directory and File Path Format

```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cf2_result.jpg");
```

### Step 2: Initialize Viewer and Configure JPG View Options

```csharp
using (Viewer viewer = new Viewer("SAMPLE.cf2"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    // Set additional rendering options if required
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    
    viewer.View(options);
}
```

## Render CF2 to PNG

### Step 1: Define Output Directory and File Path Format

```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cf2_result.png");
```

### Step 2: Initialize Viewer and Configure PNG View Options

```csharp
using (Viewer viewer = new Viewer("SAMPLE.cf2"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    // Set additional rendering options if required
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    
    viewer.View(options);
}
```

## Render CF2 to PDF

### Step 1: Define Output Directory and File Path Format

```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cf2_result.pdf");
```

### Step 2: Initialize Viewer and Configure PDF View Options

```csharp
using (Viewer viewer = new Viewer("SAMPLE.cf2"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    // Set additional rendering options if required
    // options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.7f);
    
    viewer.View(options);
}
```

## Conclusion

In this tutorial, we have learned how to render specific CAD formats, such as CF2, using GroupDocs.Viewer for .NET. By following the step-by-step guide, you can easily integrate document rendering capabilities into your .NET applications.

## FAQs

### Can GroupDocs.Viewer render other CAD formats apart from CF2?
Yes, GroupDocs.Viewer supports a wide range of CAD formats, including DWG, DXF, DGN, and more.

### Is GroupDocs.Viewer suitable for rendering documents in web applications?
Absolutely, GroupDocs.Viewer can be seamlessly integrated into web applications for rendering documents directly in the browser.

### Does GroupDocs.Viewer require any external dependencies for rendering?
No, GroupDocs.Viewer is a standalone API and does not require any external dependencies or software installations.

### Can I customize the rendering options according to my requirements?
Yes, GroupDocs.Viewer provides various rendering options that can be customized to meet your specific needs.

### Is there a trial version available for GroupDocs.Viewer?
Yes, you can get a [free trial](https://releases.groupdocs.com/) version of GroupDocs.Viewer from the official website.
