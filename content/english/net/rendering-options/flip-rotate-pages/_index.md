---
title: Flip and Rotate Pages
linktitle: Flip and Rotate Pages
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 12
url: /net/rendering-options/flip-rotate-pages/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.AdvancedUsage.Rendering.CommonRenderingOptions
{
    /// <summary>
    /// This example demonstrates how to rotate the first page 90-degree clockwise.
    /// </summary>
    class FlipRotatePages
    {
        public static void Run()
        {                       
            string outputDirectory = "Your Document Directory";
            string outputFilePath = Path.Combine(outputDirectory, "output.pdf");

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
            {
                PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
                viewOptions.RotatePage(1, Rotation.On90Degree);

                viewer.View(viewOptions);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}

```
