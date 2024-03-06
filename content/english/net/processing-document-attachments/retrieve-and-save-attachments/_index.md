---
title: Retrieve and Save Document Attachments
linktitle: Retrieve and Save Document Attachments
second_title: GroupDocs.Viewer .NET API
description: 
type: docs
weight: 12
url: /net/processing-document-attachments/retrieve-and-save-attachments/
---

## Complete Source Code
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Results;

namespace GroupDocs.Viewer.Examples.CSharp.BasicUsage.ProcessingAttachments
{
    /// <summary>
    /// This example demonstrates how to retrieve and save attachments.
    /// </summary>
    class RetrieveAndSaveDocumentAttachments
    {
        public static void Run()
        {
            string outputDirectory = "Your Document Directory";

            using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
            {
                IList<Attachment> attachments = viewer.GetAttachments();
                foreach(Attachment attachment in attachments)
                {
                    string filePath = Path.Combine(outputDirectory, attachment.FileName);  
                    viewer.SaveAttachment(attachment, File.OpenWrite(filePath)); 
                }
            }

            Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
        }
    }
}


```
