---
title: "Render Hidden Columns and Rows in .NET | GroupDocs.Viewer"
description: "Learn how to render hidden columns and rows from spreadsheets to HTML in your .NET applications using GroupDocs.Viewer. A step-by-step guide."
weight: 13
url: "/net/spreadsheet-rendering-options/render-hidden-columns-rows/"
keywords:
- render hidden columns rows .net
- groupdocs.viewer for .net
- .net spreadsheet rendering
- view hidden excel data

---

## Introduction

In the realm of document visualization, **GroupDocs.Viewer for .NET** stands out as a robust tool that facilitates the seamless rendering of various document formats. One of its intriguing capabilities is the ability to reveal hidden columns and rows within spreadsheets. In this tutorial, we will delve into the steps to unlock this feature and unleash the full potential of your data.

## Prerequisites

Before you begin, ensure you have the following:
*   A working knowledge of C# and .NET development.
*   **.NET SDK:** Installed on your machine.
*   **GroupDocs.Viewer for .NET:** Download the library [here](https://releases.groupdocs.com/viewer/net/).
*   **IDE:** Visual Studio or any other .NET development environment.
*   **Sample Document:** A spreadsheet file (e.g., `SAMPLE.XLSX`) with hidden columns and rows.

## Import Namespaces

In your .NET project, import the necessary namespaces to leverage GroupDocs.Viewer functionalities effectively:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Step 1: Set Up Output Directory and File Path Format

First, define the directory where the rendered HTML pages will be stored and the format for the output file names.

```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
**Note:** Replace `"Your Document Directory"` with the actual path.

## Step 2: Initialize Viewer and Configure HTML View Options

Create a `Viewer` instance with the path to your spreadsheet document. Then, configure the `HtmlViewOptions` to enable the rendering of hidden columns and rows.

```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHiddenColumns = true;
    options.SpreadsheetOptions.RenderHiddenRows = true;
    
    // The rendering process will go here
}
```
**Note:** Replace `"SAMPLE.XLSX"` with the path to your spreadsheet.

## Step 3: Execute the Rendering Process

Invoke the `View` method on the `Viewer` object, passing the configured options. This will initiate the rendering process.

```csharp
// Inside the using block
viewer.View(options);
```

## Step 4: Check the Output

Finally, display a message indicating the successful rendering of the source document and the location of the output.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion

Unlocking hidden columns and rows in your spreadsheets becomes a breeze with GroupDocs.Viewer for .NET. This tutorial has equipped you with the essential steps to reveal concealed data, providing a more comprehensive view of your documents.

## FAQs

### Can I render hidden columns and rows in other document formats besides spreadsheets?
GroupDocs.Viewer primarily supports this feature for spreadsheet formats. For other document types, the concept of hidden columns and rows may not apply in the same way.

### Is there a limit to the number of hidden columns and rows that can be rendered?
GroupDocs.Viewer is designed to handle large datasets efficiently. However, rendering an extremely large number of hidden columns and rows may impact performance, so it is advisable to consider system resources.

### Can I customize the output format of the rendered data?
Absolutely! GroupDocs.Viewer provides flexible options to customize the output, allowing you to render to various formats like PDF, JPG, and PNG, and to tailor the appearance to your specific needs.

### Are there any licensing considerations for using GroupDocs.Viewer?
Yes, you need a valid license for production use. You can explore licensing options at [GroupDocs Purchase](https://purchase.groupdocs.com/buy) or obtain a [temporary license](https://purchase.groupdocs.com/temporary-license/) for testing.

### Where can I seek assistance or connect with the GroupDocs community?
Visit the [GroupDocs.Viewer Forum](https://forum.groupdocs.com/c/viewer/9) for support, discussions, and community interaction.
