---
title: 渲染 CHM 文件
linktitle: 渲染 CHM 文件
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer 在 .NET 中呈现 CHM 文件。轻松将 CHM 转换为 HTML、JPG、PNG 和 PDF 格式。
type: docs
weight: 10
url: /zh/net/rendering-web-documents/render-chm/
---
## 介绍
在本教程中，我们将探讨如何使用 GroupDocs.Viewer for .NET 呈现 CHM（编译的 HTML 帮助）文件。 GroupDocs.Viewer for .NET 是一个功能强大的文档呈现 API，允许开发人员在其 .NET 应用程序中显示 170 多种文档类型，而无需安装任何外部软件。

## 先决条件

在我们深入研究渲染 CHM 文件之前，请确保您满足以下先决条件：

### 安装适用于 .NET 的 GroupDocs.Viewer

首先，您需要安装 GroupDocs.Viewer for .NET。您可以从以下位置下载该库[集团文档网站](https://releases.groupdocs.com/viewer/net/)或者通过 NuGet 包管理器在包管理器控制台中运行以下命令来安装它：

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

## 第 1 步：定义输出目录

定义要保存渲染文件的目录：

```csharp
string outputDirectory = "Your Document Directory";
```

## 第 2 步：渲染为 HTML

要将 CHM 文件呈现为 HTML，请使用以下代码片段：

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.html");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; //设置为 true 将所有 CHM 内容转换为单个页面

    viewer.View(options); //转换所有页面
}
```

## 第 3 步：渲染为 JPG

要将 CHM 文件渲染为 JPG 图像，请使用以下代码片段：

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.jpg");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); //仅转换第 1、2、3 页
}
```

## 第 4 步：渲染为 PNG

要将 CHM 文件渲染为 PNG 图像，请使用以下代码片段：

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result_{0}.png");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);

    viewer.View(options, 1, 2, 3); //仅转换第 1、2、3 页
}
```

## 第 5 步：渲染为 PDF

要将 CHM 文件呈现为 PDF 文档，请使用以下代码片段：

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "chm_result.pdf");

using (Viewer viewer = new Viewer("Your_CHM_File_Path"))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);

    viewer.View(options); //转换所有页面
}
```

## 第 6 步：检查输出

渲染过程完成后，检查渲染文件的指定输出目录：

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 结论

使用 GroupDocs.Viewer for .NET 呈现 CHM 文件是一个简单的过程。通过遵循本教程中概述的步骤，您可以在 .NET 应用程序中高效地将 CHM 文档转换为各种格式，例如 HTML、图像（JPG、PNG）和 PDF。

## 常见问题解答

### Q1：GroupDocs.Viewer 可以渲染除 CHM 之外的其他文档格式吗？

A1：是的，GroupDocs.Viewer 支持渲染 170 多种文档格式，包括 PDF、DOCX、XLSX、PPTX 等。

### Q2：GroupDocs.Viewer 与 .NET Core 兼容吗？

A2：是的，GroupDocs.Viewer 除了传统的 .NET Framework 之外还支持 .NET Core。

### Q3：我可以自定义不同输出格式的渲染选项吗？

A3：是的，GroupDocs.Viewer 提供了各种自定义渲染过程的选项，例如指定页码、设置图像质量和配置输出路径。

### Q4：GroupDocs.Viewer 渲染文档需要任何外部依赖吗？

A4：不需要，GroupDocs.Viewer 是一个独立的库，不需要任何外部依赖项或第三方软件安装。

### Q5：GroupDocs.Viewer 有免费试用版吗？

 A5：是的，您可以通过访问 GroupDocs.Viewer 免费试用[网站](https://releases.groupdocs.com/).