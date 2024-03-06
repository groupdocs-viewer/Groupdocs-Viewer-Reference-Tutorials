---
title: Adjust Image Size and Quality (JPG)
linktitle: Adjust Image Size and Quality (JPG)
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 11
url: /net/rendering-documents-images/adjust-image-size-and-quality-jpg/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.BasicUsage.RenderDocumentToImage
{
    /// <summary>
    /// This example demonstrates how to adjust size width and height of the output images.
    /// </summary>
    class AdjustImageSize
    {
        public static void Run()
        {
            string outputDirectory = "Your Document Directory";
            string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
            {
                JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
                options.Width = 600;
                options.Height = 800;

                viewer.View(options);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}

```
