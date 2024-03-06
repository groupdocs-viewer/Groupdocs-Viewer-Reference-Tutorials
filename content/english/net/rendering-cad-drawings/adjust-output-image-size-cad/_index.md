---
title: Adjust Output Image Size for CAD Drawings
linktitle: Adjust Output Image Size for CAD Drawings
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 15
url: /net/rendering-cad-drawings/adjust-output-image-size-cad/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.AdvancedUsage.Rendering.RenderingOptionsByDocumentType.RenderingCadDrawings
{
    /// <summary>
    /// This example demonstrates how to adjust output image size when rendering CAD drawings.
    /// </summary>
    class AdjustOutputImageSize
    {
        public static void Run()
        {
            string outputDirectory = "Your Document Directory";
            string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
            {
                HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
                options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);

                viewer.View(options);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}

```
