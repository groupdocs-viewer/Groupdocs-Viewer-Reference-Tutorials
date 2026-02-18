---
date: '2026-02-18'
description: 了解如何使用 GroupDocs Viewer for Java 将 WMZ 和 WMF 文件转换为 PDF、HTML、JPG 和 PNG。本指南涵盖
  GroupDocs Viewer Java 以及 Java 转换矢量图形。
keywords:
- convert WMZ/WMF documents
- GroupDocs Viewer for Java
- rendering formats
title: 如何使用 GroupDocs Viewer for Java 将 WMZ 转换为 PDF 及其他格式
type: docs
url: /zh/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

# 如何使用 GroupDocs Viewer for Java 将 WMZ 转换为 PDF 及其他格式

将 WMZ（Web Metafile）和 WMF（Windows Metafile）文件转换为更易访问的格式——尤其是 **convert WMZ to PDF**——可能比较棘手，因为这些矢量图形格式存储的是绘图指令而非像素数据。使用 **GroupDocs Viewer for Java**，您可以仅用几行代码将 WMZ/WMF 文档渲染为 HTML、JPG、PNG、**PDF** 以及其他流行格式。

![使用 GroupDocs.Viewer for Java 转换 WMZ/WMF 文档](/viewer/export-conversion/convert-wmz-wmf-documents.png)

在本教程中，您将学习如何设置库、将 WMZ/WMF 文件渲染为所需的输出，并处理常见的陷阱。完成后，您就能将 **groupdocs viewer java** 集成到您的 Java 应用程序中，快速可靠地 **java convert vector graphics**。

## 快速答案
- **WMZ/WMF 可以转换为哪些格式？** 完全支持 HTML、JPG、PNG 和 PDF。  
- **开发是否需要许可证？** 免费试用可用于测试；商业许可证可去除评估限制。  
- **需要哪个 Java 版本？** 推荐使用 Java 8 或更高版本。  
- **我可以只渲染特定页面吗？** 可以，您可以在视图选项中指定页面范围。  
- **大文件的内存使用是否是个问题？** 使用 try‑with‑resources 并仅渲染所需页面以保持低内存占用。

## 什么是 “convert WMZ to PDF”？
将 WMZ 转换为 PDF 意味着将基于矢量的 WMZ 文件进行光栅化（或保留其矢量数据）并嵌入 PDF 容器中。PDF 可在任何平台上查看、搜索和打印，非常适合归档和共享 WMZ 图形。

## 为什么使用 GroupDocs Viewer for Java 来转换矢量图形？
- **高保真**：库能够保留原始绘图质量，无论输出为 PDF 还是 PNG。  
- **零外部依赖**：无需本地 Windows 库；只要有 JDK，任何平台都能运行。  
- **简洁 API**：一个 `Viewer` 实例和一次 `view` 调用即可完成整个转换。  
- **可扩展**：对单页图标和多页技术图纸同样适用。

## 前置条件

### 必需的库
- **GroupDocs.Viewer for Java** – 核心渲染引擎。  
- Java Development Kit (JDK) 8+。

### 环境设置
- IDE，例如 IntelliJ IDEA 或 Eclipse。  
- Maven 用于依赖管理（如果喜欢也可以使用 Gradle）。

### 知识前提
- 熟悉 Java 文件 I/O（`java.nio.file.Path`）。  
- 基本了解文档查看器如何渲染内容。

## 设置 GroupDocs.Viewer for Java

将仓库和依赖添加到您的 `pom.xml` 中：

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

> **许可证提示：** 使用免费试用进行评估，然后应用临时或购买的许可证以解锁全部功能。

依赖解析后，您可以创建一个 `Viewer` 实例，该实例将在每个转换步骤中重复使用。

## 实施指南

我们将演示四种转换场景：HTML、JPG、PNG 和 PDF。每个示例遵循相同的模式——定义输出路径、使用源 WMZ 文件实例化 `Viewer`、配置相应的视图选项，然后调用 `view`。

