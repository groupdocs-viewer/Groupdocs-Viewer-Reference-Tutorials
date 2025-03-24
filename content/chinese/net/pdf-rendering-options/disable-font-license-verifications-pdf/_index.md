---
title: 禁用 PDF 中的字体许可证验证
linktitle: 禁用 PDF 中的字体许可证验证
second_title: GroupDocs.Viewer .NET API
description: 使用 GroupDocs.Viewer for .NET 解锁 .NET 中的无缝文档查看功能。以最小的依赖性轻松集成和自定义文档渲染。
weight: 12
url: /zh/net/pdf-rendering-options/disable-font-license-verifications-pdf/
---
## 介绍
在 .NET 开发领域，管理和操作文档通常是许多应用程序的一个重要方面。无论是查看 PDF、Word 文档还是其他文件类型，拥有强大的工具来高效处理这些任务都是至关重要的。这就是 GroupDocs.Viewer for .NET 发挥作用的地方。这个功能强大的库使开发人员能够将文档查看功能无缝集成到他们的 .NET 应用程序中。
## 先决条件
在深入使用 GroupDocs.Viewer for .NET 之前，您需要满足一些先决条件：
### 1.安装Visual Studio
首先，确保您的系统上安装了 Visual Studio。如果您还没有下载，可以从 Microsoft 网站下载。
### 2. 下载 .NET 版 GroupDocs.Viewer
前往[下载链接](https://releases.groupdocs.com/viewer/net/)获取最新版本的 GroupDocs.Viewer for .NET。按照提供的安装说明在您的开发环境中进行设置。
### 3. 获得临时许可证
要在开发和测试过程中充分发挥 GroupDocs.Viewer for .NET 的潜力，建议获取临时许可证。您可以从以下位置索取一份[这里](https://purchase.groupdocs.com/temporary-license/).

## 导入命名空间
完成先决条件后，您就可以开始在项目中使用 GroupDocs.Viewer for .NET。首先将必要的命名空间导入到您的代码库中。
```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

让我们将提供的示例分解为多个步骤，以便更清楚地理解：
## 第 1 步：定义输出目录
首先定义要存储渲染文档页面的目录。
```csharp
string outputDirectory = "Your Document Directory";
```
## 第2步：定义页面文件路径格式
设置文档各个页面的文件路径的格式。
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.png");
```
## 第 3 步：初始化查看器对象
创建 Viewer 类的实例，传递要查看的文档的路径。
```csharp
using (Viewer viewer = new Viewer(TestFiles.OXPS_EMBEDDED_FONT))
```
## 步骤 4：配置 HTML 视图选项
定义用于以 HTML 形式查看文档的选项，指定嵌入资源（例如图像）的格式。
```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
## 步骤 5：禁用字体许可证验证
启用禁用字体许可证验证的选项，以确保流畅的渲染。
```csharp
options.PdfOptions.DisableFontLicenseVerifications = true;
```
## 第6步：查看文档
调用 Viewer 对象的 View 方法，传递配置的选项。
```csharp
viewer.View(options);
```
## 第7步：显示输出目录
告知用户渲染文档页面的存储位置。
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 结论
GroupDocs.Viewer for .NET 为开发人员提供了一个全面的解决方案，可以轻松地将文档查看功能集成到他们的 .NET 应用程序中。通过遵循本教程中概述的步骤，您可以有效地利用这个强大的库来增强您的文档管理工作流程。
## 常见问题解答
### GroupDocs.Viewer for .NET 可以处理多种文档格式吗？
是的，GroupDocs.Viewer 支持多种文档格式，包括 PDF、Microsoft Word、Excel、PowerPoint 等。
### GroupDocs.Viewer for .NET 是否适合 Web 应用程序？
当然，GroupDocs.Viewer 可以无缝集成到使用 .NET 技术开发的桌面和 Web 应用程序中。
### GroupDocs.Viewer 是否需要任何额外的依赖项？
不会，GroupDocs.Viewer for .NET 具有最小的依赖性，并且可以轻松集成到您现有的项目中。
### 我可以自定义渲染文档的外观吗？
是的，GroupDocs.Viewer 提供了各种选项来自定义呈现文档的外观和行为，以满足您的特定要求。
### GroupDocs.Viewer for .NET 是否提供技术支持？
是的，您可以通过以下方式寻求专门支持团队的帮助和指导：[论坛](https://forum.groupdocs.com/c/viewer/9).