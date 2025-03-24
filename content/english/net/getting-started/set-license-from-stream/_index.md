---
title: Set License from Stream
linktitle: Set License from Stream
second_title: GroupDocs.Viewer .NET API
description: Enhance your .NET applications with GroupDocs.Viewer for seamless document viewing. Follow our step-by-step guide and integrate powerful document viewing capabilities effortlessly.
weight: 11
url: /net/getting-started/set-license-from-stream/
---

# Set License from Stream

## Introduction
Are you looking to empower your .NET applications with advanced document viewing capabilities? GroupDocs.Viewer for .NET offers a comprehensive solution to seamlessly integrate document viewing functionalities into your projects. In this tutorial, we'll delve into the process of leveraging GroupDocs.Viewer for .NET to enrich your applications with powerful document viewing capabilities. 
## Prerequisites
Before we dive into the integration process, ensure that you have the following prerequisites in place:
1. Basic Knowledge of .NET Development: Familiarity with C# and .NET framework is essential to follow along with this tutorial.
   
2. GroupDocs.Viewer for .NET Package: Make sure you have downloaded and installed the GroupDocs.Viewer for .NET package. You can obtain it from the [download link](https://releases.groupdocs.com/viewer/net/).
3. Access to GroupDocs Documentation: Keep the [documentation](https://tutorials.groupdocs.com/viewer/net/) handy for tutorials during the integration process.

## Import Namespaces
To begin with, import the necessary namespaces into your .NET application. Follow these steps:
### Step 1: Open your .NET project.
Ensure that you have your .NET project opened in your preferred development environment.
### Step 2: Add GroupDocs.Viewer Namespace.
In your code file, add the following namespace to access the GroupDocs.Viewer functionalities:
```csharp
using System;
using System.IO;
```
## Set License from Stream
The next step involves setting the license from a stream. Follow these detailed steps:
### Step 1: Define Output Directory.
Set the directory where your documents will be stored by defining the output directory:
```csharp
string outputDirectory = "Your Document Directory";
```
### Step 2: Check License File Existence.
Check if the license file exists in your project directory:
```csharp
if (File.Exists(Utils.LicensePath))
```
### Step 3: Set License.
If the license file exists, set the license using the provided stream:
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### Step 4: Handle License Absence.
If the license file is not found, provide instructions to obtain a license:
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://purchase.groupdocs.com/faqs/licensing. " +
                      "\nLearn how to request a temporary license at https://purchase.groupdocs.com/temporary-license.");
}
```

## Conclusion
Congratulations! You've successfully learned how to integrate GroupDocs.Viewer for .NET into your applications. With this powerful tool, you can now effortlessly view various document formats within your .NET projects, enhancing user experience and productivity.
## FAQ's
### Do I need a license to use GroupDocs.Viewer for .NET?
Yes, you need a license to use GroupDocs.Viewer for .NET. You can obtain either a temporary or permanent license from the GroupDocs website.
### Can I integrate GroupDocs.Viewer into my ASP.NET application?
Absolutely! GroupDocs.Viewer for .NET seamlessly integrates into both desktop and web applications, including ASP.NET.
### Which document formats are supported by GroupDocs.Viewer?
GroupDocs.Viewer supports a wide range of document formats, including PDF, Microsoft Office (Word, Excel, PowerPoint), images, and more.
### Is GroupDocs.Viewer compatible with .NET Core?
Yes, GroupDocs.Viewer for .NET is compatible with both .NET Framework and .NET Core.
### Can I customize the viewer interface according to my application's theme?
Yes, GroupDocs.Viewer provides extensive customization options, allowing you to tailor the viewer interface to match your application's theme seamlessly.
