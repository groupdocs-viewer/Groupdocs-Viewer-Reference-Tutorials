---
title: 获取工作表名称
linktitle: 获取工作表名称
second_title: GroupDocs.Viewer .NET API
description: 探索 GroupDocs.Viewer for .NET 的魔力 – 将文档查看无缝集成到您的应用程序中。立即免费试用！
weight: 11
url: /zh/net/spreadsheet-rendering-options/get-worksheets-names/
---

# 获取工作表名称

## 介绍
欢迎来到 GroupDocs.Viewer for .NET 的迷人世界！如果您是一位开发人员或爱好者，热衷于探索 .NET 应用程序中强大的文档查看功能，那么您将会大饱口福。在本综合指南中，我们将深入研究使用 GroupDocs.Viewer 检索工作表名称的复杂性。那么，系好安全带，让我们踏上这段激动人心的旅程吧！
## 先决条件
在我们深入研究编码魔法之前，让我们确保您已完成所有设置：
1. 安装适用于 .NET 的 GroupDocs.Viewer：转到[下载链接](https://releases.groupdocs.com/viewer/net/)获取最新版本的 GroupDocs.Viewer for .NET。按照安装说明将其无缝集成到您的开发环境中。
2. 准备好您的文档：确保您在指定的文档目录中有一个目标文档，假设有一个名为“file.xlsx”的 Excel 文件。
## 导入命名空间
现在您已经具备了先决条件，让我们通过导入必要的命名空间来开始吧。这可确保您的应用程序能够识别并利用 GroupDocs.Viewer for .NET 提供的功能。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using GroupDocs.Viewer.Results;
```
## 1. 设置文档目录
```csharp
string outputDirectory = "Your Document Directory";
```
将“您的文档目录”替换为目标文档所在目录的路径。
## 2. 初始化查看器
```csharp
using (Viewer viewer = new Viewer(Path.Combine(outputDirectory, "file.xlsx")))
```
在此步骤中，我们创建 Viewer 类的实例，提供 Excel 文件的路径。
## 3. 配置查看信息选项
```csharp
ViewInfoOptions viewInfoOptions = ViewInfoOptions.ForHtmlView();
viewInfoOptions.SpreadsheetOptions = SpreadsheetOptions.ForOnePagePerSheet();
```
在这里，我们配置 ViewInfoOptions 以生成 HTML 视图并设置用于电子表格呈现的其他选项。
## 4. 检索视图信息
```csharp
ViewInfo viewInfo = viewer.GetViewInfo(viewInfoOptions);
```
利用 Viewer 实例根据配置的选项检索视图信息。
## 5. 显示工作表名称
```csharp
Console.WriteLine("Worksheets:");
foreach (Page page in viewInfo.Pages)
{
    Console.WriteLine($" - Worksheet {page.Number} name '{page.Name}'");
}
```
循环遍历检索到的页面并将每个工作表的名称打印到控制台。
## 结论
恭喜！您已成功完成使用 GroupDocs.Viewer for .NET 获取工作表名称的过程。这为增强应用程序中的文档查看功能提供了无数的可能性。
## 常见问题解答
### 我可以将 GroupDocs.Viewer for .NET 与其他文档格式一起使用吗？
绝对地！ GroupDocs.Viewer 支持多种文档格式，包括 PDF、Microsoft Office 等。
### 有免费试用吗？
是的，您可以使用我们的 .NET 浏览器 GroupDocs.Viewer[免费试用](https://releases.groupdocs.com/).
### 我在哪里可以找到额外的支持？
前往[GroupDocs.Viewer 论坛](https://forum.groupdocs.com/c/viewer/9)以获得社区支持和讨论。
### 我可以获得临时许可证吗？
当然！访问[这个链接](https://purchase.groupdocs.com/temporary-license/)获得您的临时许可证。
### 有详细的文档资源吗？
绝对地！查看[官方文档](https://tutorials.groupdocs.com/viewer/net/)获取深入的信息和指南。