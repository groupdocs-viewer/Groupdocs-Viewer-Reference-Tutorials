---
date: '2026-02-23'
description: 了解如何设置每页项目数、嵌入资源 HTML，以及使用 GroupDocs.Viewer Java 批量将压缩包转换为单页或多页 HTML。
keywords:
- convert archives to HTML Java
- GroupDocs.Viewer Java tutorial
- render ZIP RAR to HTML
title: 设置每页项目数：使用 GroupDocs.Viewer Java 将归档转换为 HTML
type: docs
url: /zh/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# 设置每页项目数：使用 GroupDocs.Viewer Java 将归档文件转换为 HTML

将 ZIP 或 RAR 等归档文件转换为适合网页的 HTML 是在浏览器中直接共享或审阅文档时的常见需求。在本指南中，您将学习**如何设置每页项目数**，如何嵌入资源 HTML 以生成自包含的输出，以及如何使用 GroupDocs.Viewer Java 高效批量转换归档。

![使用 GroupDocs.Viewer for Java 将归档转换为 HTML](/viewer/export-conversion/convert-archives-to-html-java.png)

## 快速答复
- **“设置每页项目数” 控制什么？** 它决定了归档中的多少文件或文件夹会出现在每个生成的 HTML 页面上。  
- **我可以直接在 HTML 中嵌入图像和 CSS 吗？** 可以——使用 `forEmbeddedResources` 选项来嵌入资源 HTML。  
- **批量转换是否可行？** 完全可以；您可以遍历一组归档文件，并使用相同的设置渲染每个文件。  
- **使用 GroupDocs.Viewer 是否需要 Maven？** 是的，按下面所示添加 `maven groupdocs viewer` 依赖。  
- **支持哪些输出格式？** 单页 HTML Java 和多页 HTML Java 均可用。

## GroupDocs.Viewer 中的 “设置每页项目数” 是什么？
**设置每页项目数** 设置属于归档渲染选项。它告诉查看器在生成多页 HTML 文档时，每个 HTML 页面应显示多少归档条目（文件或文件夹）。调整此值有助于在页面大小和导航速度之间取得平衡，尤其是针对大型归档。

## 为什么要嵌入资源 HTML？
将资源（图像、CSS、字体）直接嵌入 HTML 文件可生成一个单一的可移植文档，无需外部文件即可打开。这对于电子邮件附件、离线查看或将输出嵌入其他网页非常理想。

## 前置条件

- **必需的库：** 包含 GroupDocs.Viewer 版本 25.2 或更高。  
- **环境：** 已安装并配置 Java Development Kit (JDK)。  
- **知识要求：** 基础的 Java 和 Maven 依赖管理。  

## Maven GroupDocs Viewer 设置

在您的 `pom.xml` 中添加 GroupDocs 仓库和 viewer 依赖：

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

### 获取许可证
GroupDocs.Viewer 提供 **免费试用链接**、临时许可证或完整购买选项。请选择最符合您项目时间表的方案。

### 基本初始化
完成 Maven 设置后，将 viewer 引入您的代码中：

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## 如何将归档渲染为单页 HTML

### 步骤 1：定义输出目录
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### 步骤 2：设置单页输出的文件名
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### 步骤 3：初始化 Viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### 步骤 4：配置渲染选项（嵌入资源 HTML）
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### 步骤 5：渲染为单页
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## 如何将归档渲染为多页 HTML 并设置每页项目数

### 步骤 1：复用输出目录
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### 步骤 2：定义多页的文件名格式
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### 步骤 3：再次初始化 Viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### 步骤 4：配置多页选项（嵌入资源 HTML）
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### 步骤 5：设置每页项目数（关键操作）
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## 实际应用

- **文档管理系统：** 添加归档预览功能，无需安装额外的查看器。  
- **Web 门户：** 为用户提供快速、无需下载的方式来浏览打包文档。  
- **协作工具：** 让团队直接在浏览器中检查共享的归档文件。  

## 性能考虑

- **资源管理：** 关注内存使用情况；对于大批量处理，可考虑调优 JVM 的垃圾回收器。  
- **批量转换归档：** 遍历归档文件列表并调用相同的渲染逻辑，以最大化吞吐量。  
- **缓存策略：** 如果同一归档被频繁访问，可将渲染后的 HTML 存入缓存。  

## 常见问题

**Q: 什么是 GroupDocs.Viewer Java？**  
A: 一个多功能库，用于将文档（包括归档）渲染为 HTML、PDF 和图像等格式。

**Q: 我如何获取 GroupDocs.Viewer 的免费试用？**  
A: 访问[免费试用链接](https://releases.groupdocs.com/viewer/java/)下载并测试。

**Q: 我可以转换除归档之外的其他文档类型吗？**  
A: 可以，viewer 支持 PDF、Word、Excel 等多种格式。

**Q: 如果渲染速度慢该怎么办？**  
A: 减少每页项目数，启用流式处理，或将归档分成更小的批次处理。

**Q: 我在哪里可以获得帮助或支持？**  
A: 通过[支持论坛](https://forum.groupdocs.com/c/viewer/9)联系。

**Q: 是否可以直接在 HTML 中嵌入 CSS 和图像？**  
A: 当然——如示例所示，使用 `HtmlViewOptions.forEmbeddedResources`。

**Q: 如何批量转换一个归档文件夹？**  
A: 使用 `for` 循环遍历每个文件，对每次迭代应用相同的 `Viewer` 和 `HtmlViewOptions` 配置。

## 资源

- **文档：** 通过[GroupDocs 文档](https://docs.groupdocs.com/viewer/java/)深入了解功能。  
- **API 参考：** 在[GroupDocs API](https://reference.groupdocs.com/viewer/java/)查看完整 API。  
- **下载：** 从[下载页面](https://releases.groupdocs.com/viewer/java/)获取最新二进制文件。  
- **购买与授权：** 在[购买页面](https://purchase.groupdocs.com/buy)查看选项。  
- **支持与社区：** 在[GroupDocs 论坛](https://forum.groupdocs.com/c/viewer/9)加入讨论。

---

**最后更新：** 2026-02-23  
**测试版本：** GroupDocs.Viewer 25.2  
**作者：** GroupDocs