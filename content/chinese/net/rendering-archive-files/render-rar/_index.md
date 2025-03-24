---
title: 渲染 RAR 档案
linktitle: 渲染 RAR 档案
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 将 RAR 存档呈现为 HTML、JPG、PNG 或 PDF 格式。轻松查看和共享 RAR 存档的内容。
weight: 13
url: /zh/net/rendering-archive-files/render-rar/
---
## 介绍
RAR 存档是一种流行的格式，用于将多个文件和文件夹压缩并存储到单个容器中。将 RAR 存档呈现为各种格式（例如 HTML、JPG、PNG 或 PDF）对于查看或共享这些存档的内容至关重要。在本教程中，我们将探讨如何使用 GroupDocs.Viewer for .NET 呈现 RAR 存档。
## 先决条件
在我们开始之前，请确保您满足以下先决条件：
1. GroupDocs.Viewer for .NET：从以下位置安装 GroupDocs.Viewer for .NET 库[下载链接](https://releases.groupdocs.com/viewer/net/).
2. 示例 RAR 存档：准备好示例 RAR 存档以供渲染。

## 导入命名空间
```csharp
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
using System;
using System.IO;
```
## 第 1 步：定义输出目录
```csharp
string outputDirectory = "Your Document Directory";
```
## 第 2 步：渲染为 HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.html");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## 第 3 步：渲染为 JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.jpg");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## 第 4 步：渲染为 PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_{0}.png");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## 第 5 步：渲染为 PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.pdf");
using (Viewer viewer = new Viewer("YourRarFile.rar"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## 结论
使用 GroupDocs.Viewer for .NET 将 RAR 存档呈现为各种格式变得非常简单。通过遵循本教程中概述的步骤，您可以轻松地将 RAR 存档转换为 HTML、JPG、PNG 或 PDF 格式，从而轻松查看和共享其内容。
## 常见问题解答
### GroupDocs.Viewer for .NET 可以处理加密的 RAR 存档吗？
是的，GroupDocs.Viewer for .NET 支持渲染加密的 RAR 存档，前提是在渲染过程中提供必要的密码。
### 是否可以自定义渲染文档的输出外观？
绝对地！ GroupDocs.Viewer for .NET 提供了广泛的自定义选项，允许用户根据自己的喜好定制呈现文档的外观。
### GroupDocs.Viewer for .NET 是否支持呈现除 RAR 之外的其他存档格式？
是的，GroupDocs.Viewer for .NET 支持呈现各种存档格式，包括 ZIP、TAR、7z 等。
### 我可以将 GroupDocs.Viewer for .NET 集成到我的 Web 应用程序中吗？
当然！ GroupDocs.Viewer for .NET 提供适合集成到桌面和 Web 应用程序中的 API。
### GroupDocs.Viewer for .NET 是否有试用版？
是的，您可以从以下网站免费试用 GroupDocs.Viewer for .NET[网站](https://releases.groupdocs.com/).