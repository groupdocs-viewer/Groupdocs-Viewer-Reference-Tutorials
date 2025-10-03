---
"date": "2025-04-25"
"description": "了解如何使用 GroupDocs.Viewer for .NET 将 PDF 页面转换为 PNG 图像，同时保留原始尺寸。本指南涵盖设置、配置和最佳实践。"
"title": "使用 GroupDocs.Viewer for .NET 将 PDF 转换为原始大小的 PNG"
"url": "/zh/net/export-conversion/convert-pdfs-to-png-groupdocs-viewer-net/"
"weight": 1
type: docs
---
# 使用 GroupDocs.Viewer for .NET 将 PDF 转换为原始大小的 PNG

## 介绍

将 PDF 文件转换为 PNG 图像并保持原始页面大小对于高质量文档数字化或网页内容准备至关重要。本教程将指导您使用 GroupDocs.Viewer for .NET 将 PDF 页面渲染为 PNG 文件，并保留其原始尺寸。

![使用 GroupDocs.Viewer for .NET 将 PDF 转换为原始大小的 PNG](/viewer/export-conversion/convert-pdfs-to-png-with-original-size.png)

**您将学到什么：**
- 如何在您的项目中设置和配置 GroupDocs.Viewer for .NET
- 将 PDF 渲染为 PNG 图像并保持页面大小的分步过程
- 实现最佳性能的关键配置选项和最佳实践

在本教程结束时，您将能够将此功能无缝集成到您的应用程序中。让我们从入门的必要条件开始。

## 先决条件

在您的项目中实现 GroupDocs.Viewer for .NET 之前，请确保您满足以下要求：

### 所需的库和版本
- **适用于 .NET 的 GroupDocs.Viewer**：版本 25.3.0 或更高版本。

### 环境设置要求
- 兼容的开发环境，例如 Visual Studio。
- 对 C# 编程有基本的了解。

### 知识前提
- 熟悉NuGet包管理。
- 具有在 .NET 应用程序中处理 PDF 和图像处理的一些经验。

一旦满足这些先决条件，我们就可以继续设置 GroupDocs.Viewer for .NET。

## 为 .NET 设置 GroupDocs.Viewer

要开始使用 GroupDocs.Viewer for .NET，请按照以下安装步骤操作：

### 通过 NuGet 包管理器控制台安装
在 Visual Studio 中打开您的项目并使用以下命令：
```plaintext
Install-Package GroupDocs.Viewer -Version 25.3.0
```

### 通过 .NET CLI 安装
或者，您可以使用以下命令通过 .NET CLI 安装它：
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### 许可证获取步骤
1. **免费试用**：从下载试用版 [GroupDocs 下载](https://releases。groupdocs.com/viewer/net/).
2. **临时执照**：获取临时许可证以探索完整功能 [临时许可证页面](https://purchase。groupdocs.com/temporary-license/).
3. **购买**：如需延长使用时间，请通过 [购买页面](https://purchase。groupdocs.com/buy).

### 基本初始化和设置
要在 C# 项目中初始化 GroupDocs.Viewer for .NET，请按照以下步骤操作：
1. 导入必要的命名空间：
    ```csharp
    using System;
    using GroupDocs.Viewer;
    using GroupDocs.Viewer.Options;
    ```
2. 设置输入 PDF 和输出目录的路径。
3. 初始化 `Viewer` 使用源文档的路径，如下段所示：
   ```csharp
   string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
   string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
   string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";

   using (Viewer viewer = new Viewer(documentPath))
   {
       PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
       viewer.View(viewOptions);
   }
   ```

## 实施指南
本节介绍如何将 PDF 页面渲染为 PNG 图像并保持其原始大小。

### 将 PDF 页面渲染为具有原始页面大小的 PNG
#### 概述
此功能允许您将 PDF 文档的每一页渲染为 PNG 图像，并保留其原始尺寸。这对于需要精确呈现文档视觉效果的应用程序尤其有用。

##### 步骤 1：设置路径并初始化查看器
为输入 PDF 路径和输出目录创建变量：
```csharp
string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_PDF.pdf";
string outputDirectory = "YOUR_OUTPUT_DIRECTORY";
string pageFilePathFormat = $"{outputDirectory}/page_{0}.png";
```
初始化 `Viewer` 类与您的源文档路径：
```csharp
using (Viewer viewer = new Viewer(documentPath))
{
    // 代码块将在下一步继续
}
```
##### 步骤2：配置PngViewOptions
创建一个实例 `PngViewOptions`，指定输出图像的文件命名模式：
```csharp
PngViewOptions viewOptions = new PngViewOptions(pageFilePathFormat);
```
配置查看器选项以按原始大小呈现每个页面：
```csharp
viewOptions.PdfOptions.RenderOriginalPageSize = true;
```
##### 步骤3：渲染文档页面
致电 `View` 方法 `Viewer` 实例，传入配置的视图选项：
```csharp
viewer.View(viewOptions);
```
### 故障排除提示
- 确保路径正确且目录存在。
- 验证您是否具有从输入目录读取和写入输出目录所需的权限。

## 实际应用
1. **文档数字化**：将档案 PDF 文档转换为数字图像，以便于访问和分发。
2. **门户网站**：无需 PDF 阅读器即可在网站上显示文档预览。
3. **内容管理系统（CMS）**：与 CMS 平台集成，高效管理和显示大量 PDF 内容。

## 性能考虑
要使用 GroupDocs.Viewer for .NET 优化应用程序的性能：
- 如果处理大文件，则通过分块处理文档来限制内存使用量。
- 尽可能使用异步方法来避免在渲染期间阻塞线程。
- 处置 `Viewer` 实例使用后立即释放资源。

## 结论
在本教程中，您学习了如何使用 GroupDocs.Viewer for .NET 将 PDF 页面渲染为 PNG 图像，同时保持其原始大小。我们介绍了如何设置环境、配置必要的选项以获得最佳效果，并探讨了此功能的实际应用。

下一步包括试验 GroupDocs.Viewer 中可用的其他渲染选项或将其集成到更大的项目中以增强文档管理功能。

## 常见问题解答部分
1. **使用 GroupDocs.Viewer 处理大型 PDF 文件的最佳方法是什么？**
   - 以较小的块处理文档并使用异步方法来保持性能。
2. **我可以自定义输出 PNG 文件名吗？**
   - 是的，通过指定命名模式 `PngViewOptions`。
3. **是否可以仅呈现特定页面？**
   - 当然，你可以配置 `PageNumbers` 在 `PngViewOptions` 指定要呈现哪些页面。
4. **如何处理 GroupDocs.Viewer 的许可？**
   - 选项包括免费试用、临时许可证或购买完整许可证。
5. **这个设置可以在 Web 应用程序中使用吗？**
   - 是的，它适用于 ASP.NET Core 和其他基于 .NET 的 Web 框架中的服务器端 PDF 渲染。

## 资源
- [文档](https://docs.groupdocs.com/viewer/net/)
- [API 参考](https://reference.groupdocs.com/viewer/net/)
- [下载 GroupDocs.Viewer](https://releases.groupdocs.com/viewer/net/)
- [购买许可证](https://purchase.groupdocs.com/buy)
- [免费试用](https://releases.groupdocs.com/viewer/net/)
- [临时执照](https://purchase.groupdocs.com/temporary-license/)
- [支持论坛](https://forum.groupdocs.com/c/viewer/9)