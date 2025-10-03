---
"description": "学习如何使用 GroupDocs.Viewer for .NET 将 CDR 图像渲染为 HTML、JPG、PNG 和 PDF。本教程将帮助您轻松转换 CorelDRAW 文件。"
"linktitle": "渲染 CDR 图像"
"second_title": "GroupDocs.Viewer .NET API"
"title": "渲染 CDR 图像"
"url": "/zh/net/image-rendering/render-cdr-images/"
"weight": 12
type: docs
---
# 渲染 CDR 图像

## 介绍
在本教程中，我们将指导您使用 GroupDocs.Viewer for .NET 渲染 CDR（CorelDRAW）图像。CDR 是一种主要与矢量图形编辑器 CorelDRAW 相关的文件格式。使用 GroupDocs.Viewer，您可以轻松地将 CDR 文件转换为各种格式，例如 HTML、JPG、PNG 和 PDF。

![使用 GroupDocs.Viewer for .NET 渲染 CDR 图像](/viewer/image-rendering/render-cdr-images.png)

## 先决条件
开始之前，请确保您满足以下先决条件：
1. GroupDocs.Viewer for .NET：请确保您已安装 GroupDocs.Viewer for .NET。您可以从以下网址下载： [这里](https://releases。groupdocs.com/viewer/net/).
2. 文档目录：准备一个要保存渲染图像的目录。
3. C# 基础知识：熟悉 C# 编程语言对于理解代码示例是必需的。
## 导入命名空间
在深入研究代码示例之前，请在 C# 文件中导入必要的命名空间：
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
现在，让我们将每个示例分解为多个步骤：
## 渲染为 HTML
1. 定义要保存渲染的 HTML 文件的输出目录：
```csharp
string outputDirectory = "Your Document Directory";
```
2. 指定 HTML 文件的文件路径格式：
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.html");
```
3. 使用 Viewer 类将 CDR 文件呈现为 HTML：
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
## 渲染为 JPG
1. 定义JPG文件的文件路径格式：
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. 使用Viewer类将CDR文件渲染为JPG：
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## 渲染为 PNG
1. 定义 PNG 文件的文件路径格式：
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.png");
```
2. 使用 Viewer 类将 CDR 文件渲染为 PNG：
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
## 渲染为 PDF
1. 定义PDF的文件路径格式：
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result.pdf");
```
2. 使用 Viewer 类将 CDR 文件渲染为 PDF：
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CDR))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
3. （可选）您可以通过向 `viewer.View()` 方法。
## 结论
使用 GroupDocs.Viewer for .NET 将 CDR 图像渲染为 HTML、JPG、PNG 和 PDF 等各种格式非常简单。按照本教程中概述的步骤，您可以根据需求高效地将 CDR 文件转换为不同的格式。
## 常见问题解答
### GroupDocs.Viewer for .NET 是否与所有版本的 CDR 文件兼容？
GroupDocs.Viewer for .NET 支持渲染由不同版本的 CorelDRAW 创建的 CDR 文件。
### 我可以自定义渲染文件的输出吗？
是的，GroupDocs.Viewer for .NET 提供了各种选项来自定义输出，例如调整图像质量、设置水印等。
### GroupDocs.Viewer for .NET 是否需要任何外部依赖？
不，GroupDocs.Viewer for .NET 是一个独立库，不需要任何外部依赖来呈现文档。
### GroupDocs.Viewer for .NET 有试用版吗？
是的，您可以从以下网址下载 GroupDocs.Viewer for .NET 的免费试用版 [这里](https://releases。groupdocs.com/).
### 在哪里可以获得 GroupDocs.Viewer for .NET 的支持？
您可以从 GroupDocs.Viewer 社区论坛获得支持 [这里](https://forum。groupdocs.com/c/viewer/9).