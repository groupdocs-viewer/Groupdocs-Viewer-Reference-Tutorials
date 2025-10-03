---
title: "Cancel Document Rendering .NET - GroupDocs Viewer Cancellation Token"
linktitle: "Cancel Render with Cancellation Token"
second_title: GroupDocs.Viewer .NET API
description: "Learn how to cancel document rendering in .NET using cancellation tokens with GroupDocs.Viewer. Complete guide with code examples, best practices, and troubleshooting tips."
keywords: "cancel document rendering .NET, cancellation token .NET, GroupDocs Viewer cancel, stop document processing, timeout document rendering C#"
weight: 11
url: /net/rendering-options/cancel-render-cancellation-token/
date: "2025-01-02"
lastmod: "2025-01-02"
categories: ["Document Processing"]
tags: ["cancellation-token", "document-rendering", "performance"]
type: docs
---
# Cancel Document Rendering .NET - Complete Cancellation Token Guide

## Introduction

Ever had a document rendering operation that's taking way too long? Or maybe you need to give users the ability to cancel a heavy processing task? You're in the right place. GroupDocs.Viewer for .NET provides robust cancellation token support that lets you gracefully stop document rendering operations whenever needed.

This isn't just about calling a cancel method – it's about building responsive applications that don't freeze up when dealing with large documents or slow systems. Whether you're processing massive PDFs, complex Excel spreadsheets, or just want to implement user-friendly cancel buttons, cancellation tokens are your best friend.

![Cancel Render with Cancellation Token with GroupDocs.Viewer .NET](/viewer/rendering-options/cancel-render-with-cancellation-token.png)

## Why Use Cancellation Tokens for Document Rendering?

Before we dive into the code, let's talk about why you'd want to cancel document rendering in the first place. It's not just a nice-to-have feature – it's often essential for good user experience.

**Performance Management**: Large documents can take minutes to render. Without cancellation, your application becomes unresponsive, and users get frustrated.

**Resource Control**: Document rendering is memory and CPU intensive. Cancellation tokens help you free up resources when operations are no longer needed.

**User Experience**: Think about web applications where users might navigate away from a page or change their mind about viewing a document. Cancellation tokens prevent unnecessary background processing.

**Timeout Scenarios**: Sometimes you need hard limits on processing time, especially in server environments where resources are shared.

## Common Use Cases

Here are the most practical scenarios where you'll want to implement cancellation tokens:

**User-Initiated Cancellation**: Adding a "Cancel" button to your UI that actually works. Users can stop long-running operations without closing the entire application.

**Automatic Timeouts**: Setting reasonable time limits for document processing to prevent runaway operations that consume too many resources.

**Navigation Events**: Cancelling rendering when users navigate away from a page or close a document viewer window.

**Batch Processing**: When processing multiple documents, you might want to cancel the entire batch if one document fails or takes too long.

## Prerequisites

Before you start implementing cancellation tokens with GroupDocs.Viewer for .NET, make sure you have these basics covered:

