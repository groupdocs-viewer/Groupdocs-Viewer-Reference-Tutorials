---
"description": "使用 GroupDocs.Viewer 增强您的 .NET 应用程序，实现无缝文档查看。按照我们的分步指南，轻松集成强大的文档查看功能。"
"linktitle": "从流设置许可证"
"second_title": "GroupDocs.Viewer .NET API"
"title": "从流设置许可证"
"url": "/zh/net/getting-started/set-license-from-stream/"
"weight": 11
---

# 从流设置许可证

## 介绍
您是否希望为您的 .NET 应用程序赋予高级文档查看功能？GroupDocs.Viewer for .NET 提供了一个全面的解决方案，可将文档查看功能无缝集成到您的项目中。在本教程中，我们将深入探讨如何利用 GroupDocs.Viewer for .NET 为您的应用程序提供强大的文档查看功能。 

![使用 GroupDocs.Viewer for .NET 从流中设置许可证](/viewer/getting-started/set-license-from-stream.png)

## 先决条件
在深入研究集成过程之前，请确保您已满足以下先决条件：
1. .NET 开发基础知识：熟悉 C# 和 .NET 框架对于学习本教程至关重要。
   
2. GroupDocs.Viewer for .NET 软件包：请确保您已下载并安装了 GroupDocs.Viewer for .NET 软件包。您可以从 [下载链接](https://releases。groupdocs.com/viewer/net/).
3. 访问 GroupDocs 文档：保留 [文档](https://tutorials.groupdocs.com/viewer/net/) 方便集成过程中的教程。

## 导入命名空间
首先，将必要的命名空间导入到您的 .NET 应用程序中。请按照以下步骤操作：
### 步骤 1：打开您的 .NET 项目。
确保您已在您首选的开发环境中打开了 .NET 项目。
### 第 2 步：添加 GroupDocs.Viewer 命名空间。
在您的代码文件中，添加以下命名空间以访问 GroupDocs.Viewer 功能：
```csharp
using System;
using System.IO;
```
## 从流设置许可证
下一步是从流中设置许可证。请遵循以下详细步骤：
### 步骤 1：定义输出目录。
通过定义输出目录来设置存储文档的目录：
```csharp
string outputDirectory = "Your Document Directory";
```
### 第 2 步：检查许可证文件是否存在。
检查许可证文件是否存在于您的项目目录中：
```csharp
if (File.Exists(Utils.LicensePath))
```
### 步骤3：设置许可证。
如果许可证文件存在，则使用提供的流设置许可证：
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### 步骤4：处理许可证缺失。
如果找不到许可证文件，请提供获取许可证的说明：
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://purchase.groupdocs.com/faqs/licensing。" +
                      "\nLearn how to request a temporary license at https://purchase.groupdocs.com/temporary-license。");
}
```

## 结论
恭喜！您已成功学习如何将 GroupDocs.Viewer for .NET 集成到您的应用程序中。借助这款强大的工具，您现在可以轻松地在 .NET 项目中查看各种文档格式，从而提升用户体验和工作效率。
## 常见问题解答
### 我需要许可证才能使用 GroupDocs.Viewer for .NET 吗？
是的，您需要许可证才能使用 GroupDocs.Viewer for .NET。您可以从 GroupDocs 网站获取临时或永久许可证。
### 我可以将 GroupDocs.Viewer 集成到我的 ASP.NET 应用程序中吗？
当然！GroupDocs.Viewer for .NET 无缝集成到桌面和 Web 应用程序（包括 ASP.NET）。
### GroupDocs.Viewer 支持哪些文档格式？
GroupDocs.Viewer 支持多种文档格式，包括 PDF、Microsoft Office（Word、Excel、PowerPoint）、图像等。
### GroupDocs.Viewer 是否与 .NET Core 兼容？
是的，GroupDocs.Viewer for .NET 与 .NET Framework 和 .NET Core 兼容。
### 我可以根据我的应用程序的主题自定义查看器界面吗？
是的，GroupDocs.Viewer 提供了广泛的自定义选项，允许您定制查看器界面以无缝匹配您的应用程序主题。