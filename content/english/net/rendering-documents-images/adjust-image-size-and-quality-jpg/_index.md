---
title: Adjust Image Size and Quality (JPG)
linktitle: Adjust Image Size and Quality (JPG)
second_title: GroupDocs.Viewer .NET API
description: Learn how to optimize image size and quality in JPEG format using Groupdocs.Viewer for .NET. Enhance your document viewing experience.
type: docs
weight: 11
url: /net/rendering-documents-images/adjust-image-size-and-quality-jpg/
---
## Introduction
Groupdocs.Viewer for .NET is a powerful library that enables developers to seamlessly integrate document viewing functionality into their .NET applications. One common requirement in document viewing applications is the ability to adjust the size and quality of images, particularly when dealing with JPEG (JPG) images. In this tutorial, we'll walk you through the process of adjusting image size and quality using Groupdocs.Viewer for .NET.
## Prerequisites
Before we begin, ensure you have the following:
1. Basic understanding of C# programming language.
2. Visual Studio installed on your system.
3. Groupdocs.Viewer for .NET library installed. You can download it from [here](https://releases.groupdocs.com/viewer/net/).

## Import Namespaces
First, you need to import the necessary namespaces into your C# code. These namespaces provide access to the classes and methods required for working with Groupdocs.Viewer.
## Step 1: Import Namespaces
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Now, let's break down the example code provided into multiple steps for a better understanding.
## Step 2: Set Output Directory and Page File Path Format
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
In this step, we specify the output directory where the rendered images will be saved and define the format for the file path of each page image.
## Step 3: Initialize Viewer and Configure JPG View Options
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
Here, we initialize the Viewer object with the path to the document to be viewed. Then, we create an instance of JpgViewOptions and set the desired width and height for the JPEG images.
## Step 4: Render Source Document
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Finally, we print a message indicating the successful rendering of the source document and the location where the output images are saved.

## Conclusion
In this tutorial, we've learned how to adjust the size and quality of JPEG images using Groupdocs.Viewer for .NET. By following the steps outlined above, you can easily incorporate this functionality into your .NET applications, providing users with optimized image viewing experience.
## FAQ's
### Can I adjust the image quality as well?
Yes, you can adjust the image quality by setting the Quality property in the JpgViewOptions.
### What document formats are supported by Groupdocs.Viewer for .NET?
Groupdocs.Viewer for .NET supports a wide range of document formats including DOCX, PDF, PPTX, XLSX, and more.
### Is Groupdocs.Viewer for .NET compatible with .NET Core?
Yes, Groupdocs.Viewer for .NET is compatible with .NET Core along with the traditional .NET Framework.
### Can I customize the output file naming format?
Yes, you can customize the output file naming format by modifying the pageFilePathFormat variable in the code.
### Does Groupdocs.Viewer for .NET support document annotations?
Yes, Groupdocs.Viewer for .NET provides comprehensive support for document annotations including text highlighting, underlining, and commenting.
