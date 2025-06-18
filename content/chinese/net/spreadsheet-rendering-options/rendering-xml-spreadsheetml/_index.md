---
"description": "探索使用 GroupDocs.Viewer for .NET 无缝渲染各种格式的 XML SpreadSheetML 文件。轻松集成到您的应用程序中。"
"linktitle": "渲染 XML SpreadSheetML"
"second_title": "GroupDocs.Viewer .NET API"
"title": "渲染 XML SpreadSheetML"
"url": "/zh/net/spreadsheet-rendering-options/rendering-xml-spreadsheetml/"
"weight": 16
---

# 渲染 XML SpreadSheetML

## 介绍
欢迎来到 GroupDocs.Viewer for .NET 的世界！在本教程中，我们将指导您使用功能强大的 .NET 库 GroupDocs.Viewer 轻松渲染 XML SpreadSheetML 文件。无论您是经验丰富的开发人员还是刚刚入门，本分步指南都能帮助您轻松地将 XML SpreadSheetML 渲染功能集成到您的应用程序中。
## 先决条件
在深入学习本教程之前，请确保您已满足以下先决条件：
- 支持.NET 的开发环境。
- 已安装 GroupDocs.Viewer for .NET 库。您可以下载 [这里](https://releases。groupdocs.com/viewer/net/).
- 对 C# 编程有基本的了解。
## 导入命名空间
首先将必要的命名空间导入到您的 C# 项目中。这可确保您能够访问 GroupDocs.Viewer 提供的功能。
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
## 步骤 1：设置文档目录
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
明确指定文件类型为 Excel 2003 XML SpreadSheetML 以便准确呈现它。
```csharp
LoadOptions loadOptions = new LoadOptions(FileType.Excel2003XML);
```
## 步骤 4：渲染为多页 HTML
利用 HTML 视图选项将 XML SpreadSheetML 文件呈现为多页 HTML 文档。
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFileFullPath);
    viewer.View(options);
}
```
## 步骤5：渲染为JPG
使用指定的选项将 XML SpreadSheetML 文件渲染为 JPG 图像。
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.jpg");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 步骤6：渲染为PNG
类似地，使用指定的选项将文件渲染为 PNG 图像。
```csharp
pageFileFullPath = Path.Combine(outputDirectory, "Excel_2003_Xml_result.png");
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_XML_SPREADSHEETML, loadOptions))
{
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.View(options);
}
```
## 步骤 7：渲染为 PDF
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
恭喜！您已成功学习如何使用 GroupDocs.Viewer for .NET 渲染 XML SpreadSheetML 文件。探索这个多功能库提供的更多功能和选项，提升您的文档查看能力。
## 常见问题解答
### GroupDocs.Viewer 是否与其他文件格式兼容？
是的，GroupDocs.Viewer 支持多种文档格式，包括 PDF、Word、Excel 等。
### 我可以自定义渲染文档的外观吗？
当然！GroupDocs.Viewer 提供各种自定义选项，让您可以根据特定需求定制输出。
### 我可以在哪里找到额外的支持和资源？
访问 [GroupDocs.Viewer 论坛](https://forum.groupdocs.com/c/viewer/9) 寻求社区支持并探索 [文档](https://tutorials.groupdocs.com/viewer/net/) 了解详细信息。
### 有免费试用吗？
是的，您可以免费试用 [这里](https://releases。groupdocs.com/).
### 如何获得临时执照？
您可以获得临时驾照 [这里](https://purchase。groupdocs.com/temporary-license/).