1. **Installation**: Download and install the GroupDocs.Viewer for .NET library from the provided [download link](https://releases.groupdocs.com/viewer/net/). The library has excellent NuGet support, so you can also install it directly through your IDE.
   
2. **License**: You'll need a license from [GroupDocs](https://purchase.groupdocs.com/buy) for production use. Don't worry though – you can start with a free trial using the [temporary license](https://purchase.groupdocs.com/temporary-license/) to test everything out.
   
3. **Development Environment**: Visual Studio or any .NET IDE that supports async/await patterns. Cancellation tokens work best with asynchronous operations, so make sure you're comfortable with basic async programming.

## Import Namespaces

Here's what you need to import to get cancellation tokens working properly with GroupDocs.Viewer:

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

The key namespace here is `System.Threading` – that's where all the cancellation token magic happens.

## Step-by-Step Implementation

Let's break down how to implement cancellation tokens in your document rendering operations. This example shows the complete workflow from setup to execution.

## Step 1: Define Output Directory
```csharp
string outputDirectory = "Your Document Directory";
```

This step sets up where your rendered document pages will be saved. Make sure this directory exists and your application has write permissions. A common mistake is forgetting to create the directory first, which will cause the rendering to fail.

## Step 2: Define Page File Path Format
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

Here we're setting up the naming pattern for individual document pages. The `{0}` placeholder gets replaced with the page number, so you'll end up with files like `page_1.html`, `page_2.html`, etc. This approach works well for most scenarios, but you might want to include timestamps or document names for more complex applications.

## Step 3: Initialize CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```

This is where the cancellation magic starts. `CancellationTokenSource` is the control center that manages cancellation requests. Think of it as the "cancel button" that you can trigger from anywhere in your code. You'll typically want to keep this reference accessible to whatever part of your UI handles the cancel action.

## Step 4: Obtain CancellationToken
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```

The token itself is what gets passed around to the actual operations. It's lightweight and thread-safe, so you can pass it to multiple operations if needed. The token doesn't do the cancelling – it just carries the cancellation signal from the source.

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

This is the core rendering operation. We're using `Task.Run()` to make sure the rendering happens asynchronously, which is crucial for maintaining UI responsiveness. Notice that we pass the cancellation token to both `Task.Run()` and `viewer.View()` – this ensures cancellation works at both the task level and the rendering level.

The `using` statement is important here because it ensures the Viewer gets properly disposed of, even if cancellation occurs. You don't want to leak resources when operations are cancelled.

## Step 6: Set Render Timeout
```csharp
cancellationTokenSource.CancelAfter(10);
```

Here we're setting an automatic timeout of 10 milliseconds. In real applications, you'd probably want something more reasonable like 30 seconds or a few minutes, depending on your typical document sizes. The short timeout in this example is just for demonstration purposes.

**Pro tip**: You can call `CancelAfter()` multiple times to extend or shorten the timeout as needed. This is useful for adaptive timeouts based on document size or user preferences.

## Step 7: Display Success Message
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

This final step confirms successful completion. In a real application, you'd probably update your UI, send notifications, or trigger the next step in your workflow.

## Performance Considerations

When implementing cancellation tokens for document rendering, keep these performance aspects in mind:

**Memory Management**: Cancelled operations should clean up their resources promptly. The GroupDocs.Viewer library handles most of this automatically, but make sure you're disposing of Viewer instances properly.

**Thread Safety**: Cancellation tokens are thread-safe by design, but your surrounding code might not be. Be careful when sharing state between the UI thread and rendering tasks.

**Partial Results**: When rendering is cancelled, you might end up with partial output files. Decide whether you want to keep these or clean them up. For user-initiated cancellations, keeping partial results often makes sense.

**Response Time**: The cancellation response time depends on where the rendering operation currently is. Page boundaries are natural cancellation points, so very large individual pages might not respond to cancellation immediately.

## Troubleshooting Common Issues

**Cancellation Not Working**: Make sure you're passing the cancellation token to the actual rendering method, not just the Task.Run wrapper. Both levels need the token for proper cancellation.

**Resources Not Cleaning Up**: Always use `using` statements or proper disposal patterns. Cancelled operations can leave resources in inconsistent states if not handled properly.

**UI Freezing**: If your UI is still freezing, double-check that you're running the rendering operation asynchronously. `Task.Run()` should handle this, but blocking calls in your UI thread can still cause problems.

**Timeout Too Short**: If operations are being cancelled too quickly, adjust your timeout values. Different document types and sizes need different timeout allowances.

**Exception Handling**: Cancelled operations throw `OperationCancelledException`. Make sure you're catching and handling these appropriately rather than treating them as errors.

## Best Practices

Here are some proven patterns for using cancellation tokens effectively with document rendering:

**Always Use Timeouts**: Even if you don't expose cancel buttons to users, implement reasonable timeouts to prevent runaway operations.

**Provide User Feedback**: When operations are cancelled, tell users what happened. Silent cancellations lead to confusion.

**Clean Up Properly**: Implement proper disposal patterns and clean up partial files when appropriate.

**Test with Large Documents**: Cancellation behavior can be very different with small vs. large documents. Test with realistic file sizes.

**Consider Batch Operations**: When processing multiple documents, decide whether cancelling one should cancel all, or allow individual cancellations.

## Advanced Scenarios

For more complex applications, you might want to implement these advanced patterns:

**Progressive Cancellation**: Cancel operations in stages, allowing critical cleanup to complete before final termination.

**Conditional Timeouts**: Adjust timeout values based on document type, size, or user preferences.

**Cancellation Callbacks**: Use `CancellationToken.Register()` to set up cleanup callbacks that run when cancellation occurs.

**Linked Tokens**: Combine multiple cancellation sources (user action + timeout + system shutdown) using `CancellationTokenSource.CreateLinkedTokenSource()`.

## Conclusion

Cancellation tokens might seem like a small feature, but they're crucial for building responsive, professional applications that handle document rendering gracefully. They're the difference between an application that freezes up on large documents and one that gives users control over their experience.

The key is to implement cancellation at multiple levels – not just the task level, but also passing tokens through to the actual rendering operations. This ensures that cancellation works quickly and cleanly, regardless of where in the process the operation currently sits.

Remember that cancellation is as much about user experience as it is about technical implementation. Users should always know what's happening and have reasonable control over long-running operations.

## FAQ's

### Is GroupDocs.Viewer for .NET compatible with all document formats?
GroupDocs.Viewer for .NET supports a wide range of document formats, including PDF, Microsoft Office documents, images, and more. The cancellation token feature works consistently across all supported formats, though rendering times will vary based on document complexity.

### Can I customize the appearance of the rendered document pages?
Yes, you can customize various aspects of the rendering process, including page size, quality, watermarking, and more. Cancellation tokens work with all rendering options, so you don't lose functionality when implementing cancellation support.

### Does GroupDocs.Viewer for .NET require internet connectivity?
No, GroupDocs.Viewer for .NET operates locally within your .NET environment and does not require internet connectivity for document viewing. This makes cancellation tokens particularly useful since you're not dealing with network timeouts or connectivity issues.

### How do I handle cancelled operations in my UI?
Cancelled operations throw `OperationCancelledException`, which you should catch and handle gracefully. Typically, you'd update your UI to show that the operation was cancelled and clean up any partial results. Don't treat cancellation as an error – it's normal operation.

### Can I adjust timeout values dynamically based on document size?
Absolutely! You can call `CancelAfter()` multiple times or create new cancellation token sources as needed. A common pattern is to estimate timeout based on document size, then adjust based on actual rendering progress.

### Is technical support available for GroupDocs.Viewer for .NET?
Yes, technical support is available through the [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9), where you can ask questions, report issues, and interact with the community. The forum has good coverage of cancellation token scenarios and troubleshooting.

### Can I try GroupDocs.Viewer for .NET before purchasing?
Yes, you can start with a free trial using the provided [trial version](https://releases.groupdocs.com/). The trial includes full cancellation token support, so you can test this functionality thoroughly before making a purchase decision.