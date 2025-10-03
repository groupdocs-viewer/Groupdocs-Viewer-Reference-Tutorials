---
"description": "了解如何使用 GroupDocs.Viewer 在 .NET 中呈现 CHM 文件。轻松将 CHM 转换为 HTML、JPG、PNG 和 PDF 格式。"
"linktitle": "渲染 CHM 文件"
"second_title": "GroupDocs.Viewer .NET API"
"title": "渲染 CHM 文件"
"url": "/zh/net/rendering-web-documents/render-chm/"
"weight": 10
type: docs
---
# 渲染 CHM 文件

## 介绍
在本教程中，我们将探索如何使用 GroupDocs.Viewer for .NET 渲染 CHM（已编译 HTML 帮助）文件。GroupDocs.Viewer for .NET 是一个强大的文档渲染 API，允许开发人员在其 .NET 应用程序中显示超过 170 种文档类型，而无需安装任何外部软件。

## 先决条件

在深入渲染 CHM 文件之前，请确保您满足以下先决条件：

### 安装 GroupDocs.Viewer for .NET

首先，您需要安装 GroupDocs.Viewer for .NET。您可以从 [GroupDocs 网站](https://releases.groupdocs.com/viewer/net/) 或者通过在包管理器控制台中运行以下命令通过 NuGet 包管理器进行安装：

```bash
Install-Package GroupDocs.Viewer
```

## 导入命名空间

确保将必要的命名空间导入到您的项目中：

```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```

现在让我们将渲染过程分解为多个步骤：

## 步骤 1：定义输出目录

定义要保存渲染文件的目录：

```csharp
string outputDirectory = "Your Document Directory";
```

## 步骤 2：渲染为 HTML

要将 CHM 文件呈现为 HTML，请使用以下代码片段：

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; // 设置为 true 以将所有 CHM 内容转换为单个页面

    viewer.View(options); // 转换所有页面
}
```

## 步骤3：渲染为JPG

要将 CHM 文件渲染为 JPG 图像，请使用以下代码片段：

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // 仅转换第 1、2、3 页
}
```

## 步骤 4：渲染为 PNG

要将 CHM 文件渲染为 PNG 图像，请使用以下代码片段：

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); // 仅转换第 1、2、3 页
}
```

## 步骤 5：渲染为 PDF

要将 CHM 文件呈现为 PDF 文档，请使用以下代码片段：

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); // 转换所有页面
}
```

## 步骤6：检查输出

渲染过程完成后，检查指定的输出目录中是否存在渲染文件：

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 结论

使用 GroupDocs.Viewer for .NET 渲染 CHM 文件非常简单。按照本教程概述的步骤，您可以在 .NET 应用程序中高效地将 CHM 文档转换为各种格式，例如 HTML、图像（JPG、PNG）和 PDF。

## 常见问题解答

### 问题 1：GroupDocs.Viewer 除了可以呈现 CHM 之外，还可以呈现其他文档格式吗？

A1：是的，GroupDocs.Viewer 支持呈现超过 170 种文档格式，包括 PDF、DOCX、XLSX、PPTX 等。

### Q2：GroupDocs.Viewer 与 .NET Core 兼容吗？

A2：是的，GroupDocs.Viewer 除了支持传统的 .NET Framework 之外，还支持 .NET Core。

### 问题 3：我可以自定义不同输出格式的渲染选项吗？

A3：是的，GroupDocs.Viewer 提供了各种用于自定义渲染过程的选项，例如指定页码、设置图像质量和配置输出路径。

### Q4：GroupDocs.Viewer 是否需要任何外部依赖来呈现文档？

A4：否，GroupDocs.Viewer 是一个独立库，不需要任何外部依赖或第三方软件安装。

### Q5：GroupDocs.Viewer 有免费试用版吗？

A5：是的，您可以访问以下网址免费试用 GroupDocs.Viewer： [网站](https://releases。groupdocs.com/).