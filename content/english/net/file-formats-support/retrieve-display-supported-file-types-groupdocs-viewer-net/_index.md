---
title: "Retrieve and Display Supported File Types in .NET Using GroupDocs.Viewer"
description: "Learn how to efficiently retrieve and display supported file types with GroupDocs.Viewer for .NET. Ideal for document management systems."
date: "2025-04-25"
weight: 1
url: "/net/file-formats-support/retrieve-display-supported-file-types-groupdocs-viewer-net/"
keywords:
- GroupDocs.Viewer
- Net
- Document Processing

---


# Retrieve and Display Supported File Types in .NET Using GroupDocs.Viewer

## Introduction

Managing and displaying supported file types in your .NET applications can be streamlined using the GroupDocs.Viewer .NET API. Whether you're building a document management system or enhancing an existing application, knowing which files are supported is crucial for seamless user experiences.

In this tutorial, we'll guide you through retrieving and displaying file types with GroupDocs.Viewer for .NET. By the end of this article, you’ll gain valuable insights into:
- Retrieving a list of supported file formats
- Displaying these formats in an ordered manner
- Integrating GroupDocs.Viewer within your .NET projects

Ready to dive in? Let's first set up the prerequisites.

## Prerequisites

Before we begin, ensure you have the following in place:
- **Libraries & Dependencies**: Install the GroupDocs.Viewer for .NET package via NuGet Package Manager or .NET CLI.
- **Environment Setup**: Configure your development environment with Visual Studio and .NET Framework 4.7.2 or later.
- **Knowledge Prerequisites**: A basic understanding of C# programming and .NET application structure is beneficial.

## Setting Up GroupDocs.Viewer for .NET

### Installation

Start by installing the GroupDocs.Viewer package using one of the following methods:

**NuGet Package Manager Console**
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**\.NET CLI**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### License Acquisition

GroupDocs offers various licensing options, including free trials and temporary licenses for evaluation purposes. To get started:
- **Free Trial**: Download the latest version to explore its features.
- **Temporary License**: Obtain a license for extended testing without limitations.
- **Purchase**: Buy a full license for unlimited use.

### Basic Initialization

To initialize GroupDocs.Viewer in your application, follow these steps:

```csharp
using GroupDocs.Viewer;

// Initialize Viewer object with input file path
using (Viewer viewer = new Viewer("sample.pdf"))
{
    // Your code logic here
}
```

## Implementation Guide

Now that we've set up our environment and installed the necessary packages, let's implement the feature to retrieve and display supported file types.

### Feature Overview

This section will guide you through fetching a list of supported file formats from GroupDocs.Viewer and displaying them by their extensions. This functionality can enhance user interaction by clearly showing what files are manageable within your application.

#### Step 1: Define File Type Class

First, define a class to represent the file types:

```csharp
using System;

// Simulated FileType class for demonstration purposes
class DummyFileTypeClass 
{ 
    public string Extension; 
    public override string ToString() => Extension; 
}

type FileType = DummyFileTypeClass;
```

#### Step 2: Retrieve Supported File Types

Next, simulate a method to mimic the retrieval of supported file formats:

```csharp
static IEnumerable<FileType> GetSupportedFileTypes()
{
    return new List<FileType>
    {
        new FileType { Extension = ".pdf\
