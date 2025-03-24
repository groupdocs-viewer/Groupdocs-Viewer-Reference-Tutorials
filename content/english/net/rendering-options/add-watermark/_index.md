---
title: Add Watermark in Document
linktitle: Add Watermark in Document
second_title: GroupDocs.Viewer .NET API
description: Learn how to seamlessly add watermarks to documents using GroupDocs.Viewer for .NET. Enhance document security and branding with this easy-to-follow tutorial.
weight: 10
url: /net/rendering-options/add-watermark/
---
## Introduction
In today's digital age, managing and viewing various document formats seamlessly is a necessity for many businesses and individuals alike. Fortunately, with tools like GroupDocs.Viewer for .NET, handling documents becomes a breeze. This powerful .NET library enables developers to effortlessly integrate document viewing functionality into their applications, allowing users to view documents without needing the original software that created them.
## Prerequisites
Before diving into using GroupDocs.Viewer for .NET to add watermarks to documents, ensure you have the following:
1. Environment Setup: Have a development environment set up with .NET Framework or .NET Core installed.
2. GroupDocs.Viewer for .NET: Download and install GroupDocs.Viewer for .NET library from the [download page](https://releases.groupdocs.com/viewer/net/).
3. Document Files: Prepare the document files you want to work with, such as DOCX, PDF, or others.
4. Basic Knowledge of C#: Familiarity with C# programming language is necessary to implement the code examples.

## Import Namespaces
Before starting to add watermarks to documents using GroupDocs.Viewer for .NET, make sure to import the required namespaces in your C# code. This step allows you to access the classes and methods provided by the library seamlessly.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Now, let's walk through the process of adding a watermark to a document using GroupDocs.Viewer for .NET. Follow these steps to seamlessly integrate watermarking functionality into your application.
## Step 1: Set Output Directory
```csharp
string outputDirectory = "Your Document Directory";
```
Specify the directory where you want the output files to be saved after applying the watermark.
## Step 2: Define Page File Path Format
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Set the format for the file paths of the rendered pages. In this example, HTML files with page numbers will be generated.
## Step 3: Instantiate Viewer Object
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    // Code continues in the next step...
}
```
Create an instance of the Viewer class, passing the path to the document file as a parameter. In this example, we're using a sample DOCX file.
## Step 4: Configure HTML View Options
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
Configure the HTML view options, including the watermark text that you want to add to the document.
## Step 5: View Document with Watermark
```csharp
viewer.View(options);
```
Invoke the View method of the Viewer object, passing the configured options. This will render the document with the specified watermark.
## Step 6: Display Output Directory Path
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Inform the user about the successful rendering of the document and indicate the directory where the output files are saved.

## Conclusion
GroupDocs.Viewer for .NET provides a convenient way to add watermarks to documents programmatically. By following the steps outlined in this tutorial, you can seamlessly integrate watermarking functionality into your .NET applications, enhancing document security and branding.
## FAQ's
### Can I customize the appearance of the watermark?
Yes, you can customize various properties of the watermark, such as text, font, color, size, and position.
### Does GroupDocs.Viewer support viewing documents from remote sources?
Yes, GroupDocs.Viewer supports viewing documents from local storage as well as remote URLs.
### Is there a trial version available for GroupDocs.Viewer for .NET?
Yes, you can download a free trial version from [here](https://releases.groupdocs.com/).
### Can I add watermarks to multiple pages of a document?
Absolutely, GroupDocs.Viewer allows adding watermarks to individual pages or all pages of a document.
### How can I get support or assistance if I encounter any issues?
You can seek help and support from the GroupDocs community forums [here](https://forum.groupdocs.com/c/viewer/9).
