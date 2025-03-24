---
title: Render Single Layout in CAD Drawings
linktitle: Render Single Layout in CAD Drawings
second_title: GroupDocs.Viewer .NET API
description: Learn how to render single layout in CAD drawings using GroupDocs.Viewer for .NET. Easy steps for seamless integration in your .NET applications.
weight: 14
url: /net/rendering-cad-drawings/render-single-layout-cad/
---

# Render Single Layout in CAD Drawings

## Introduction
In the realm of .NET development, handling and viewing CAD drawings is a common requirement. GroupDocs.Viewer for .NET simplifies this task by providing a comprehensive solution for rendering CAD drawings within .NET applications. In this tutorial, we'll delve into rendering a single layout in CAD drawings using GroupDocs.Viewer for .NET.
## Prerequisites
Before diving into the tutorial, ensure you have the following prerequisites:
- Basic understanding of C# programming language and .NET framework.
- Visual Studio installed on your system.
- GroupDocs.Viewer for .NET library downloaded and tutorialsd in your project. You can download it from [here](https://releases.groupdocs.com/viewer/net/).
- Familiarity with CAD file formats and their structures.

## Import Namespaces
Firstly, import the necessary namespaces into your C# code to access GroupDocs.Viewer functionalities.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Step 1: Define Output Directory
Specify the directory where you want the rendered output to be saved.
```csharp
string outputDirectory = "Your Document Directory";
```
## Step 2: Define Page File Path Format
Define the format for the file path of each rendered page.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Step 3: Instantiate Viewer Object
Create an instance of the Viewer class provided by GroupDocs.Viewer.
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## Step 4: Configure HTML View Options
Configure options for rendering HTML output with embedded resources.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## Step 5: Specify CAD Layout Name
Specify the name of the CAD layout you want to render.
```csharp
options.CadOptions.LayoutName = "Model";
```
## Step 6: Render CAD Drawing
Invoke the View method of the Viewer object with the specified options.
```csharp
viewer.View(options);
```
## Step 7: Display Success Message
Inform the user about the successful rendering of the source document.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion
Rendering CAD drawings, especially when dealing with layouts, can be a daunting task. However, with GroupDocs.Viewer for .NET, the process becomes seamless and efficient. By following the steps outlined in this tutorial, you can effortlessly render a single layout in CAD drawings within your .NET applications.
## FAQ's
### Can I render multiple layouts simultaneously using GroupDocs.Viewer for .NET?
Yes, GroupDocs.Viewer for .NET supports rendering multiple layouts from CAD drawings.
### Is GroupDocs.Viewer compatible with different CAD file formats?
Absolutely, GroupDocs.Viewer supports a wide range of CAD file formats, including DWG, DXF, DGN, and more.
### Can I customize the rendering options for CAD drawings?
Yes, GroupDocs.Viewer provides extensive options to customize rendering settings according to your requirements.
### Is there a free trial available for GroupDocs.Viewer for .NET?
Yes, you can explore the features of GroupDocs.Viewer with a free trial available [here](https://releases.groupdocs.com/).
### Where can I get support for GroupDocs.Viewer for .NET?
For any queries or assistance, you can visit the GroupDocs.Viewer forum [here](https://forum.groupdocs.com/c/viewer/9).
