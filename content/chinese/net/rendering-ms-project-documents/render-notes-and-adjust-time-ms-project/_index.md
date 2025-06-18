---
"description": "使用 GroupDocs.Viewer for .NET 轻松渲染 MS Project 文档。轻松渲染注释、调整时间单位并探索各种输出格式。"
"linktitle": "渲染注释并调整时间单位（MS Project）"
"second_title": "GroupDocs.Viewer .NET API"
"title": "渲染注释并调整时间单位（MS Project）"
"url": "/zh/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/"
"weight": 11
---

# 渲染注释并调整时间单位（MS Project）

## 介绍
GroupDocs.Viewer for .NET 是一款功能强大的文档渲染 API，允许开发人员在其 .NET 应用程序中查看和操作各种文档格式。在本教程中，我们将重点介绍如何渲染注释并调整 MS Project 文档的时间单位。
## 先决条件
在开始之前，请确保您满足以下先决条件：
1. GroupDocs.Viewer for .NET：确保您已下载并安装了 GroupDocs.Viewer for .NET 库。您可以从 [这里](https://releases。groupdocs.com/viewer/net/).
2. 开发环境：设置具有 .NET 支持的首选开发环境。
3. MS Project 文档：准备好一个 MS Project 示例文档以供测试。
## 导入命名空间
首先，让我们导入必要的命名空间以开始渲染 MS Project 文档：
## 步骤 1：导入命名空间
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
现在我们已经导入了所需的命名空间，让我们将每个示例分解为多个步骤，以便全面理解。
## 将 MS Project 文档渲染为 HTML
要将 MS Project 文档呈现为包含注释的 HTML 格式，请按照以下步骤操作：
### 第 2 步：设置输出目录和文件格式
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### 步骤3：初始化查看器对象并设置选项
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### 步骤 4：将文档渲染为 HTML
```csharp
viewer.View(options);
```
## 将 MS Project 文档渲染为图像格式
您还可以将 MS Project 文档渲染为 JPG 和 PNG 等图像格式。操作方法如下：
### 步骤5：设置JPG的输出目录和文件格式
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### 步骤6：初始化查看器对象并设置JPG选项
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### 步骤 7：将文档渲染为 JPG
```csharp
viewer.View(options);
```
重复类似步骤以渲染为 PNG 和其他图像格式。
## 将 MS Project 文档渲染为 PDF
要将 MS Project 文档呈现为 PDF 格式，请按以下步骤操作：
### 步骤8：设置PDF的输出目录和文件格式
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### 步骤 9：初始化查看器对象并设置 PDF 选项
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### 步骤 10：将文档渲染为 PDF
```csharp
viewer.View(options);
```

## 结论
恭喜！您已成功学习如何使用 GroupDocs.Viewer for .NET 渲染 MS Project 文档并调整时间单位。请将这些知识运用到您的项目中，以增强文档查看功能。
## 常见问题解答
### 我可以将 MS Project 文档渲染为 HTML、图像和 PDF 以外的其他格式吗？
是的，GroupDocs.Viewer for .NET 支持渲染为各种格式，例如 DOCX、XLSX、PPTX 等。
### GroupDocs.Viewer for .NET 有试用版吗？
是的，你可以从 [这里](https://releases。groupdocs.com/).
### 如何获得 GroupDocs.Viewer for .NET 的临时许可？
访问 [此链接](https://purchase.groupdocs.com/temporary-license/) 获得临时执照。
### 在哪里可以找到 GroupDocs.Viewer for .NET 的文档？
请参阅文档 [这里](https://tutorials。groupdocs.com/viewer/net/).
### 我可以在哪里寻求支持或询问与 GroupDocs.Viewer for .NET 相关的问题？
您可以访问支持论坛 [这里](https://forum。groupdocs.com/c/viewer/9).