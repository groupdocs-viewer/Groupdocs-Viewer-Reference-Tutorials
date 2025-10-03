---
"description": "了解如何使用 GroupDocs.Viewer for .NET 调整 CAD 图纸的输出图像大小。轻松提升可视性和可用性。"
"linktitle": "调整 CAD 绘图的输出图像大小"
"second_title": "GroupDocs.Viewer .NET API"
"title": "调整 CAD 绘图的输出图像大小"
"url": "/zh/net/rendering-cad-drawings/adjust-output-image-size-cad/"
"weight": 15
type: docs
---
# 调整 CAD 绘图的输出图像大小

## 介绍
CAD 图纸通常需要进行特定调整才能获得最佳的查看和呈现效果。GroupDocs.Viewer for .NET 提供了一套强大的工具集来管理和自定义 CAD 图纸输出。在本教程中，我们将逐步指导您调整 CAD 图纸的输出图像大小。
## 先决条件
开始之前，请确保您满足以下先决条件：
1. GroupDocs.Viewer for .NET：从以下位置下载并安装 GroupDocs.Viewer for .NET [这里](https://releases。groupdocs.com/viewer/net/).
2. 文档目录：准备您的文档所在的目录。
3. 基本理解：熟悉.NET 编程的基本概念。

## 导入命名空间
首先，确保导入必要的命名空间以访问 GroupDocs.Viewer 功能：
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 步骤1：设置输出目录
定义要存储 CAD 图纸输出图像的目录：
```csharp
string outputDirectory = "Your Document Directory";
```
## 步骤2：定义页面文件路径格式
设置页面文件路径的格式。此格式将用于命名各个页面并将其保存为 HTML 文件：
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 步骤3：调整图像大小
在查看器对象的使用块内，通过设置适当的选项来调整 CAD 绘图的图像大小：
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.CadOptions = CadOptions.ForRenderingByScaleFactor(0.5f);
    
    viewer.View(options);
}
```
## 步骤4：显示输出目录
渲染文档后，显示一条指示渲染成功的消息并提供输出目录的位置：
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 结论
调整 CAD 图纸的输出图像大小对于增强其可视性和可用性至关重要。使用 GroupDocs.Viewer for .NET，此过程变得精简高效，让您能够根据特定需求自定义输出。
## 常见问题解答
### 除了 CAD 图纸之外，我还可以调整其他类型文档的输出图像大小吗？
是的，GroupDocs.Viewer for .NET 支持各种文档类型，并且您可以调整大多数文档格式的输出图像大小。
### GroupDocs.Viewer for .NET 是否与不同版本的 .NET 框架兼容？
是的，GroupDocs.Viewer for .NET 与 .NET 框架的多个版本兼容，确保在不同环境中的灵活性和可用性。
### GroupDocs.Viewer for .NET 是否有任何可用的许可选项？
是的，您可以探索不同的许可选项，包括临时许可和商业许可，以满足您的需求。
### 我可以自定义渲染文档的输出格式吗？
当然，GroupDocs.Viewer for .NET 提供了各种自定义选项，允许您根据教程定制输出格式。
### 在哪里可以找到有关 GroupDocs.Viewer for .NET 的更多支持或帮助？
您可以访问 GroupDocs.Viewer 论坛 [这里](https://forum.groupdocs.com/c/viewer/9) 获得支持、提出问题并与社区互动。