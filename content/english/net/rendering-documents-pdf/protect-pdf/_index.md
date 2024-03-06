---
title: Protect Rendered PDF with Password
linktitle: Protect Rendered PDF with Password
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 12
url: /net/rendering-documents-pdf/protect-pdf/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.BasicUsage.RenderDocumentToPdf
{
    /// <summary>
    /// This example demonstrates how to protect output PDF document.
    /// </summary>
    class ProtectPdfDocument
    {
        public static void Run()
        {
            string outputDirectory = "Your Document Directory";
            string filePath = Path.Combine(outputDirectory, "output.pdf");

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
            {
                Security security = new Security
                {
                    DocumentOpenPassword = "o123",
                    PermissionsPassword = "p123",
                    Permissions = Permissions.AllowAll ^ Permissions.DenyPrinting
                };

                PdfViewOptions options = new PdfViewOptions(filePath)
                {
                    Security = security
                };

                viewer.View(options);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}
```
