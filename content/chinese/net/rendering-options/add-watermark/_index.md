---
title: 在文档中添加水印
linktitle: 在文档中添加水印
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 向文档无缝添加水印。通过这个易于理解的教程增强文档安全性和品牌形象。
type: docs
weight: 10
url: /zh/net/rendering-options/add-watermark/
---
## 介绍
在当今的数字时代，无缝管理和查看各种文档格式对于许多企业和个人来说都是必需的。幸运的是，借助 GroupDocs.Viewer for .NET 等工具，处理文档变得轻而易举。这个强大的 .NET 库使开发人员能够轻松地将文档查看功能集成到他们的应用程序中，从而允许用户无需使用创建文档的原始软件即可查看文档。
## 先决条件
在深入使用 GroupDocs.Viewer for .NET 向文档添加水印之前，请确保您具备以下条件：
1. 环境设置：设置开发环境并安装.NET Framework 或.NET Core。
2.  GroupDocs.Viewer for .NET：从以下位置下载并安装 GroupDocs.Viewer for .NET 库[下载页面](https://releases.groupdocs.com/viewer/net/).
3. 文档文件：准备您要使用的文档文件，例如 DOCX、PDF 或其他文件。
4. C# 基础知识：需要熟悉 C# 编程语言才能实现代码示例。

## 导入命名空间
在开始使用 GroupDocs.Viewer for .NET 向文档添加水印之前，请确保在 C# 代码中导入所需的命名空间。此步骤允许您无缝访问库提供的类和方法。

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

现在，让我们逐步了解使用 GroupDocs.Viewer for .NET 向文档添加水印的过程。按照以下步骤将水印功能无缝集成到您的应用程序中。
## 第1步：设置输出目录
```csharp
string outputDirectory = "Your Document Directory";
```
指定应用水印后保存输出文件的目录。
## 第2步：定义页面文件路径格式
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
设置渲染页面的文件路径的格式。在此示例中，将生成带有页码的 HTML 文件。
## 第 3 步：实例化查看器对象
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
{
    //代码将在下一步中继续...
}
```
创建 Viewer 类的实例，并将文档文件的路径作为参数传递。在此示例中，我们使用示例 DOCX 文件。
## 步骤 4：配置 HTML 视图选项
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.Watermark = new Watermark("This is a watermark");
```
配置 HTML 视图选项，包括要添加到文档的水印文本。
## 第5步：查看带水印的文档
```csharp
viewer.View(options);
```
调用 Viewer 对象的 View 方法，传递配置的选项。这将呈现带有指定水印的文档。
## 第6步：显示输出目录路径
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
通知用户文档已成功渲染并指示保存输出文件的目录。

## 结论
GroupDocs.Viewer for .NET 提供了一种以编程方式向文档添加水印的便捷方法。通过遵循本教程中概述的步骤，您可以将水印功能无缝集成到 .NET 应用程序中，从而增强文档安全性和品牌化。
## 常见问题解答
### 我可以自定义水印的外观吗？
是的，您可以自定义水印的各种属性，例如文本、字体、颜色、大小和位置。
### GroupDocs.Viewer 是否支持查看远程源文档？
是的，GroupDocs.Viewer 支持查看本地存储和远程 URL 中的文档。
### GroupDocs.Viewer for .NET 是否有试用版？
是的，您可以从以下位置下载免费试用版[这里](https://releases.groupdocs.com/).
### 我可以为文档的多个页面添加水印吗？
当然，GroupDocs.Viewer 允许向文档的单个页面或所有页面添加水印。
### 如果遇到任何问题，如何获得支持或帮助？
您可以从 GroupDocs 社区论坛寻求帮助和支持[这里](https://forum.groupdocs.com/c/viewer/9).