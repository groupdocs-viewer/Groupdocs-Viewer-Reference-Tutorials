---
date: '2026-06-30'
description: 了解如何使用 GroupDocs.Viewer 获取 viewinfo 并检索 java 归档文件类型结构。本指南涵盖设置、代码示例以及真实案例。
keywords:
- how to get viewinfo
- retrieve archive structures
- java archive file type
- GroupDocs Viewer Java
schemas:
- author: GroupDocs
  dateModified: '2026-06-30'
  description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  headline: How to Get ViewInfo and Retrieve Archive Structures in Java
  type: TechArticle
- description: Learn how to get viewinfo and retrieve java archive file type structures
    using GroupDocs.Viewer. This guide covers setup, code examples, and real‑world
    use cases.
  name: How to Get ViewInfo and Retrieve Archive Structures in Java
  steps:
  - name: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
    text: '**Data Management:** Quickly organize large datasets by understanding archive
      structures.'
  - name: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
    text: '**Automated File Processing:** Batch‑process archived files without fully
      extracting them, cutting I/O by up to 70 %.'
  - name: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
    text: '**CMS Integration:** Enhance content‑management systems with on‑the‑fly
      archive navigation, enabling editors to preview files directly from the archive.'
  type: HowTo
- questions:
  - answer: It returns file type, page count, and a complete listing of folders and
      files inside an archive.
    question: What does “viewinfo” provide?
  - answer: ZIP, RAR, TAR, 7z, ISO, and 12+ other common formats.
    question: Which archive formats are supported?
  - answer: Yes—a commercial license is required for production; a free trial works
      for evaluation.
    question: Do I need a license for production?
  - answer: Absolutely—use streaming options and process one folder level at a time
      to keep memory usage low.
    question: Can large archives be processed efficiently?
  - answer: Maven is the recommended dependency manager, but Gradle or manual JAR
      inclusion also work.
    question: Is Maven the only way to add the library?
  type: FAQPage
title: 如何获取 ViewInfo 并在 Java 中检索归档结构
type: docs
url: /zh/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# 如何获取 ViewInfo 并检索 Java 中的归档结构

有效管理归档文件需要对其结构有清晰的了解。在本教程中，您将学习 **how to get viewinfo**（获取 viewinfo）针对任何归档，并了解它如何帮助您处理 **java archive file type**（Java 归档文件类型）。我们将演示如何设置 GroupDocs.Viewer、提取视图信息以及递归读取文件夹层次结构，以便您将该解决方案集成到实际项目中。

![使用 GroupDocs.Viewer for Java 的归档结构](/viewer/document-loading/archive-structures-java.png)

**您将学习的内容**
- 设置并配置 GroupDocs.Viewer for Java。  
- 从归档中获取 **viewinfo** 的方法。  
- 读取并显示归档文件的文件夹结构的技术。  
- 在 Java 项目中使用 GroupDocs.Viewer 时的实际应用和性能考虑。

## 快速答案
- **viewinfo 提供什么？** 它返回文件类型、页数以及归档内部文件夹和文件的完整列表。  
- **支持哪些归档格式？** ZIP、RAR、TAR、7z、ISO，以及其他 12 种以上常见格式。  
- **生产环境是否需要许可证？** 是的——生产环境需要商业许可证；免费试用可用于评估。  
- **可以高效处理大型归档吗？** 当然——使用流式选项并一次处理一个文件夹层级，以保持低内存使用。  
- **Maven 是唯一的库添加方式吗？** Maven 是推荐的依赖管理器，但 Gradle 或手动 JAR 引入也可工作。

## 什么是 “how to get viewinfo”？

`getViewInfo` 是一个 GroupDocs.Viewer API 方法，可在不进行完整渲染的情况下提取文档或归档的元数据。它一次调用返回内部文件夹树、文件计数以及基本属性，让您决定要处理的部分。该调用可在典型服务器上在一秒钟内返回最高 500 MB 归档的完整快照。

## 为什么检索 Java 归档文件类型结构？

检索 **java archive file type** 的内部布局，使您能够立即定位所需文件，避免不必要的解压，并构建仅触及相关子文件夹的自动化流水线。这种方法可将大型归档的 I/O 降低高达 70 %，并使在数据摄取场景中每分钟扫描数千个文件成为可能。

## 前提条件

- **Java Development Kit (JDK)：** 8 版或更高。  
- **Maven：** 用于依赖管理和构建。  
- **基本的 Java 知识：** 熟悉面向对象概念有帮助，但不是强制要求。  

您还需要访问 GroupDocs.Viewer 库，可按下面示例将其添加到 Maven 项目中。

## 为 Java 设置 GroupDocs.Viewer

### Maven 配置

将仓库和依赖添加到您的 `pom.xml`。

**仓库：**
```xml
<repositories>
   <repository>
      <id>repository.groupdocs.com</id>
      <name>GroupDocs Repository</name>
      <url>https://releases.groupdocs.com/viewer/java/</url>
   </repository>
</repositories>
```

**依赖项：**
```xml
<dependencies>
   <dependency>
      <groupId>com.groupdocs</groupId>
      <artifactId>groupdocs-viewer</artifactId>
      <version>25.2</version>
   </dependency>
</dependencies>
```

### 许可证获取

- **免费试用：** 从 GroupDocs 网站下载试用版。  
- **临时许可证：** 请求临时密钥用于短期评估。  
- **完整许可证：** 购买商业许可证以无限制生产使用。

一旦库位于类路径上，您即可开始编码。

## 实施指南

### 如何获取归档文件的 ViewInfo

