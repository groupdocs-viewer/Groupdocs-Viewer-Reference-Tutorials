---
title: Skip Rendering of Empty Rows
linktitle: Skip Rendering of Empty Rows
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 20
url: /net/spreadsheet-rendering-options/skip-rendering-empty-rows/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.AdvancedUsage.Rendering.RenderingOptionsByDocumentType.RenderingSpreadsheets
{
    /// <summary>
    /// This example demonstrates how to skip rendering of empty rows.
    /// </summary>
    class SkipRenderingOfEmptyRows
    {
        public static void Run()
        {
            string outputDirectory = "Your Document Directory";
            string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX_WITH_EMPTY_ROW))
            {
                HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
                options.SpreadsheetOptions.SkipEmptyRows = true;

                viewer.View(options);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}


```
