---
title: Exclude Fonts from Rendered HTML
linktitle: Exclude Fonts from Rendered HTML
second_title: GroupDocs.Viewer .NET API
description: Learn how to exclude fonts from rendered HTML using GroupDocs.Viewer for .NET. Follow this step-by-step guide for seamless document display.
weight: 10
url: /net/rendering-documents-html/exclude-fonts-html/
---

# Exclude Fonts from Rendered HTML

## Introduction
GroupDocs.Viewer for .NET is a powerful document rendering library that allows developers to display over 50 document formats in their .NET applications without the need for external dependencies. In this tutorial, we'll focus on a specific feature of GroupDocs.Viewer: excluding fonts from rendered HTML output. 

![Exclude Fonts from Rendered HTML with GroupDocs.Viewer .NET](/viewer/rendering-documents-html/exclude-fonts-from-rendered-html.png)

## Prerequisites
Before you begin, ensure you have the following:
1. Basic understanding of C# and .NET development.
2. GroupDocs.Viewer for .NET installed. You can download it from [here](https://releases.groupdocs.com/viewer/net/).
3. Visual Studio or any other IDE for C# development.

## Import Namespaces
In your C# code, make sure to include the necessary namespaces:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Step 1: Define Output Directory
Set up the directory where you want the rendered HTML files to be saved.
```csharp
string outputDirectory = "Your Document Directory";
```
## Step 2: Define Page File Path Format
Specify the format for the file paths of individual pages of the rendered document.
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## Step 3: Initialize Viewer Object
Instantiate the Viewer object with the document you want to render.
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // Your code goes here
}
```
## Step 4: Set HTML View Options
Define the options for HTML rendering, including the format of embedded resources and fonts to exclude.
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## Step 5: Render Document
Pass the HTML view options to the Viewer object to render the document.
```csharp
viewer.View(options);
```
## Step 6: Output Rendered Document Location
Inform the user about the location where the rendered HTML files are saved.
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion
In this tutorial, we've learned how to use GroupDocs.Viewer for .NET to exclude fonts from rendered HTML output. By following the steps outlined above, you can customize the rendering process to meet your specific requirements, ensuring optimal display of documents in your applications.
## FAQ's
### Can I exclude multiple fonts from the rendered HTML?
Yes, you can add multiple font names to the `FontsToExclude` list in the HTML view options.
### Is GroupDocs.Viewer compatible with all .NET frameworks?
Yes, GroupDocs.Viewer supports .NET Framework 4.6.1 and higher.
### Can I render documents from remote storage locations?
Yes, GroupDocs.Viewer supports rendering documents from local storage as well as remote storage locations and streams.
### Does GroupDocs.Viewer support responsive design for HTML output?
Yes, you can enable responsive rendering by adjusting the HTML view options accordingly.
### Is technical support available for GroupDocs.Viewer?
Yes, you can seek assistance and participate in discussions on the [GroupDocs.Viewer forum](https://forum.groupdocs.com/c/viewer/9).
