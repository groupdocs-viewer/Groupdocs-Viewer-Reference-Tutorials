---
title: 使用取消令牌取消渲染
linktitle: 使用取消令牌取消渲染
second_title: GroupDocs.Viewer .NET API
description: 将 Groupdocs.Viewer for .NET 无缝集成到您的 .NET 项目中，以实现高效的文档查看。
weight: 11
url: /zh/net/rendering-options/cancel-render-cancellation-token/
---
## 介绍
Groupdocs.Viewer for .NET 是一款功能强大的工具，旨在简化 .NET 应用程序中的文档查看和处理。无论您处理的是 PDF、Microsoft Office 文档还是其他常见格式，该库都提供了强大的功能，可以将文档查看功能无缝集成到您的 .NET 项目中。
## 先决条件
在深入研究 Groupdocs.Viewer for .NET 的集成之前，请确保满足以下先决条件：
1. 安装：从提供的下载并安装 Groupdocs.Viewer for .NET 库[下载链接](https://releases.groupdocs.com/viewer/net/).
   
2. 许可证： 获得许可证[组文档](https://purchase.groupdocs.com/buy)释放图书馆的全部潜力。或者，您可以使用以下方式开始免费试用：[临时执照](https://purchase.groupdocs.com/temporary-license/).
   
3. 开发环境：确保您设置了兼容的开发环境，包括 Visual Studio 或您选择的任何其他 .NET IDE。

## 导入命名空间
为了有效地利用 Groupdocs.Viewer for .NET，您需要将必要的命名空间导入到您的项目中。按着这些次序：

```csharp
using System;
using System.IO;
using GroupDocs.Viewer.Options;
using System.Threading.Tasks;
using System.Threading;
```

现在，让我们将提供的示例分解为多个步骤，以便更好地理解和实现：
## 第 1 步：定义输出目录
```csharp
string outputDirectory = "Your Document Directory";
```
此步骤设置将存储渲染的文档页面的目录。
## 第2步：定义页面文件路径格式
```csharp
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
```
在这里，我们定义各个文档页面的文件路径的格式。
## 步骤3：初始化CancellationTokenSource
```csharp
CancellationTokenSource cancellationTokenSource = new CancellationTokenSource();
```
CancellationTokenSource 用于生成可用于取消异步操作的 CancellationToken 实例。
## 第四步：获取CancellationToken
```csharp
CancellationToken cancellationToken = cancellationTokenSource.Token;
```
此步骤从 CancellationTokenSource 检索令牌，该令牌将用于取消渲染操作。
## 第 5 步：渲染文档页面
```csharp
Task.Run(() =>
{
    using (Viewer viewer = new Viewer(TestFiles.SAMPLE_DOCX, new ViewerSettings(new GroupDocs.Viewer.Logging.ConsoleLogger())))
    {
        HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
        options.RenderComments = true;
        viewer.View(options, cancellationToken);
    }
}, cancellationToken);
```
在这里，我们使用 Task.Run() 异步启动文档页面的渲染。 Viewer 实例是使用指定的文档文件 (SAMPLE_DOCX) 创建的，并配置了呈现选项。然后使用 Viewer 类的 View 方法开始渲染过程。
## 第 6 步：设置渲染超时
```csharp
cancellationTokenSource.CancelAfter(10);
```
此步骤为渲染操作设置 10 毫秒的超时。如果操作超过这个超时时间，就会自动取消。
## 第7步：显示成功消息
```csharp
Console.WriteLine($"\nSource document rendered successfully.\nCheck output in {outputDirectory}.");
```
最后，会显示一条成功消息，表明文档已成功呈现。

## 结论
在本教程中，我们介绍了将 Groupdocs.Viewer for .NET 集成到项目中的基础知识。通过执行上述步骤，您可以将文档查看功能无缝合并到 .NET 应用程序中，从而增强用户体验和工作效率。
## 常见问题解答
### Groupdocs.Viewer for .NET 是否与所有文档格式兼容？
Groupdocs.Viewer for .NET 支持多种文档格式，包括 PDF、Microsoft Office 文档、图像等。
### 我可以自定义渲染文档页面的外观吗？
是的，您可以自定义渲染过程的各个方面，包括页面大小、质量、水印等等。
### Groupdocs.Viewer for .NET 是否需要互联网连接？
不需要，Groupdocs.Viewer for .NET 在您的 .NET 环境中本地运行，并且不需要 Internet 连接即可查看文档。
### Groupdocs.Viewer for .NET 是否提供技术支持？
是的，可以通过以下方式获得技术支持[组文档论坛](https://forum.groupdocs.com/c/viewer/9)，您可以在其中提问、报告问题以及与社区互动。
### 我可以在购买前试用 Groupdocs.Viewer for .NET 吗？
是的，您可以使用提供的免费试用版开始[试用版](https://releases.groupdocs.com/).