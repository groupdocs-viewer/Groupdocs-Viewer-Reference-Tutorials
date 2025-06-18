---
"description": "了解如何使用 GroupDocs.Viewer for .NET 在 PDF 文档中启用分层渲染。轻松提升文档查看体验。"
"linktitle": "在 PDF 中启用分层渲染"
"second_title": "GroupDocs.Viewer .NET API"
"title": "在 PDF 中启用分层渲染"
"url": "/zh/net/pdf-rendering-options/enable-layered-rendering-pdf/"
"weight": 15
---

# 在 PDF 中启用分层渲染

## 介绍
在本教程中，我们将深入研究如何使用 GroupDocs.Viewer for .NET 在 PDF 文档中启用分层渲染的过程。分层渲染可以增强文档的显示和操作，为用户提供更具交互性的查看体验。

![使用 GroupDocs.Viewer .NET 在 PDF 中启用分层渲染](/viewer/pdf-rendering-options/enable-layered-rendering-in-pdf.png)

## 先决条件
在开始之前，请确保您满足以下先决条件：
1. GroupDocs.Viewer for .NET：确保您已安装在项目中使用 GroupDocs.Viewer for .NET 所需的包或库。
2. Visual Studio：您应该在系统上安装 Visual Studio 来编码和执行提供的示例。
3. 对 C# 的基本了解：本教程假设您熟悉 C# 编程语言语法和概念。

## 导入命名空间
首先将所需的命名空间导入到您的项目中：
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 步骤 1：定义输出目录
```csharp
string outputDirectory = "Your Document Directory";
```
确保指定要保存渲染输出的目录路径。
## 步骤2：定义页面文件路径格式
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
此步骤设置渲染输出中各个页面的文件路径的格式。 `{0}` 是页码的占位符。
## 步骤3：启用分层渲染
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_PDF))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.PdfOptions.EnableLayeredRendering = true;
    viewer.View(options, 1);
}
```
在这里，我们创建一个 `Viewer` 对象并指定要处理的 PDF 文档。然后我们配置 `HtmlViewOptions` 使用定义的页面文件路径格式。通过设置 `EnableLayeredRendering` 财产 `true` 在 `PdfOptions`，我们为PDF文档启用分层渲染。
## 步骤4：显示输出目录
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
最后，我们打印一条消息，表明源文档渲染成功，并提示用户检查指定目录中的输出。

## 结论
使用 GroupDocs.Viewer for .NET 在 PDF 文档中启用分层渲染可增强文档查看功能，为用户提供更丰富、更具交互性的体验。按照本教程中概述的步骤，您可以将此功能无缝集成到您的 .NET 应用程序中。
## 常见问题解答
### PDF 文档中的分层渲染是什么？
分层渲染允许分离和操作 PDF 文档内的不同组件，从而实现交互式查看并增强用户体验。
### 我可以自定义渲染文档的输出目录吗？
是的，您可以根据需要为输出指定任何目录路径。
### GroupDocs.Viewer 除了 PDF 之外还支持其他文件格式吗？
是的，GroupDocs.Viewer 支持多种文档格式，包括 Word、Excel、PowerPoint 等。
### GroupDocs.Viewer 是否与 .NET Core 兼容？
是的，GroupDocs.Viewer 与 .NET Framework 和 .NET Core 环境兼容。
### 我可以在哪里找到额外的支持或帮助？
您可以访问 GroupDocs.Viewer 论坛以获取有关查看器库的任何疑问或帮助。