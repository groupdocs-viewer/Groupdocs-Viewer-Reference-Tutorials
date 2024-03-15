---
title: CAD 工程图中的渲染图层
linktitle: CAD 工程图中的渲染图层
second_title: GroupDocs.Viewer .NET API
description: 使用 GroupDocs.Viewer for .NET 在 .NET 应用程序中无缝渲染 CAD 绘图。探索渲染选项、自定义图层等。
type: docs
weight: 13
url: /zh/net/rendering-cad-drawings/render-layers-cad/
---
## 介绍
GroupDocs.Viewer for .NET 是一个功能强大的工具，使开发人员能够将文档呈现功能无缝集成到他们的 .NET 应用程序中。无论您需要渲染 CAD 绘图、PDF、Microsoft Office 文档还是其他文档，GroupDocs.Viewer 都能提供全面的解决方案。
## 先决条件
在深入使用 GroupDocs.Viewer for .NET 之前，请确保您满足以下先决条件：
- 对 C# 编程语言有基本了解。
- 在您的计算机上设置.NET 开发环境。
- 安装了适用于 .NET 的 GroupDocs.Viewer。您可以从以下位置下载：[这里](https://releases.groupdocs.com/viewer/net/).
- 访问 GroupDocs.Viewer for .NET 文档以供参考，可以找到[这里](https://reference.groupdocs.com/viewer/net/).

## 导入命名空间
要开始使用 GroupDocs.Viewer for .NET，您需要在项目中导入所需的命名空间。按着这些次序：

```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

让我们将提供的示例分解为多个步骤：
## 第 1 步：定义输出目录
```csharp
string outputDirectory = "Your Document Directory";
```
## 第2步：定义页面文件路径格式
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 第 3 步：初始化查看器对象
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
{
    //代码块继续...
}
```
## 第 4 步：设置 HTML 视图选项
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## 第 5 步：定义 CAD 图层
```csharp
options.CadOptions.Layers = new List<Layer>
{
    new Layer("QUADRANT")
};
```
## 第 6 步：渲染文档
```csharp
viewer.View(options);
```
## 第7步：输出渲染文档位置
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 结论
借助 GroupDocs.Viewer for .NET，在 .NET 应用程序中渲染 CAD 绘图成为一个无缝过程。通过遵循本指南中概述的步骤，您可以轻松地将文档渲染功能集成到您的项目中。
## 常见问题解答
### GroupDocs.Viewer 是否与所有类型的 CAD 绘图兼容？
是的，GroupDocs.Viewer 支持渲染多种 CAD 绘图格式，包括 DWG 和 DXF。
### 我可以自定义 CAD 工程图的渲染选项吗？
当然，GroupDocs.Viewer 提供了各种自定义选项，例如指定要渲染的图层或设置输出格式。
### GroupDocs.Viewer 是否需要互联网连接来呈现文档？
不需要，GroupDocs.Viewer 在本地执行渲染，无需互联网连接。
### GroupDocs.Viewer for .NET 是否有免费试用版？
是的，您可以免费试用 GroupDocs.Viewer for .NET[这里](https://releases.groupdocs.com/).
### 在哪里可以获得 GroupDocs.Viewer for .NET 的支持？
如需任何技术帮助或疑问，您可以访问 GroupDocs.Viewer 论坛[这里](https://forum.groupdocs.com/c/viewer/9).