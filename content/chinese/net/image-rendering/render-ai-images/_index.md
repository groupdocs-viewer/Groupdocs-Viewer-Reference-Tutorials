---
title: 渲染 AI 图像
linktitle: 渲染 AI 图像
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 在 .NET 应用程序中轻松渲染 AI 图像。请按照我们的分步教程进行无缝集成。
weight: 10
url: /zh/net/image-rendering/render-ai-images/
---
## 介绍
GroupDocs.Viewer for .NET 是一个功能强大的库，使开发人员能够在其 .NET 应用程序中轻松呈现各种文档格式。无论您需要显示 AI 图像、PDF 还是其他文档类型，GroupDocs.Viewer 都能简化流程，提供多种输出格式，以便无缝集成到您的项目中。本教程将指导您使用 GroupDocs.Viewer for .NET 逐步渲染 AI 图像。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
1. Visual Studio：在您的系统上安装 Visual Studio IDE。
2.  GroupDocs.Viewer for .NET：从以下位置下载并安装 GroupDocs.Viewer for .NET[网站](https://releases.groupdocs.com/viewer/net/).
3. C# 基础知识：需要熟悉 C# 编程语言才能理解代码示例。

## 导入命名空间
在您的 C# 项目中，导入必要的命名空间以访问 GroupDocs.Viewer for .NET 的功能。

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

使用 GroupDocs.Viewer for .NET 渲染 AI 图像涉及多个步骤，每个步骤都适合特定的输出格式。为了清楚起见，下面我们将把这个过程分解为单独的步骤。
## 第 1 步：指定输出目录
```csharp
string outputDirectory = "Your Document Directory";
```
## 第 2 步：渲染为 HTML
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
## 第 3 步：渲染为 JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## 第 4 步：渲染为 PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```
## 第 5 步：渲染为 PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "ai_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_AI))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.View(options);
}
```

## 结论
GroupDocs.Viewer for .NET 提供了一个无缝解决方案，用于在 .NET 应用程序中渲染 AI 图像和各种文档格式。通过遵循本教程中提供的分步指南，开发人员可以轻松地将文档渲染功能集成到他们的项目中。
## 常见问题解答
### 渲染 AI 图像时可以自定义输出外观吗？
是的，GroupDocs.Viewer for .NET 提供了用于自定义输出外观的各种选项，包括页面大小、图像质量等。
### 是否有可用于测试目的的试用版？
是的，您可以从 GroupDocs 下载免费试用版[网站](https://releases.groupdocs.com/viewer/net/)在购买之前评估图书馆的功能。
### GroupDocs.Viewer是否支持渲染加密的AI图像？
是的，GroupDocs.Viewer for .NET 支持使用提供的适当解密密钥渲染加密的 AI 图像。
### 我可以直接从 URL 渲染 AI 图像吗？
是的，GroupDocs.Viewer for .NET 允许通过指定 URL 路径而不是本地文件路径来从 URL 渲染 AI 图像。
### GroupDocs.Viewer for .NET 是否提供技术支持？
是的，可以通过 GroupDocs 获得技术支持[论坛](https://forum.groupdocs.com/c/viewer/9)，您可以在其中提问、报告问题以及寻求社区帮助。