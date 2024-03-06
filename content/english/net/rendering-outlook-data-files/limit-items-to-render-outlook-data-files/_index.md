---
title: Limit Number of Items to Render in Outlook Data Files
linktitle: Limit Number of Items to Render in Outlook Data Files
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 12
url: /net/rendering-outlook-data-files/limit-items-to-render-outlook-data-files/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.AdvancedUsage.Rendering.RenderingOptionsByDocumentType.RenderingOutlookDataFiles
{
    /// <summary>
    /// This example demonstrates how to limit count of items when rendering Outlook data files.
    /// </summary>
    class LimitCountOfItemsToRender
    {
        public static void Run()
        {
            string outputDirectory = "Your Document Directory";
            string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST))
            {
                HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
                options.OutlookOptions.MaxItemsInFolder = 3;

                viewer.View(options);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}


```
