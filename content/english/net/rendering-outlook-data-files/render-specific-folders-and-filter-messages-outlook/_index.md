---
title: Render Specific Folders and Filter Messages (Outlook)
linktitle: Render Specific Folders and Filter Messages (Outlook)
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 11
url: /net/rendering-outlook-data-files/render-specific-folders-and-filter-messages-outlook/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.AdvancedUsage.Rendering.RenderingOptionsByDocumentType.RenderingOutlookDataFiles
{
    /// <summary>
    /// This example demonstrates how to render messages from Inbox folder of Outlook data file.
    /// </summary>
    class RenderOutlookDataFileFolder
    {
        public static void Run()
        {
            string outputDirectory = "Your Document Directory";
            string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST_SUBFOLDERS))
            {
                HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
                options.OutlookOptions.Folder = "Входящие";

                viewer.View(options);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}


```
