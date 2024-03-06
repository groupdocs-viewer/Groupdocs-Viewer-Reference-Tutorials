---
title: Load Documents with Specific Encoding
linktitle: Load Documents with Specific Encoding
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 11
url: /net/advanced-loading/load-documents-encoding/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using System.Text;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.AdvancedUsage.Loading
{
    /// <summary>
    /// This example demonstrates how to specify encoding.
    /// </summary>
    class LoadDocumentsWithEncoding
    {
        public static void Run()
        {
            string filePath = TestFiles.SAMPLE_TXT_SHIFT_JS_ENCODED;
            string outputDirectory = "Your Document Directory";
            string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

            LoadOptions loadOptions = new LoadOptions
            {
                Encoding = Encoding.GetEncoding("shift_jis")
            };

            using (Viewer viewer = new Viewer(filePath, loadOptions))
            {
                HtmlViewOptions options =
                    HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);

                viewer.View(options);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}


```
