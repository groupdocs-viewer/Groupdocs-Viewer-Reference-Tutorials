---
title: Get View Information for Outlook Data Files (PST, OST)
linktitle: Get View Information for Outlook Data Files (PST, OST)
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 10
url: /net/rendering-outlook-data-files/get-view-info-outlook-data-file/
---

## Complete Source Code
```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;

namespace GroupDocs.Viewer.Examples.CSharp.AdvancedUsage.Rendering.RenderingOptionsByDocumentType.RenderingOutlookDataFiles
{
    /// <summary>
    /// This example demonstrates how to get view info for Outlook data file.
    /// </summary>
    class GetViewInfoForOutlookDataFile
    {
        public static void Run()
        {
            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_OST_SUBFOLDERS))
            {
                ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
                OutlookViewInfo rootFolderInfo = viewer.GetViewInfo(options)
                    as OutlookViewInfo;

                Console.WriteLine("File type is: " + rootFolderInfo.FileType);
                Console.WriteLine("Pages count: " + rootFolderInfo.Pages.Count);

                foreach (string folder in rootFolderInfo.Folders)
                    Console.WriteLine(folder);
            }

            Console.WriteLine("\nView info retrieved successfully.");
        }
    }
}


```
