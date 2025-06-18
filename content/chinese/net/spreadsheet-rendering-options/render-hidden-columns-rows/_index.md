---
"description": "使用 GroupDocs.Viewer for .NET 轻松解锁电子表格中的隐藏数据。按照我们的分步指南，显示隐藏的列和行。"
"linktitle": "渲染隐藏的列和行"
"second_title": "GroupDocs.Viewer .NET API"
"title": "渲染隐藏的列和行"
"url": "/zh/net/spreadsheet-rendering-options/render-hidden-columns-rows/"
"weight": 13
---

# 渲染隐藏的列和行

## 介绍
在文档可视化领域，GroupDocs.Viewer for .NET 是一款功能强大的工具，能够无缝呈现各种文档格式。其中一项引人入胜的功能是能够显示电子表格中隐藏的列和行。在本教程中，我们将深入探讨解锁此功能的步骤，并释放数据的潜力。
## 先决条件
在踏上这一旅程之前，请确保您已满足以下先决条件：
- GroupDocs.Viewer for .NET：请确保您已安装最新版本。如果没有，您可以从 [官方网站](https://releases。groupdocs.com/viewer/net/).
- 文档文件：准备电子表格格式的示例文档（例如，SAMPLE.XLSX）来试验隐藏的列和行。
- 开发环境：设置工作环境，最好使用 Visual Studio 或任何其他适合 .NET 开发的 IDE。
## 导入命名空间
在您的 .NET 项目中，导入必要的命名空间以有效利用 GroupDocs.Viewer 功能：
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```
## 步骤 1：设置输出目录
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
定义渲染后的 HTML 页面的输出目录。请相应地调整文件路径格式。
## 步骤 2：初始化查看器并配置选项
```csharp
using (Viewer viewer = new Viewer("SAMPLE.XLSX"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.SpreadsheetOptions.RenderHiddenColumns = true;
    options.SpreadsheetOptions.RenderHiddenRows = true;
```
通过提供电子表格文档的路径来创建查看器实例。配置 HTML 视图选项以嵌入资源并启用隐藏列和行的渲染。
## 步骤3：执行渲染过程
```csharp
    viewer.View(options);
}
```
调用查看器对象上的 View 方法，并传递已配置的选项。这将启动渲染过程。
## 步骤 4：检查输出
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
验证源文档是否成功呈现并将输出定位在指定的目录中。
## 结论
使用 GroupDocs.Viewer for .NET，轻松解锁电子表格中隐藏的列和行。本教程将指导您如何揭示隐藏数据，从而更全面地查看文档。
## 常见问题
### 除了电子表格之外，我可以在其它文档格式中呈现隐藏的列和行吗？
是的，除了电子表格之外，GroupDocs.Viewer 还支持各种文档格式，包括 Word、PDF 和 PowerPoint。
### 可渲染的隐藏列和隐藏行的数量是否有限制？
GroupDocs.Viewer 可以高效地处理各种隐藏列和行的渲染。然而，在极端情况下，如果隐藏数据量过大，可能会影响性能。
### 我可以自定义渲染数据的输出格式吗？
当然！GroupDocs.Viewer 提供了灵活的选项来自定义输出，让您可以根据特定需求定制渲染的数据。
### 使用 GroupDocs.Viewer 是否有任何许可注意事项？
是的，请确保您拥有适合您用途的许可证。探索许可选项，请访问 [GroupDocs 购买](https://purchase.groupdocs.com/buy) 或获得 [临时执照](https://purchase.groupdocs.com/temporary-license/) 用于测试。
### 我可以在哪里寻求帮助或联系 GroupDocs 社区以获得支持？
访问 [GroupDocs.Viewer 论坛](https://forum.groupdocs.com/c/viewer/9) 以获得支持、讨论和社区互动。