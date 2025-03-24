---
title: Set DateTime Format and Time Zone Offset (Email)
linktitle: Set DateTime Format and Time Zone Offset (Email)
second_title: GroupDocs.Viewer .NET API
description: Integrate GroupDocs.Viewer for .NET seamlessly into your applications for powerful document viewing capabilities. Enhance user experience with customizable options.
weight: 11
url: /net/rendering-email-messages/set-date-time-format-offset-email/
---

## Introduction
GroupDocs.Viewer for .NET is a powerful tool that enables developers to seamlessly integrate document viewing capabilities into their .NET applications. With GroupDocs.Viewer, you can display a wide range of document formats including PDFs, Microsoft Office documents, images, and more directly within your application, without the need for any external plugins or viewers. In this comprehensive tutorial, we'll guide you through the process of setting up GroupDocs.Viewer for .NET, exploring its features, and demonstrating how to utilize it effectively to enhance your application's document viewing capabilities.
## Prerequisites
Before diving into this tutorial, ensure that you have the following prerequisites set up:
1. Visual Studio: Make sure you have Visual Studio installed on your system. GroupDocs.Viewer for .NET is fully compatible with Visual Studio, enabling seamless integration into your .NET projects.
2. GroupDocs.Viewer for .NET: Download and install GroupDocs.Viewer for .NET from the [download link](https://releases.groupdocs.com/viewer/net/). Follow the installation instructions provided to set up the library within your development environment.
3. .NET Framework: Ensure that you have the appropriate version of the .NET Framework installed. GroupDocs.Viewer for .NET supports various versions of the .NET Framework, including .NET Core and .NET Standard.

## Import Namespaces
In order to utilize GroupDocs.Viewer for .NET effectively, you need to import the necessary namespaces into your project. Follow these steps to import the required namespaces:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```


Let's break down the provided example into multiple steps to understand each component and its functionality.
## Step 1: Set Output Directory and File Path
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.html");
```
In this step, we define the output directory where the rendered document will be saved and specify the file path for the output HTML file.
## Step 2: Instantiate Viewer Object
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
```
Here, we create a new instance of the `Viewer` class, passing the path of the document to be viewed (in this case, a sample EML file) as a parameter.
## Step 3: Define HTML View Options
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
```
In this step, we configure the HTML view options for the document rendering, specifying the output file path for the rendered HTML document.
## Step 4: Set DateTime Format and Time Zone Offset
```csharp
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
Here, we customize the date and time format for email messages and set the time zone offset according to the desired timezone.
## Step 5: Render Document
```csharp
viewer.View(options);
```
Finally, we call the `View` method of the `Viewer` object, passing the configured HTML view options to render the document into HTML format.
## Step 6: Display Output Directory
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
This step simply displays a message indicating the successful rendering of the document and provides the path to the output directory where the rendered HTML document is located.

## Conclusion
GroupDocs.Viewer for .NET offers a robust solution for integrating document viewing capabilities into your .NET applications. By following the steps outlined in this tutorial, you can easily set up GroupDocs.Viewer, import the necessary namespaces, and utilize its features to render documents with customizable options. Whether you're working with PDFs, Microsoft Office documents, or other formats, GroupDocs.Viewer simplifies the process of document viewing, enhancing the user experience of your applications.
## FAQ's
### Is GroupDocs.Viewer compatible with .NET Core?
Yes, GroupDocs.Viewer for .NET supports .NET Core, enabling cross-platform compatibility for your applications.
### Can I customize the appearance of the rendered documents?
Absolutely! GroupDocs.Viewer provides various customization options including zoom levels, page rotation, and more to tailor the viewing experience according to your ptutorialss.
### Is there a trial version available for testing purposes?
Yes, you can download a free trial version of GroupDocs.Viewer for .NET from the [website link](https://releases.groupdocs.com/viewer/net/) to evaluate its features before making a purchase.
### Does GroupDocs.Viewer support rendering password-protected documents?
Yes, GroupDocs.Viewer has built-in support for rendering password-protected documents, ensuring secure document viewing within your applications.
### Where can I find additional support or assistance with GroupDocs.Viewer?
For any technical queries or assistance, you can visit the GroupDocs.Viewer [forum](https://forum.groupdocs.com/c/viewer/9) or reach out to their support team for prompt help and guidance.
