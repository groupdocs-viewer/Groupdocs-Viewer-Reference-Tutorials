---
title: 获取 CAD 工程图的查看信息
linktitle: 获取 CAD 工程图的查看信息
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 检索 CAD 工程图的视图信息。通过无缝 CAD 文件处理增强您的 .NET 应用程序。
type: docs
weight: 10
url: /zh/net/rendering-cad-drawings/get-view-info-cad-drawing/
---
## 介绍
在软件开发领域，有效处理 CAD 绘图至关重要。无论您是为建筑师、工程师还是设计师构建应用程序，为 CAD 文件提供无缝的查看体验都可以极大地提高用户满意度。 GroupDocs.Viewer for .NET 提供了一个强大的解决方案，可以轻松地将 CAD 文件查看功能集成到您的 .NET 应用程序中。在本教程中，我们将引导您完成使用 GroupDocs.Viewer for .NET 获取 CAD 绘图视图信息的过程。
## 先决条件
在我们深入学习本教程之前，请确保您具备以下先决条件：
### 1. 安装适用于.NET的GroupDocs.Viewer
首先，您需要在开发环境中安装 GroupDocs.Viewer for .NET。您可以从以下位置下载最新版本[集团文档网站](https://releases.groupdocs.com/viewer/net/).
### 2. .NET Framework 的基本了解
熟悉 .NET 框架和 C# 编程语言对于学习本教程至关重要。
### 3.搭建开发环境
确保您拥有使用 Visual Studio 或任何其他 .NET 兼容 IDE 设置的开发环境。

## 导入命名空间
在您的 C# 项目中，导入必要的命名空间以利用 GroupDocs.Viewer 功能。

```csharp
using System;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```

## 第 1 步：定义查看信息选项
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
```
在这一步中，我们初始化一个实例`ViewInfoOptions`指定检索视图信息的选项。我们用`ForHtmlView()`方法来指示我们要检索 HTML 视图的信息。
## 步骤 2：配置 CAD 渲染选项
```csharp
viewInfoOptions.CadOptions.RenderLayouts = true;
```
在这里，我们设置`RenderLayouts`财产给`true`包括所有布局。这可确保渲染 CAD 文件中的所有布局。
## 步骤 3：检索 CAD 视图信息
```csharp
CadViewInfo info = viewer.GetViewInfo(viewInfoOptions) as CadViewInfo;
```
我们称之为`GetViewInfo()`查看器对象上的方法，传递`viewInfoOptions`作为检索 CAD 文件视图信息的参数。我们投射返回的`ViewInfo`反对`CadViewInfo`类型。
## 步骤 4：显示文档类型和页数
```csharp
Console.WriteLine("Document type is: " + info.FileType);
Console.WriteLine("Pages count: " + info.Pages.Count);
```
在此步骤中，我们将 CAD 文件中的文档类型和总页数打印到控制台。
## 第 5 步：显示布局和图层
```csharp
Console.WriteLine("\nLayouts:");
foreach (Layout layout in info.Layouts)
    Console.WriteLine(layout);
Console.WriteLine("\nLayers:");
foreach (Layer layer in info.Layers)
    Console.WriteLine(layer);
```
最后，我们迭代从 CAD 文件检索的布局和图层并将它们打印到控制台。

## 结论
通过学习本教程，您已了解如何利用 GroupDocs.Viewer for .NET 无缝获取 CAD 工程图的视图信息。将此功能集成到您的 .NET 应用程序中可以显着增强用户体验并简化 CAD 文件处理。
## 常见问题解答
### 问：GroupDocs.Viewer for .NET 是否与所有 CAD 文件格式兼容？
GroupDocs.Viewer for .NET 支持各种 CAD 文件格式，包括 DWG、DXF、DWF 等。
### 问：我可以自定义 CAD 文件的渲染选项吗？
是的，您可以根据您的要求自定义渲染选项，例如布局、图层和输出格式。
### 问：GroupDocs.Viewer for .NET 是否有免费试用版？
是的，您可以在购买前从网站访问 GroupDocs.Viewer for .NET 免费试用版，以探索其功能。
### 问：GroupDocs.Viewer for .NET 的更新发布频率如何？
GroupDocs 定期发布更新和增强功能，以确保与最新 CAD 文件格式的兼容性并提高整体性能。
### 问：我可以在哪里寻求有关 GroupDocs.Viewer for .NET 的支持或帮助？
您可以访问 GroupDocs.Viewer 论坛或联系支持人员以获取任何疑问、技术帮助或故障排除。