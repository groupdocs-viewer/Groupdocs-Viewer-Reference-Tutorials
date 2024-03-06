---
title: Render with Text Overlaid for Display
linktitle: Render with Text Overlaid for Display
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 13
url: /net/rendering-documents-images/render-with-text-overlay/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.BasicUsage.RenderDocumentToImage
{
    /// <summary>
    /// This example demonstrates how to render document so extracted text may be placed as top layer over the image.
    /// </summary>
    class RenderForDisplayWithText
    {
        public static void Run()
        {
            string outputDirectory = "Your Document Directory";
            string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
            {
                PngViewOptions options = new PngViewOptions(pageFilePathFormat);
                options.ExtractText = true;

                viewer.View(options);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}

```
