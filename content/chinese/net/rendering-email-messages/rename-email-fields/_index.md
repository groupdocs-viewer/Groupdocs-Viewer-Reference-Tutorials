---
title: 在渲染期间重命名电子邮件字段
linktitle: 在渲染期间重命名电子邮件字段
second_title: GroupDocs.Viewer .NET API
description: 使用 GroupDocs.Viewer for .NET 增强文档查看体验。无缝渲染和自定义电子邮件。
weight: 12
url: /zh/net/rendering-email-messages/rename-email-fields/
---

# 在渲染期间重命名电子邮件字段

## 介绍

在当今的数字时代，有效管理和查看文档对于企业和个人来说至关重要。无论是合同、报告还是电子邮件，能够无缝浏览这些文档都可以大大提高工作效率。这就是 GroupDocs.Viewer for .NET 发挥作用的地方。这个强大的库允许开发人员将文档查看功能直接集成到他们的 .NET 应用程序中，提供用于呈现各种文档格式的广泛功能。

## 先决条件

在深入了解有关使用 GroupDocs.Viewer for .NET 进行渲染期间重命名电子邮件字段的教程之前，请确保您满足以下先决条件：

1.  GroupDocs.Viewer for .NET 库：从以下位置下载并安装 GroupDocs.Viewer for .NET 库[这里](https://releases.groupdocs.com/viewer/net/).

2. 开发环境：确保您拥有适合 .NET 开发的开发环境，例如 Visual Studio。

3. C# 的基本了解：熟悉 C# 编程语言的基础知识，因为本教程将涉及 C# 代码片段。

4. 文档目录：准备一个目录，用于存放要渲染的文档。

## 导入命名空间

为了在 .NET 应用程序中使用 GroupDocs.Viewer 功能，您需要导入必要的命名空间。

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
```

现在，让我们将使用 GroupDocs.Viewer for .NET 在渲染期间重命名电子邮件字段的过程分解为多个步骤：

## 第 1 步：定义输出目录

首先，指定保存渲染的 HTML 页面的目录。

```csharp
string outputDirectory = "Your Document Directory";
```

## 第2步：定义页面文件路径格式

定义所呈现的 HTML 页面的文件路径的格式。每个页面都将保存为单独的 HTML 文件。

```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```

## 第 3 步：初始化查看器对象

创建 Viewer 类的实例，并将要查看的文档的路径作为参数传递。

```csharp
using (Viewer viewer = new Viewer(TestFiles.SAMPLE_MSG))
{
```

## 步骤 4：配置 HTML 视图选项

配置 HTML 视图的选项，包括指定输出文件格式和设置电子邮件字段映射。

```csharp
HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
options.EmailOptions.FieldTextMap[Field.From] = "Sender";
options.EmailOptions.FieldTextMap[Field.To] = "Receiver";
options.EmailOptions.FieldTextMap[Field.Sent] = "Date";
options.EmailOptions.FieldTextMap[Field.Subject] = "Topic";
```

## 第5步：渲染文档

调用 Viewer 对象的 View 方法，传递配置的 HTML 视图选项。

```csharp
viewer.View(options);
```

## 第6步：显示成功消息

通知用户文档已成功呈现。

```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```

## 结论

总之，GroupDocs.Viewer for .NET 提供了在 .NET 应用程序中呈现文档的无缝解决方案。通过遵循本教程中概述的步骤，您可以在渲染期间轻松重命名电子邮件字段，从而增强电子邮件文档的可读性和可用性。凭借其直观的 API 和全面的功能，GroupDocs.Viewer 使开发人员能够有效地简化文档查看流程。

## 常见问题解答

### 问：我可以使用 GroupDocs.Viewer for .NET 呈现电子邮件以外的文档吗？

答：是的，GroupDocs.Viewer 支持渲染各种文档格式，包括 PDF、Microsoft Office 文档、图像等。

### 问：GroupDocs.Viewer 与 .NET Core 兼容吗？

答：是的，GroupDocs.Viewer 支持 .NET Core 以及传统的 .NET Framework。

### 问：我可以自定义渲染文档的外观吗？

答：当然，GroupDocs.Viewer 提供了广泛的自定义选项来控制渲染文档的外观和行为。

### 问：GroupDocs.Viewer 是否支持文档流？

答：是的，GroupDocs.Viewer 允许将文档直接流式传输到客户端的浏览器，而无需将它们存储在服务器上。

### 问：GroupDocs.Viewer 适合企业级应用吗？

答：当然，GroupDocs.Viewer 旨在以其可扩展性、可靠性和强大的功能集满足企业级应用程序的需求。
