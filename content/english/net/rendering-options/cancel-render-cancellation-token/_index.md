---
title: "Cancel Document Rendering with a Cancellation Token in .NET"
description: "Learn how to cancel a document rendering process in your .NET applications using GroupDocs.Viewer and a CancellationToken. A step-by-step guide."
weight: 11
url: "/net/rendering-options/cancel-render-cancellation-token/"
keywords:
- cancel render .net
- groupdocs.viewer for .net
- .net document rendering
- cancellationtoken .net

---

## Introduction

**GroupDocs.Viewer for .NET** is a powerful tool designed to simplify document viewing and processing within .NET applications. Whether you are dealing with PDFs, Microsoft Office documents, or other common formats, this library offers robust functionality to seamlessly integrate document viewing capabilities into your .NET projects.

## Prerequisites

Before you begin, ensure you have the following:
*   A working knowledge of C# and .NET development.
*   **.NET SDK:** Installed on your machine.
*   **GroupDocs.Viewer for .NET:** Download the library [here](https://releases.groupdocs.com/viewer/net/).
*   **IDE:** Visual Studio or any other .NET development environment.
*   **License:** Obtain a license from [GroupDocs](https://purchase.groupdocs.com/buy) to unlock the full potential of the library. Alternatively, you can start with a [free trial](https://releases.groupdocs.com/) or a [temporary license](https://purchase.groupdocs.com/temporary-license/).

## Import Namespaces

To utilize GroupDocs.Viewer for .NET effectively, you need to import the necessary namespaces into your project.

```csharp
using System;
using System.IO;
using System.Threading;
using System.Threading.Tasks;
using GroupDocs.Viewer.Options;
```

Now, let's break down the provided example into multiple steps for better understanding and implementation.

## Step 1: Define Output Directory and Page File Path Format

First, set the directory where the rendered document pages will be stored and define the format for the file paths of individual pages.

```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
**Note:** Replace `"Your Document Directory"` with the actual path.

## Step 2: Initialize CancellationTokenSource

`CancellationTokenSource` is used to generate a `CancellationToken` that can be used to cancel asynchronous operations.

```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```

## Step 3: Render Document Pages Asynchronously

Initiate the rendering of document pages asynchronously using `Task.Run()`. The `Viewer` instance is created with the specified document file, and the rendering options are configured. The rendering process is then started using the `View` method, passing the `CancellationToken`.

```csharp
Task.Run(() =>
{
    using (Viewer viewer = new Viewer("SAMPLE.docx"))
    {
        HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
        viewer.View(options, cancellationTokenSource.Token);
    }
}, cancellationTokenSource.Token);
```
**Note:** Replace `"SAMPLE.docx"` with the path to your document.

## Step 4: Set a Render Timeout

Set a timeout for the rendering operation. If the operation exceeds this timeout, it will be automatically canceled.

```csharp
cancellationTokenSource.CancelAfter(10000); // Cancel after 10 seconds
```

## Step 5: Display Success Message

Finally, a success message is displayed, indicating that the document has been rendered successfully (if not canceled).

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## Conclusion

In this tutorial, we have covered the basics of integrating GroupDocs.Viewer for .NET into your projects and how to cancel a rendering operation using a `CancellationToken`. By following the steps outlined above, you can seamlessly incorporate document viewing capabilities into your .NET applications, enhancing user experience and productivity.

## FAQs

### Is GroupDocs.Viewer for .NET compatible with all document formats?
GroupDocs.Viewer for .NET supports a wide range of document formats, including PDF, Microsoft Office documents, images, and more.

### Can I customize the appearance of the rendered document pages?
Yes, you can customize various aspects of the rendering process, including page size, quality, watermarking, and more.

### Does GroupDocs.Viewer for .NET require an internet connection?
No, GroupDocs.Viewer for .NET operates locally within your .NET environment and does not require an internet connection for document viewing.

### Is technical support available for GroupDocs.Viewer for .NET?
Yes, technical support is available through the [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9), where you can ask questions, report issues, and interact with the community.

### Can I try GroupDocs.Viewer for .NET before purchasing?
Yes, you can start with a [free trial](https://releases.groupdocs.com/) to evaluate the library's features.

```
