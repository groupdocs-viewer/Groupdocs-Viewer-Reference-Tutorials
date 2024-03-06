---
title: Enable Layered Rendering in PDF
linktitle: Enable Layered Rendering in PDF
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 15
url: /net/pdf-rendering-options/enable-layered-rendering-pdf/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.AdvancedUsage.Rendering.RenderingOptionsByDocumentType.RenderingPdfDocuments
{
    /// <summary>
    /// This example demonstrates how to render PDF document and place content according to Z-Index of the content in source PDF document.
    /// </summary>
    class EnableLayeredRendering
    {
        public static void Run()
        {
            string outputDirectory = "Your Document Directory";
            string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
            {
                HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
                options.PdfOptions.EnableLayeredRendering = true;

                viewer.View(options, 1);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}


```
