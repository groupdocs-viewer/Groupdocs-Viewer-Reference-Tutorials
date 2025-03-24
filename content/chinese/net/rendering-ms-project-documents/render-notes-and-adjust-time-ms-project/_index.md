---
title: 渲染注释并调整时间单位 (MS Project)
linktitle: 渲染注释并调整时间单位 (MS Project)
second_title: GroupDocs.Viewer .NET API
description: 使用 GroupDocs.Viewer for .NET 掌握 MS Project 文档的渲染。轻松渲染注释、调整时间单位并探索各种输出格式。
weight: 11
url: /zh/net/rendering-ms-project-documents/render-notes-and-adjust-time-ms-project/
---
## 介绍
GroupDocs.Viewer for .NET 是一个功能强大的文档呈现 API，允许开发人员在其 .NET 应用程序中查看和操作各种文档格式。在本教程中，我们将重点关注专门针对 MS Project 文档渲染注释和调整时间单位。
## 先决条件
在我们开始之前，请确保您具备以下先决条件：
1. GroupDocs.Viewer for .NET：确保您已下载并安装 GroupDocs.Viewer for .NET 库。您可以从以下位置下载：[这里](https://releases.groupdocs.com/viewer/net/).
2. 开发环境：设置您首选的具有 .NET 支持的开发环境。
3. MS 项目文档：准备好示例 MS 项目文档以供测试。
## 导入命名空间
首先，让我们导入必要的命名空间以开始渲染 MS Project 文档：
## 第 1 步：导入命名空间
```csharp
using GroupDocs.Viewer.Options;
using System;
using System.IO;
```
现在我们已经导入了所需的命名空间，让我们将每个示例分解为多个步骤以便全面理解。
## 将 MS Project 文档渲染为 HTML
要将 MS Project 文档呈现为包含注释的 HTML 格式，请按照下列步骤操作：
### 第2步：设置输出目录和文件格式
```csharp
string outputDirectory = "Your Document Directory";
string pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.html");
```
### 第 3 步：初始化查看器对象并设置选项
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.RenderNotes = true;
```
### 第 4 步：将文档渲染为 HTML
```csharp
viewer.View(options);
```
## 将 MS Project 文档渲染为图像格式
您还可以将 MS Project 文档渲染为 JPG 和 PNG 等图像格式。就是这样：
### 第5步：设置JPG的输出目录和文件格式
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_{0}_result.jpg");
```
### 第 6 步：初始化查看器对象并设置 JPG 选项
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### 第 7 步：将文档渲染为 JPG
```csharp
viewer.View(options);
```
重复类似的步骤以渲染为 PNG 和其他图像格式。
## 将 MS 项目文档渲染为 PDF
要将 MS Project 文档呈现为 PDF 格式，请按照下列步骤操作：
### 步骤8：设置PDF的输出目录和文件格式
```csharp
pageFilePathFormat = Path.Combine(outputDirectory, "mpp_result.pdf");
```
### 第 9 步：初始化查看器对象并设置 PDF 选项
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MPP))
{
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    options.RenderNotes = true;
```
### 第 10 步：将文档渲染为 PDF
```csharp
viewer.View(options);
```

## 结论
恭喜！您已成功学习如何使用 GroupDocs.Viewer for .NET 呈现 MS Project 文档并调整时间单位。将这些知识融入您的项目中以增强文档查看功能。
## 常见问题解答
### 我可以将 MS Project 文档呈现为除 HTML、图像和 PDF 之外的其他格式吗？
是的，GroupDocs.Viewer for .NET 支持呈现为各种格式，例如 DOCX、XLSX、PPTX 等。
### GroupDocs.Viewer for .NET 是否有试用版？
是的，您可以从以下位置获得免费试用[这里](https://releases.groupdocs.com/).
### 如何获得 GroupDocs.Viewer for .NET 的临时许可？
访问[这个链接](https://purchase.groupdocs.com/temporary-license/)获得临时许可证。
### 在哪里可以找到 GroupDocs.Viewer for .NET 的文档？
参考文档[这里](https://tutorials.groupdocs.com/viewer/net/).
### 我可以在哪里寻求与 GroupDocs.Viewer for .NET 相关的支持或提出问题？
您可以访问支持论坛[这里](https://forum.groupdocs.com/c/viewer/9).