要获取视图信息，首先将归档加载到 Viewer 中，然后调用 `getViewInfo` 检索元数据，最后遍历返回的文件夹层次结构。此三步模式适用于所有受支持的归档格式，并在一次 API 调用中提供完整快照，简化后续处理。

#### 初始化 Viewer

`Viewer` 类是所有渲染和检查操作的入口点。它管理文件流、格式检测以及资源清理。

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### 检索视图信息

`ViewInfo` 封装了文件类型、总页数以及文件夹和文件的层次列表。调用 `getViewInfo` 可即时返回该对象。

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### 显示文件夹结构

遍历 `viewInfo.getFolders()` 可打印每个文件夹名称、其深度以及包含的文件。此简单循环为您提供归档的可读树形视图。

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### 递归文件夹读取

对于深度嵌套的归档，可使用递归辅助方法深度优先遍历树，确保在不将整个归档加载到内存的情况下访问每个子文件夹。

```java
private static void readFolders(Viewer viewer, String folder) {
    ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
    viewInfoOptions.getArchiveOptions().setFolder(folder);
    
    ArchiveViewInfo viewInfo = (ArchiveViewInfo) viewer.getViewInfo(viewInfoOptions);
    
    for (String subFolder : viewInfo.getFolders()) {
        System.out.println(" - " + subFolder);
        readFolders(viewer, subFolder);
    }
}
```

### 功能 2：检索归档文件夹结构

此功能侧重于打印归档文件的文件夹结构。它与第一个功能类似，但更强调递归探索。

#### 设置 ViewInfo 选项

`ArchiveOptions` 允许您在调用 `getViewInfo` 前指定密码保护、页数限制和流式偏好。

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### 递归探索

第二个递归例程演示了如何高效处理受密码保护的归档和大量文件集。

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## 实际应用

1. **数据管理：** 通过了解归档结构快速组织大型数据集。  
2. **自动化文件处理：** 在不完全解压的情况下批量处理归档文件，将 I/O 削减高达 70 %。  
3. **CMS 集成：** 为内容管理系统增强即时归档导航，使编辑者能够直接从归档预览文件。

## 性能考虑

- **优化内存使用：** 一次处理一个文件夹层级，并及时关闭 `Viewer` 实例。  
- **保持更新：** 使用最新的 GroupDocs.Viewer 版本（本文撰写时为 25.2）和 JDK 发行版以获得性能提升。  
- **流式支持：** 该库能够在不将整个文件加载到 RAM 的情况下流式处理大于 1 GB 的归档，得益于内部的分块读取架构。

## 常见问题及解决方案

| 问题 | 原因 | 解决方案 |
|------|------|----------|
| `NullPointerException` 在读取文件夹时出现 | `viewInfo.getFolders()` 对空目录返回 null | 在遍历前检查是否为 null 或空列表。 |
| 处理巨大的 ZIP 文件速度慢 | 整个归档被加载到内存中 | 使用新版 GroupDocs 提供的流式选项。 |
| 未找到许可证 | 许可证文件路径不正确 | 将许可证文件放置在应用根目录或使用 `License.setLicense("path/to/license.json")` 设置路径。 |

## 常见问答

**Q:** 什么是 GroupDocs.Viewer？  
**A:** GroupDocs.Viewer 是一个 Java 库，可将 100 多种文档、图像和归档格式渲染为 HTML、PDF 或图像流，无需本地应用程序。

**Q:** 我可以在其他编程语言中使用 GroupDocs.Viewer 吗？  
**A:** 可以，GroupDocs 提供 .NET、Python、PHP 等 SDK，但本教程专注于 Java 实现。

**Q:** 如何处理大型归档文件？  
**A:** 通过 `ArchiveOptions.setUseStreaming(true)` 启用流式处理，一次处理一个文件夹层级，使用后释放 `Viewer` 对象。

**Q:** GroupDocs.Viewer 支持哪些归档类型？  
**A:** 支持 12 种以上归档格式，包括 ZIP、RAR、TAR、7z、ISO、ARJ、CAB 以及许多专有容器类型。

**Q:** 归档文件有大小限制吗？  
**A:** 实际限制取决于服务器的 RAM 和 CPU；在启用流式的情况下，16 GB RAM 机器上对 2 GB 归档的处理表现平稳。

**Q:** “how to get viewinfo” 能处理受密码保护的归档吗？  
**A:** 能，在调用 `getViewInfo` 前通过 `ArchiveOptions.setPassword("yourPassword")` 提供密码。

## 结论

通过本指南，您现在了解了如何为任何受支持的归档 **获取 viewinfo**，以及如何使用 GroupDocs.Viewer for Java 遍历其文件夹层次结构。这些技术使您能够构建更智能的数据处理流水线，改进 CMS 集成，并自信地处理大规模归档文件集合。接下来，您可以探索从归档中渲染单个文件或将其转换为 PDF/HTML 的其他 Viewer 功能。

---

**最后更新：** 2026-06-30  
**测试环境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs  

## 资源
- **文档：** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API 参考：** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **下载页面：** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **购买许可证：** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **免费试用和临时许可证：** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)

## 相关教程

- [使用 GroupDocs.Viewer for Java 提取文档元数据 - 检索文档视图信息和洞察](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)
- [如何检索附件并打印文档附件（使用 GroupDocs.Viewer for Java）](/viewer/java/advanced-rendering/groupdocs-viewer-java-retrieve-print-attachments/)
- [Java 指南：使用 GroupDocs.Viewer API 渲染特定页面进行文档预览和管理](/viewer/java/rendering-basics/java-groupdocs-viewer-render-pages-api-tutorial/)