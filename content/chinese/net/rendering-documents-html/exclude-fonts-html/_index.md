---
"description": "了解如何使用 GroupDocs.Viewer for .NET 从渲染的 HTML 中排除字体。按照此分步指南操作，即可实现无缝文档显示。"
"linktitle": "从渲染的 HTML 中排除字体"
"second_title": "GroupDocs.Viewer .NET API"
"title": "从渲染的 HTML 中排除字体"
"url": "/zh/net/rendering-documents-html/exclude-fonts-html/"
"weight": 10
type: docs
---
# 从渲染的 HTML 中排除字体

## 介绍
GroupDocs.Viewer for .NET 是一个功能强大的文档渲染库，它允许开发人员在其 .NET 应用程序中显示 50 多种文档格式，而无需任何外部依赖项。在本教程中，我们将重点介绍 GroupDocs.Viewer 的一项特定功能：从渲染的 HTML 输出中排除字体。 
## 先决条件
开始之前，请确保您已准备好以下内容：
1. 对 C# 和 .NET 开发有基本的了解。
2. 已安装 GroupDocs.Viewer for .NET。您可以从 [这里](https://releases。groupdocs.com/viewer/net/).
3. Visual Studio 或任何其他用于 C# 开发的 IDE。

## 导入命名空间
在您的 C# 代码中，确保包含必要的命名空间：
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 步骤 1：定义输出目录
设置您想要保存渲染的 HTML 文件的目录。
```csharp
string outputDirectory = "Your Document Directory";
```
## 步骤2：定义页面文件路径格式
指定所呈现文档的各个页面的文件路径的格式。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 步骤3：初始化查看器对象
使用您想要呈现的文档实例化 Viewer 对象。
```csharp
using (Viewer viewer = new Viewer("YourDocumentPath"))
{
    // 您的代码在此处
}
```
## 步骤 4：设置 HTML 视图选项
定义 HTML 渲染的选项，包括嵌入资源的格式和要排除的字体。
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.FontsToExclude.Add("Arial");
```
## 步骤5：渲染文档
将 HTML 视图选项传递给 Viewer 对象以呈现文档。
```csharp
viewer.View(options);
```
## 步骤6：输出渲染文档位置
告知用户渲染后的 HTML 文件的保存位置。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 结论
在本教程中，我们学习了如何使用 GroupDocs.Viewer for .NET 从渲染的 HTML 输出中排除字体。按照上面概述的步骤，您可以自定义渲染过程以满足您的特定需求，确保在应用程序中以最佳方式显示文档。
## 常见问题解答
### 我可以从呈现的 HTML 中排除多种字体吗？
是的，您可以添加多个字体名称到 `FontsToExclude` HTML 视图选项中的列表。
### GroupDocs.Viewer 是否与所有 .NET 框架兼容？
是的，GroupDocs.Viewer 支持 .NET Framework 4.6.1 及更高版本。
### 我可以从远程存储位置呈现文档吗？
是的，GroupDocs.Viewer 支持从本地存储以及远程存储位置和流呈现文档。
### GroupDocs.Viewer 是否支持 HTML 输出的响应式设计？
是的，您可以通过相应地调整 HTML 视图选项来启用响应式渲染。
### GroupDocs.Viewer 是否提供技术支持？
是的，您可以寻求帮助并参与讨论 [GroupDocs.Viewer 论坛](https://forum。groupdocs.com/c/viewer/9).