---
title: Render with Embedded or External Resources
linktitle: Render with Embedded or External Resources
second_title: GroupDocs.Viewer .NET API
description: Enhance .NET document viewing with GroupDocs.Viewer for seamless rendering. Follow our tutorial for efficient integration and superior user experience.
weight: 12
url: /net/rendering-documents-html/render-html-resources/
---

# Render with Embedded or External Resources

## Introduction

In the world of .NET development, efficient document viewing is a crucial aspect of many applications. GroupDocs.Viewer for .NET provides a powerful solution for rendering documents with embedded or external resources. In this tutorial, we'll explore how to utilize GroupDocs.Viewer to render documents seamlessly, breaking down each step for clarity and understanding.

## Prerequisites

Before diving into the tutorial, ensure you have the following prerequisites:

1. Basic Understanding of .NET Development: Familiarity with C# programming language and .NET framework is necessary.
2. Installation of GroupDocs.Viewer for .NET: Download and install GroupDocs.Viewer for .NET from [here](https://releases.groupdocs.com/viewer/net/).
3. Document File to Render: Prepare a sample document file (e.g., DOCX, PDF) for rendering.

## Import Namespaces

Firstly, let's import the necessary namespaces for our .NET project:

```csharp
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;
using System.IO;
```

Now, let's break down the process of rendering a document with embedded or external resources into manageable steps:

## Step 1: Define Output Directory

```csharp
string outputDirectory = "Your Document Directory";
```

Specify the directory where you want the rendered HTML pages to be saved.

## Step 2: Define Page File Path Format

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

Set the format for the file path where each rendered page will be saved. `{0}` is a placeholder for page number.

## Step 3: Initialize Viewer Instance

```csharp
using (Viewer viewer = new Viewer("YourDocumentFilePath"))
{
    // Viewer initialization code goes here
}
```

Create a Viewer instance by passing the path of the document file to be rendered.

## Step 4: Configure HTML View Options

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

Configure HTML view options, specifying the format for embedded resources and page file path format.

## Step 5: Render Document

```csharp
viewer.View(options);
```

Invoke the `View` method on the Viewer instance, passing the configured HTML view options.

## Step 6: Display Output Directory Path

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in: {outputDirectory}");
```

Print a message indicating successful rendering along with the path of the output directory.

## Conclusion

GroupDocs.Viewer for .NET simplifies the process of rendering documents with embedded or external resources, enhancing document viewing capabilities in .NET applications. By following the steps outlined in this tutorial, developers can seamlessly integrate document rendering functionality into their projects, providing users with a smooth and efficient document viewing experience.

## FAQ's

### Q: Is GroupDocs.Viewer for .NET compatible with various document formats?

A: Yes, GroupDocs.Viewer supports a wide range of document formats, including DOCX, PDF, XLSX, and more.

### Q: Can I customize the rendering options according to my requirements?

A: Absolutely, GroupDocs.Viewer provides extensive options for configuring the rendering process to meet specific needs.

### Q: Is there a free trial available for GroupDocs.Viewer for .NET?

A: Yes, you can avail of a free trial from [here](https://releases.groupdocs.com/).

### Q: How can I get support or assistance with GroupDocs.Viewer integration?

A: You can seek help from the GroupDocs.Viewer community forum [here](https://forum.groupdocs.com/c/viewer/9).

### Q: Are temporary licenses available for testing purposes?

A: Yes, temporary licenses can be obtained from [here](https://purchase.groupdocs.com/temporary-license/).
