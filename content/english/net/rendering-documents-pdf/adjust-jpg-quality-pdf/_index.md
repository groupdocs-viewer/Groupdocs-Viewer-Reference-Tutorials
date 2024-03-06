---
title: Adjust JPG Image Quality in Rendered PDF
linktitle: Adjust JPG Image Quality in Rendered PDF
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 11
url: /net/rendering-documents-pdf/adjust-jpg-quality-pdf/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.BasicUsage.RenderDocumentToPdf
{
    /// <summary>
    /// This example demonstrates how to adjust quality of JPG images of the output PDF document.
    /// </summary>
    class AdjustQualityOfJpgImages
    {
        public static void Run()
        {
            string outputDirectory = "Your Document Directory";
            string filePath = Path.Combine(outputDirectory, "output.pdf");

            using (Viewer viewer = new Viewer(TestFiles.JPG_IMAGE_PPTX))
            {               
                PdfViewOptions options = new PdfViewOptions(filePath);

                viewer.View(options);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}


```
