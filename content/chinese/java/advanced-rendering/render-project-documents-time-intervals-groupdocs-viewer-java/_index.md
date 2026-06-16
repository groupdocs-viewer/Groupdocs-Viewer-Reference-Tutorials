---
date: '2026-03-29'
description: 学习如何在 Java 中使用 GroupDocs Viewer 创建 MPP 的 HTML 视图，按时间间隔渲染项目文档，并提供一步步的代码示例。
keywords:
- render project documents
- time intervals Java
- GroupDocs Viewer API
title: 使用 GroupDocs Viewer（Java）创建 MPP 的 HTML 视图
type: docs
url: /zh/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/
weight: 1
---

# 如何使用 GroupDocs Viewer 在 Java 中按时间间隔渲染项目文档

在本教程中，您将学习如何使用 GroupDocs Viewer for Java **create html view mpp**，从而仅渲染位于特定时间间隔内的 Microsoft Project 文件的部分。我们将逐步介绍 Maven 设置、代码配置以及实际场景，帮助您将精确的时间线视图直接嵌入到应用程序中。

![Render Project Documents by Time Intervals with GroupDocs.Viewer for Java](/viewer/advanced-rendering/render-project-documents-by-time-intervals-java.png)

## 快速答案
- **此功能的作用是什么？** 它仅渲染位于开始日期和结束日期之间的 Microsoft Project 文件的部分。  
- **使用哪种输出格式？** 使用嵌入资源的 HTML，适合网页集成。  
- **我需要许可证吗？** 免费试用可用于评估；生产环境需要完整许可证。  
- **我可以在运行时更改日期范围吗？** 可以——在渲染选项中调整 `setStartDate` 和 `setEndDate` 的值。  
- **此功能在所有 Java 版本上都受支持吗？** 只要使用 GroupDocs.Viewer 25.2 或更高版本，即可在 Java 8+ 上运行。

## 如何为项目文档创建 html view mpp
GroupDocs Viewer 可以将 Microsoft Project 文件（`.mpp`、`.mpt`）转换为 HTML 页面。通过在渲染选项中配置开始和结束日期，您可以将输出限制在所需的时间段，从而减小文件大小并加快页面加载速度。

## 在此上下文中，“How to Use GroupDocs” 是什么？
GroupDocs Viewer 是一个 Java 库，可将超过 100 种文件格式转换为适合网页的表示形式。当您 **how to use GroupDocs** 项目文件时，您能够在客户端无需 Microsoft Project 即可提取、可视化和共享计划数据。

## 为什么按时间间隔渲染项目文档？
- **聚焦分析：** 仅显示您关注的阶段（例如，2024 年第三季度）。  
- **性能：** 更小的 HTML 输出意味着更快的页面加载。  
- **集成：** 将时间线视图嵌入仪表板、报告门户或自定义项目管理工具中。  

## 前提条件

- **GroupDocs.Viewer for Java** 版本 25.2 或更高。  
- Java Development Kit (JDK) 8 或更高版本。  
- 如 IntelliJ IDEA 或 Eclipse 等 IDE。  
- 基本的 Maven 知识。  

## 设置 GroupDocs.Viewer for Java

### Maven 依赖

在您的 `pom.xml` 中添加仓库和依赖项：

```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### 获取许可证步骤

1. **免费试用** – 从 [GroupDocs 的下载页面](https://releases.groupdocs.com/viewer/java/) 下载试用版。  
2. **临时许可证** – 通过 [此链接](https://purchase.groupdocs.com/temporary-license/) 获取用于延长测试的临时许可证。  
3. **购买** – 若需在生产环境中无限制使用，请在 [GroupDocs 购买页面](https://purchase.groupdocs.com/buy) 购买许可证。  

### 基本 Viewer 初始化

以下代码片段展示了如何创建指向 Microsoft Project 文件（`.mpp`）的 `Viewer` 实例：

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.mpp")) {
            // Your rendering code goes here
        }
    }
}
```

## 步骤实现指南

### 1. 定义输出目录

创建一个文件夹，用于保存生成的 HTML 页面：

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY", "RenderProjectTimeInterval");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

