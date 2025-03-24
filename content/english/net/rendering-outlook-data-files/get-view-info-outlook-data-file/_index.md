---
title: Get View Information for Outlook Data Files (PST, OST)
linktitle: Get View Information for Outlook Data Files (PST, OST)
second_title: GroupDocs.Viewer .NET API
description: Explore how to extract view information from Outlook Data Files (PST, OST) using GroupDocs.Viewer for .NET. Enhance your document management capabilities effortlessly.
weight: 10
url: /net/rendering-outlook-data-files/get-view-info-outlook-data-file/
---

# Get View Information for Outlook Data Files (PST, OST)

## Introduction
In the realm of document management and viewing, GroupDocs.Viewer for .NET stands as a powerful tool, particularly when it comes to handling Outlook Data Files (PST, OST). In this tutorial, we'll delve into the process of extracting view information for these files step by step.
## Prerequisites
Before we embark on this tutorial, ensure you have the following prerequisites in place:
### 1. Installation of GroupDocs.Viewer for .NET
Firstly, you need to have GroupDocs.Viewer for .NET installed in your development environment. You can download the necessary package from the [GroupDocs.Viewer for .NET website](https://releases.groupdocs.com/viewer/net/).
### 2. Familiarity with C# Programming Language
Basic knowledge of C# programming language is essential to understand and implement the provided code examples.
### 3. Outlook Data Files (PST, OST)
Make sure you have Outlook Data Files (PST, OST) available for testing purposes. You can obtain sample files from various sources or use your own data files.

## Import Namespaces
Before diving into the code, let's ensure we import the necessary namespaces:
```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

Now, let's break down the provided example into multiple steps:
## Step 1: Instantiate the Viewer Object
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST_SUBFOLDERS))
```
Here, we're initializing a Viewer object with the path to the Outlook Data File (OST) specified as the argument.
## Step 2: Configure View Information Options
```csharp
ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
```
We're setting up the options for retrieving view information. In this case, we're opting for HTML view.
## Step 3: Retrieve Outlook View Information
```csharp
OutlookViewInfo rootFolderInfo = viewer.GetViewInfo(options) as OutlookViewInfo;
```
This line fetches the view information for the Outlook Data File.
## Step 4: Display File Type and Page Count
```csharp
Console.WriteLine("File type is: " + rootFolderInfo.FileType);
Console.WriteLine("Pages count: " + rootFolderInfo.Pages.Count);
```
We're printing out the file type and the count of pages in the Outlook Data File.
## Step 5: Iterate Through Folders
```csharp
foreach (string folder in rootFolderInfo.Folders)
    Console.WriteLine(folder);
```
This loop iterates through the folders contained within the Outlook Data File and prints their names.
## Step 6: Finalize Retrieval
```csharp
Console.WriteLine("\nView info retrieved successfully.");
```
A message indicating the successful retrieval of view information is displayed.

## Conclusion
GroupDocs.Viewer for .NET provides a seamless solution for extracting view information from Outlook Data Files (PST, OST). By following the steps outlined in this tutorial, you can effortlessly obtain valuable insights into these files for enhanced document management.
## FAQ's
### Is GroupDocs.Viewer for .NET compatible with different versions of Outlook Data Files?
Yes, GroupDocs.Viewer for .NET supports various versions of Outlook Data Files, ensuring compatibility across different environments.
### Can I customize the view options for Outlook Data Files using GroupDocs.Viewer for .NET?
Absolutely! GroupDocs.Viewer for .NET offers extensive customization options, allowing you to tailor the viewing experience according to your requirements.
### Does GroupDocs.Viewer for .NET support other file formats besides Outlook Data Files?
Yes, GroupDocs.Viewer for .NET supports a wide range of file formats, including but not limited to PDF, DOCX, XLSX, and more.
### Is there a free trial available for GroupDocs.Viewer for .NET?
Yes, you can access a free trial of GroupDocs.Viewer for .NET from the website: [Free Trial](https://releases.groupdocs.com/).
### Where can I find additional support or assistance for GroupDocs.Viewer for .NET?
For any inquiries or assistance, you can visit the GroupDocs.Viewer for .NET support forum: [Support](https://forum.groupdocs.com/c/viewer/9).
