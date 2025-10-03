---
"date": "2025-04-25"
"description": "了解如何使用 GroupDocs.Viewer for .NET 高效提取存档信息。本指南涵盖设置、代码示例和实际应用。"
"title": "如何使用 GroupDocs.Viewer for .NET 检索存档信息——综合指南"
"url": "/zh/net/metadata-properties/groupdocs-viewer-net-retrieve-archive-info/"
"weight": 1
type: docs
---
# 如何使用 GroupDocs.Viewer for .NET 检索存档信息：综合指南

## 介绍

您是否希望高效地从 ZIP 等存档文件中提取详细信息？了解其结构对于文档管理至关重要。本指南将向您展示如何使用 **适用于 .NET 的 GroupDocs.Viewer** 检索并显示有关存档文件的详细信息。

![使用 GroupDocs.Viewer for .NET 检索存档信息](/viewer/metadata-properties/retrieve-archive-information.png)

在本教程中，我们将介绍：
- 在 .NET 应用程序中设置 GroupDocs.Viewer
- 从存档文件中检索视图信息
- 显示档案中的文件夹结构

读完本指南后，您将对如何实现这些功能有深入的了解。在深入研究代码之前，我们先了解一下您需要什么。

### 先决条件

确保您已准备好以下物品：

- **库和版本**：安装适用于 .NET 的 GroupDocs.Viewer（版本 25.3.0）。
- **环境设置**：使用合适的.NET 开发环境，如 Visual Studio。
- **知识前提**：对 C# 和 .NET 应用程序中的文件处理有基本的了解。

## 为 .NET 设置 GroupDocs.Viewer

要使用 GroupDocs.Viewer for .NET，请通过 NuGet 包管理器安装它：

### 安装说明

**NuGet 包管理器控制台**
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**.NET CLI**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### 获取许可证

GroupDocs.Viewer 提供多种许可选项：
- **免费试用**：探索基本功能。
- **临时执照**：评估期间可访问全部功能。
- **购买**：为了长期使用，请考虑购买许可证。

安装并设置许可证后，请在应用程序中初始化 GroupDocs.Viewer。以下是示例设置：

```csharp
using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS"))
{
    // 在此处使用查看器功能。
}
```

## 实施指南

我们将把实施过程分解为结构化方法的关键特征。

### 检索存档文件的视图信息

了解档案库的结构至关重要。以下是如何实现这一点：

#### 初始化查看器对象

创建一个实例 `Viewer` 类与您的存档文件路径：

```csharp
string documentPath = "YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS";
using (Viewer viewer = new Viewer(documentPath))
{
    // 您的处理代码将放在这里。
}
```

#### 获取视图信息

检索视图信息，格式为 JPG 图像：

```csharp
ViewInfo info = viewer.GetViewInfo(ViewInfoOptions.ForJpgView());
Console.WriteLine("File type: " + info.FileType);
Console.WriteLine("Pages count: " + info.Pages.Count);
```

#### 显示根文件夹信息

为了全面概述，请打印根文件夹详细信息：

```csharp
Console.WriteLine("Folders:");
Console.WriteLine(" - /");
```

#### 递归读取并打印子文件夹名称

要探索档案中的子文件夹，请使用此递归方法：

```csharp
string rootFolder = string.Empty;
ReadArchiveFolders(viewer, rootFolder);

private static void ReadArchiveFolders(Viewer viewer, string folder)
{
    ViewInfoOptions options = ViewInfoOptions.ForJpgView();
    options.ArchiveOptions.Folder = folder;

    ArchiveViewInfo viewInfo = viewer.GetViewInfo(options) as ArchiveViewInfo;
    foreach (string subFolder in viewInfo.Folders)
    {
        Console.WriteLine($" - {subFolder}");
        ReadArchiveFolders(viewer, subFolder);
    }
}
```

### 实际应用

GroupDocs.Viewer for .NET 可用于各种场景：
- **文档管理系统**：自动提取并显示档案结构。
- **内容交付平台**：向用户提供存档内容的预览。
- **数据分析工具**：分析档案中的文件夹层次结构以获取业务洞察。

与 ASP.NET 或 WPF 等其他框架的集成非常简单，可以无缝地融入现有系统。

## 性能考虑

为了获得最佳性能：
- **优化资源使用**：高效管理内存和处理大文件。
- **内存管理最佳实践**：处理 `Viewer` 对象以便及时释放资源。

## 结论

在本教程中，您学习了如何利用 GroupDocs.Viewer for .NET 从存档文件中检索详细信息。实现这些功能可以显著增强您的文档管理能力。

### 后续步骤

不妨探索 GroupDocs.Viewer 提供的更多高级功能，或将其与应用程序的其他组件集成。尝试不同的文件类型和复杂的文件夹结构，以加深您的理解。

## 常见问题解答部分

1. **目的是什么 `ViewInfoOptions`？**
   - 它配置您想要如何查看文档，例如呈现 JPG 等特定格式。

2. **如何高效地处理大型档案？**
   - 使用内存管理技术并适当处理资源。

3. **GroupDocs.Viewer 可以处理受密码保护的文件吗？**
   - 是的，有了正确的许可证和配置，它可以处理加密文档。

4. **可处理的存档文件大小有限制吗？**
   - 该限制取决于系统的内存容量；文件越大，需要的资源就越多。

5. **如何将 GroupDocs.Viewer 与 ASP.NET 应用程序集成？**
   - 在控制器操作或服务中使用 Viewer 类，类似于在控制台应用程序中的操作。

## 资源

- [文档](https://docs.groupdocs.com/viewer/net/)
- [API 参考](https://reference.groupdocs.com/viewer/net/)
- [下载 GroupDocs.Viewer for .NET](https://releases.groupdocs.com/viewer/net/)
- [购买许可证](https://purchase.groupdocs.com/buy)
- [免费试用版](https://releases.groupdocs.com/viewer/net/)
- [临时执照申请](https://purchase.groupdocs.com/temporary-license/)
- [支持论坛](https://forum.groupdocs.com/c/viewer/9)