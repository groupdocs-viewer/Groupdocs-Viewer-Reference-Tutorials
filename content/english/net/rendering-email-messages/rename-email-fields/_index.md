---
title: "Rename Email Fields During Rendering in .NET | GroupDocs.Viewer"
description: "Learn how to rename email fields (From, To, Subject) when rendering email messages to HTML in your .NET applications using GroupDocs.Viewer."
weight: 12
url: "/net/rendering-email-messages/rename-email-fields/"
keywords:
- rename email fields .net
- groupdocs.viewer for .net
- .net email rendering
- customize email view

---

## Introduction

In today's digital age, managing and viewing documents efficiently is paramount for businesses and individuals alike. Whether it is contracts, reports, or emails, having the ability to navigate through these documents seamlessly can greatly enhance productivity. This is where **GroupDocs.Viewer for .NET** comes into play. This powerful library allows developers to integrate document viewing capabilities directly into their .NET applications, offering a wide range of features for rendering various document formats.

## Prerequisites

Before diving into the tutorial on renaming email fields during rendering using GroupDocs.Viewer for .NET, ensure you have the following:
*   A working knowledge of C# and .NET development.
*   **.NET SDK:** Installed on your machine.
*   **GroupDocs.Viewer for .NET:** Download the library [here](https://releases.groupdocs.com/viewer/net/).
*   **IDE:** Visual Studio or any other .NET development environment.
*   **Sample Email File:** An MSG file for testing purposes.

## Import Namespaces

To use GroupDocs.Viewer functionalities in your .NET application, you need to import the necessary namespaces.

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

Now, let's break down the process of renaming email fields during rendering using GroupDocs.Viewer for .NET into multiple steps.

## Step 1: Define Output Directory and File Path Format

First, specify the directory where the rendered HTML pages will be saved and the format for the file paths of the rendered pages.

```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
**Note:** Replace `"Your Document Directory"` with the actual path.

## Step 2: Initialize Viewer and Configure HTML View Options

Create an instance of the `Viewer` class and pass the path of the document to be viewed as a parameter. Then, configure the `HtmlViewOptions` and set up the email field mappings.

```csharp
using (Viewer viewer = new Viewer("SAMPLE.msg"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.EmailOptions.FieldTextMap[Field.From] = "Sender";
    options.EmailOptions.FieldTextMap[Field.To] = "Receiver";
    options.EmailOptions.FieldTextMap[Field.Sent] = "Date";
    options.EmailOptions.FieldTextMap[Field.Subject] = "Topic";
    
    // The rendering process will go here
}
```
**Note:** Replace `"SAMPLE.msg"` with the path to your email file.

## Step 3: Render the Document

Invoke the `View` method of the `Viewer` object, passing the configured HTML view options.

```csharp
// Inside the using block
viewer.View(options);
```

## Step 4: Display Success Message

Finally, inform the user that the document has been rendered successfully.

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion

In conclusion, GroupDocs.Viewer for .NET provides a seamless solution for rendering documents within .NET applications. By following the steps outlined in this tutorial, you can easily rename email fields during rendering, enhancing the readability and usability of email documents. With its intuitive API and comprehensive features, GroupDocs.Viewer empowers developers to streamline document viewing processes effectively.

## FAQs

### Can I render documents other than emails using GroupDocs.Viewer for .NET?
Yes, GroupDocs.Viewer supports rendering various document formats, including PDF, Microsoft Office documents, images, and more.

### Is GroupDocs.Viewer compatible with .NET Core?
Yes, GroupDocs.Viewer supports .NET Core along with the traditional .NET Framework.

### Can I customize the appearance of rendered documents?
Absolutely, GroupDocs.Viewer offers extensive customization options for controlling the appearance and behavior of rendered documents.

### Does GroupDocs.Viewer support document streaming?
Yes, GroupDocs.Viewer allows streaming documents directly to the client's browser without the need for storing them on the server.

### Is GroupDocs.Viewer suitable for enterprise-level applications?
Certainly, GroupDocs.Viewer is designed to meet the demands of enterprise-level applications with its scalability, reliability, and robust feature set.

