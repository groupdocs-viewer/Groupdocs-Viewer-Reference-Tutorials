---
title: 在 CAD 工程图中渲染单一布局
linktitle: 在 CAD 工程图中渲染单一布局
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 在 CAD 绘图中渲染单一布局。在 .NET 应用程序中无缝集成的简单步骤。
weight: 14
url: /zh/net/rendering-cad-drawings/render-single-layout-cad/
---

# 在 CAD 工程图中渲染单一布局

## 介绍
在 .NET 开发领域，处理和查看 CAD 绘图是一项常见要求。 GroupDocs.Viewer for .NET 通过提供在 .NET 应用程序中渲染 CAD 绘图的全面解决方案来简化此任务。在本教程中，我们将深入研究使用 GroupDocs.Viewer for .NET 在 CAD 绘图中渲染单个布局。
## 先决条件
在深入学习本教程之前，请确保您具备以下先决条件：
- 对 C# 编程语言和 .NET 框架有基本了解。
- Visual Studio 安装在您的系统上。
- 下载并在项目中引用的 .NET 库的 GroupDocs.Viewer。您可以从以下位置下载：[这里](https://releases.groupdocs.com/viewer/net/).
- 熟悉 CAD 文件格式及其结构。

## 导入命名空间
首先，将必要的命名空间导入到 C# 代码中以访问 GroupDocs.Viewer 功能。

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

## 第 1 步：定义输出目录
指定要保存渲染输出的目录。
```csharp
string outputDirectory = "Your Document Directory";
```
## 第2步：定义页面文件路径格式
定义每个呈现页面的文件路径的格式。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
## 第 3 步：实例化查看器对象
创建 GroupDocs.Viewer 提供的 Viewer 类的实例。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DWG_WITH_LAYOUTS_AND_LAYERS))
```
## 步骤 4：配置 HTML 视图选项
配置用于使用嵌入资源呈现 HTML 输出的选项。
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## 步骤 5：指定 CAD 布局名称
指定要渲染的 CAD 布局的名称。
```csharp
options.CadOptions.LayoutName = "Model";
```
## 第 6 步：渲染 CAD 绘图
使用指定选项调用 Viewer 对象的 View 方法。
```csharp
viewer.View(options);
```
## 第7步：显示成功消息
通知用户源文档已成功呈现。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 结论
渲染 CAD 工程图，尤其是在处理布局时，可能是一项艰巨的任务。然而，使用 GroupDocs.Viewer for .NET，该过程变得无缝且高效。通过遵循本教程中概述的步骤，您可以轻松地在 .NET 应用程序中渲染 CAD 绘图中的单个布局。
## 常见问题解答
### 我可以使用 GroupDocs.Viewer for .NET 同时渲染多个布局吗？
是的，GroupDocs.Viewer for .NET 支持从 CAD 绘图渲染多个布局。
### GroupDocs.Viewer 是否与不同的 CAD 文件格式兼容？
当然，GroupDocs.Viewer 支持多种 CAD 文件格式，包括 DWG、DXF、DGN 等。
### 我可以自定义 CAD 工程图的渲染选项吗？
是的，GroupDocs.Viewer 提供了广泛的选项来根据您的要求自定义渲染设置。
### GroupDocs.Viewer for .NET 是否有免费试用版？
是的，您可以通过免费试用来探索 GroupDocs.Viewer 的功能[这里](https://releases.groupdocs.com/).
### 在哪里可以获得 GroupDocs.Viewer for .NET 的支持？
如有任何疑问或帮助，您可以访问 GroupDocs.Viewer 论坛[这里](https://forum.groupdocs.com/c/viewer/9).