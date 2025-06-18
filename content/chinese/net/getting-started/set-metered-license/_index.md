---
"description": "使用 GroupDocs.Viewer 增强您的 .NET 应用程序，实现无缝文档查看。轻松将文档渲染功能集成到您的项目中。"
"linktitle": "设置计量许可证"
"second_title": "GroupDocs.Viewer .NET API"
"title": "设置计量许可证"
"url": "/zh/net/getting-started/set-metered-license/"
"weight": 12
---

# 设置计量许可证

## 介绍
在 .NET 开发领域，将强大的文档查看功能集成到应用程序中对于提升用户体验和功能至关重要。GroupDocs.Viewer for .NET 提供了一个强大的解决方案，可将文档查看功能无缝集成到您的 .NET 项目中。无论您处理的是 PDF、Microsoft Office 文档还是各种图像格式，GroupDocs.Viewer 都能简化在应用程序中渲染和显示这些文档的过程。

![使用 GroupDocs.Viewer for .NET 设置计量许可证](/viewer/getting-started/set-metered-license.png)

## 先决条件
在深入研究 GroupDocs.Viewer for .NET 的实现之前，请确保您已满足以下先决条件：
### 1. 安装 GroupDocs.Viewer for .NET
首先，您需要下载并安装 GroupDocs.Viewer for .NET。您可以找到下载链接 [这里](https://releases.groupdocs.com/viewer/net/)按照提供的安装说明在您的开发环境中设置库。
### 2. 获取计量许可证
要使用 GroupDocs.Viewer for .NET，您需要获取计量许可证。此许可证允许您根据预定义的配额控制和监控 API 的使用情况。请按照以下步骤设置您的计量许可证：

## 导入命名空间
首先，确保导入必要的命名空间以访问 GroupDocs.Viewer for .NET 提供的功能：
```csharp
using System;
```

现在，让我们将提供的示例代码分解为多个步骤：
## 步骤 1：声明公钥和私钥
声明变量来存储您的公钥和私钥：
```csharp
string publicKey = "YOUR_PUBLIC_KEY";
string privateKey = "YOUR_PRIVATE_KEY";
```
确保更换 `"YOUR_PUBLIC_KEY"` 和 `"YOUR_PRIVATE_KEY"` 使用你的真实钥匙。
## 步骤 2：设置计量许可证
检查是否提供了公钥。如果没有，则提示用户设置密钥：
```csharp
if (string.IsNullOrEmpty(publicKey))
{
    Console.WriteLine("\n[SetMeteredLicense] Please make sure to set Metered keys. Learn more at https://purchase.groupdocs.com/faqs/licensing/metered。");
    return;
}
```
## 步骤3：初始化计量对象并设置许可证
初始化 Metered 对象并使用您的公钥和私钥设置计量许可证：
```csharp
Metered metered = new Metered();
metered.SetMeteredKey(publicKey, privateKey);
```
## 步骤4：确认消息
显示许可证设置成功的确认信息：
```csharp
Console.WriteLine("License set successfully.");
```

## 结论
总而言之，GroupDocs.Viewer for .NET 提供了一个全面的解决方案，可将文档查看功能集成到您的 .NET 应用程序中。按照概述的步骤，您可以轻松设置计量许可证，并开始在您的项目中利用 GroupDocs.Viewer 的功能。
## 常见问题解答
### 问：在哪里可以找到 GroupDocs.Viewer for .NET 的文档？
您可以找到文档 [这里](https://tutorials。groupdocs.com/viewer/net/).
### 问：GroupDocs.Viewer for .NET 有免费试用版吗？
是的，您可以免费试用 [这里](https://releases。groupdocs.com/).
### 问：如何获得用于测试目的的临时许可证？
可以获得临时许可证 [这里](https://purchase。groupdocs.com/temporary-license/).
### 问：我可以在哪里寻求支持或询问与 GroupDocs.Viewer for .NET 相关的问题？
您可以在 GroupDocs.Viewer 论坛上寻求支持并提出问题 [这里](https://forum。groupdocs.com/c/viewer/9).
### 问：我可以在哪里购买 GroupDocs.Viewer for .NET 的许可证？
您可以购买许可证 [这里](https://purchase。groupdocs.com/buy).