---
"description": "了解如何使用 GroupDocs.Viewer for .NET 渲染具有原始页面大小的 PDF。按照我们的分步指南操作，即可无缝集成此功能。"
"linktitle": "使用原始页面大小渲染 PDF"
"second_title": "GroupDocs.Viewer .NET API"
"title": "使用原始页面大小渲染 PDF"
"url": "/zh/net/pdf-rendering-options/render-pdf-original-page-size/"
"weight": 17
---

# 使用原始页面大小渲染 PDF

## 介绍
在 .NET 开发领域，GroupDocs.Viewer 是一款功能强大的工具，可用于渲染各种文档格式，包括 PDF。文档处理中的一个常见需求是在渲染 PDF 的同时保留其原始页面大小。要无缝地完成此任务，需要全面了解 GroupDocs.Viewer for .NET 及其功能。

![使用 GroupDocs.Viewer .NET 渲染具有原始页面大小的 PDF](/viewer/pdf-rendering-options/render-pdf-with-original-page-size.png)

## 先决条件
在使用 GroupDocs.Viewer for .NET 渲染具有原始页面大小的 PDF 之前，请确保您已满足以下先决条件：
### 1. 安装 GroupDocs.Viewer for .NET
首先从网站下载 GroupDocs.Viewer 库。您可以从提供的 [下载链接](https://releases.groupdocs.com/viewer/net/)按照文档中提供的安装说明，将其有效地集成到您的.NET项目中。
### 2. 设置开发环境
确保已设置好 .NET 开发的开发环境。这包括安装兼容的 IDE（例如 Visual Studio），以及对 C# 编程有基本的了解。
### 3. 获取 PDF 文档
您需要一个示例 PDF 文档来使用 GroupDocs.Viewer 进行渲染。您可以使用任何 PDF 文档进行测试。如果您没有，可以从各种在线资源下载示例 PDF。

## 导入命名空间
在继续渲染 PDF 之前，必须将必要的命名空间导入到您的 C# 项目中。此步骤允许您从 GroupDocs.Viewer 库访问所需的类和方法。

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

现在您已经满足了先决条件并导入了必要的命名空间，让我们将使用 GroupDocs.Viewer for .NET 呈现具有原始页面大小的 PDF 的过程分解为简单的步骤：
## 步骤 1：定义输出目录
```csharp
string outputDirectory = "Your Document Directory";
```
确保指定要保存渲染页面的目录。替换 `"Your Document Directory"` 使用您所需目录的路径。
## 步骤2：定义页面文件路径格式
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
设置渲染页面文件的命名格式。在本例中，页面将保存为 PNG 图像，文件名格式如下： `"page_1.png"`， `"page_2.png"`， 等等。
## 步骤 3：使用原始页面大小渲染 PDF
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
实例化 `Viewer` 对象，其中包含 PDF 文件的路径。然后，创建 `PngViewOptions` 使用指定的页面文件路径格式。设置 `RenderOriginalPageSize` 财产 `true` 在渲染时保留原始页面大小。
## 步骤 4：显示渲染文档位置
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
打印一条指示渲染成功的消息并提供渲染页面的保存目录。

## 结论
按照本教程中概述的步骤操作，使用 GroupDocs.Viewer for .NET 渲染具有原始页面大小的 PDF 非常简单。通过导入必要的命名空间并遵循分步指南，您可以将此功能无缝集成到您的 .NET 应用程序中。
## 常见问题解答
### GroupDocs.Viewer 除了 PDF 之外还能呈现其他文档格式吗？
是的，GroupDocs.Viewer 支持呈现各种文档格式，包括 Word、Excel、PowerPoint 等。
### GroupDocs.Viewer 是否与 .NET Core 兼容？
是的，GroupDocs.Viewer 与 .NET Framework 和 .NET Core 环境兼容。
### 我可以自定义渲染页面的输出格式吗？
是的，您可以通过调整 GroupDocs.Viewer 提供的选项来自定义输出格式，例如设置不同的图像格式或指定自定义渲染选项。
### GroupDocs.Viewer 是否支持基于云的文档渲染？
是的，GroupDocs.Viewer 提供基于云的文档渲染 API，允许您直接从云存储提供商渲染文档。
### GroupDocs.Viewer 有免费试用版吗？
是的，您可以访问提供的 [关联](https://releases。groupdocs.com/).