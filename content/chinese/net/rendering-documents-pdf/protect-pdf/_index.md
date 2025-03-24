---
title: 使用密码保护渲染的 PDF
linktitle: 使用密码保护渲染的 PDF
second_title: GroupDocs.Viewer .NET API
description: 使用 Groupdocs.Viewer for .NET，使用密码轻松保护渲染的 PDF。确保您的文档安全且保密。
weight: 12
url: /zh/net/rendering-documents-pdf/protect-pdf/
---

# 使用密码保护渲染的 PDF

## 介绍
在本教程中，您将学习如何使用 Groupdocs.Viewer for .NET 通过密码保护渲染的 PDF。通过添加安全措施，您可以控制对 PDF 文档的访问，确保机密性和完整性。
## 先决条件
在开始之前，请确保您具备以下条件：
1.  Groupdocs.Viewer for .NET Library：从以下位置下载并安装该库：[网站](https://releases.groupdocs.com/viewer/net/).
2. 开发环境：确保您有一个用于 .NET 开发的工作开发环境。

## 导入命名空间
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 第 1 步：定义输出目录和文件路径
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## 第 2 步：初始化查看器对象并设置安全选项
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
## 步骤 3：设置 PDF 查看选项
```csharp
    PdfViewOptions options = new PdfViewOptions(filePath)
    {
        Security = security
    };
```
## 步骤 4：使用安全选项渲染文档
```csharp
    viewer.View(options);
}
```
## 第 5 步：检查渲染文档
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
通过执行以下步骤，您可以使用 Groupdocs.Viewer for .NET 使用密码保护渲染的 PDF。这可确保您的文档保持安全，并且只有授权用户才能访问。

## 结论
保护 PDF 文档的安全对于维护机密性和完整性至关重要。借助 Groupdocs.Viewer for .NET，您可以轻松地使用密码保护渲染的 PDF，控制对敏感信息的访问。

## 常见问题解答
### 我可以使用不同级别的权限来保护 PDF 吗？
是的，您可以指定不同的查看、打印、复制等权限，同时使用密码保护 PDF。
### Groupdocs.Viewer 是否与各种文件格式兼容？
绝对地！ Groupdocs.Viewer 支持渲染多种文件格式，包括 DOCX、XLSX、PPTX、PDF 等。
### 我可以将 Groupdocs.Viewer 集成到我现有的 .NET 应用程序中吗？
当然！ Groupdocs.Viewer 提供用于无缝集成到 .NET 应用程序中的 API，从而提供强大的文档查看功能。
### Groupdocs.Viewer 是否提供云存储服务支持？
是的，Groupdocs.Viewer 支持与 Dropbox、Google Drive 和 Amazon S3 等流行的云存储服务集成，允许您呈现存储在云中的文档。
### Groupdocs.Viewer 是否有试用版？
是的，您可以通过访问免费试用版来开始使用 Groupdocs.Viewer[网站](https://releases.groupdocs.com/).