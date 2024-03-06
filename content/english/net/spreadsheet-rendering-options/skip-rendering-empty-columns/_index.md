---
title: Skip Rendering of Empty Columns
linktitle: Skip Rendering of Empty Columns
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 19
url: /net/spreadsheet-rendering-options/skip-rendering-empty-columns/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.AdvancedUsage.Rendering.RenderingOptionsByDocumentType.RenderingSpreadsheets
{
    /// <summary>
    /// This example demonstrates how to skip rendering of empty columns.
    /// </summary>
    class SkipRenderingOfEmptyColumns
    {
        public static void Run()
        {
            string outputDirectory = "Your Document Directory";
            string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX_WITH_EMPTY_COLUMN))
            {
                HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
                options.SpreadsheetOptions.SkipEmptyColumns = true;

                viewer.View(options);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}


```
