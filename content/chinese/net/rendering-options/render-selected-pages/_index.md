---
"description": "了解如何使用 Groupdocs.Viewer for .NET 渲染文档中的选定页面。包含代码示例的分步教程。"
"linktitle": "渲染选定的页面"
"second_title": "GroupDocs.Viewer .NET API"
"title": "渲染选定的页面"
"url": "/zh/net/rendering-options/render-selected-pages/"
"weight": 17
type: docs
---
# 渲染选定的页面

## 介绍

在本教程中，我们将深入探讨如何使用 Groupdocs.Viewer for .NET 渲染文档中的选定页面。无论您是经验丰富的开发人员还是刚刚入门，本分步指南都能帮助您轻松完成整个过程。

## 先决条件

在开始之前，请确保您已满足以下先决条件：

### 1.安装

确保您的开发环境中已安装 Groupdocs.Viewer for .NET。如果没有，您可以从 [下载链接](https://releases。groupdocs.com/viewer/net/).

## 导入命名空间

在 C# 代码文件中，导入必要的命名空间以访问所需的类和方法。您可以使用 `using` 指示：

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

现在让我们将提供的示例代码分解为多个步骤：

## 步骤1：设置输出目录

定义要保存渲染页面的目录。替换 `"Your Document Directory"` 使用所需的目录路径。

```csharp
string outputDirectory = "Your Document Directory";
```

## 步骤2：定义页面文件路径格式

指定渲染页面文件路径的格式。这将用于将每个页面保存为输出目录中的 HTML 文件。

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## 步骤3：实例化查看器对象

创建 Viewer 类的实例，并将您想要呈现的文档的路径作为参数传递。

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX))
```

## 步骤 4：配置 HTML 视图选项

设置 HTML 视图渲染选项。在本例中，我们将配置选项以将资源嵌入到 HTML 输出中。

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```

## 步骤 5：渲染选定的页面

指定要渲染的页码。在本例中，我们将渲染第 1 至第 3 页。然后，调用 Viewer 对象的 View 方法，并将选项和页码作为参数传递。

```csharp
viewer.View(options, 1, 3);
```

## 步骤6：输出结果

最后，显示一条消息，表明文档渲染成功以及输出文件的保存位置。

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 结论

恭喜！您已成功学习使用 Groupdocs.Viewer for .NET 渲染文档中的选定页面。掌握这些知识后，您现在可以轻松地将文档渲染功能集成到您的 .NET 应用程序中。

## 常见问题解答

### 问：我可以渲染不同类型的文档（例如 PDF 或图像）的页面吗？

答：是的，Groupdocs.Viewer for .NET 支持呈现各种文档格式的页面，包括 PDF、Microsoft Office 文档和图像文件。

### 问：购买前是否有试用版可供测试？

答：是的，您可以从以下位置访问 Groupdocs.Viewer for .NET 的免费试用版 [网站](https://releases。groupdocs.com/).

### 问：我可以自定义 HTML 以外的输出格式吗？

答：当然，除了 HTML 之外，Groupdocs.Viewer for .NET 还提供将页面呈现为图像、PDF 等的选项。

### 问：如何获得用于测试目的的临时许可证？

答：临时许可证可以从 [临时执照页面](https://purchase.groupdocs.com/temporary-license/) 在 Groupdocs 网站上。

### 问：我遇到任何问题可以在哪里寻求帮助或获得帮助？

答：您可以访问 [Groupdocs.Viewer 论坛](https://forum.groupdocs.com/c/viewer/9) 寻求社区和开发人员的支持和指导。