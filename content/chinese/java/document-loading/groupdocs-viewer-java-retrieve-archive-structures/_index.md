---
date: '2026-02-05'
description: 了解如何使用 GroupDocs.Viewer 获取 viewinfo 并检索 Java 存档文件类型结构。本指南涵盖设置、代码示例以及实际使用案例。
keywords:
- GroupDocs.Viewer for Java
- retrieve archive structures
- Java document viewer
title: 如何在 Java 中获取 ViewInfo 并检索归档结构
type: docs
url: /zh/java/document-loading/groupdocs-viewer-java-retrieve-archive-structures/
weight: 1
---

# 如何在 Java 中获取 ViewInfo 并检索归档结构

有效管理归档文件需要清晰了解其结构。在本教程中，您将学习 **如何获取 viewinfo**，以及它如何帮助您处理 **java archive file type**。我们将演示如何设置 GroupDocs.Viewer、提取视图信息，并递归读取文件夹层级，以便您将该方案集成到实际项目中。

![使用 GroupDocs.Viewer for Java 的归档结构](/viewer/document-loading/archive-structures-java.png)

**您将学到的内容**
- 为 Java 设置和配置 GroupDocs.Viewer。  
- 从归档中 **获取 viewinfo** 的方法。  
- 读取并显示归档文件夹结构的技术。  
- 在 Java 项目中使用 GroupDocs.Viewer 的实际应用和性能注意事项。

## 快速答案
- **“viewinfo” 提供了什么？** 它返回文件类型、页数以及归档文件夹列表。  
- **支持哪些归档格式？** ZIP、RAR、TAR 以及其他常见格式。  
- **需要许可证吗？** 免费试用可用于评估；生产环境需要商业许可证。  
- **可以处理大型归档吗？** 可以——后文将展示如何使用流式处理和适当的内存管理。  
- **必须使用 Maven 吗？** 推荐使用 Maven 来管理 GroupDocs.Viewer 依赖。

## 什么是 “how to get viewinfo”？
`getViewInfo` 是 GroupDocs.Viewer API 中的一个方法，用于在不渲染完整内容的情况下提取文档或归档的元数据。对于归档，它会显示内部文件夹树，帮助您决定要渲染或进一步处理的部分。

## 为什么要检索 Java 归档文件类型结构？
了解 **java archive file type**（例如 ZIP、RAR）的内部布局可以让您：
- 在不解压全部内容的情况下快速定位所需文件。  
- 构建仅处理相关子文件夹的自动化流水线。  
- 将归档导航集成到内容管理或数据摄取系统中。

## 前置条件

- **Java Development Kit (JDK)：** 8 版或更高。  
- **Maven：** 用于依赖管理和构建。  
- **基本的 Java 知识：** 熟悉面向对象概念有帮助，但不是必需的。

您还需要获取 GroupDocs.Viewer 库，可按下面方式将其添加到 Maven 项目中。

## 为 Java 设置 GroupDocs.Viewer

### Maven 配置

在 `pom.xml` 中添加仓库和依赖。

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

**依赖：**  
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
- **临时许可证：** 申请短期评估的临时密钥。  
- **完整许可证：** 购买商业许可证以获得无限制的生产使用。

将库加入类路径后，即可开始编写代码。

## 实现指南

### 如何获取归档文件的 ViewInfo

本节展示调用 `getViewInfo` 并读取文件夹层级的完整步骤。

#### 初始化 Viewer

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_ZIP_WITH_FOLDERS")) {
    // Additional steps will follow here.
}
```

#### 检索视图信息

```java
ViewInfo viewInfo = viewer.getViewInfo(ViewInfoOptions.forHtmlView());
System.out.println("File type: " + viewInfo.getFileType());
System.out.println("Pages count: " + viewInfo.getPages().size());
```

#### 显示文件夹结构

```java
String rootFolder = "";
readFolders(viewer, rootFolder);
```

##### 递归读取文件夹

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

此功能侧重于打印归档文件的文件夹结构。它与第一个功能类似，但更强调递归遍历。

#### 设置 ViewInfo 选项

```java
ViewInfoOptions viewInfoOptions = ViewInfoOptions.forHtmlView();
viewInfoOptions.getArchiveOptions().setFolder(folder);
```

#### 递归遍历

```java
for (String subFolder : viewInfo.getFolders()) {
    System.out.println(" - " + subFolder);
    readFolders(viewer, subFolder);
}
```

## 实际应用

1. **数据管理：** 通过了解归档结构快速组织大型数据集。  
2. **自动化文件处理：** 在不完整解压的情况下批量处理归档文件。  
3. **CMS 集成：** 为内容管理系统提供即时归档导航功能。

## 性能注意事项

- **优化内存使用：** 一次只处理一个层级的文件夹，并及时关闭 `Viewer` 实例。  
- **保持更新：** 使用最新的 GroupDocs.Viewer 版本和 JDK 发行版以获得性能提升。

## 常见问题及解决方案

| 问题 | 产生原因 | 解决方案 |
|------|----------|----------|
| 读取文件夹时出现 `NullPointerException` | `viewInfo.getFolders()` 对空目录返回 null | 在遍历前检查是否为 null 或空列表。 |
| 处理巨大的 ZIP 文件速度慢 | 整个归档被加载到内存中 | 使用新版 GroupDocs 提供的流式选项。 |
| 未找到许可证 | 许可证文件路径不正确 | 将许可证文件放在应用根目录或使用 `License.setLicense("path/to/license.json")` 设置路径。 |

## 常见问答

**问：什么是 GroupDocs.Viewer？**  
答：它是一个强大的 Java 库，可将文档（包括归档）渲染为 HTML、图像和 PDF 等格式。

**问：可以在其他编程语言中使用 GroupDocs.Viewer 吗？**  
答：可以，GroupDocs 为多个平台提供 SDK，但本教程专注于 Java 实现。

**问：如何处理大型归档文件？**  
答：采用高效的内存管理实践，必要时将归档拆分处理。

**问：GroupDocs.Viewer 支持哪些归档类型？**  
答：支持包括 ZIP、RAR、TAR 等多种格式。

**问：处理归档的大小是否有限制？**  
答：限制取决于系统资源。请在目标环境中进行测试以确定实际可处理的上限。

**问：“how to get viewinfo” 能处理受密码保护的归档吗？**  
答：可以，在调用 `getViewInfo` 前通过 `ArchiveOptions.setPassword("yourPassword")` 提供密码。

## 结论

通过本指南，您已经掌握了 **如何获取 viewinfo** 以读取任意受支持归档的文件夹层级，并了解了使用 GroupDocs.Viewer for Java 的实现方式。这些技术帮助您构建更智能的数据处理流水线、提升 CMS 集成，并自信地处理大规模归档文件。接下来，您可以探索从归档中渲染单个文件或使用其他 Viewer 功能将其转换为 PDF/HTML。

---

**最后更新：** 2026-02-05  
**测试环境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs  

**资源**
- **文档：** [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)
- **API 参考：** [GroupDocs API Reference for Java](https://reference.groupdocs.com/viewer/java/)
- **下载 GroupDocs.Viewer：** [GroupDocs Download Page](https://releases.groupdocs.com/viewer/java/)
- **购买许可证：** [Buy GroupDocs](https://purchase.groupdocs.com/buy)
- **免费试用和临时许可证：** [GroupDocs Free Trial](https://releases.groupdocs.com/viewer/java/) | [Temporary License](https://purchase.groupdocs.com/temporary-license/)