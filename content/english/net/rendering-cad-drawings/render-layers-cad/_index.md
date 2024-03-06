---
title: Render Layers in CAD Drawings
linktitle: Render Layers in CAD Drawings
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 13
url: /net/rendering-cad-drawings/render-layers-cad/
---

## Complete Source Code
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;

namespace GroupDocs.Viewer.Examples.CSharp.AdvancedUsage.Rendering.RenderingOptionsByDocumentType.RenderingCadDrawings
{
    /// <summary>
    /// This example demonstrates how to render layers.
    /// </summary>
    class RenderLayers
    {
        public static void Run()
        {
            string outputDirectory = "Your Document Directory";
            string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
            {              
                HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
                options.CadOptions.Layers = new List<Layer>
                {
                    new Layer("QUADRANT")
                };

                viewer.View(options);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}

```
