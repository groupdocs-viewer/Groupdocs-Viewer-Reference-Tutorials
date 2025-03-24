---
title: Cancel Render with Cancellation Token
linktitle: Cancel Render with Cancellation Token
second_title: GroupDocs.Viewer .NET API
description: Integrate Groupdocs.Viewer for .NET seamlessly into your .NET projects for efficient document viewing.
weight: 11
url: /net/rendering-options/cancel-render-cancellation-token/
---
## Introduction
Groupdocs.Viewer for .NET is a powerful tool designed to simplify document viewing and processing within .NET applications. Whether you're dealing with PDFs, Microsoft Office documents, or other common formats, this library offers robust functionality to seamlessly integrate document viewing capabilities into your .NET projects.
## Prerequisites
Before diving into the integration of Groupdocs.Viewer for .NET, ensure you have the following prerequisites in place:
1. Installation: Download and install the Groupdocs.Viewer for .NET library from the provided [download link](https://releases.groupdocs.com/viewer/net/).
   
2. License: Obtain a license from [Groupdocs](https://purchase.groupdocs.com/buy) to unlock the full potential of the library. Alternatively, you can start with a free trial using the [temporary license](https://purchase.groupdocs.com/temporary-license/).
   
3. Development Environment: Ensure you have a compatible development environment set up, including Visual Studio or any other .NET IDE of your choice.

## Import Namespaces
In order to utilize Groupdocs.Viewer for .NET effectively, you need to import the necessary namespaces into your project. Follow these steps:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

Now, let's break down the provided example into multiple steps for better understanding and implementation:
## Step 1: Define Output Directory
```csharp
string outputDirectory = "Your Document Directory";
```
This step sets the directory where the rendered document pages will be stored.
## Step 2: Define Page File Path Format
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
Here, we define the format for the file paths of individual document pages.
## Step 3: Initialize CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource is used to generate CancellationToken instances that can be used to cancel asynchronous operations.
## Step 4: Obtain CancellationToken
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
This step retrieves the token from the CancellationTokenSource, which will be used to cancel the rendering operation.
## Step 5: Render Document Pages
```csharp
Task.Run(() =>
{
    using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX, new ViewerSettings(new GroupDocs.Viewer.Logging.ConsoleLogger())))
    {
        HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
        options.RenderComments = true;
        viewer.View(options, cancellationToken);
    }
}, cancellationToken);
```
Here, we initiate the rendering of document pages asynchronously using Task.Run(). The Viewer instance is created with the specified document file (SAMPLE_DOCX), and rendering options are configured. The rendering process is then started using the View method of the Viewer class.
## Step 6: Set Render Timeout
```csharp
cancellationTokenSource.CancelAfter(10);
```
This step sets a timeout of 10 milliseconds for the rendering operation. If the operation exceeds this timeout, it will be automatically canceled.
## Step 7: Display Success Message
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
Finally, a success message is displayed indicating that the document has been rendered successfully.

## Conclusion
In this tutorial, we've covered the basics of integrating Groupdocs.Viewer for .NET into your projects. By following the steps outlined above, you can seamlessly incorporate document viewing capabilities into your .NET applications, enhancing user experience and productivity.
## FAQ's
### Is Groupdocs.Viewer for .NET compatible with all document formats?
Groupdocs.Viewer for .NET supports a wide range of document formats, including PDF, Microsoft Office documents, images, and more.
### Can I customize the appearance of the rendered document pages?
Yes, you can customize various aspects of the rendering process, including page size, quality, watermarking, and more.
### Does Groupdocs.Viewer for .NET require internet connectivity?
No, Groupdocs.Viewer for .NET operates locally within your .NET environment and does not require internet connectivity for document viewing.
### Is technical support available for Groupdocs.Viewer for .NET?
Yes, technical support is available through the [Groupdocs forum](https://forum.groupdocs.com/c/viewer/9), where you can ask questions, report issues, and interact with the community.
### Can I try Groupdocs.Viewer for .NET before purchasing?
Yes, you can start with a free trial using the provided [trial version](https://releases.groupdocs.com/).
