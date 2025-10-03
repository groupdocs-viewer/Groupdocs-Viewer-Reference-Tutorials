---
"description": "使用 GroupDocs.Viewer 高效管理 .NET 应用程序中的文档附件。轻松检索和保存附件。"
"linktitle": "检索并保存文档附件"
"second_title": "GroupDocs.Viewer .NET API"
"title": "检索并保存文档附件"
"url": "/zh/net/processing-document-attachments/retrieve-and-save-attachments/"
"weight": 12
type: docs
---
# 检索并保存文档附件

## 介绍
在数字时代，高效的文档处理对企业和个人都至关重要。无论是管理电子邮件、查看合同还是访问报告，拥有一个可靠的文档可视化工具都至关重要。GroupDocs.Viewer for .NET 是一款强大的解决方案，使用户能够直接在 .NET 应用程序中轻松查看各种文档格式并进行交互。

![使用 GroupDocs.Viewer .NET 检索和保存文档附件](/viewer/processing-document-attachments/retrieve-and-save-document-attachments.png)

## 先决条件
在深入研究利用 GroupDocs.Viewer for .NET 检索和保存文档附件之前，请确保您满足以下先决条件：
1. 运行环境：采用.NET框架搭建的工作环境。
2. 安装：已下载并安装 GroupDocs.Viewer for .NET 库。您可以从 [下载链接](https://releases。groupdocs.com/viewer/net/).
3. 基本了解：熟悉 C# 编程语言。
4. 文档来源：访问带有附件的示例文档以供演示。

## 导入命名空间
要开始利用 GroupDocs.Viewer for .NET 检索和保存文档附件，请导入必要的命名空间：
```csharp
using System;
using System.Collections.Generic;
using System.IO;
using GroupDocs.Viewer.Results;
```

## 步骤 1：定义输出目录
```csharp
string outputDirectory = "Your Document Directory";
```
定义要保存从文档中检索到的附件的目录。
## 步骤2：实例化查看器对象
```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG_WITH_ATTACHMENTS))
```
使用包含附件的文档的路径实例化 Viewer 对象。
## 步骤 3：检索附件
```csharp
IList<Attachment> attachments = viewer.GetAttachments();
```
检索文档中存在的附件列表。
## 步骤 4：保存附件
```csharp
foreach(Attachment attachment in attachments)
{
    string filePath = Path.Combine(outputDirectory, attachment.FileName);  
    viewer.SaveAttachment(attachment, File.OpenWrite(filePath)); 
}
```
遍历每个附件，定义文件路径，并将附件保存到指定目录。
## 步骤5：显示成功消息
```csharp
Console.WriteLine($"\nAttachments saved successfully.\nCheck output in {outputDirectory}.");
```
显示成功消息，表明附件保存成功，并显示目录路径。

## 结论
将 GroupDocs.Viewer for .NET 集成到您的文档处理工作流程中，可以简化附件管理流程，提高效率和便捷性。按照上述分步指南操作，用户可以在其 .NET 应用程序中无缝检索和保存文档附件。
## 常见问题解答
### GroupDocs.Viewer for .NET 能处理各种文档格式吗？
是的，GroupDocs.Viewer 支持多种文档格式，包括 PDF、Microsoft Office 文档、图像等。
### GroupDocs.Viewer for .NET 有免费试用版吗？
是的，您可以从 [这里](https://releases。groupdocs.com/).
### 如何获得 GroupDocs.Viewer for .NET 的临时许可证？
临时许可证可从 [此链接](https://purchase。groupdocs.com/temporary-license/).
### 在哪里可以找到 GroupDocs.Viewer for .NET 的文档？
提供全面的文档 [这里](https://tutorials。groupdocs.com/viewer/net/).
### GroupDocs.Viewer for .NET 有哪些支持选项？
您可以从社区论坛寻求帮助 [这里](https://forum。groupdocs.com/c/viewer/9).