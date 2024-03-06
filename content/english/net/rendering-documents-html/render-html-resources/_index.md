---
title: Render with Embedded or External Resources
linktitle: Render with Embedded or External Resources
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 12
url: /net/rendering-documents-html/render-html-resources/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.BasicUsage.RenderDocumentToHtml
{
    /// <summary>
    /// This example demonstrates how to render document into HTML with embedded resources.
    /// </summary>
    class RenderToHtmlWithEmbeddedResources
    {
        public static void Run()
        {
            string outputDirectory = "Your Document Directory";
            string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
            {                
                HtmlViewOptions options = 
                    HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);    
                
                viewer.View(options);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in: {outputDirectory}");
        }
    }
}

```
