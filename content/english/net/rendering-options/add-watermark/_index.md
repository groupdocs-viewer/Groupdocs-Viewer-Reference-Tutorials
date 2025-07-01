---
title: "Add a Watermark to a Document in .NET | GroupDocs.Viewer"
description: "Learn how to seamlessly add watermarks to documents when rendering to HTML in your .NET applications using GroupDocs.Viewer. Enhance document security and branding."
weight: 10
url: "/net/rendering-options/add-watermark/"
keywords:
- add watermark .net
- groupdocs.viewer for .net
- .net document watermarking
- secure documents .net

---

## Introduction

In today's digital age, managing and viewing various document formats seamlessly is a necessity for many businesses and individuals alike. Fortunately, with tools like **GroupDocs.Viewer for .NET**, handling documents becomes a breeze. This powerful .NET library enables developers to effortlessly integrate document viewing functionality into their applications, allowing users to view documents without needing the original software that created them.

## Prerequisites

Before diving into using GroupDocs.Viewer for .NET to add watermarks to documents, ensure you have the following:
*   A working knowledge of C# and .NET development.
*   **.NET SDK:** Installed on your machine.
*   **GroupDocs.Viewer for .NET:** Download the library [here](https://releases.groupdocs.com/viewer/net/).
*   **IDE:** Visual Studio or any other .NET development environment.
*   **Document Files:** Prepare the document files you want to work with, such as DOCX, PDF, or others.

## Import Namespaces

Before starting to add watermarks to documents, make sure to import the required namespaces in your C# code. This step allows you to access the classes and methods provided by the library seamlessly.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Now, let's walk through the process of adding a watermark to a document using GroupDocs.Viewer for .NET.

## Step 1: Define Output Directory and File Path Format

First, specify the directory where you want the output files to be saved after applying the watermark and the format for the file paths of the rendered pages.

```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
**Note:** Replace `"Your Document Directory"` with the actual path.

## Step 2: Initialize Viewer and Configure HTML View Options

Create an instance of the `Viewer` class, passing the path to the document file as a parameter. Then, configure the `HtmlViewOptions`, including the watermark text you want to add.

```csharp
using (Viewer viewer = new Viewer("SAMPLE.docx"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.Watermark = new Watermark("This is a watermark");
    
    // The rendering process will go here
}
```
**Note:** Replace `"SAMPLE.docx"` with the path to your document.

## Step 3: View Document with Watermark

Invoke the `View` method of the `Viewer` object, passing the configured options. This will render the document with the specified watermark.

```csharp
// Inside the using block
viewer.View(options);
```

## Step 4: Display Output Directory Path

Finally, inform the user about the successful rendering of the document and indicate the directory where the output files are saved.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion

GroupDocs.Viewer for .NET provides a convenient way to add watermarks to documents programmatically. By following the steps outlined in this tutorial, you can seamlessly integrate watermarking functionality into your .NET applications, enhancing document security and branding.

## FAQs

### Can I customize the appearance of the watermark?
Yes, you can customize various properties of the watermark, such as text, font, color, size, and position.

### Does GroupDocs.Viewer support viewing documents from remote sources?
Yes, GroupDocs.Viewer supports viewing documents from local storage as well as remote URLs.

### Is there a trial version available for GroupDocs.Viewer for .NET?
Yes, you can download a [free trial](https://releases.groupdocs.com/) from the official website.

### Can I add watermarks to multiple pages of a document?
Absolutely, GroupDocs.Viewer allows you to add watermarks to individual pages or all pages of a document.

### How can I get support or assistance if I encounter any issues?
You can seek help and support from the [GroupDocs community forums](https://forum.groupdocs.com/c/viewer/9).
