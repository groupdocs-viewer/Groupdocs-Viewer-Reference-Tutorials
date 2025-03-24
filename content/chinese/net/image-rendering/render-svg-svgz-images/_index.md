---
title: 渲染 SVG 和 SVGZ 图像
linktitle: 渲染 SVG 和 SVGZ 图像
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 渲染 SVG 和 SVGZ 图像。轻松将矢量图形转换为 HTML、JPG、PNG 和 PDF。
weight: 16
url: /zh/net/image-rendering/render-svg-svgz-images/
---

# 渲染 SVG 和 SVGZ 图像

## 介绍
在本教程中，我们将指导您完成使用 GroupDocs.Viewer for .NET 渲染 SVG 和 SVGZ 图像的过程。 GroupDocs.Viewer for .NET 是一个功能强大的文档呈现 API，使开发人员能够在其 .NET 应用程序中呈现各种文档格式。 SVG 和 SVGZ 是用于矢量图形的流行图像格式，通过 GroupDocs.Viewer for .NET，您可以轻松将它们渲染为不同的输出格式，例如 HTML、JPG、PNG 和 PDF。
## 先决条件
在开始之前，请确保您已安装并设置以下先决条件：
1.  GroupDocs.Viewer for .NET：从以下位置下载并安装 GroupDocs.Viewer for .NET[这里](https://releases.groupdocs.com/viewer/net/).
2. 开发环境：确保您拥有用于 .NET 开发的有效开发环境，例如 Visual Studio。
3. 示例 SVGZ 文件：准备好示例 SVGZ 文件以供测试。

## 导入命名空间
在深入研究代码之前，让我们导入必要的名称空间：
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 第 1 步：将 SVGZ 渲染为 HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## 第 2 步：将 SVGZ 渲染为 JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## 第 3 步：将 SVGZ 渲染为 PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## 第 4 步：将 SVGZ 渲染为 PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## 结论
在本教程中，我们学习了如何使用 GroupDocs.Viewer for .NET 渲染 SVG 和 SVGZ 图像。只需几个简单的步骤，您就可以将 SVGZ 图像转换为各种输出格式，如 HTML、JPG、PNG 和 PDF，从而使它们在不同的环境中均可访问和查看。
## 常见问题解答
### GroupDocs.Viewer 可以渲染其他图像格式吗？
是的，GroupDocs.Viewer 支持渲染各种图像格式，包括 PNG、JPEG、BMP、TIFF、GIF 等。
### GroupDocs.Viewer 与 .NET Core 兼容吗？
是的，GroupDocs.Viewer 与 .NET Framework 和 .NET Core 兼容。
### 我可以自定义渲染选项吗？
是的，GroupDocs.Viewer 提供了广泛的渲染选项，允许您根据您的要求自定义输出。
### GroupDocs.Viewer 是否需要任何第三方依赖项？
不需要，GroupDocs.Viewer 是一个独立的 API，不需要任何第三方依赖项即可呈现文档。
### 有试用版可供测试吗？
是的，您可以从以下位置下载 GroupDocs.Viewer 的免费试用版：[这里](https://releases.groupdocs.com/)在购买之前评估其功能。