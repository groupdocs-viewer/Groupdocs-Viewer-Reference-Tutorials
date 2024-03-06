---
title: Specify File Type When Loading Documents
linktitle: Specify File Type When Loading Documents
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 10
url: /net/advanced-loading/specify-file-type/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.AdvancedUsage.Loading
{
    /// <summary>
    /// This example demonstrates how to specify file type when loading document.
    /// </summary>
    class SpecifyFileTypeWhenLoadingDocument
    {
        public static void Run()
        {                       
            string outputDirectory = "Your Document Directory";
            string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
            
            LoadOptions loadOptions = new LoadOptions
            {
                FileType = FileType.DOCX
            };

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX, loadOptions))
            {
                HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
                viewer.View(options);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}

```
