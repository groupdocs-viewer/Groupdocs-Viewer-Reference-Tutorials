---
title: Adjust Page Size When Rendering Email Messages
linktitle: Adjust Page Size When Rendering Email Messages
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 10
url: /net/rendering-email-messages/adjust-page-size-email/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.AdvancedUsage.Rendering.RenderingOptionsByDocumentType.RenderingEMailMessages
{
    /// <summary>
    /// This example demonstrates how to change page size when rendering email messages.
    /// </summary>
    class AdjustPageSize
    {
        public static void Run()
        {
            string outputDirectory = "Your Document Directory";
            string filePath = Path.Combine(outputDirectory, "output.pdf");

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
            {
                PdfViewOptions options = new PdfViewOptions(filePath);
                options.EmailOptions.PageSize = PageSize.A4;

                viewer.View(options);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}
```
