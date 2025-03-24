---
title: 渲染跟踪更改
linktitle: 渲染跟踪更改
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 轻松呈现文档中的跟踪更改。提高您的文档管理效率。
weight: 10
url: /zh/net/rendering-word-processing-documents/render-tracked-changes/
---

# 渲染跟踪更改

## 介绍
在当今的数字时代，有效管理和查看文档对于企业和个人都至关重要。随着先进技术的出现，GroupDocs.Viewer for .NET 等解决方案彻底改变了我们与各种文档格式（包括 Word 文档、PDF 等）交互的方式。在本综合指南中，我们将深入研究如何利用 GroupDocs.Viewer for .NET 无缝呈现文档中的跟踪更改。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
1. GroupDocs.Viewer for .NET 安装：从以下位置下载并安装 GroupDocs.Viewer for .NET[网站](https://releases.groupdocs.com/viewer/net/).
2. .NET Framework：确保您的系统上安装了 .NET Framework。
3. 文档目录：准备一个用于存储文档的目录。

## 导入命名空间
首先，将必要的命名空间导入到您的项目中。这些命名空间对于有效利用 GroupDocs.Viewer 功能至关重要。
## 脚步：
1. 打开您的 IDE：启动您首选的集成开发环境 (IDE)，例如 Visual Studio。
2. 创建或打开您的项目：开始一个新项目或打开您打算使用 GroupDocs.Viewer 的现有项目。
3. 导入命名空间：在项目文件或代码文件中，添加以下命名空间：
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

现在，让我们将提供的示例分解为多个步骤，以指导您使用 GroupDocs.Viewer for .NET 呈现跟踪的更改。
## 第1步：设置输出目录
首先，定义要保存渲染输出的目录。
```csharp
string outputDirectory = "Your Document Directory";
```
代替`"Your Document Directory"`以及您所需目录的路径。
## 第2步：定义页面文件路径格式
指定页面文件路径的格式。此格式将确定呈现的页面的命名和存储方式。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
这里，`"page_{0}.html"`表示页面将被命名为`page_1.html`, `page_2.html`， 等等。
## 第 3 步：初始化查看器对象
初始化一个`Viewer`通过将文档的路径作为参数传递来获取对象。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX_WITH_TRACKED_CHANGES))
{
    //代码继续下一步...
}
```
确保更换`TestFiles.SAMPLE_DOCX_WITH_TRACKED_CHANGES`以及您的文档的路径。
## 步骤 4：配置 HTML 视图选项
配置 HTML 视图选项以自定义呈现设置，例如呈现跟踪更改。
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.WordProcessingOptions.RenderTrackedChanges = true;
```
此步骤允许在输出 HTML 中呈现跟踪的更改。
## 第5步：渲染文档
使用配置的选项渲染文档。
```csharp
viewer.View(options);
```
此命令根据提供的设置启动渲染过程。
## 第6步：显示输出目录
告知用户渲染输出的存储位置。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
此消息通知用户渲染成功以及在哪里可以找到输出文件。

## 结论
总之，GroupDocs.Viewer for .NET 提供了一个强大的解决方案，可以轻松呈现文档中跟踪的更改。通过遵循本文概述的分步指南，您可以将此功能无缝集成到您的 .NET 应用程序中，从而提高文档管理效率。
## 常见问题解答
### 我可以使用 GroupDocs.Viewer for .NET 以各种文档格式呈现跟踪的更改吗？
是的，GroupDocs.Viewer 支持以多种格式呈现跟踪的更改，包括 DOCX、PDF 等。
### GroupDocs.Viewer for .NET 是否与所有 .NET Framework 版本兼容？
是的，GroupDocs.Viewer for .NET 与各种版本的 .NET Framework 兼容，确保广泛的兼容性。
### GroupDocs.Viewer 是否提供任何用于测试目的的免费试用版？
是的，您可以在做出购买决定之前免费试用 GroupDocs.Viewer 以探索其功能。
### 我可以自定义渲染设置以满足特定要求吗？
当然，GroupDocs.Viewer 提供了广泛的自定义选项，允许您根据需要定制渲染过程。
### 如果我遇到任何问题或对 GroupDocs.Viewer 有疑问，可以在哪里寻求帮助？
如需支持和社区帮助，您可以访问 GroupDocs.Viewer 论坛：[这个链接](https://forum.groupdocs.com/c/viewer/9).