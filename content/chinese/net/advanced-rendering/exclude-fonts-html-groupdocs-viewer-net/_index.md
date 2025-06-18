---
"date": "2025-04-25"
"description": "了解如何使用 GroupDocs.Viewer for .NET 从 HTML 转换中排除 Arial 等字体，确保跨平台的品牌一致性。"
"title": "如何使用 GroupDocs.Viewer for .NET 从 HTML 输出中排除特定字体"
"url": "/zh/net/advanced-rendering/exclude-fonts-html-groupdocs-viewer-net/"
"weight": 1
---

# 如何使用 GroupDocs.Viewer for .NET 从 HTML 输出中排除字体

## 介绍

将文档转换为 HTML 格式时，控制所用字体至关重要，尤其对于品牌一致性而言。本教程将向您展示如何使用 GroupDocs.Viewer for .NET 排除特定字体（例如 Arial）。通过本指南，您将学习如何有效地管理文档到 HTML 转换中的字体渲染。

![在 GroupDocs.Viewer for .NET 中从 HTML 输出中排除特定字体](/viewer/advanced-rendering/exclude-specific-fonts-from-html-output-img.png)

### 您将学到什么：
- 设置和配置 GroupDocs.Viewer for .NET
- 从 HTML 输出中排除特定字体的技术
- 优化性能和与其他 .NET 系统集成的实用技巧
- 这些技术的实际应用

## 先决条件

开始之前，请确保您已准备好以下内容：
- **库和版本**：GroupDocs.Viewer 版本 25.3.0 或更高版本。
- **环境设置**：使用.NET Framework或.NET Core搭建的开发环境。
- **知识前提**：对 C# 和 .NET 开发有基本的了解。

## 为 .NET 设置 GroupDocs.Viewer

### 安装说明：

**使用 NuGet 包管理器控制台：**
```bash
Install-Package GroupDocs.Viewer -Version 25.3.0
```

**使用 .NET CLI：**
```bash
dotnet add package GroupDocs.Viewer --version 25.3.0
```

### 许可证获取：
您可以从 [GroupDocs 购买页面](https://purchase.groupdocs.com/buy)。如需临时访问，请考虑申请 [临时执照](https://purchase。groupdocs.com/temporary-license/).

### 基本初始化和设置：

以下是在 .NET 项目中初始化 GroupDocs.Viewer 的方法：
```csharp
using System;
using System.IO;
using GroupDocs.Viewer;
using GroupDocs.Viewer.Options;

string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY", "RenderedHTML");
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

if (!Directory.Exists(outputDirectory))
{
    Directory.CreateDirectory(outputDirectory);
}

using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY\\Sample.docx"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    // 您的配置将放在这里
}
```
此设置确保您已准备好使用 GroupDocs.Viewer 操作文档渲染。

## 实施指南

### 从 HTML 输出中排除字体

在本节中，我们将重点介绍如何使用 GroupDocs.Viewer for .NET 从 HTML 输出中排除特定字体。 

#### 步骤 1：准备您的环境
确保输出目录存在并且设置正确：
```csharp
string outputDirectory = Path.Combine("YOUR_OUTPUT_DIRECTORY", "RenderedHTML");
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");

if (!Directory.Exists(outputDirectory))
{
    Directory.CreateDirectory(outputDirectory);
}
```
此步骤可确保您的渲染文件具有指定位置。

#### 步骤 2：配置 HTML 视图选项
下面介绍如何配置查看器以输出嵌入的资源 HTML 文件：
```csharp
using (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY\\Sample.docx"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
```
这 `HtmlViewOptions` 对象对于指定如何将文档呈现为 HTML 至关重要。

#### 步骤 3：排除特定字体
要排除 Arial 字体，请修改 `options` 配置：
```csharp
options.FontsToExclude.Add("Arial");
```
此行指示 GroupDocs.Viewer 在输出 HTML 中嵌入的任何字体中省略 Arial。通过指定 `FontsToExclude`，您可以控制如何在不同环境中保留文档的视觉样式。

#### 步骤 4：渲染文档
最后，使用以下设置渲染您的文档：
```csharp
viewer.View(options);
```
通过调用 `View()`，GroupDocs.Viewer 根据指定的选项处理您的文档并将其输出为不带排除字体的 HTML 格式。

### 故障排除提示
- 确保文件路径设置正确。
- 验证您使用的 GroupDocs.Viewer for .NET 是否兼容版本。
- 仔细检查字体名称，因为它们必须完全匹配，包括区分大小写。

## 实际应用

### 用例：
1. **一致的品牌**：排除不需要的字体，以确保您的品牌字体在所有平台上保持一致。
2. **Web 集成**：与需要特定字体的 CMS 系统集成，以保持网页设计的一致性。
3. **文件归档**：以 HTML 格式存档文档，不带多余的字体，从而减小文件大小。

### 集成可能性：
- 利用 .NET 应用程序中的 GroupDocs.Viewer 创建自定义文档查看解决方案。
- 与 ASP.NET MVC 或 Blazor 等框架结合，在 Web 上实现动态文档渲染。

## 性能考虑

处理大型文档时，优化性能至关重要。以下是一些技巧：

- **资源管理**：注意应用程序的内存使用情况，尤其是大文件。
- **批处理**：如果适用，请分批处理文档以避免占用过多的系统资源。
- **高效缓存**：对经常访问的文档实施缓存策略。

## 结论

在本教程中，我们探讨了如何使用 GroupDocs.Viewer for .NET 从 HTML 输出中排除特定字体。按照以下步骤操作，您可以控制转换后文档的视觉呈现效果。 

为了进一步探索，请考虑集成 GroupDocs.Viewer 提供的更多高级功能或探索其完整的 API 功能。

## 常见问题解答部分

**问题 1：我可以一次排除多种字体吗？**
是的，只需拨打 `options.FontsToExclude.Add("FontName")` 对于您想要排除的每种字体。

**Q2：如果在文档中找不到指定的字体，会发生什么情况？**
GroupDocs.Viewer 将忽略它并继续使用可用的字体进行渲染。

**问题 3：我可以排除的字体数量有限制吗？**
没有具体的限制，但在排除大量字体时要考虑性能影响。

**Q4：此功能可以与其他输出格式（如 PDF 或图像）一起使用吗？**
GroupDocs.Viewer 支持多种格式，但字体排除的具体细节可能有所不同。详情请参阅文档。

**Q5：如何使用 GroupDocs.Viewer 处理不同类型的文档？**
该库功能强大，原生支持多种文件格式。请查看 API 参考，了解每种格式支持的功能。

## 资源
- **文档**： [GroupDocs 查看器 .NET 文档](https://docs.groupdocs.com/viewer/net/)
- **API 参考**： [GroupDocs API 参考](https://reference.groupdocs.com/viewer/net/)
- **下载**： [GroupDocs 下载](https://releases.groupdocs.com/viewer/net/)
- **购买**： [购买 GroupDocs 许可证](https://purchase.groupdocs.com/buy)
- **免费试用**： [获取免费试用](https://releases.groupdocs.com/viewer/net/)
- **临时执照**： [申请临时许可证](https://purchase.groupdocs.com/temporary-license/)
- **支持**： [GroupDocs 支持论坛](https://forum.groupdocs.com/c/viewer/9)

准备好将您的文档渲染项目提升到新的水平了吗？立即尝试实施这些解决方案！