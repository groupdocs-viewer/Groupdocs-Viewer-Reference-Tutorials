---
title: 从 Stream 设置许可证
linktitle: 从 Stream 设置许可证
second_title: GroupDocs.Viewer .NET API
description: 使用 GroupDocs.Viewer 增强您的 .NET 应用程序，以实现无缝文档查看。按照我们的分步指南，轻松集成强大的文档查看功能。
type: docs
weight: 11
url: /zh/net/getting-started/set-license-from-stream/
---
## 介绍
您是否希望为您的 .NET 应用程序提供高级文档查看功能？ GroupDocs.Viewer for .NET 提供了一个全面的解决方案，可将文档查看功能无缝集成到您的项目中。在本教程中，我们将深入研究利用 GroupDocs.Viewer for .NET 通过强大的文档查看功能丰富您的应用程序的过程。 
## 先决条件
在我们深入了解集成过程之前，请确保您满足以下先决条件：
1. .NET 开发的基本知识：熟悉 C# 和 .NET 框架对于学习本教程至关重要。
   
2.  GroupDocs.Viewer for .NET 软件包：确保您已下载并安装 GroupDocs.Viewer for .NET 软件包。您可以从[下载链接](https://releases.groupdocs.com/viewer/net/).
3. 访问 GroupDocs 文档：保留[文档](https://reference.groupdocs.com/viewer/net/)方便集成过程中参考。

## 导入命名空间
首先，将必要的命名空间导入到您的 .NET 应用程序中。按着这些次序：
### 第 1 步：打开您的 .NET 项目。
确保您已在首选开发环境中打开 .NET 项目。
### 步骤 2：添加 GroupDocs.Viewer 命名空间。
在您的代码文件中，添加以下命名空间以访问 GroupDocs.Viewer 功能：
```csharp
using System;
using System.IO;
```
## 从 Stream 设置许可证
下一步涉及从流设置许可证。请按照以下详细步骤操作：
### 第 1 步：定义输出目录。
通过定义输出目录来设置存储文档的目录：
```csharp
string outputDirectory = "Your Document Directory";
```
### 步骤 2：检查许可证文件是否存在。
检查您的项目目录中是否存在许可证文件：
```csharp
if (File.Exists(Utils.LicensePath))
```
### 步骤 3：设置许可证。
如果许可证文件存在，请使用提供的流设置许可证：
```csharp
using (FileStream stream = File.OpenRead(Utils.LicensePath))
{
    License license = new License();
    license.SetLicense(stream);
}
```
### 第 4 步：处理许可证缺失问题。
如果未找到许可证文件，请提供获取许可证的说明：
```csharp
else
{
    Console.WriteLine("\nWe do not ship any license with this example. " +
                      "\nVisit the GroupDocs site to obtain either a temporary or permanent license. " +
                      "\nLearn more about licensing at https://buy.groupdocs.com/faqs/licensing。 ” +
                      "\nLearn how to request a temporary license at https://buy.groupdocs.com/temporary-license。”）；
}
```

## 结论
恭喜！您已经成功学习了如何将 GroupDocs.Viewer for .NET 集成到您的应用程序中。借助这个强大的工具，您现在可以轻松查看 .NET 项目中的各种文档格式，从而增强用户体验和工作效率。
## 常见问题解答
### 我需要许可证才能使用 GroupDocs.Viewer for .NET 吗？
是的，您需要许可证才能使用 GroupDocs.Viewer for .NET。您可以从 GroupDocs 网站获取临时或永久许可证。
### 我可以将 GroupDocs.Viewer 集成到我的 ASP.NET 应用程序中吗？
绝对地！ GroupDocs.Viewer for .NET 无缝集成到桌面和 Web 应用程序（包括 ASP.NET）中。
### GroupDocs.Viewer 支持哪些文档格式？
GroupDocs.Viewer 支持多种文档格式，包括 PDF、Microsoft Office（Word、Excel、PowerPoint）、图像等。
### GroupDocs.Viewer 与 .NET Core 兼容吗？
是的，GroupDocs.Viewer for .NET 与 .NET Framework 和 .NET Core 兼容。
### 我可以根据应用程序的主题自定义查看器界面吗？
是的，GroupDocs.Viewer 提供了广泛的自定义选项，允许您定制查看器界面以无缝匹配您的应用程序主题。