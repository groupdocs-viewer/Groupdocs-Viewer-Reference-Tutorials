---
title: "Exclude Fonts from Rendered HTML in .NET | GroupDocs.Viewer"
description: "Learn how to exclude specific fonts from rendered HTML in your .NET applications using GroupDocs.Viewer. A step-by-step guide for seamless document display."
weight: 10
url: "/net/rendering-documents-html/exclude-fonts-html/"
keywords:
- exclude fonts html .net
- groupdocs.viewer for .net
- .net document rendering
- optimize html fonts

---

## Introduction

**GroupDocs.Viewer for .NET** is a powerful document rendering library that allows developers to display over 170 document formats in their .NET applications without the need for external dependencies. In this tutorial, we will focus on a specific feature of GroupDocs.Viewer: excluding fonts from the rendered HTML output.

## Prerequisites

Before you begin, ensure you have the following:
*   A basic understanding of C# and .NET development.
*   **GroupDocs.Viewer for .NET:** Installed in your project. You can download it from [here](https://releases.groupdocs.com/viewer/net/).
*   **Visual Studio:** Or any other IDE for C# development.

## Import Namespaces

In your C# code, make sure to include the necessary namespaces:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Step 1: Define Output Directory and Page File Path Format

Set up the directory where you want the rendered HTML files to be saved and specify the format for the file paths of individual pages.

```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
**Note:** Replace `"Your Document Directory"` with the actual path.

## Step 2: Initialize Viewer and Configure HTML View Options

Instantiate the `Viewer` object with the document you want to render. Then, define the `HtmlViewOptions` and specify the fonts to exclude.

```csharp
using (Viewer viewer = new Viewer("SAMPLE.docx"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.FontsToExclude.Add("Arial");
    
    // The rendering process will go here
}
```
**Note:** Replace `"SAMPLE.docx"` with the path to your document.

## Step 3: Render the Document

Pass the configured `HtmlViewOptions` to the `Viewer` object to render the document.

```csharp
// Inside the using block
viewer.View(options);
```

## Step 4: Display the Output Location

Inform the user about the location where the rendered HTML files are saved.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion

In this tutorial, we have learned how to use GroupDocs.Viewer for .NET to exclude fonts from rendered HTML output. By following the steps outlined above, you can customize the rendering process to meet your specific requirements, ensuring an optimal display of documents in your applications.

## FAQs

### Can I exclude multiple fonts from the rendered HTML?
Yes, you can add multiple font names to the `FontsToExclude` list in the `HtmlViewOptions`.

### Is GroupDocs.Viewer compatible with all .NET frameworks?
Yes, GroupDocs.Viewer supports .NET Framework 4.6.1 and higher, as well as .NET Core 2.0 and higher.

### Can I render documents from remote storage locations?
Yes, GroupDocs.Viewer supports rendering documents from local storage, remote storage locations, and streams.

### Does GroupDocs.Viewer support responsive design for HTML output?
Yes, you can enable responsive rendering by setting the `RenderResponsive` property in the `HtmlViewOptions`.

### Is technical support available for GroupDocs.Viewer?
Yes, you can seek assistance and participate in discussions on the [GroupDocs.Viewer forum](https://forum.groupdocs.com/c/viewer/9).
