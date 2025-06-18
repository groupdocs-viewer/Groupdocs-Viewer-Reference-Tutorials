---
"description": "使用 Groupdocs.Viewer for .NET 轻松设置密码保护渲染的 PDF。确保您的文档安全保密。"
"linktitle": "使用密码保护渲染的 PDF"
"second_title": "GroupDocs.Viewer .NET API"
"title": "使用密码保护渲染的 PDF"
"url": "/zh/net/rendering-documents-pdf/protect-pdf/"
"weight": 12
---

# 使用密码保护渲染的 PDF

## 介绍
在本教程中，您将学习如何使用 Groupdocs.Viewer for .NET 为渲染的 PDF 添加密码保护。通过添加安全措施，您可以控制对 PDF 文档的访问，确保其机密性和完整性。
## 先决条件
开始之前，请确保您已准备好以下内容：
1. Groupdocs.Viewer for .NET 库：从 [网站](https://releases。groupdocs.com/viewer/net/).
2. 开发环境：确保您已为 .NET 开发设置了有效的开发环境。

## 导入命名空间
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 步骤 1：定义输出目录和文件路径
```csharp
string outputDirectory = "Your Document Directory";
string filePath = Path.Combine(outputDirectory, "output.pdf");
```
## 步骤 2：初始化查看器对象并设置安全选项
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
## 步骤5：检查渲染文档
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
按照以下步骤，您可以使用 Groupdocs.Viewer for .NET 为渲染的 PDF 设置密码保护。这可确保您的文档安全无虞，并且只有授权用户才能访问。

## 结论
保护 PDF 文档的安全对于维护其机密性和完整性至关重要。使用 Groupdocs.Viewer for .NET，您可以轻松使用密码保护渲染的 PDF，从而控制对敏感信息的访问。

## 常见问题解答
### 我可以使用不同级别的权限保护 PDF 吗？
是的，您可以指定查看、打印、复制等的不同权限，同时使用密码保护 PDF。
### Groupdocs.Viewer 是否兼容各种文件格式？
当然！Groupdocs.Viewer 支持渲染多种文件格式，包括 DOCX、XLSX、PPTX、PDF 等。
### 我可以将 Groupdocs.Viewer 集成到我现有的 .NET 应用程序中吗？
当然！Groupdocs.Viewer 提供可无缝集成到 .NET 应用程序的 API，提供强大的文档查看功能。
### Groupdocs.Viewer 是否支持云存储服务？
是的，Groupdocs.Viewer 支持与 Dropbox、Google Drive 和 Amazon S3 等流行的云存储服务集成，允许您呈现存储在云中的文档。
### Groupdocs.Viewer 有试用版吗？
是的，您可以通过访问免费试用版开始使用 Groupdocs.Viewer [网站](https://releases。groupdocs.com/).