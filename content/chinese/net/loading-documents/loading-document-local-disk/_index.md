---
"description": "了解如何使用 Groupdocs.Viewer for .NET 从本地磁盘无缝渲染文档。使用高效的文档功能增强您的 .NET 应用程序。"
"linktitle": "从本地磁盘加载文档"
"second_title": "GroupDocs.Viewer .NET API"
"title": "从本地磁盘加载文档"
"url": "/zh/net/loading-documents/loading-document-local-disk/"
"weight": 10
---

# 从本地磁盘加载文档

## 介绍
在当今的数字时代，高效的文档渲染对于各种应用程序至关重要。Groupdocs.Viewer for .NET 提供了一个强大的解决方案，可直接从本地磁盘渲染文档。在本教程中，我们将指导您使用 Groupdocs.Viewer for .NET 从本地磁盘加载文档的过程。无论您是经验丰富的开发人员还是刚刚入门，本分步指南都将帮助您将文档渲染无缝集成到您的 .NET 应用程序中。

![使用 GroupDocs.Viewer .NET 从本地磁盘加载文档](/viewer/loading-documents/load-documents-from-local-disk.png)

## 先决条件
在深入学习本教程之前，请确保您满足以下先决条件：
1. Groupdocs.Viewer for .NET：从下载并安装最新版本 [这里](https://releases。groupdocs.com/viewer/net/).
2. .NET 开发环境：确保您的系统上已设置可用的 .NET 开发环境。
3. 本地文档：将您想要渲染的文档存储在本地磁盘上。

## 导入命名空间
首先，让我们导入必要的命名空间来访问 .NET 的 Groupdocs.Viewer 的功能。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 步骤 1：从本地磁盘加载文档
首先设置将保存呈现的 HTML 页面的输出目录。
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 第 2 步：初始化查看器并渲染文档
使用文档的路径初始化查看器对象并使用 HTML 视图选项呈现它。
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_Document"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## 步骤3：显示输出
一旦渲染完成，将显示一条消息，表明源文档渲染成功以及输出文件的位置。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 结论
恭喜！您已成功学习如何使用 Groupdocs.Viewer for .NET 从本地磁盘加载文档。这款强大的工具为您的 .NET 应用程序的文档渲染开辟了无限可能。
## 常见问题解答
### 我可以使用 Groupdocs.Viewer for .NET 呈现不同格式的文档吗？
是的，Groupdocs.Viewer for .NET 支持多种文档格式，包括 DOCX、PDF、XLSX、PPTX 等。
### Groupdocs.Viewer for .NET 是否与所有 .NET 框架兼容？
Groupdocs.Viewer for .NET 与大多数 .NET 框架兼容，包括 .NET Core、.NET Framework 和 .NET Standard。
### 我可以自定义文档的渲染选项吗？
当然！Groupdocs.Viewer for .NET 提供了丰富的自定义选项，让您可以根据特定需求定制渲染过程。
### Groupdocs.Viewer for .NET 有试用版吗？
是的，您可以从下载免费试用版 [这里](https://releases。groupdocs.com/).
### 在哪里可以找到 Groupdocs.Viewer for .NET 的支持或其他资源？
如需支持和其他资源，请访问 Groupdocs.Viewer for .NET [论坛](https://forum。groupdocs.com/c/viewer/9).