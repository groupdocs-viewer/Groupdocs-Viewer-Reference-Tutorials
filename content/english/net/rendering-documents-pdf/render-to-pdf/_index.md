---
title: Render Document to PDF
linktitle: Render Document to PDF
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 10
url: /net/rendering-documents-pdf/render-to-pdf/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.BasicUsage.RenderDocumentToPdf
{
    /// <summary>
    /// This example demonstrates how to render document into PDF file.              
    /// </summary>
    class RenderToPdf
    {
        public static void Run()
        {
            string outputDirectory = "Your Document Directory";
            string outputFilePath = Path.Combine(outputDirectory, "output.pdf");

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
            {
                PdfViewOptions options = new PdfViewOptions(outputFilePath);
                viewer.View(options);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }        
    }
}

```
