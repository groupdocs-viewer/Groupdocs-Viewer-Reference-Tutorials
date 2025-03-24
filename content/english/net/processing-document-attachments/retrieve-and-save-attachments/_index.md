---
title: Retrieve and Save Document Attachments
linktitle: Retrieve and Save Document Attachments
second_title: GroupDocs.Viewer .NET API
description: Efficiently manage document attachments within .NET applications using GroupDocs.Viewer. Retrieve and save attachments hassle-free.
weight: 12
url: /net/processing-document-attachments/retrieve-and-save-attachments/
---
## Introduction
In the digital era, efficient document handling is crucial for businesses and individuals alike. Whether it's managing emails, viewing contracts, or accessing reports, having a reliable tool for document visualization is essential. GroupDocs.Viewer for .NET emerges as a robust solution, empowering users to effortlessly view and interact with various document formats directly within their .NET applications.
## Prerequisites
Before delving into utilizing GroupDocs.Viewer for .NET for document attachment retrieval and saving, ensure you have the following prerequisites:
1. Operating Environment: A working environment set up with .NET framework.
2. Installation: GroupDocs.Viewer for .NET library downloaded and installed. You can access the library from the [download link](https://releases.groupdocs.com/viewer/net/).
3. Basic Understanding: Familiarity with C# programming language.
4. Document Source: Access to a sample document with attachments for demonstration purposes.

## Import Namespaces
To begin utilizing GroupDocs.Viewer for .NET for document attachment retrieval and saving, import the necessary namespaces:
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Results;
```

## Step 1: Define Output Directory
```csharp
string outputDirectory = "Your Document Directory";
```
Define the directory where you want to save the attachments retrieved from the document.
## Step 2: Instantiate Viewer Object
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
Instantiate the Viewer object with the path to the document containing attachments.
## Step 3: Retrieve Attachments
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
Retrieve a list of attachments present in the document.
## Step 4: Save Attachments
```csharp
foreach(Attachment attachment in attachments)
{
    string filePath = Path.Combine(outputDirectory, attachment.FileName);  
    viewer.SaveAttachment(attachment, File.OpenWrite(filePath)); 
}
```
Iterate through each attachment, define the file path, and save the attachment to the specified directory.
## Step 5: Display Success Message
```csharp
Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
```
Display a success message indicating the successful saving of attachments along with the directory path.

## Conclusion
Incorporating GroupDocs.Viewer for .NET into your document handling workflows streamlines the process of managing attachments, offering efficiency and convenience. By following the step-by-step guide outlined above, users can seamlessly retrieve and save document attachments within their .NET applications.
## FAQ's
### Can GroupDocs.Viewer for .NET handle various document formats?
Yes, GroupDocs.Viewer supports a wide range of document formats, including PDF, Microsoft Office documents, images, and more.
### Is there a free trial available for GroupDocs.Viewer for .NET?
Yes, you can access the free trial from [here](https://releases.groupdocs.com/).
### How can I obtain temporary licenses for GroupDocs.Viewer for .NET?
Temporary licenses can be acquired from [this link](https://purchase.groupdocs.com/temporary-license/).
### Where can I find documentation for GroupDocs.Viewer for .NET?
Comprehensive documentation is available [here](https://tutorials.groupdocs.com/viewer/net/).
### What support options are available for GroupDocs.Viewer for .NET?
You can seek assistance from the community forum [here](https://forum.groupdocs.com/c/viewer/9).
