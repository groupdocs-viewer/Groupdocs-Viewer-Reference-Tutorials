---
title: Load Documents from Local Disk
linktitle: Load Documents from Local Disk
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 10
url: /net/loading-documents/loading-document-local-disk/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.AdvancedUsage.Loading.LoadingDocumentsFromDifferentSources
{
    /// <summary>
    /// This example demonstrates how to render document from local disk.
    /// </summary>
    class LoadDocumentFromLocalDisk
    {
        public static void Run()
        {
            string outputDirectory = "Your Document Directory";
            string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX)) 
            {
                HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);

                viewer.View(options);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}

```
