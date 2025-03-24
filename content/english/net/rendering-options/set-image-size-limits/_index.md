---
title: Set Image Size Limits
linktitle: Set Image Size Limits
second_title: GroupDocs.Viewer .NET API
description: Learn how to set image size limits in .NET applications effortlessly using GroupDocs.Viewer for .NET, enhancing document viewing experiences.
weight: 21
url: /net/rendering-options/set-image-size-limits/
---
## Introduction
GroupDocs.Viewer for .NET is a powerful tool designed to facilitate seamless document viewing within .NET applications. With its robust features and intuitive interface, developers can effortlessly integrate document viewing capabilities into their projects, enhancing user experience and productivity. In this tutorial, we will explore how to set image size limits using GroupDocs.Viewer for .NET, ensuring optimal display of documents while maintaining performance and efficiency.
## Prerequisites
Before diving into the tutorial, make sure you have the following prerequisites in place:
1. GroupDocs.Viewer for .NET: Ensure you have the necessary GroupDocs.Viewer for .NET library installed in your development environment. You can download it from the [website](https://releases.groupdocs.com/viewer/net/).
2. Development Environment: Set up your preferred .NET development environment, such as Visual Studio, with the required configurations.
3. Document Directory: Have a designated directory where your documents are stored, and ensure that the directory path is accessible within your application.

## Import Namespaces
Before proceeding with the implementation, it's essential to import the required namespaces to access the functionalities of GroupDocs.Viewer for .NET effectively.
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Step 1: Define Output Directory and File Path
```csharp
string outputDirectory = "Your Document Directory";
string outputFile = Path.Combine(outputDirectory, "result_image_size_limit.jpg");
```
Ensure to replace `"Your Document Directory"` with the actual path to your document directory.
## Step 2: Initialize Viewer Object and Specify Document Path
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // TestFiles.SAMPLE_DOCX represents the path to the sample document.
    // Replace it with the path to your desired document.
```
Replace `TestFiles.SAMPLE_DOCX` with the path to your document. This could be a DOCX, PDF, or any other supported file format.
## Step 3: Configure JPEG View Options
```csharp
JpgViewOptions options = new JpgViewOptions(outputFile);
options.MaxWidth = 400;
```
Adjust the `MaxWidth` property to set the maximum width of the rendered image as per your requirements. This ensures that the image does not exceed the specified width, maintaining optimal display.
## Step 4: Render Document with Specified Options
```csharp
viewer.View(options);
```
This line of code triggers the rendering process, generating the output image with the defined size limits.
## Step 5: Display Success Message
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Upon successful rendering, a message indicating the successful completion along with the output directory path is displayed.

## Conclusion
In conclusion, mastering the art of setting image size limits using GroupDocs.Viewer for .NET can significantly enhance document viewing experiences within your .NET applications. By following the step-by-step guide outlined in this tutorial, you can effortlessly optimize image display while ensuring performance and efficiency.
## FAQ's
### Can I set both maximum width and height for the rendered images?
Yes, you can set both maximum width and height using the appropriate properties in the view options.
### What document formats are supported by GroupDocs.Viewer for .NET?
GroupDocs.Viewer for .NET supports a wide range of document formats, including DOCX, PDF, PPT, XLS, and more.
### Is GroupDocs.Viewer for .NET compatible with .NET Core?
Yes, GroupDocs.Viewer for .NET offers compatibility with .NET Core, allowing seamless integration into modern .NET applications.
### Can I customize the output image format other than JPEG?
Yes, GroupDocs.Viewer for .NET provides support for various output formats, including PNG, TIFF, and PDF.
### Is there a trial version available for testing before purchasing?
Yes, you can avail of a free trial version from the [website](https://releases.groupdocs.com/viewer/net/). to explore the features and functionalities of GroupDocs.Viewer for .NET before making a purchase.
