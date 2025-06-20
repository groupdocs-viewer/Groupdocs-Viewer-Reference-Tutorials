---
"description": "了解如何使用 Groupdocs.Viewer for .NET 优化 JPEG 格式的图像大小和质量。提升您的文档查看体验。"
"linktitle": "调整图像大小和质量 (JPG)"
"second_title": "GroupDocs.Viewer .NET API"
"title": "调整图像大小和质量 (JPG)"
"url": "/zh/net/rendering-documents-images/adjust-image-size-and-quality-jpg/"
"weight": 11
---

# 调整图像大小和质量 (JPG)

## 介绍
Groupdocs.Viewer for .NET 是一个功能强大的库，使开发人员能够将文档查看功能无缝集成到他们的 .NET 应用程序中。文档查看应用程序的一个常见需求是能够调整图像的大小和质量，尤其是在处理 JPEG (JPG) 图像时。在本教程中，我们将引导您完成使用 Groupdocs.Viewer for .NET 调整图像大小和质量的过程。
## 先决条件
在开始之前，请确保您具备以下条件：
1. 对 C# 编程语言有基本的了解。
2. 您的系统上安装了 Visual Studio。
3. 已安装 Groupdocs.Viewer for .NET 库。您可以从 [这里](https://releases。groupdocs.com/viewer/net/).

## 导入命名空间
首先，您需要将必要的命名空间导入到您的 C# 代码中。这些命名空间提供对使用 Groupdocs.Viewer 所需的类和方法的访问。
## 步骤 1：导入命名空间
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

现在，让我们将提供的示例代码分解为多个步骤，以便更好地理解。
## 步骤2：设置输出目录和页面文件路径格式
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.jpg");
```
在此步骤中，我们指定将保存渲染图像的输出目录并定义每个页面图像的文件路径的格式。
## 步骤 3：初始化查看器并配置 JPG 视图选项
```csharp
using (Viewer viewer = new Viewer("Your Document Path"))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.Width = 600;
    options.Height = 800;
    viewer.View(options);
}
```
这里，我们用要查看的文档的路径初始化 Viewer 对象。然后，我们创建一个 JpgViewOptions 实例，并设置 JPEG 图像所需的宽度和高度。
## 步骤4：渲染源文档
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
最后，我们打印一条消息，表明源文档渲染成功以及输出图像的保存位置。

## 结论
在本教程中，我们学习了如何使用 Groupdocs.Viewer for .NET 调整 JPEG 图像的大小和质量。按照上面概述的步骤，您可以轻松地将此功能合并到您的 .NET 应用程序中，为用户提供优化的图像查看体验。
## 常见问题解答
### 我也可以调整图像质量吗？
是的，您可以通过设置 JpgViewOptions 中的 Quality 属性来调整图像质量。
### Groupdocs.Viewer for .NET 支持哪些文档格式？
Groupdocs.Viewer for .NET 支持多种文档格式，包括 DOCX、PDF、PPTX、XLSX 等。
### Groupdocs.Viewer for .NET 是否与 .NET Core 兼容？
是的，Groupdocs.Viewer for .NET 与 .NET Core 以及传统的 .NET Framework 兼容。
### 我可以自定义输出文件命名格式吗？
是的，您可以通过修改代码中的 pageFilePathFormat 变量来自定义输出文件命名格式。
### Groupdocs.Viewer for .NET 是否支持文档注释？
是的，Groupdocs.Viewer for .NET 为文档注释提供全面支持，包括文本突出显示、下划线和注释。