*为什么？* 将渲染的文件组织起来，可更容易从 Web 服务器提供或嵌入到 UI 中。

### 2. 使用项目文件初始化 Viewer

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Continue with rendering steps
}
```

*为什么？* 加载文档会准备内部解析器，并使项目特定的元数据可访问。

### 3. 检索项目文件的视图信息

```java
import com.groupdocs.viewer.options.ViewInfoOptions;
import com.groupdocs.viewer.results.ProjectManagementViewInfo;

ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
ProjectManagementViewInfo viewInfo = (ProjectManagementViewInfo) viewer.getViewInfo(viewInfoOptions);
```

*为什么？* `ProjectManagementViewInfo` 为您提供计划的开始和结束日期，稍后您将使用这些日期来限制渲染范围。

### 4. 配置 HTML 渲染选项（从项目生成 HTML）

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getProjectManagementOptions().setStartDate(viewInfo.getStartDate());
viewOptions.getProjectManagementOptions().setEndDate(viewInfo.getEndDate());
```

*为什么？* 设置 `StartDate` 和 `EndDate` 可指示 GroupDocs 仅在该时间窗口内 **generate html view mpp** 数据。

### 5. 执行渲染过程

```java
viewer.view(viewOptions);
```

*为什么？* 此调用会生成一系列自包含的 HTML 页面，表示您项目计划中选定的时间片段。

## 常见问题与故障排除

- **文件路径不正确** – 请再次确认源 `.mpp` 文件和输出目录均存在。  
- **不支持的文件类型** – 确保文档是受支持的 Project 格式（例如，`.mpp`、`.mpt`）。  
- **许可证错误** – 试用许可证可能会限制渲染；切换到完整许可证以获得无限制使用。  

## 实际应用

1. **项目时间线分析** – 仅向利益相关者展示当前阶段。  
2. **自动化报告** – 为每周状态更新生成时间限定的 HTML 报告。  
3. **与仪表板集成** – 将渲染的页面嵌入 BI 工具或自定义门户。  
4. **归档** – 存储项目计划的网页友好快照以供将来参考。  

## 性能技巧

- 使用 *embedded resources* 选项，使每个 HTML 页面自包含，减少 HTTP 请求。  
- 对于非常大的项目，考虑将渲染分成更小的日期块，以降低内存使用。  
- 在提供后清理临时文件，以避免磁盘膨胀。  

## 结论

您现在了解了如何 **how to use GroupDocs** Viewer 在特定时间间隔内渲染项目文档，并在 Java 中 **generate HTML from project** 数据。此功能简化了时间线可视化，提高了报告效率，并可顺畅集成到现代 Web 应用中。

### 下一步
- 探索其他 Viewer 功能，如水印、密码保护或自定义 CSS 样式。  
- 将此渲染管道与 REST API 结合，以按需提供时间线视图。  

## 常见问题

**问：GroupDocs.Viewer 支持哪些文件格式？**  
答：GroupDocs.Viewer 支持包括 Microsoft Project (MPP)、PDF、Word、Excel、PowerPoint 等在内的多种格式。

**问：如何开始使用 GroupDocs.Viewer 的免费试用？**  
答：您可以从 [此处](https://releases.groupdocs.com/viewer/java/) 下载试用版。

**问：我可以在渲染文档时不嵌入资源吗？**  
答：可以，您可以选择引用外部资源而非嵌入的其他 HTML 视图选项。

**问：如果我的文档太大而无法渲染怎么办？**  
答：考虑将文档拆分为更小的部分，或仅渲染所需的日期范围，如上所示。

**问：我该如何处理渲染错误？**  
答：检查所有配置设置，确保拥有有效许可证，并查阅 GroupDocs 文档获取详细错误代码。

## 资源
- **文档**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API 参考**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)
- **下载**: [GroupDocs Downloads](https://releases.groupdocs.com/viewer/java/)
- **购买**: [Buy GroupDocs License](https://purchase.groupdocs.com/buy)
- **免费试用**: [Try the Free Version](https://releases.groupdocs.com/viewer/java/)
- **临时许可证**: [Get a Temporary License](https://purchase.groupdocs.com/temporary-license/)
- **支持**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**最后更新：** 2026-03-29  
**测试环境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs  

---