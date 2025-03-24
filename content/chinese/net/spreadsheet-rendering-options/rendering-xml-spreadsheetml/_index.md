---
title: 呈现 XML SpreadSheetML
linktitle: 呈现 XML SpreadSheetML
second_title: GroupDocs.Viewer .NET API
description: 使用 GroupDocs.Viewer for .NET 探索各种格式的 XML SpreadSheetML 文件的无缝呈现。轻松集成到您的应用程序中。
weight: 16
url: /zh/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/
---

# 呈现 XML SpreadSheetML

## 介绍
欢迎来到 GroupDocs.Viewer for .NET 的世界！在本教程中，我们将指导您使用强大的 .NET 库 GroupDocs.Viewer 轻松渲染 XML SpreadSheetML 文件。无论您是经验丰富的开发人员还是新手，本分步指南都将帮助您轻松地将 XML SpreadSheetML 渲染集成到您的应用程序中。
## 先决条件
在深入学习本教程之前，请确保您已设置以下先决条件：
- 具有 .NET 支持的开发环境。
- 安装了 .NET 库的 GroupDocs.Viewer。你可以下载它[这里](https://releases.groupdocs.com/viewer/net/).
- 对 C# 编程有基本了解。
## 导入命名空间
首先将必要的命名空间导入到您的 C# 项目中。这可确保您能够访问 GroupDocs.Viewer 提供的功能。
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 第 1 步：设置您的文档目录
定义保存输出的文档目录的路径。
```csharp
string outputDirectory = "Your Document Directory";
```
## 步骤 2：指定输出文件路径
设置 HTML、JPG、PNG 和 PDF 输出文件的完整路径。
```csharp
string pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.html");
```
## 步骤 3：指定加载选项
将文件类型显式指定为 Excel 2003 XML SpreadSheetML 以准确呈现它。
```csharp
LoadOptions loadOptions = new LoadOptions(FileType.Excel2003XML);
```
## 第 4 步：渲染为多页 HTML
利用 HTML 视图选项将 XML SpreadSheetML 文件呈现为多页 HTML 文档。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## 第5步：渲染为JPG
使用指定的选项将 XML SpreadSheetML 文件渲染为 JPG 图像。
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 第 6 步：渲染为 PNG
同样，使用指定的选项将文件渲染为 PNG 图像。
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 第 7 步：渲染为 PDF
最后，使用指定的选项将 XML SpreadSheetML 文件呈现为 PDF 文档。
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.pdf");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 结论
恭喜！您已成功学习如何使用 GroupDocs.Viewer for .NET 呈现 XML SpreadSheetML 文件。通过探索这个多功能库提供的更多功能和选项来增强您的文档查看能力。
## 常见问题解答
### GroupDocs.Viewer 是否与其他文件格式兼容？
是的，GroupDocs.Viewer 支持多种文档格式，包括 PDF、Word、Excel 等。
### 我可以自定义渲染文档的外观吗？
绝对地！ GroupDocs.Viewer 提供各种自定义选项，允许您根据您的特定需求定制输出。
### 我在哪里可以找到额外的支持和资源？
参观[GroupDocs.Viewer 论坛](https://forum.groupdocs.com/c/viewer/9)寻求社区支持并探索[文档](https://tutorials.groupdocs.com/viewer/net/)获取详细信息。
### 有免费试用吗？
是的，您可以免费试用[这里](https://releases.groupdocs.com/).
### 如何获得临时许可证？
您可以获得临时许可证[这里](https://purchase.groupdocs.com/temporary-license/).