---
"description": "了解如何使用 GroupDocs.Viewer for .NET 呈现 Visio 图形，并增强 .NET 应用程序中的文档查看功能。"
"linktitle": "渲染 Visio 图形"
"second_title": "GroupDocs.Viewer .NET API"
"title": "渲染 Visio 图形"
"url": "/zh/net/rendering-visio-documents/render-visio-figures/"
"weight": 10
---

# 渲染 Visio 图形

## 介绍
在当今的数字时代，文档渲染在各种应用程序中都扮演着至关重要的角色。无论是在网站上显示文档，还是将其转换为不同的格式，高效的渲染都至关重要。GroupDocs.Viewer for .NET 为在 .NET 应用程序中查看和操作文档提供了一个强大的解决方案。在本教程中，我们将深入研究如何使用 GroupDocs.Viewer for .NET 渲染 Visio 图形，并将该过程分解为几个简单的步骤。
## 先决条件
在深入学习本教程之前，请确保您满足以下先决条件：
1. 环境设置：确保您有一个用于 .NET 开发的工作环境。
2. GroupDocs.Viewer for .NET：从 [下载链接](https://releases。groupdocs.com/viewer/net/).
3. C# 基本了解：熟悉 C# 编程语言基础知识。
4. 示例 Visio 文档：准备好要呈现的示例 Visio 文档。

## 导入命名空间
在您的 C# 项目中，首先导入必要的命名空间：
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 1.渲染为HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "result_page.html");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- 输出目录：定义保存渲染的 HTML 的目录。
- 页面文件路径格式：指定 HTML 页面的路径格式。
- 查看器初始化：使用 Visio 文档的路径初始化查看器对象。
- HTML 视图选项：配置呈现 HTML 的选项。
- Visio 渲染选项：设置特定于 Visio 渲染的选项，例如仅渲染图形和图形宽度。
## 2.渲染为JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.jpg");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- 与渲染为 HTML 类似，配置渲染为 JPG 格式的选项。
## 3.渲染为PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.png");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- 渲染为 PNG 格式的配置遵循与 JPG 渲染类似的模式。
## 4.渲染为PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "visio_result.pdf");
using (Viewer viewer = new Viewer("YourVisioDocumentPath"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.VisioRenderingOptions.RenderFiguresOnly = true;
    options.VisioRenderingOptions.FigureWidth = 250;
    viewer.View(options);
}
```
- 要渲染为 PDF，请配置特定于 PDF 格式的选项。

## 结论
在本教程中，我们探讨了如何使用 GroupDocs.Viewer for .NET 渲染 Visio 图形。按照分步指南操作，您可以将文档渲染功能无缝集成到 .NET 应用程序中，从而增强用户体验和工作效率。
## 常见问题解答
### 我可以自定义 Visio 图形的渲染选项吗？
是的，GroupDocs.Viewer for .NET 提供了大量自定义渲染选项，包括图形宽度、仅渲染图形等。
### GroupDocs.Viewer for .NET 是否适合大规模文档渲染？
当然，GroupDocs.Viewer for .NET 针对高效处理大规模文档渲染进行了优化。
### GroupDocs.Viewer 除了支持 Visio 之外还支持其他文档格式吗？
是的，GroupDocs.Viewer 支持多种文档格式，包括 PDF、Microsoft Office、AutoCAD 等。
### 我可以将 GroupDocs.Viewer 集成到 Web 应用程序中吗？
是的，GroupDocs.Viewer 可以无缝集成到 Web 应用程序中以查看和操作文档。
### 购买前是否有可供测试的试用版？
是的，你可以从 [网站](https://releases.groupdocs.com/) 测试 GroupDocs.Viewer for .NET 的功能。