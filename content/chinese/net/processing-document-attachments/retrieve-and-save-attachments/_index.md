---
title: 检索并保存文档附件
linktitle: 检索并保存文档附件
second_title: GroupDocs.Viewer .NET API
description: 使用 GroupDocs.Viewer 有效管理 .NET 应用程序中的文档附件。轻松检索和保存附件。
type: docs
weight: 12
url: /zh/net/processing-document-attachments/retrieve-and-save-attachments/
---
## 介绍
在数字时代，高效的文档处理对于企业和个人都至关重要。无论是管理电子邮件、查看合同还是访问报告，拥有可靠的文档可视化工具都是至关重要的。 GroupDocs.Viewer for .NET 作为一个强大的解决方案出现，使用户能够直接在其 .NET 应用程序中轻松查看各种文档格式并与之交互。
## 先决条件
在深入研究使用 GroupDocs.Viewer for .NET 进行文档附件检索和保存之前，请确保您具备以下先决条件：
1. 运行环境：使用.NET框架搭建的工作环境。
2. 安装：下载并安装适用于 .NET 库的 GroupDocs.Viewer。您可以从以下位置访问图书馆[下载链接](https://releases.groupdocs.com/viewer/net/).
3. 基本了解：熟悉C#编程语言。
4. 文档来源：访问带有附件的示例文档以进行演示。

## 导入命名空间
要开始使用 GroupDocs.Viewer for .NET 进行文档附件检索和保存，请导入必要的命名空间：
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Results;
```

## 第 1 步：定义输出目录
```csharp
string outputDirectory = "Your Document Directory";
```
定义要保存从文档中检索的附件的目录。
## 第 2 步：实例化查看器对象
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
使用包含附件的文档的路径实例化 Viewer 对象。
## 第 3 步：检索附件
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
检索文档中存在的附件列表。
## 第 4 步：保存附件
```csharp
foreach(Attachment attachment in attachments)
{
    string filePath = Path.Combine(outputDirectory, attachment.FileName);  
    viewer.SaveAttachment(attachment, File.OpenWrite(filePath)); 
}
```
迭代每个附件，定义文件路径，并将附件保存到指定目录。
## 第5步：显示成功消息
```csharp
Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
```
显示一条成功消息，指示已成功保存附件以及目录路径。

## 结论
将 GroupDocs.Viewer for .NET 合并到文档处理工作流程中可以简化附件管理过程，提高效率和便利性。通过遵循上述分步指南，用户可以在其 .NET 应用程序中无缝检索和保存文档附件。
## 常见问题解答
### GroupDocs.Viewer for .NET 可以处理各种文档格式吗？
是的，GroupDocs.Viewer 支持多种文档格式，包括 PDF、Microsoft Office 文档、图像等。
### GroupDocs.Viewer for .NET 是否有免费试用版？
是的，您可以通过以下方式访问免费试用版：[这里](https://releases.groupdocs.com/).
### 如何获取 GroupDocs.Viewer for .NET 的临时许可证？
临时许可证可以从[这个链接](https://purchase.groupdocs.com/temporary-license/).
### 在哪里可以找到 GroupDocs.Viewer for .NET 的文档？
提供全面的文档[这里](https://reference.groupdocs.com/viewer/net/).
### GroupDocs.Viewer for .NET 提供哪些支持选项？
您可以从社区论坛寻求帮助[这里](https://forum.groupdocs.com/c/viewer/9).