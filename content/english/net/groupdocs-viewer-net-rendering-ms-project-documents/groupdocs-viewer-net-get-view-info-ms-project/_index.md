---
title: Get View Information for Microsoft Project Documents
linktitle: Get View Information for Microsoft Project Documents
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 10
url: /net/groupdocs-viewer-net-rendering-ms-project-documents/groupdocs-viewer-net-get-view-info-ms-project/
---

## Complete Source Code
```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;

namespace GroupDocs.Viewer.Examples.CSharp.AdvancedUsage.Rendering.RenderingOptionsByDocumentType.RenderingMsProjectDocuments
{
    /// <summary>
    /// This example demonstrates how to get view info for MS Project document.
    /// </summary>
    class GetViewInfoForProjectDocument
    {
        public static void Run()
        {
            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
            {
                ProjectManagementViewInfo info = viewer.GetViewInfo(
                    ViewInfoOptions.ForHtmlView()) as ProjectManagementViewInfo;

                Console.WriteLine("Document type is: " + info.FileType);
                Console.WriteLine("Pages count: " + info.Pages.Count);
                Console.WriteLine("Project start date: {0}", info.StartDate);
                Console.WriteLine("Project end date: {0}", info.EndDate);                
            }

            Console.WriteLine("\nView info retrieved successfully.");
        }
    }
}


```
