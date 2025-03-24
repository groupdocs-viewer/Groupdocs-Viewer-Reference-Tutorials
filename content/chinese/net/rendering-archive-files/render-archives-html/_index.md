---
title: 将档案渲染到单个或多个 HTML 页面
linktitle: 将档案渲染到单个或多个 HTML 页面
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 将存档呈现为 HTML 页面。轻松地将文档查看功能集成到您的 .NET 应用程序中。
weight: 12
url: /zh/net/rendering-archive-files/render-archives-html/
---
## 介绍
GroupDocs.Viewer for .NET 是一个功能强大的文档呈现库，允许开发人员轻松地将文档查看功能集成到他们的 .NET 应用程序中。无论您需要将存档呈现为单个还是多个 HTML 页面，本教程都将逐步指导您完成该过程。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
1.  GroupDocs.Viewer for .NET：确保您的项目中安装了该库。您可以从以下位置下载：[这里](https://releases.groupdocs.com/viewer/net/).
2. 开发环境：为 .NET 开发设置一个工作开发环境。
3. 文档目录：准备一个存储文档的目录。
4. C# 的基本了解：熟悉 C# 编程语言基础知识。

## 导入命名空间
在您的 C# 代码中，确保导入必要的命名空间：
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

请按照以下步骤使用 GroupDocs.Viewer for .NET 将存档呈现到单个或多个 HTML 页面：
## 第1步：设置输出目录
定义要保存渲染的 HTML 页面的目录：
```csharp
string outputDirectory = "Your Document Directory";
```
## 第2步：定义文件路径格式
指定 HTML 页面的文件路径格式。对于单页渲染：
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result.html");
```
对于多页面渲染：
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "RAR_result_page_{0}.html");
```
## 第 3 步：渲染为单页 HTML
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderToSinglePage = true; 
    viewer.View(options);
}
```
## 第 4 步：渲染为多个 HTML 页面
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.ArchiveOptions.ItemsPerPage = 10; //设置每页的项目
    viewer.View(options);
}
```
## 第 5 步：检查输出
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 结论
使用 GroupDocs.Viewer for .NET 将存档呈现为 HTML 页面是一个简单的过程。通过遵循本教程中概述的步骤，您可以将文档查看功能无缝集成到您的 .NET 应用程序中。
## 常见问题解答
### 除了档案之外，我还可以渲染其他文档格式吗？
是的，GroupDocs.Viewer 支持多种文档格式，包括 PDF、DOCX、XLSX、PPTX 等。
### GroupDocs.Viewer 是否适用于桌面和 Web 应用程序？
当然，GroupDocs.Viewer 可以在桌面和 Web 应用程序中无缝使用。
### GroupDocs.Viewer 是否提供查看器界面的自定义选项？
是的，您可以根据您的要求自定义查看器界面。
### 我可以使用 GroupDocs.Viewer 异步呈现文档吗？
是的，GroupDocs.Viewer 提供异步渲染功能以提高性能。
### GroupDocs.Viewer是否支持文档注释？
是的，GroupDocs.Viewer 允许用户高效地查看和管理文档注释。