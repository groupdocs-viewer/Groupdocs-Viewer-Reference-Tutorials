---
title: Render Responsive HTML
linktitle: Render Responsive HTML
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 13
url: /net/rendering-documents-html/render-responsive-html/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.BasicUsage.RenderDocumentToHtml
{
    /// <summary>
    /// This example demonstrates how to render document into responsive HTML.
    /// </summary>
    class RenderToResponsiveHtml
    {
        public static void Run()
        {                       
            string outputDirectory = "Your Document Directory";
            string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
            {
                HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
                options.RenderResponsive = true;                

                viewer.View(options);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}

```
