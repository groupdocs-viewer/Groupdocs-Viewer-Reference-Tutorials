---
title: Set Metered License
linktitle: Set Metered License
second_title: GroupDocs.Viewer .NET API
description: Enhance your .NET applications with GroupDocs.Viewer for seamless document viewing. Easily integrate document rendering functionalities into your projects.
weight: 12
url: /net/getting-started/set-metered-license/
---
## Introduction
In the world of .NET development, incorporating powerful document viewing capabilities into your applications is essential for enhancing user experience and functionality. GroupDocs.Viewer for .NET offers a robust solution for seamlessly integrating document viewing functionalities into your .NET projects. Whether you're working with PDFs, Microsoft Office documents, or various image formats, GroupDocs.Viewer simplifies the process of rendering and displaying these documents within your applications.
## Prerequisites
Before diving into the implementation of GroupDocs.Viewer for .NET, ensure you have the following prerequisites in place:
### 1. Install GroupDocs.Viewer for .NET
To begin, you'll need to download and install GroupDocs.Viewer for .NET. You can find the download link [here](https://releases.groupdocs.com/viewer/net/). Follow the installation instructions provided to set up the library within your development environment.
### 2. Obtain Metered License
In order to utilize GroupDocs.Viewer for .NET, you need to obtain a metered license. This license allows you to control and monitor your API usage based on predefined quotas. Follow the steps below to set up your metered license:

## Import Namespaces
First, ensure you import the necessary namespaces to access the functionality provided by GroupDocs.Viewer for .NET:
```csharp
using System;
```

Now, let's break down the example code provided into multiple steps:
## Step 1: Declare Public and Private Keys
Declare variables to store your public and private keys:
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
Ensure to replace `"YOUR_PUBLIC_KEY"` and `"YOUR_PRIVATE_KEY"` with your actual keys.
## Step 2: Set Metered License
Check if the public key is provided. If not, prompt the user to set the keys:
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://purchase.groupdocs.com/faqs/licensing/metered.");
    return;
}
```
## Step 3: Initialize Metered Object and Set License
Initialize the Metered object and set the metered license using your public and private keys:
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## Step 4: Confirmation Message
Display a confirmation message indicating that the license has been set successfully:
```csharp
Console.WriteLine("License set successfully.");
```

## Conclusion
In conclusion, GroupDocs.Viewer for .NET provides a comprehensive solution for incorporating document viewing functionalities into your .NET applications. By following the outlined steps, you can easily set up a metered license and start leveraging the capabilities of GroupDocs.Viewer within your projects.
## FAQ's
### Q: Where can I find documentation for GroupDocs.Viewer for .NET?
You can find the documentation [here](https://tutorials.groupdocs.com/viewer/net/).
### Q: Is there a free trial available for GroupDocs.Viewer for .NET?
Yes, you can access the free trial [here](https://releases.groupdocs.com/).
### Q: How can I obtain temporary licenses for testing purposes?
Temporary licenses can be obtained [here](https://purchase.groupdocs.com/temporary-license/).
### Q: Where can I seek support or ask questions related to GroupDocs.Viewer for .NET?
You can seek support and ask questions on the GroupDocs.Viewer forum [here](https://forum.groupdocs.com/c/viewer/9).
### Q: Where can I purchase a license for GroupDocs.Viewer for .NET?
You can purchase a license [here](https://purchase.groupdocs.com/buy).
