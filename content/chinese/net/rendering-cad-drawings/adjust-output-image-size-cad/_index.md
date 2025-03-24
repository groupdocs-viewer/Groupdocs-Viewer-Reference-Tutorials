---
title: 调整 CAD 工程图的输出图像尺寸
linktitle: 调整 CAD 工程图的输出图像尺寸
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 调整 CAD 绘图的输出图像大小。轻松增强可见性和可用性。
weight: 15
url: /zh/net/rendering-cad-drawings/adjust-output-image-size-cad/
---
## 介绍
CAD 绘图通常需要进行特定调整才能获得最佳查看和呈现效果。 GroupDocs.Viewer for .NET 提供了强大的工具集来管理和自定义 CAD 绘图输出。在本教程中，我们将指导您逐步完成调整 CAD 工程图的输出图像尺寸的过程。
## 先决条件
在开始之前，请确保您具备以下先决条件：
1.  GroupDocs.Viewer for .NET：从以下位置下载并安装 GroupDocs.Viewer for .NET[这里](https://releases.groupdocs.com/viewer/net/).
2. 文档目录：准备您的文档所在的目录。
3. 基本理解：熟悉 .NET 编程的基本概念。

## 导入命名空间
首先，确保导入必要的命名空间以访问 GroupDocs.Viewer 功能：
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 第1步：设置输出目录
定义要存储 CAD 绘图输出图像的目录：
```csharp
string outputDirectory = "Your Document Directory";
```
## 第2步：定义页面文件路径格式
设置页面文件路径的格式。此格式将用于命名各个页面并将其保存为 HTML 文件：
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 步骤 3：调整图像大小
在 Viewer 对象的 using 块内，通过设置适当的选项来调整 CAD 绘图的图像大小：
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## 第4步：显示输出目录
渲染文档后，显示一条指示渲染成功的消息并提供输出目录的位置：
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 结论
调整 CAD 工程图的输出图像尺寸对于增强其可视性和可用性至关重要。借助 GroupDocs.Viewer for .NET，此过程变得精简且高效，允许您根据特定要求自定义输出。
## 常见问题解答
### 除了 CAD 图纸之外，我可以调整其他类型文档的输出图像尺寸吗？
是的，GroupDocs.Viewer for .NET 支持各种文档类型，并且您可以调整大多数文档格式的输出图像大小。
### GroupDocs.Viewer for .NET 是否与不同版本的 .NET 框架兼容？
是的，GroupDocs.Viewer for .NET 与多个版本的 .NET 框架兼容，确保跨不同环境的灵活性和可用性。
### GroupDocs.Viewer for .NET 是否有任何可用的许可选项？
是的，您可以探索不同的许可选项，包括临时许可和商业许可，以满足您的需求。
### 我可以自定义渲染文档的输出格式吗？
当然，GroupDocs.Viewer for .NET 提供了各种自定义选项，允许您根据自己的喜好定制输出格式。
### 在哪里可以找到有关 GroupDocs.Viewer for .NET 的其他支持或帮助？
您可以访问 GroupDocs.Viewer 论坛[这里](https://forum.groupdocs.com/c/viewer/9)获得支持、提出问题并与社区互动。