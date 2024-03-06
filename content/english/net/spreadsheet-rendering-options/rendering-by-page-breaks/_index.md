---
title: Rendering by Page Breaks
linktitle: Rendering by Page Breaks
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 14
url: /net/spreadsheet-rendering-options/rendering-by-page-breaks/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.AdvancedUsage.Rendering.RenderingOptionsByDocumentType.RenderingSpreadsheets
{
    /// <summary>
    /// This example demonstrates how to render spreadsheets by page breaks.
    /// More details at https://docs.groupdocs.com/viewer/net/render-spreadsheets-by-page-breaks/
    /// </summary>
    class RenderingByPageBreaks
    {
        public static void Run()
        {
            string outputDirectory = "Your Document Directory";
            string outputFilePath = Path.Combine(outputDirectory, "output.pdf");

            using (Viewer viewer = new Viewer(TestFiles.PAGE_BREAKS_XLSX))
            {
                PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);
                viewOptions.SpreadsheetOptions = SpreadsheetOptions.ForRenderingByPageBreaks();

                // Enable rendering gird lines and headings to check that proper areas are rendered
                viewOptions.SpreadsheetOptions.RenderGridLines = true;
                viewOptions.SpreadsheetOptions.RenderHeadings = true;

                viewer.View(viewOptions);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}
```
