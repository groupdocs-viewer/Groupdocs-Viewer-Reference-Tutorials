---
title: Protect Rendered PDF with Password
linktitle: Protect Rendered PDF with Password
second_title: GroupDocs.Viewer .NET API
description: Protect your rendered PDFs with passwords easily using Groupdocs.Viewer for .NET. Keep your documents secure and confidential.
weight: 12
url: /net/rendering-documents-pdf/protect-pdf/
---

# Protect Rendered PDF with Password

## Introduction
In this tutorial, you'll learn how to use Groupdocs.Viewer for .NET to protect a rendered PDF with a password. By adding security measures, you can control access to your PDF documents, ensuring confidentiality and integrity.
## Prerequisites
Before you begin, ensure you have the following:
1. Groupdocs.Viewer for .NET Library: Download and install the library from the [website](https://releases.groupdocs.com/viewer/net/).
2. Development Environment: Make sure you have a working development environment set up for .NET development.

## Import Namespaces
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## Step 1: Define Output Directory and File Path
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## Step 2: Initialize Viewer Object and Set Security Options
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    Security security = new Security
    {
        DocumentOpenPassword = "o123",
        PermissionsPassword = "p123",
        Permissions = Permissions.AllowAll ^ Permissions.DenyPrinting
    };
```
## Step 3: Set PDF View Options
```csharp
    PdfViewOptions options = new PdfViewOptions(filePath)
    {
        Security = security
    };
```
## Step 4: Render Document with Security Options
```csharp
    viewer.View(options);
}
```
## Step 5: Check Rendered Document
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
By following these steps, you can protect a rendered PDF with a password using Groupdocs.Viewer for .NET. This ensures that your documents remain secure and accessible only to authorized users.

## Conclusion
Securing PDF documents is essential for maintaining confidentiality and integrity. With Groupdocs.Viewer for .NET, you can easily protect rendered PDFs with passwords, controlling access to sensitive information.

## FAQ's
### Can I protect PDFs with different levels of permissions?
Yes, you can specify different permissions for viewing, printing, copying, and more while protecting PDFs with passwords.
### Is Groupdocs.Viewer compatible with various file formats?
Absolutely! Groupdocs.Viewer supports rendering a wide range of file formats, including DOCX, XLSX, PPTX, PDF, and more.
### Can I integrate Groupdocs.Viewer into my existing .NET application?
Certainly! Groupdocs.Viewer provides APIs for seamless integration into .NET applications, offering robust document viewing capabilities.
### Does Groupdocs.Viewer offer support for cloud storage services?
Yes, Groupdocs.Viewer supports integration with popular cloud storage services like Dropbox, Google Drive, and Amazon S3, allowing you to render documents stored in the cloud.
### Is there a trial version available for Groupdocs.Viewer?
Yes, you can get started with Groupdocs.Viewer by accessing the free trial version from the [website](https://releases.groupdocs.com/).
