---
"description": "探索 Groupdocs.Viewer for .NET 的强大功能，无缝渲染 Numbers 文件。轻松转换为 HTML、JPG、PNG 和 PDF。"
"linktitle": "渲染数字"
"second_title": "GroupDocs.Viewer .NET API"
"title": "渲染数字"
"url": "/zh/net/spreadsheet-rendering-options/rendering-numbers/"
"weight": 15
type: docs
---
# 渲染数字

## 介绍
欢迎学习本教程，了解如何使用 Groupdocs.Viewer for .NET 渲染 Numbers 文件。无论您是经验丰富的开发人员还是初学者，本指南都将指导您完成将 Numbers 文档转换为各种格式的过程。Groupdocs.Viewer for .NET 是一款功能强大的工具，可让您将文档查看功能无缝集成到您的 .NET 应用程序中。
## 先决条件
在深入学习本教程之前，请确保您已满足以下先决条件：
- 具备 C# 和 .NET 开发的工作知识。
- Groupdocs.Viewer for .NET 库已安装。您可以下载 [这里](https://releases。groupdocs.com/viewer/net/).
- 保存输出文件的文档目录路径。
## 导入命名空间
在您的 C# 项目中，确保导入必要的命名空间以使用 Groupdocs.Viewer 库：
```csharp
using System;
using System.Collections.Generic;
using System.Text;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 步骤 1：设置输出目录
在开始渲染之前，请定义转换后文件保存的输出目录。将“您的文档目录”替换为实际路径：
```csharp
string outputDirectory = "Your Document Directory";
```
## 步骤 2：渲染为多页 HTML
使用以下代码将 Numbers 文件转换为多页 HTML：
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.html");
using (Viewer viewer = new Viewer("SAMPLE.NUMBERS"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## 步骤3：渲染为JPG
使用以下代码将 Numbers 文件转换为 JPG 格式：
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 步骤 4：渲染为 PNG
使用以下代码将 Numbers 文件转换为 PNG 格式：
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 步骤 5：渲染为 PDF
最后，使用以下代码将 Numbers 文件转换为 PDF 格式：
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Numbers_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_NUMBERS))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
恭喜！您已成功使用 Groupdocs.Viewer for .NET 将 Numbers 文件渲染为各种格式。
## 结论
在本教程中，我们介绍了使用 Groupdocs.Viewer for .NET 渲染 Numbers 文件的基础知识。这个强大的库提供了无缝集成，可在 .NET 应用程序中查看和转换文档。
## 常见问题解答
### 我可以将 Groupdocs.Viewer for .NET 与其他文档类型一起使用吗？
是的，Groupdocs.Viewer 支持多种文档格式，包括 Word、Excel、PDF 等。
### 是否有可用于测试目的的临时许可证？
是的，您可以获得临时驾照 [这里](https://purchase.groupdocs.com/temporary-license/) 用于测试。
### 在哪里可以找到对 Groupdocs.Viewer for .NET 的支持？
访问 [Groupdocs.Viewer 论坛](https://forum.groupdocs.com/c/viewer/9) 寻求帮助和讨论。
### 如何购买 Groupdocs.Viewer for .NET 的完整版本？
您可以购买完整版 [这里](https://purchase。groupdocs.com/buy).
### 有免费试用版吗？
是的，您可以探索免费试用版 [这里](https://releases。groupdocs.com/).