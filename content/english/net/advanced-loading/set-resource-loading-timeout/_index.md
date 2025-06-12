---
title: Set Resource Loading Timeout (Advanced)
linktitle: Set Resource Loading Timeout (Advanced)
second_title: GroupDocs.Viewer .NET API
description: Learn how to configure resource loading timeouts in GroupDocs.Viewer for .NET efficiently. Master document rendering with precision and stability.
weight: 13
url: /net/advanced-loading/set-resource-loading-timeout/
---

# Set Resource Loading Timeout (Advanced)

## Introduction
In the realm of .NET development, GroupDocs.Viewer provides a powerful toolset for rendering documents and images with precision and efficiency. Leveraging its capabilities requires understanding its intricacies, including setting resource loading timeouts. In this tutorial, we'll delve into the process of configuring resource loading timeouts in GroupDocs.Viewer for .NET.

![Set Resource Loading Timeout (Advanced) in GroupDocs.Viewer for .NET](/viewer/advanced-loading/set-resource-loading-timeout-img.png)

## Prerequisites
Before embarking on this tutorial, ensure you have the following prerequisites:
1. Basic Knowledge of .NET Development: Familiarity with C# programming and .NET framework fundamentals is essential.
2. Installation of GroupDocs.Viewer for .NET: Download and install GroupDocs.Viewer for .NET library from the [download page](https://releases.groupdocs.com/viewer/net/).
3. Integrated Development Environment (IDE): Have an IDE such as Visual Studio installed on your system.

## Import Namespaces
Before diving into the coding process, import the necessary namespaces:
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## Step 1: Define Output Directory
Firstly, define the directory where the rendered documents will be saved:
```csharp
string outputDirectory = "Your Document Directory";
```
Replace `"Your Document Directory"` with the path where you want to save the rendered documents.
## Step 2: Define Page File Path Format
Define the format for the file paths of individual pages:
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
This format will generate file names like `page_1.html`, `page_2.html`, etc., within the specified output directory.
## Step 3: Configure Load Options
Configure the load options, including the resource loading timeout:
```csharp
LoadOptions loadOptions = new LoadOptions
{
    ResourceLoadingTimeout = TimeSpan.FromSeconds(5)
};
```
In this example, a timeout of 5 seconds is set for resource loading.
## Step 4: Initialize Viewer Object
Initialize the `Viewer` object with the document to be rendered and the defined load options:
```csharp
using (Viewer viewer = new Viewer(TestFiles.WITH_EXTERNAL_IMAGE_DOC, loadOptions))
```
Replace `TestFiles.WITH_EXTERNAL_IMAGE_DOC` with the path to the document you want to render.
## Step 5: Configure HTML View Options
Configure HTML view options for embedded resources:
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
This configuration ensures that embedded resources like images are included in the rendered HTML.
## Step 6: Render Document
Render the document using the configured options:
```csharp
viewer.View(options);
```
This step initiates the rendering process.
## Step 7: Display Output Directory
Display a message indicating the successful rendering and the location of the output directory:
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion
Mastering resource loading timeouts in GroupDocs.Viewer for .NET is crucial for ensuring smooth document rendering processes. By following this tutorial, you've gained insights into configuring timeouts effectively, enhancing your proficiency in .NET development.
## FAQ's
### What is the significance of setting resource loading timeouts?
Setting resource loading timeouts ensures that rendering processes do not hang indefinitely, enhancing application stability.
### Can resource loading timeouts be customized based on document types?
Yes, resource loading timeouts can be adjusted based on the complexity and size of the documents being rendered.
### Are there any performance implications of setting shorter timeouts?
Shorter timeouts may lead to incomplete rendering of complex documents if resources cannot be loaded within the specified duration.
### Is GroupDocs.Viewer suitable for rendering various document formats?
Yes, GroupDocs.Viewer supports rendering a wide range of document formats including PDF, DOCX, XLSX, and more.
### Can resource loading timeouts be disabled?
While it's not recommended, resource loading timeouts can be set to a high value or disabled altogether depending on specific requirements.
