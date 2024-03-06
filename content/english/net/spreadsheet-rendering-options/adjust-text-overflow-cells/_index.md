---
title: Adjust Text Overflow in Cells
linktitle: Adjust Text Overflow in Cells
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 10
url: /net/spreadsheet-rendering-options/adjust-text-overflow-cells/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.AdvancedUsage.Rendering.RenderingOptionsByDocumentType.RenderingSpreadsheets
{
    /// <summary>
    /// This example demonstrates how to hide text that overflows cells.
    /// </summary>
    class AdjustTextOverflowInCells
    {
        public static void Run()
        {
            string outputDirectory = "Your Document Directory";
            string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XLSX_WITH_TEXT_OVERFLOW))
            {
                HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
                options.SpreadsheetOptions.TextOverflowMode = TextOverflowMode.HideText;

                viewer.View(options);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}


```
