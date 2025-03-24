---
title: 渲染 CDR 图像
linktitle: 渲染 CDR 图像
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 将 CDR 图像呈现为 HTML、JPG、PNG 和 PDF。使用本教程轻松转换 CorelDRAW 文件。
weight: 12
url: /zh/net/image-rendering/render-cdr-images/
---
## 介绍
在本教程中，我们将指导您完成使用 GroupDocs.Viewer for .NET 渲染 CDR (CorelDRAW) 图像的过程。 CDR 是一种主要与矢量图形编辑器 CorelDRAW 相关的文件格式。使用 GroupDocs.Viewer，您可以轻松地将 CDR 文件转换为各种格式，如 HTML、JPG、PNG 和 PDF。
## 先决条件
在开始之前，请确保您具备以下先决条件：
1.  GroupDocs.Viewer for .NET：确保您已安装 GroupDocs.Viewer for .NET。您可以从以下位置下载：[这里](https://releases.groupdocs.com/viewer/net/).
2. 文档目录：准备一个要保存渲染图像的目录。
3. C# 基础知识：为了理解代码示例，需要熟悉 C# 编程语言。
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
1. 定义 JPG 文件的文件路径格式：
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "cdr_result_{0}.jpg");
```
2. 使用 Viewer 类将 CDR 文件渲染为 JPG：
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
1. 定义 PDF 的文件路径格式：
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
3. 或者，您可以通过将附加参数传递给`viewer.View()`方法。
## 结论
使用 GroupDocs.Viewer for .NET 将 CDR 图像呈现为各种格式（例如 HTML、JPG、PNG 和 PDF）是一个简单的过程。通过遵循本教程中概述的步骤，您可以根据您的要求有效地将 CDR 文件转换为不同的格式。
## 常见问题解答
### GroupDocs.Viewer for .NET 是否与所有版本的 CDR 文件兼容？
GroupDocs.Viewer for .NET 支持渲染由不同版本的 CorelDRAW 创建的 CDR 文件。
### 我可以自定义渲染文件的输出吗？
是的，GroupDocs.Viewer for .NET 提供了各种自定义输出的选项，例如调整图像质量、设置水印等。
### GroupDocs.Viewer for .NET 是否需要任何外部依赖项？
不需要，GroupDocs.Viewer for .NET 是一个独立的库，不需要任何外部依赖项来呈现文档。
### GroupDocs.Viewer for .NET 是否有试用版？
是的，您可以从以下位置下载 GroupDocs.Viewer for .NET 的免费试用版：[这里](https://releases.groupdocs.com/).
### 在哪里可以获得 GroupDocs.Viewer for .NET 的支持？
您可以从 GroupDocs.Viewer 社区论坛获得支持[这里](https://forum.groupdocs.com/c/viewer/9).