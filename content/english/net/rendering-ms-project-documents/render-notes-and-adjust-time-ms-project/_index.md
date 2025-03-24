---
title: Render Notes and Adjust Time Units (MS Project)
linktitle: Render Notes and Adjust Time Units (MS Project)
second_title: GroupDocs.Viewer .NET API
description: Master rendering MS Project documents with GroupDocs.Viewer for .NET. Render notes, adjust time units, and explore various output formats effortlessly.
weight: 11
url: /net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/
---

# Render Notes and Adjust Time Units (MS Project)

## Introduction
GroupDocs.Viewer for .NET is a powerful document rendering API that allows developers to view and manipulate various document formats within their .NET applications. In this tutorial, we will focus on rendering notes and adjusting time units specifically for MS Project documents.
## Prerequisites
Before we begin, make sure you have the following prerequisites:
1. GroupDocs.Viewer for .NET: Ensure you have downloaded and installed the GroupDocs.Viewer for .NET library. You can download it from [here](https://releases.groupdocs.com/viewer/net/).
2. Development Environment: Set up your preferred development environment with .NET support.
3. MS Project Document: Have a sample MS Project document ready for testing.
## Import Namespaces
First, let's import the necessary namespaces to get started with rendering MS Project documents:
## Step 1: Import Namespaces
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
Now that we have imported the required namespaces, let's break down each example into multiple steps for a comprehensive understanding.
## Rendering MS Project Document to HTML
To render an MS Project document to HTML format with notes included, follow these steps:
### Step 2: Set Output Directory and File Format
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### Step 3: Initialize Viewer Object and Set Options
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### Step 4: Render Document to HTML
```csharp
viewer.View(options);
```
## Rendering MS Project Document to Image Formats
You can also render MS Project documents to image formats like JPG and PNG. Here's how:
### Step 5: Set Output Directory and File Format for JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### Step 6: Initialize Viewer Object and Set JPG Options
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Step 7: Render Document to JPG
```csharp
viewer.View(options);
```
Repeat similar steps for rendering to PNG and other image formats.
## Rendering MS Project Document to PDF
To render an MS Project document to PDF format, proceed as follows:
### Step 8: Set Output Directory and File Format for PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### Step 9: Initialize Viewer Object and Set PDF Options
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### Step 10: Render Document to PDF
```csharp
viewer.View(options);
```

## Conclusion
Congratulations! You have successfully learned how to render MS Project documents and adjust time units using GroupDocs.Viewer for .NET. Incorporate this knowledge into your projects to enhance document viewing capabilities.
## FAQ's
### Can I render MS Project documents to other formats apart from HTML, images, and PDF?
Yes, GroupDocs.Viewer for .NET supports rendering to various formats such as DOCX, XLSX, PPTX, and more.
### Is there a trial version available for GroupDocs.Viewer for .NET?
Yes, you can get a free trial from [here](https://releases.groupdocs.com/).
### How can I get temporary licensing for GroupDocs.Viewer for .NET?
Visit [this link](https://purchase.groupdocs.com/temporary-license/) to obtain a temporary license.
### Where can I find documentation for GroupDocs.Viewer for .NET?
Refer to the documentation [here](https://tutorials.groupdocs.com/viewer/net/).
### Where can I seek support or ask questions related to GroupDocs.Viewer for .NET?
You can visit the support forum [here](https://forum.groupdocs.com/c/viewer/9).
