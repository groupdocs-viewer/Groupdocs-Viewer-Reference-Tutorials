---
title: Disable Font License Verifications in PDF
linktitle: Disable Font License Verifications in PDF
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 12
url: /net/pdf-rendering-options/disable-font-license-verifications-pdf/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.AdvancedUsage.Rendering.RenderingOptionsByDocumentType.RenderingPdfDocuments
{
    /// <summary>
    /// This example demonstrates how to render XPS/OXPS document with embedded font license restrictions
    /// </summary>

    class DisableFontLicenseVerifications
    {
        public static void Run()
        {
            string outputDirectory = "Your Document Directory";
            string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");

            using (Viewer viewer = new Viewer(TestFiles.OXPS_EMBEDDED_FONT))
            {
                HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
                options.PdfOptions.DisableFontLicenseVerifications = true;
                viewer.View(options);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}

```
