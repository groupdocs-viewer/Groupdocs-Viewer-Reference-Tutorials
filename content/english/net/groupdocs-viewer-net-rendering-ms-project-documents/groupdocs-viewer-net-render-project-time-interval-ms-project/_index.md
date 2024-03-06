---
title: Render Specific Project Time Interval (MS Project)
linktitle: Render Specific Project Time Interval (MS Project)
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 12
url: /net/groupdocs-viewer-net-rendering-ms-project-documents/groupdocs-viewer-net-render-project-time-interval-ms-project/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;

namespace GroupDocs.Viewer.Examples.CSharp.AdvancedUsage.Rendering.RenderingOptionsByDocumentType.RenderingMsProjectDocuments
{
    /// <summary>
    /// This example demonstrates how to render project document within the specified time interval.
    /// </summary>
    class RenderProjectTimeInterval
    {
        public static void Run()
        {
            string outputDirectory = "Your Document Directory";
            string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
            {
                HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);

                ProjectManagementViewInfo viewInfo = 
                    viewer.GetViewInfo(ViewInfoOptions.FromHtmlViewOptions(options)) as ProjectManagementViewInfo;

                options.ProjectManagementOptions.StartDate = viewInfo.StartDate;
                options.ProjectManagementOptions.EndDate = viewInfo.StartDate.AddDays(7);

                viewer.View(options);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}


```
