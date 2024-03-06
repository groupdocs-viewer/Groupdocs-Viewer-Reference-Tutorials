---
title: Render Hidden Columns and Rows
linktitle: Render Hidden Columns and Rows
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 13
url: /net/spreadsheet-rendering-options/render-hidden-columns-rows/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.AdvancedUsage.Rendering.RenderingOptionsByDocumentType.RenderingSpreadsheets
{
    /// <summary>
    /// This example demonstrates how to render hidden rows and columns.
    /// </summary>
    class RenderHiddenRowsAndColumns
    {
        public static void Run()
        {
            string outputDirectory = "Your Document Directory";
            string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX_WITH_HIDDEN_ROW_AND_COLUMN))
            {
                HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
                options.SpreadsheetOptions.RenderHiddenColumns = true;
                options.SpreadsheetOptions.RenderHiddenRows = true;

                viewer.View(options);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}


```
