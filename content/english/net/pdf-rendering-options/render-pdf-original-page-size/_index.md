---
title: Render PDF with Original Page Size
linktitle: Render PDF with Original Page Size
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 17
url: /net/pdf-rendering-options/render-pdf-original-page-size/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.AdvancedUsage.Rendering.RenderingOptionsByDocumentType.RenderingPdfDocuments
{
    /// <summary>
    /// This example demonstrates how to render pages to PNG and set page size to be the same as size of pages in a source document.
    /// </summary>
    class RenderOriginalPageSize
    {
        public static void Run()
        {
            string outputDirectory = "Your Document Directory";
            string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
            {
                PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
                viewOptions.PdfOptions.RenderOriginalPageSize = true;

                viewer.View(viewOptions);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}


```
