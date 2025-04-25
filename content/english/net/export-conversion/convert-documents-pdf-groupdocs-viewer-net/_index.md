---
title: "How to Convert Documents to PDF Using GroupDocs Viewer for .NET (With Stream Handling)"
description: "Learn how to efficiently convert documents like DOCX to PDF using GroupDocs.Viewer in .NET, including handling file streams."
date: "2025-04-25"
weight: 1
url: "/net/export-conversion/convert-documents-pdf-groupdocs-viewer-net/"
keywords:
- GroupDocs.Viewer
- Net
- Document Processing

---


# How to Convert Documents to PDF Using GroupDocs Viewer for .NET

## Introduction

Transforming documents into PDF format is a common task in .NET applications. Whether you're working with DOCX files or other document types, using GroupDocs.Viewer for .NET simplifies this process by offering seamless conversion and stream handling capabilities. This guide will walk you through converting documents to PDFs and retrieving them as streams.

**What You'll Learn:**
- Converting documents to PDF format with GroupDocs.Viewer
- Implementing custom MemoryStream in C# using GroupDocs interfaces
- Writing PDF files from streams

## Prerequisites
Before starting the conversion process, ensure you have:

### Required Libraries and Dependencies:
- **GroupDocs.Viewer for .NET**: Essential for document viewing and conversion.

### Environment Setup Requirements:
- A C# development environment (.NET Framework or .NET Core/5+).
- Visual Studio installed on your machine.

### Knowledge Prerequisites:
- Basic understanding of C# programming.
- Familiarity with file I/O operations in .NET.

## Setting Up GroupDocs.Viewer for .NET
Install the GroupDocs.Viewer package via NuGet or .NET CLI:

**NuGet Package Manager Console:**
```shell
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**\.NET CLI:**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### License Acquisition Steps:
1. **Free Trial**: Start with a free trial to explore features.
2. **Temporary License**: Apply for extended access if needed.
3. **Purchase**: Consider purchasing for full feature access.

Initialize GroupDocs.Viewer like this:
```csharp
using GroupDocs.Viewer;

// Initialize the Viewer object with your document path
using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY\sample.docx"))
{
    // Your conversion logic will go here
}
```

## Implementation Guide
### Convert Document to PDF and Retrieve Stream
#### Overview
This feature demonstrates converting a document into PDF format and retrieving the resulting file as a stream, ideal for dynamic content delivery.

##### Step 1: Initialize Viewer with Document Path
Create an instance of `Viewer` using your document's path:
```csharp
using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY\sample.docx"))
{
    // Conversion logic follows
}
```

##### Step 2: Implement Custom MemoryStream Factory
Implement the `MemoryStream` factory to capture output as a stream:
```csharp
class MemoryFileStreamFactory : IFileStreamFactory
{
    public MemoryStream Stream { get; }

    public MemoryFileStreamFactory()
    {
        Stream = new MemoryStream();
    }

    public Stream CreateFileStream()
    	=> Stream;

    public void ReleaseFileStream(Stream fileStream)
    {
        // Do not dispose to retain stream data until explicit disposal
    }
}
```

##### Step 3: Set Up PDF Rendering Options
Configure `PdfViewOptions` with the custom stream factory:
```csharp
MemoryFileStreamFactory streamFactory = new MemoryFileStreamFactory();
PdfViewOptions options = new PdfViewOptions(streamFactory);
viewer.View(options);
```

##### Step 4: Retrieve and Save the PDF Stream
Access the resulting PDF stream and optionally save it to a file:
```csharp
MemoryStream pdfStream = streamFactory.Stream;
using (FileStream outputFileStream = new FileStream("YOUR_OUTPUT_DIRECTORY\output.pdf\
