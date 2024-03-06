---
title: Adjust Image Quality in PDF
linktitle: Adjust Image Quality in PDF
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 10
url: /net/pdf-rendering-options/adjust-image-quality-pdf/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.AdvancedUsage.Rendering.RenderingOptionsByDocumentType.RenderingPdfDocuments
{
    /// <summary>
    /// This example demonstrates how to adjust quality of images contained by the source PDF document.
    /// </summary>
    class AdjustImageQuality
    {
        public static void Run()
        {
            string outputDirectory = "Your Document Directory";
            string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
            {
                HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
                options.PdfOptions.ImageQuality = ImageQuality.Medium;

                viewer.View(options);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}


```
