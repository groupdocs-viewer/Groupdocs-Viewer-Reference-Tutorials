---
title: "Get View Info for Outlook Data Files (PST, OST) in .NET"
description: "Learn how to extract view information from Outlook Data Files (PST, OST) in your .NET applications using GroupDocs.Viewer. Enhance your document management capabilities."
weight: 10
url: "/net/rendering-outlook-data-files/get-view-info-outlook-data-file/"
keywords:
- get outlook view info .net
- groupdocs.viewer for .net
- .net pst viewer
- .net ost viewer

---

## Introduction

In the realm of document management and viewing, **GroupDocs.Viewer for .NET** stands as a powerful tool, particularly when it comes to handling Outlook Data Files (PST, OST). In this tutorial, we will delve into the process of extracting view information for these files step by step.

## Prerequisites

Before we begin, ensure you have the following:
*   A working knowledge of C# and .NET development.
*   **.NET SDK:** Installed on your machine.
*   **GroupDocs.Viewer for .NET:** Download the library [here](https://releases.groupdocs.com/viewer/net/).
*   **IDE:** Visual Studio or any other .NET development environment.
*   **Outlook Data Files (PST, OST):** Have sample PST or OST files available for testing.

## Import Namespaces

Before diving into the code, let's ensure we import the necessary namespaces:

```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Now, let's break down the example into multiple steps.

## Step 1: Instantiate the Viewer Object

Initialize a `Viewer` object with the path to your Outlook Data File (PST or OST).

```csharp
using (Viewer viewer = new Viewer("SAMPLE.OST"))
{
    // The rest of the code will go here
}
```
**Note:** Replace `"SAMPLE.OST"` with the path to your data file.

## Step 2: Configure View Information Options

Set up the options for retrieving the view information. In this case, we will opt for an HTML view.

```csharp
// Inside the using block
ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
```

## Step 3: Retrieve Outlook View Information

Fetch the view information for the Outlook Data File.

```csharp
// Inside the using block
OutlookViewInfo rootFolderInfo = viewer.GetViewInfo(options) as OutlookViewInfo;
```

## Step 4: Display File Type and Page Count

Print the file type and the number of pages (in this context, the number of items in the root folder).

```csharp
// Inside the using block
Console.WriteLine("File type is: " + rootFolderInfo.FileType);
Console.WriteLine("Pages count: " + rootFolderInfo.Pages.Count);
```

## Step 5: Iterate Through Folders

Loop through the folders contained within the Outlook Data File and print their names.

```csharp
// Inside the using block
Console.WriteLine("\nFolders:");
foreach (string folder in rootFolderInfo.Folders)
{
    Console.WriteLine(folder);
}
```

## Step 6: Finalize Retrieval

Display a message indicating the successful retrieval of the view information.

```csharp
Console.WriteLine("\nView info retrieved successfully.");
```

## Conclusion

GroupDocs.Viewer for .NET provides a seamless solution for extracting view information from Outlook Data Files (PST, OST). By following the steps outlined in this tutorial, you can effortlessly obtain valuable insights into these files for enhanced document management.

## FAQs

### Is GroupDocs.Viewer for .NET compatible with different versions of Outlook Data Files?
Yes, GroupDocs.Viewer for .NET supports various versions of Outlook Data Files, ensuring compatibility across different environments.

### Can I customize the view options for Outlook Data Files using GroupDocs.Viewer for .NET?
Absolutely! GroupDocs.Viewer for .NET offers extensive customization options, allowing you to tailor the viewing experience according to your requirements.

### Does GroupDocs.Viewer for .NET support other file formats besides Outlook Data Files?
Yes, GroupDocs.Viewer for .NET supports a wide range of file formats, including but not limited to PDF, DOCX, XLSX, and more.

### Is there a free trial available for GroupDocs.Viewer for .NET?
Yes, you can access a [free trial](https://releases.groupdocs.com/) of GroupDocs.Viewer for .NET from the official website.

### Where can I find additional support or assistance for GroupDocs.Viewer for .NET?
For any inquiries or assistance, you can visit the [GroupDocs.Viewer support forum](https://forum.groupdocs.com/c/viewer/9).
