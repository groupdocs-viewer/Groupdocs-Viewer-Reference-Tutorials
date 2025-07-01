---
title: "Get Worksheet Names from Spreadsheets in .NET | GroupDocs.Viewer"
description: "Learn how to retrieve worksheet names from spreadsheets in your .NET applications using GroupDocs.Viewer. A step-by-step guide for seamless integration."
weight: 11
url: "/net/spreadsheet-rendering-options/get-worksheets-names/"
keywords:
- get worksheet names .net
- groupdocs.viewer for .net
- .net spreadsheet info
- view excel worksheet names

---

## Introduction

Welcome to the world of **GroupDocs.Viewer for .NET**! If you are a developer looking to explore powerful document viewing capabilities within your .NET applications, you are in for a treat. In this comprehensive guide, we will delve into the intricacies of retrieving worksheet names from spreadsheets using GroupDocs.Viewer.

## Prerequisites

Before we dive into the code, let's ensure you have everything set up:
*   A working knowledge of C# and .NET development.
*   **.NET SDK:** Installed on your machine.
*   **GroupDocs.Viewer for .NET:** Download the library [here](https://releases.groupdocs.com/viewer/net/).
*   **IDE:** Visual Studio or any other .NET development environment.
*   **Sample Document:** An Excel file (e.g., `SAMPLE.XLSX`) in your designated document directory.

## Import Namespaces

Now that you have the prerequisites in place, let's start by importing the necessary namespaces. This ensures that your application can recognize and use the functionalities provided by GroupDocs.Viewer for .NET.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

## Step 1: Initialize Viewer and Configure View Information Options

First, create an instance of the `Viewer` class with the path to your Excel file. Then, configure `ViewInfoOptions` to specify how you want to retrieve the view information.

```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
    viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
    
    // The rest of the code will go here
}
```
**Note:** Replace `"SAMPLE.XLSX"` with the path to your spreadsheet.

## Step 2: Retrieve View Information

Use the `Viewer` instance to get the view information based on the configured options.

```csharp
// Inside the using block
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```

## Step 3: Display Worksheet Names

Finally, loop through the retrieved pages (which represent the worksheets in this case) and print the name of each worksheet to the console.

```csharp
// Inside the using block
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```

## Conclusion

Congratulations! You have successfully navigated the process of fetching worksheet names using GroupDocs.Viewer for .NET. This opens up a myriad of possibilities for enhancing document viewing functionalities within your applications.

## FAQs

### Can I use GroupDocs.Viewer for .NET with other document formats?
Absolutely! GroupDocs.Viewer supports a wide range of document formats, including PDF, Microsoft Office, and more.

### Is there a free trial available?
Yes, you can explore GroupDocs.Viewer for .NET with our [free trial](https://releases.groupdocs.com/).

### Where can I find additional support?
Head to the [GroupDocs.Viewer forum](https://forum.groupdocs.com/c/viewer/9) for community support and discussions.

### Can I obtain a temporary license?
Certainly! Visit [this link](https://purchase.groupdocs.com/temporary-license/) to get your temporary license.

### Are there detailed documentation resources available?
Absolutely! Check out the [official documentation](https://reference.groupdocs.com/viewer/net/) for in-depth information and guides.
