---
title: Set DateTime Format and Time Zone Offset (Email)
linktitle: Set DateTime Format and Time Zone Offset (Email)
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 11
url: /net/rendering-email-messages/set-date-time-format-offset-email/
---

## Complete Source Code
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;

namespace GroupDocs.Viewer.Examples.CSharp.AdvancedUsage.Rendering.RenderingOptionsByDocumentType.RenderingEMailMessages
{
    /// <summary>
    /// This example demonstrates how to set custom date-time format and time zone offset
    /// </summary>
    class DateTimeFormatAndTimeZoneOffset
    {
        public static void Run()
        {
            string outputDirectory = "Your Document Directory";
            string filePath = Path.Combine(outputDirectory, "output.html");

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EML))
            {
                HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePath);
                options.EmailOptions.DateTimeFormat = "MM d yyyy HH:mm tt zzz";
                options.EmailOptions.TimeZoneOffset = new TimeSpan(1, 0, 0);

                viewer.View(options);
            }

            Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
        }
    }
}
```
