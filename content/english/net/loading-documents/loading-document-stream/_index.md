---
title: Load Documents from Stream
linktitle: Load Documents from Stream
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 12
url: /net/loading-documents/loading-document-stream/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.AdvancedUsage.Loading.LoadingDocumentsFromDifferentSources
{
    /// <summary>
    /// This example demonstrates how to render document from stream.
    /// </summary>
    class LoadDocumentFromStream
    {
        public static void Run()
        {
            string outputDirectory = "Your Document Directory";
            string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
            Stream stream = GetFileStream();         
            
            using (Viewer viewer = new Viewer(stream)) 
            {
                HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);

                viewer.View(options);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }

        private static Stream GetFileStream()
        {
            return File.OpenRead(TestFiles.SAMPLE_DOCX);
        }
    }
}

```
