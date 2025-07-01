---
title: "Set DateTime Format & Time Zone for Email Rendering in .NET"
description: "Learn how to set the DateTime format and time zone offset when rendering email messages to HTML in your .NET applications using GroupDocs.Viewer."
weight: 11
url: "/net/rendering-email-messages/set-date-time-format-offset-email/"
keywords:
- set datetime format email .net
- groupdocs.viewer for .net
- .net email rendering
- time zone offset email

---

## Introduction

**GroupDocs.Viewer for .NET** is a powerful tool that enables developers to seamlessly integrate document viewing capabilities into their .NET applications. With GroupDocs.Viewer, you can display a wide range of document formats, including PDFs, Microsoft Office documents, images, and more, directly within your application without the need for any external plugins or viewers. In this comprehensive tutorial, we will guide you through the process of setting up GroupDocs.Viewer for .NET, exploring its features, and demonstrating how to utilize it effectively to enhance your application's document viewing capabilities.

## Prerequisites

Before you begin, ensure you have the following:
*   A working knowledge of C# and .NET development.
*   **.NET SDK:** Installed on your machine.
*   **GroupDocs.Viewer for .NET:** Download the library [here](https://releases.groupdocs.com/viewer/net/).
*   **IDE:** Visual Studio or any other .NET development environment.
*   **Sample Email File:** An EML file for testing purposes.

## Import Namespaces

To utilize GroupDocs.Viewer for .NET effectively, you need to import the necessary namespaces into your project.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Let's break down the provided example into multiple steps to understand each component and its functionality.

## Step 1: Define Output Directory and File Path

First, define the directory where the rendered document will be saved and specify the file path for the output HTML file.

```csharp
string outputDirectory = "Your Document Directory";
string outputFilePath = Path.Combine(outputDirectory, "output.html");
```
**Note:** Replace `"Your Document Directory"` with the actual path.

## Step 2: Initialize Viewer and Configure HTML View Options

Create a new instance of the `Viewer` class, passing the path of the document to be viewed. Then, configure the `HtmlViewOptions` for the document rendering.

```csharp
using (Viewer viewer = new Viewer("SAMPLE.eml"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(outputFilePath);
    
    // The rest of the configuration will go here
}
```
**Note:** Replace `"SAMPLE.eml"` with the path to your email file.

## Step 3: Set DateTime Format and Time Zone Offset

Customize the date and time format for the email messages and set the time zone offset according to your desired time zone.

```csharp
// Inside the using block
options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);
```
In this example, we are setting the time zone offset to UTC+1.

## Step 4: Render the Document

Finally, call the `View` method of the `Viewer` object, passing the configured HTML view options to render the document into HTML format.

```csharp
// Inside the using block
viewer.View(options);
```

## Step 5: Display Output Directory

Display a message indicating the successful rendering of the document and provide the path to the output directory where the rendered HTML document is located.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion

GroupDocs.Viewer for .NET offers a robust solution for integrating document viewing capabilities into your .NET applications. By following the steps outlined in this tutorial, you can easily set up GroupDocs.Viewer, import the necessary namespaces, and utilize its features to render documents with customizable options. Whether you are working with PDFs, Microsoft Office documents, or other formats, GroupDocs.Viewer simplifies the process of document viewing, enhancing the user experience of your applications.

## FAQs

### Is GroupDocs.Viewer compatible with .NET Core?
Yes, GroupDocs.Viewer for .NET supports .NET Core, enabling cross-platform compatibility for your applications.

### Can I customize the appearance of the rendered documents?
Absolutely! GroupDocs.Viewer provides various customization options, including zoom levels, page rotation, and more, to tailor the viewing experience according to your preferences.

### Is there a trial version available for testing purposes?
Yes, you can download a [free trial](https://releases.groupdocs.com/) of GroupDocs.Viewer for .NET from the official website to evaluate its features before making a purchase.

### Does GroupDocs.Viewer support rendering password-protected documents?
Yes, GroupDocs.Viewer has built-in support for rendering password-protected documents, ensuring secure document viewing within your applications.

### Where can I find additional support or assistance with GroupDocs.Viewer?
For any technical queries or assistance, you can visit the [GroupDocs.Viewer forum](https://forum.groupdocs.com/c/viewer/9) or reach out to their support team for prompt help and guidance.
