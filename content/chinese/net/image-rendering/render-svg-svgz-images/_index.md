---
"description": "了解如何使用 GroupDocs.Viewer for .NET 渲染 SVG 和 SVGZ 图像。轻松将矢量图形转换为 HTML、JPG、PNG 和 PDF。"
"linktitle": "渲染 SVG 和 SVGZ 图像"
"second_title": "GroupDocs.Viewer .NET API"
"title": "渲染 SVG 和 SVGZ 图像"
"url": "/zh/net/image-rendering/render-svg-svgz-images/"
"weight": 16
---

# 渲染 SVG 和 SVGZ 图像

## 介绍
在本教程中，我们将指导您使用 GroupDocs.Viewer for .NET 渲染 SVG 和 SVGZ 图像。GroupDocs.Viewer for .NET 是一个强大的文档渲染 API，使开发人员能够在其 .NET 应用程序中渲染各种文档格式。SVG 和 SVGZ 是用于矢量图形的常用图像格式，使用 GroupDocs.Viewer for .NET，您可以轻松地将它们渲染为不同的输出格式，例如 HTML、JPG、PNG 和 PDF。

![使用 GroupDocs.Viewer for .NET 渲染 SVG 和 SVGZ 图像](/viewer/image-rendering/render-svg-and-svgz-images.png)

## 先决条件
在开始之前，请确保您已安装并设置以下先决条件：
1. GroupDocs.Viewer for .NET：从以下位置下载并安装 GroupDocs.Viewer for .NET [这里](https://releases。groupdocs.com/viewer/net/).
2. 开发环境：确保您有一个适用于 .NET 开发的开发环境，例如 Visual Studio。
3. 示例 SVGZ 文件：准备好示例 SVGZ 文件以供测试。

## 导入命名空间
在深入研究代码之前，让我们导入必要的命名空间：
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 步骤 1：将 SVGZ 渲染为 HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```

## 步骤2：将SVGZ渲染为JPG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```

## 步骤3：将SVGZ渲染为PNG
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## 步骤 4：将 SVGZ 渲染为 PDF
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "svgz_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_SVGZ))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```

## 结论
在本教程中，我们学习了如何使用 GroupDocs.Viewer for .NET 渲染 SVG 和 SVGZ 图像。只需几个简单的步骤，您就可以将 SVGZ 图像转换为各种输出格式，例如 HTML、JPG、PNG 和 PDF，从而可以在不同的环境中访问和查看它们。
## 常见问题解答
### GroupDocs.Viewer 可以呈现其他图像格式吗？
是的，GroupDocs.Viewer 支持渲染各种图像格式，包括 PNG、JPEG、BMP、TIFF、GIF 等。
### GroupDocs.Viewer 是否与 .NET Core 兼容？
是的，GroupDocs.Viewer 与 .NET Framework 和 .NET Core 兼容。
### 我可以自定义渲染选项吗？
是的，GroupDocs.Viewer 提供了广泛的渲染选项，允许您根据自己的要求自定义输出。
### GroupDocs.Viewer 是否需要任何第三方依赖项？
不，GroupDocs.Viewer 是一个独立的 API，不需要任何第三方依赖来呈现文档。
### 是否有可供测试的试用版？
是的，您可以从以下网址下载 GroupDocs.Viewer 的免费试用版 [这里](https://releases.groupdocs.com/) 在购买之前评估其功能。