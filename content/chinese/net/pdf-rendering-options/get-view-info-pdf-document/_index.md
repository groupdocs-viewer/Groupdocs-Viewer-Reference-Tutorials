---
title: 获取 PDF 文档的查看信息
linktitle: 获取 PDF 文档的查看信息
second_title: GroupDocs.Viewer .NET API
description: 在这个综合教程中了解如何使用 GroupDocs.Viewer for .NET 从 PDF 文档中提取视图信息。
weight: 16
url: /zh/net/pdf-rendering-options/get-view-info-pdf-document/
---

# 获取 PDF 文档的查看信息

## 介绍
GroupDocs.Viewer for .NET 是一款功能强大的工具，旨在简化 .NET 应用程序中的文档查看。无论您是处理 PDF、Word 文档、Excel 电子表格还是 PowerPoint 演示文稿，该库都可以简化各种文件格式的渲染和交互过程。在本教程中，我们将重点关注如何利用 GroupDocs.Viewer 的功能专门从 PDF 文档中提取视图信息。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
1. 安装适用于 .NET 的 GroupDocs.Viewer：确保您已下载并安装 GroupDocs.Viewer 库。您可以从[下载链接](https://releases.groupdocs.com/viewer/net/).   
2. C# 基础知识：熟悉 C# 编程语言对于理解和实现所提供的代码示例至关重要。
3. 访问 PDF 文档：准备好一个 PDF 文档，您将用它来提取视图信息。

## 导入命名空间
在您的 C# 项目中，导入必要的命名空间以利用 GroupDocs.Viewer 功能。

```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```


现在，让我们分解一下使用 GroupDocs.Viewer for .NET 从 PDF 文档检索视图信息的过程。
## 第 1 步：初始化查看器对象
创建一个 Viewer 对象并提供 PDF 文档的路径作为参数。
```csharp
using (Viewer viewer = new Viewer("path/to/your/sample.pdf"))
{
```
## 第 2 步：定义 ViewInfoOptions
指定视图选项（例如 HTML 视图）以检索视图信息。
```csharp
	ViewInfoOptions options = ViewInfoOptions.ForHtmlView();
```
## 第三步：获取查看信息
调用 GetViewInfo 方法从 PDF 文档中提取视图信息。
```csharp
	PdfViewInfo info = viewer.GetViewInfo(options) as PdfViewInfo;
```
## 第四步：输出视图信息
显示提取的视图信息，例如文档类型、页数和打印权限。
```csharp
	Console.WriteLine("Document type is: " + info.FileType);
	Console.WriteLine("Pages count: " + info.Pages.Count);
	Console.WriteLine("Printing allowed: " + info.PrintingAllowed);
}
```

## 结论
在本教程中，我们探讨了如何利用 GroupDocs.Viewer for .NET 从 PDF 文档中提取视图信息。通过遵循提供的步骤，您可以将此功能无缝集成到您的 .NET 应用程序中，从而增强文档管理和查看功能。
## 常见问题解答
### GroupDocs.Viewer 是否与 PDF 之外的其他文件格式兼容？
是的，GroupDocs.Viewer 支持多种文档格式，包括 Word、Excel、PowerPoint 等。
### 我可以根据应用程序的要求自定义视图选项吗？
当然，GroupDocs.Viewer 提供了各种选项来根据您的特定需求定制查看体验。
### GroupDocs.Viewer 是否适用于桌面和 Web 应用程序？
是的，GroupDocs.Viewer 用途广泛，可以无缝集成到桌面和基于 Web 的 .NET 应用程序中。
### 如果我在实施过程中遇到任何问题，GroupDocs.Viewer 是否提供支持和帮助？
当然，您可以从 GroupDocs.Viewer 社区论坛寻求帮助或访问专业支持服务以迅速解决任何问题。
### 我可以在购买前试用 GroupDocs.Viewer 吗？
是的，您可以通过访问以下网站上提供的免费试用版来探索 GroupDocs.Viewer 的功能：[网站](https://purchase.groupdocs.com/buy).