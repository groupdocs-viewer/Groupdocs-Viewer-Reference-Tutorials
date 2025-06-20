---
title: Adjust Output Image Size for CAD Drawings
linktitle: Adjust Output Image Size for CAD Drawings
second_title: GroupDocs.Viewer .NET API
description: Learn how to adjust output image size for CAD drawings using GroupDocs.Viewer for .NET. Enhance visibility and usability effortlessly.
weight: 15
url: /net/rendering-cad-drawings/adjust-output-image-size-cad/
---

# Adjust Output Image Size for CAD Drawings

## Introduction
CAD drawings often require specific adjustments for optimal viewing and presentation. GroupDocs.Viewer for .NET provides a powerful toolset to manage and customize CAD drawings output. In this tutorial, we will guide you through the process of adjusting output image size for CAD drawings step by step.

![Adjust Output Image Size for CAD Drawings with GroupDocs.Viewer .NET](/viewer/rendering-cad-drawings/adjust-output-image-size-for-cad-drawings.png)

## Prerequisites
Before you begin, ensure you have the following prerequisites:
1. GroupDocs.Viewer for .NET: Download and install GroupDocs.Viewer for .NET from [here](https://releases.groupdocs.com/viewer/net/).
2. Document Directory: Prepare the directory where your document is located.
3. Basic Understanding: Familiarize yourself with basic concepts of .NET programming.

## Import Namespaces
First, make sure to import the necessary namespaces to access GroupDocs.Viewer functionalities:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Step 1: Set Output Directory
Define the directory where you want to store the output images of CAD drawings:
```csharp
string outputDirectory = "Your Document Directory";
```
## Step 2: Define Page File Path Format
Set the format for page file paths. This format will be used to name and save individual pages as HTML files:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Step 3: Adjust Image Size
Inside a using block for the Viewer object, adjust the image size for CAD drawings by setting appropriate options:
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## Step 4: Display Output Directory
After rendering the document, display a message indicating the successful rendering and provide the location of the output directory:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion
Adjusting the output image size for CAD drawings is crucial for enhancing their visibility and usability. With GroupDocs.Viewer for .NET, this process becomes streamlined and efficient, allowing you to customize the output according to your specific requirements.
## FAQ's
### Can I adjust the output image size for other types of documents besides CAD drawings?
Yes, GroupDocs.Viewer for .NET supports various document types, and you can adjust the output image size for most document formats.
### Is GroupDocs.Viewer for .NET compatible with different versions of the .NET framework?
Yes, GroupDocs.Viewer for .NET is compatible with multiple versions of the .NET framework, ensuring flexibility and usability across different environments.
### Are there any licensing options available for GroupDocs.Viewer for .NET?
Yes, you can explore different licensing options, including temporary licenses and commercial licenses, to suit your needs.
### Can I customize the output format of rendered documents?
Absolutely, GroupDocs.Viewer for .NET offers various customization options, allowing you to tailor the output format according to your ptutorialss.
### Where can I find additional support or assistance with GroupDocs.Viewer for .NET?
You can visit the GroupDocs.Viewer forum [here](https://forum.groupdocs.com/c/viewer/9) to get support, ask questions, and engage with the community.
