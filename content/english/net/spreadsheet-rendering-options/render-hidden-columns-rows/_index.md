---
title: Render Hidden Columns and Rows
linktitle: Render Hidden Columns and Rows
second_title: GroupDocs.Viewer .NET API
description: Unlock hidden data in spreadsheets effortlessly using GroupDocs.Viewer for .NET. Follow our step-by-step guide to reveal concealed columns and rows.
type: docs
weight: 13
url: /net/spreadsheet-rendering-options/render-hidden-columns-rows/
---
## Introduction
In the realm of document visualization, GroupDocs.Viewer for .NET stands tall as a robust tool that facilitates seamless rendering of various document formats. One intriguing capability is the ability to reveal hidden columns and rows within spreadsheets. In this tutorial, we'll delve into the steps to unlock this feature and unleash the potential of your data.
## Prerequisites
Before embarking on this journey, ensure you have the following prerequisites in place:
- GroupDocs.Viewer for .NET: Make sure you have the latest version installed. If not, you can download it from the [official website](https://releases.groupdocs.com/viewer/net/).
- Document File: Prepare a sample document in a spreadsheet format (e.g., SAMPLE.XLSX) to experiment with hidden columns and rows.
- Development Environment: Set up a working environment, preferably using Visual Studio or any other suitable IDE for .NET development.
## Import Namespaces
In your .NET project, import the necessary namespaces to leverage GroupDocs.Viewer functionalities effectively:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Step 1: Set up Output Directory
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Define the output directory where the rendered HTML pages will be stored. Adjust the file path format accordingly.
## Step 2: Initialize Viewer and Configure Options
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHiddenColumns = true;
    options.SpreadsheetOptions.RenderHiddenRows = true;
```
Create a Viewer instance by providing the path to your spreadsheet document. Configure HTML view options to embed resources and enable the rendering of hidden columns and rows.
## Step 3: Execute Rendering Process
```csharp
    viewer.View(options);
}
```
Invoke the View method on the viewer object, passing the configured options. This initiates the rendering process.
## Step 4: Check the Output
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Verify the successful rendering of the source document and locate the output in the specified directory.
## Conclusion
Unlocking hidden columns and rows in your spreadsheets becomes a breeze with GroupDocs.Viewer for .NET. This tutorial has equipped you with the essential steps to reveal concealed data, providing a more comprehensive view of your documents.
## Frequently Asked Questions
### Can I render hidden columns and rows in other document formats besides spreadsheets?
Yes, GroupDocs.Viewer supports various document formats, including Word, PDF, and PowerPoint, in addition to spreadsheets.
### Is there a limit to the number of hidden columns and rows that can be rendered?
GroupDocs.Viewer efficiently handles rendering for a wide range of hidden columns and rows. However, extreme cases with an extensive amount of hidden data may impact performance.
### Can I customize the output format of the rendered data?
Absolutely! GroupDocs.Viewer provides flexible options to customize the output, allowing you to tailor the rendered data to your specific needs.
### Are there any licensing considerations for using GroupDocs.Viewer?
Yes, ensure you have the appropriate license for your usage. Explore licensing options at [GroupDocs Purchase](https://purchase.groupdocs.com/buy) or obtain a [temporary license](https://purchase.groupdocs.com/temporary-license/) for testing.
### Where can I seek assistance or connect with the GroupDocs community for support?
Visit the [GroupDocs.Viewer Forum](https://forum.groupdocs.com/c/viewer/9) for support, discussions, and community interaction.