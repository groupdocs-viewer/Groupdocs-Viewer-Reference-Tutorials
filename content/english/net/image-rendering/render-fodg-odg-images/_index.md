---
title: Render FODG and ODG Images
linktitle: Render FODG and ODG Images
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 15
url: /net/image-rendering/render-fodg-odg-images/
---

## Complete Source Code
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;


namespace GroupDocs.Viewer.Examples.CSharp.AdvancedUsage.Rendering.RenderingOptionsByDocumentType.RenderingImageFiles
{
    /// <summary>
    /// This example demonstrates how to render FODG/ODG document into HTML, JPG, PNG, PDF.
    /// </summary>
    public class RenderingFodgAndOdg
    {
        public static void Run()
        {
            string outputDirectory = "Your Document Directory";
            string pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.html");

            // TO HTML
            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
            {
                HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);

                viewer.View(options);
            }

            // TO JPG
            pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.jpg");

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
            {
                JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
                
                viewer.View(options);
            }

            // TO PNG
            pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.png");

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
            {
                PngViewOptions options = new PngViewOptions(pageFilePathFormat);
               
                viewer.View(options);
            }

            // TO PDF
            pageFilePathFormat = Path.Combine(outputDirectory, "fodg_result.pdf");

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_FODG))
            {
                PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
               
                viewer.View(options);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}

```
