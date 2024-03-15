---
title: 渲染 CMX 图像
linktitle: 渲染 CMX 图像
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 轻松将 CMX 图像渲染为各种格式。增强您的文档管理。
type: docs
weight: 13
url: /zh/net/image-rendering/render-cmx-images/
---
## 介绍
在文档管理和操作领域，渲染各种格式的图像是一项关键任务。 GroupDocs.Viewer for .NET 通过提供将 CMX 图像渲染为不同格式（例如 HTML、JPG、PNG 和 PDF）的全面功能，简化了此过程。本教程将指导您完成使用 GroupDocs.Viewer for .NET 渲染 CMX 图像的分步过程。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
1.  GroupDocs.Viewer for .NET 库：从以下位置下载并安装 GroupDocs.Viewer for .NET 库[这里](https://releases.groupdocs.com/viewer/net/).
2. 开发环境：拥有一个使用.NET框架设置的工作开发环境。
3. CMX 图像文件：获取您想要渲染的 CMX 图像文件。

## 导入命名空间
在继续之前，请确保导入必要的命名空间以访问 .NET 应用程序中的 GroupDocs.Viewer 功能：
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

## 渲染为 HTML
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.html");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    viewer.View(options);
}
```
- 定义输出目录：设置要存储渲染的 HTML 文件的目录。
- 指定文件路径格式：定义输出 HTML 文件的格式。
- 实例化 Viewer 对象：使用 CMX 图像文件创建 Viewer 类的实例。
- HTML 呈现选项：配置 HTML 呈现选项，例如嵌入资源。
- 将 CMX 渲染为 HTML：调用查看器对象的 View 方法将 CMX 图像渲染为 HTML。
## 渲染为 JPG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
- 定义输出目录：设置存储渲染的 JPG 文件的目录。
- 指定文件路径格式：定义输出 JPG 文件的格式。
- 实例化 Viewer 对象：使用 CMX 图像文件创建 Viewer 类的实例。
- JPG 渲染选项：配置 JPG 渲染选项。
- 将 CMX 渲染为 JPG：调用查看器对象的 View 方法将 CMX 图像渲染为 JPG。
## 渲染为 PNG
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result_{0}.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- 定义输出目录：设置用于存储渲染的 PNG 文件的目录。
- 指定文件路径格式：定义输出 PNG 文件的格式。
- 实例化 Viewer 对象：使用 CMX 图像文件创建 Viewer 类的实例。
- PNG 渲染选项：配置 PNG 渲染选项。
- 将 CMX 渲染为 PNG：调用查看器对象的 View 方法将 CMX 图像渲染为 PNG。
## 渲染为 PDF
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "cmx_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_CMX))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
   
    viewer.View(options);
}
```
- 定义输出目录：设置用于存储渲染的 PDF 文件的目录。
- 指定文件路径格式：定义输出 PDF 文件的格式。
- 实例化 Viewer 对象：使用 CMX 图像文件创建 Viewer 类的实例。
- PDF 渲染选项：配置 PDF 渲染选项。
- 将 CMX 渲染为 PDF：调用查看器对象的 View 方法将 CMX 图像渲染为 PDF。

## 结论
总之，GroupDocs.Viewer for .NET 提供了一个强大的解决方案，可以将 CMX 图像无缝呈现为各种格式。通过遵循本教程中概述的步骤，您可以轻松地将 CMX 图像渲染功能集成到您的 .NET 应用程序中，从而提高文档管理效率。
## 常见问题解答
### 我可以渲染 CMX 图像的特定页面吗？
是的，您可以通过在渲染选项中指定页码来渲染特定页面。
### GroupDocs.Viewer for .NET 是否与所有 .NET 框架兼容？
是的，GroupDocs.Viewer for .NET 与多个 .NET 框架兼容，包括 .NET Core 和 .NET Framework。
### GroupDocs.Viewer 是否支持渲染加密的 CMX 图像？
是的，GroupDocs.Viewer 支持使用适当的解密密钥渲染加密的 CMX 图像。
### 我可以为不同的输出格式自定义渲染选项吗？
当然，GroupDocs.Viewer 提供了广泛的选项，可根据您的要求自定义渲染参数。
### 是否有提供 GroupDocs.Viewer 支持的社区论坛？
是的，您可以在支持论坛上寻求帮助并与 GroupDocs.Viewer 社区互动[这里](https://forum.groupdocs.com/c/viewer/9).