### 将 WMZ/WMF 渲染为 HTML

#### 概述
HTML 输出允许您将图形直接嵌入网页，所有资源（图像、CSS）都包含在单个文件中。

**步骤 1：定义输出目录路径**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.html");
```

**步骤 2：初始化 Viewer 并渲染为 HTML**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    // Create options that embed all resources inside the HTML file
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    // Perform the rendering
    viewer.view(options);
}
```

### 将 WMZ/WMF 渲染为 JPG

#### 概述
JPG 是一种广泛支持的光栅格式，适合快速预览或电子邮件附件。

**步骤 1：定义输出目录路径**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.jpg");
```

**步骤 2：初始化 Viewer 并渲染为 JPG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### 将 WMZ/WMF 渲染为 PNG

#### 概述
PNG 支持透明度，非常适合需要与不同背景混合的图形。

**步骤 1：定义输出目录路径**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.png");
```

**步骤 2：初始化 Viewer 并渲染为 PNG**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### 将 WMZ/WMF 渲染为 PDF

#### 概述
PDF 提供了一个跨平台、可搜索的文档，保留原始布局。

**步骤 1：定义输出目录路径**

```java
Path outputDirectory = Utils.getOutputDirectoryPath("RenderingWmzAndWmf");
Path pageFilePathFormat = outputDirectory.resolve("wmz_result.pdf");
```

**步骤 2：初始化 Viewer 并渲染为 PDF**

```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_WMZ)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## 常见问题及解决方案

| 问题 | 原因 | 解决方案 |
|------|------|----------|
| **OutOfMemoryError** 在大型 WMZ 文件上 | Viewer 将整个文档加载到内存中 | 使用 `PageStreamViewOptions` 一次渲染一页，或增加 JVM 堆大小（`-Xmx`）。 |
| **PDF 中缺少字体** | 源 WMZ 中未嵌入字体 | 在主机上安装所需字体，或使用 `FontSettings` 提供自定义字体。 |
| **PNG 输出为空白** | 输出路径不正确或写权限不足 | 确认 `outputDirectory` 存在且应用程序具有写入权限。 |
| **HTML 资源未加载** | 使用 `forExternalResources` 而未复制文件 | 使用 `forEmbeddedResources` 以获得自包含的 HTML 文件。 |

## 常见问答

**问：我可以使用相同的代码将 WMF 转换为 PNG 吗？**  
**答：** 可以。PNG 示例适用于 WMZ 和 WMF 文件，只需将 `TestFiles.SAMPLE_WMZ` 替换为您的 WMF 源文件。

**问：是否可以只转换部分页面？**  
**答：** 当然。使用 `PdfViewOptions`（或其他格式对应的选项），并在渲染前调用 `setPageNumbers(List<Integer>)`。

**问：每种输出格式需要单独的许可证吗？**  
**答：** 不需要。单一的 GroupDocs Viewer 许可证覆盖所有支持的格式，包括 HTML、JPG、PNG 和 PDF。

**问：“java convert vector graphics” 对性能有何影响？**  
**答：** 矢量转光栅的转换会消耗大量 CPU。对于大批量处理，考虑使用多线程并在文件之间复用同一个 `Viewer` 实例。

**问：PDF 会保留矢量质量，还是会被光栅化？**  
**答：** 将 WMZ/WMF 转换为 PDF 时，GroupDocs Viewer 会在可能的情况下保留矢量指令，从而生成可缩放的 PDF。

## 结论

现在，您已经拥有一份完整的、可用于生产环境的指南，使用 **GroupDocs Viewer for Java** 将 **convert WMZ to PDF** 以及其他常见格式进行转换。无论您是构建即时提供图形的 Web 服务，还是用于将文档存储为 PDF 的归档工具，上述步骤都能帮助您快速实现目标。

---

**最后更新：** 2026-02-18  
**测试版本：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs