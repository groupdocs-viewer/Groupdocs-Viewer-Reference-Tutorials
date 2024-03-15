---
title: 使用原始页面大小渲染 PDF
linktitle: 使用原始页面大小渲染 PDF
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 以原始页面大小呈现 PDF。按照我们的分步指南无缝集成此功能。
type: docs
weight: 17
url: /zh/net/pdf-rendering-options/render-pdf-original-page-size/
---
## 介绍
在 .NET 开发领域，GroupDocs.Viewer 作为渲染各种文档格式（包括 PDF）的强大工具而脱颖而出。文档处理中的一项常见要求是渲染 PDF，同时保留其原始页面大小。要无缝地完成此任务，需要全面了解 GroupDocs.Viewer for .NET 及其功能。
## 先决条件
在深入使用 GroupDocs.Viewer for .NET 以原始页面大小渲染 PDF 之前，请确保满足以下先决条件：
### 1. 安装适用于.NET的GroupDocs.Viewer
首先从网站下载 GroupDocs.Viewer 库。您可以从提供的库中获取该库[下载链接](https://releases.groupdocs.com/viewer/net/)。按照文档中提供的安装说明将其有效地集成到您的 .NET 项目中。
### 2. 搭建开发环境
确保您已设置用于 .NET 开发的开发环境。这包括安装兼容的 IDE（例如 Visual Studio）以及对 C# 编程的基本了解。
### 3. 获取PDF文档
您需要一个示例 PDF 文档才能使用 GroupDocs.Viewer 进行呈现。您可以使用任何 PDF 文档进行测试。如果您没有，可以从各种在线资源下载 PDF 示例。

## 导入命名空间
在继续渲染 PDF 之前，必须将必要的命名空间导入到您的 C# 项目中。此步骤允许您从 GroupDocs.Viewer 库访问所需的类和方法。

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

现在您已经具备了先决条件并导入了必要的命名空间，让我们将使用 GroupDocs.Viewer for .NET 以原始页面大小渲染 PDF 的过程分解为简单的步骤：
## 第 1 步：定义输出目录
```csharp
string outputDirectory = "Your Document Directory";
```
确保指定要保存渲染页面的目录。代替`"Your Document Directory"`与您所需目录的路径。
## 第2步：定义页面文件路径格式
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
设置渲染页面文件的命名格式。在此示例中，页面将保存为 PNG 图像，文件名格式为`"page_1.png"`, `"page_2.png"`， 等等。
## 第 3 步：使用原始页面大小渲染 PDF
```csharp
using (Viewer viewer = new Viewer("Path_to_Your_PDF_File.pdf"))
{
    PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
    viewOptions.PdfOptions.RenderOriginalPageSize = true;
    
    viewer.View(viewOptions);
}
```
实例化一个`Viewer`包含 PDF 文件路径的对象。然后，创建`PngViewOptions`具有指定的页面文件路径格式。放`RenderOriginalPageSize`财产给`true`在渲染时保留原始页面大小。
## 第 4 步：显示渲染文档位置
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
打印一条指示渲染成功的消息，并提供保存渲染页面的目录。

## 结论
当您按照本教程中概述的步骤操作时，使用 GroupDocs.Viewer for .NET 呈现原始页面大小的 PDF 是一个简单的过程。通过导入必要的命名空间并遵循分步指南，您可以将此功能无缝集成到您的 .NET 应用程序中。
## 常见问题解答
### GroupDocs.Viewer 可以呈现除 PDF 之外的其他文档格式吗？
是的，GroupDocs.Viewer 支持渲染各种文档格式，包括 Word、Excel、PowerPoint 等。
### GroupDocs.Viewer 与 .NET Core 兼容吗？
是的，GroupDocs.Viewer 与 .NET Framework 和 .NET Core 环境兼容。
### 我可以自定义渲染页面的输出格式吗？
是的，您可以通过调整 GroupDocs.Viewer 提供的选项来自定义输出格式，例如设置不同的图像格式或指定自定义渲染选项。
### GroupDocs.Viewer 是否提供对基于云的文档呈现的支持？
是的，GroupDocs.Viewer 提供用于基于云的文档渲染的 API，允许您直接从云存储提供商渲染文档。
### GroupDocs.Viewer 是否有免费试用版？
是的，您可以通过访问提供的免费试用版探索 GroupDocs.Viewer[关联](https://releases.groupdocs.com/).