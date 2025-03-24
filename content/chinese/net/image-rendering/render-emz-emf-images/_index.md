---
title: 渲染 EMZ 和 EMF 图像
linktitle: 渲染 EMZ 和 EMF 图像
second_title: GroupDocs.Viewer .NET API
description: 了解如何使用 GroupDocs.Viewer for .NET 将 EMZ 和 EMF 图像呈现为各种格式。面向开发人员的易于理解的教程。
weight: 14
url: /zh/net/image-rendering/render-emz-emf-images/
---
## 介绍

GroupDocs.Viewer for .NET 是一个功能强大的文档呈现 API，允许开发人员在其 .NET 应用程序中显示各种文档类型，包括 EMZ（增强型 Windows 图元文件）和 EMF（增强型图元文件）图像。在本教程中，我们将探索如何使用 GroupDocs.Viewer for .NET 将 EMZ 和 EMF 图像渲染为不同的格式，例如 HTML、JPG、PNG 和 PDF。

## 先决条件

在我们开始之前，请确保您具备以下先决条件：

1.  GroupDocs.Viewer for .NET：您可以从以下位置下载该库：[这里](https://releases.groupdocs.com/viewer/net/).
2. 开发环境：确保您为 .NET 开发设置了兼容的开发环境。
3. 示例 EMZ/EMF 图像：具有可用于渲染的示例 EMZ 和 EMF 图像。

## 导入命名空间

在深入研究代码之前，让我们导入必要的名称空间：

```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```

现在，让我们以分步指南的形式将每个示例分解为多个步骤：

## 将 EMZ/EMF 图像渲染为 HTML

### 第1步：设置输出目录：
```csharp
string outputDirectory = "Your Document Directory";
```
代替`"Your Document Directory"`以及要保存渲染的 HTML 文件的路径。

### 第2步：定义页面文件路径格式：
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.html");
```
这将指定渲染的 HTML 文件的文件路径格式。

### 第 3 步：渲染为 HTML：
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    
    viewer.View(options);
}
```
此代码初始化`Viewer`对象与示例 EMZ 图像并使用指定选项将其呈现为 HTML 格式。

## 将 EMZ/EMF 图像渲染为 JPG、PNG 和 PDF

重复以下步骤渲染为 JPG、PNG 和 PDF 格式：

### 步骤1：定义页面文件路径格式：
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "emz_result.jpg");
```
根据所需的输出格式调整文件名和扩展名（`jpg`, `png` ， 或者`pdf`）。

### 第 2 步：渲染为相应格式：
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_EMZ))
{
    //根据输出格式（Jpg、Png、Pdf）调整选项
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    
    viewer.View(options);
}
```
代替`JpgViewOptions`和`PngViewOptions`或者`PdfViewOptions`基于所需的输出格式。

## 结论

总之，GroupDocs.Viewer for .NET 提供了一个无缝解决方案，可在 .NET 应用程序中将 EMZ 和 EMF 图像呈现为各种格式。通过遵循本教程中概述的步骤，开发人员可以轻松地将文档渲染功能集成到他们的应用程序中。

## 常见问题解答

### 问：GroupDocs.Viewer 能否呈现除 EMZ 和 EMF 图像之外的其他文档格式？
答：是的，GroupDocs.Viewer 支持多种文档格式，包括 PDF、DOCX、PPTX、XLSX 等。

### 问：GroupDocs.Viewer for .NET 是否有免费试用版？
答：是的，您可以免费试用[这里](https://releases.groupdocs.com/).

### 问：GroupDocs.Viewer 是否为开发人员提供支持？
答：是的，GroupDocs 通过其[论坛](https://forum.groupdocs.com/c/viewer/9)开发人员可以在这里提出问题并寻求帮助。

### 问：我可以购买 GroupDocs.Viewer for .NET 的临时许可证吗？
答：是的，可以购买临时许可证[这里](https://purchase.groupdocs.com/temporary-license/).

### 问：在哪里可以找到 GroupDocs.Viewer for .NET 的详细文档？
答：可以参考文档[这里](https://tutorials.groupdocs.com/viewer/net/)有关使用 API 的全面指导。