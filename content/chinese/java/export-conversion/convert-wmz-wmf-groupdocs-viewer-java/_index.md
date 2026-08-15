---
date: '2026-07-19'
description: 了解如何使用 GroupDocs Viewer for Java 将 WMZ 转换为 PDF、HTML、JPG 和 PNG。针对 java
  转换矢量图形的分步指南。
keywords:
- convert wmz to pdf
- convert wmf to png
- convert wmf to jpg
- java convert vector graphics
- groupdocs viewer java
lastmod: '2026-07-19'
og_description: 使用 GroupDocs Viewer for Java 将 WMZ 转换为 PDF、HTML、JPG 和 PNG。本教程展示了高保真度的
  java 转换矢量图形的分步操作。
og_image_alt: 'Guide: Convert WMZ/WMF files to PDF, HTML, JPG, PNG using GroupDocs
  Viewer for Java'
og_title: 使用 GroupDocs Viewer for Java 将 WMZ 转换为 PDF – 快速指南
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  headline: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to convert WMZ to PDF, HTML, JPG, and PNG with GroupDocs
    Viewer for Java. Step-by-step guide for java convert vector graphics.
  name: Convert WMZ to PDF and Other Formats Using GroupDocs Viewer for Java
  steps:
  - name: '**Define the output directory** where the rendered files will be saved.'
    text: '**Define the output directory** where the rendered files will be saved.'
  - name: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
    text: '**Create a `Viewer` instance** pointing at the source WMZ/WMF file.'
  - name: '**Configure format‑specific view options** and invoke the `view` method.'
    text: '**Configure format‑specific view options** and invoke the `view` method.'
  type: HowTo
- questions:
  - answer: Yes. The PNG example works for both WMZ and WMF files; just replace `TestFiles.SAMPLE_WMZ`
      with your WMF source.
    question: Can I convert WMF to PNG using the same code?
  - answer: Absolutely. Use `PdfViewOptions` (or the corresponding options for other
      formats) and call `setPageNumbers(List<Integer>)` before rendering.
    question: Is it possible to convert only a subset of pages?
  - answer: No. A single GroupDocs Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: Vector‑to‑raster conversion is CPU‑intensive. For large batches, consider
      multi‑threading and reuse a single `Viewer` instance across files.
    question: How does “java convert vector graphics” impact performance?
  - answer: When converting WMZ/WMF to PDF, GroupDocs Viewer preserves the vector
      instructions where possible, resulting in a scalable PDF.
    question: Will the PDF retain vector quality, or is it rasterized?
  type: FAQPage
tags:
- convert wmz
- groupdocs viewer
- java document conversion
- vector graphics
- pdf generation
title: 使用 GroupDocs Viewer for Java 将 WMZ 转换为 PDF 及其他格式
type: docs
url: /zh/java/export-conversion/convert-wmz-wmf-groupdocs-viewer-java/
weight: 1
---

# 使用 GroupDocs Viewer for Java 将 WMZ 转换为 PDF 及其他格式

将 WMZ（Web Metafile）和 WMF（Windows Metafile）文件转换为更易访问的格式——尤其是 **convert WMZ to PDF**——可能比较棘手，因为这些矢量图形格式存储的是绘图指令而非像素数据。使用 **GroupDocs Viewer for Java**，您可以仅用几行代码将 WMZ/WMF 文档渲染为 HTML、JPG、PNG、**PDF** 等流行格式，同时保持原始视觉保真度。

![使用 GroupDocs.Viewer for Java 转换 WMZ/WMF 文档](/viewer/export-conversion/convert-wmz-wmf-documents.png)

[使用 GroupDocs.Viewer for Java 转换 WMZ/WMF 文档](/viewer/export-conversion/convert-wmz-wmf-documents.png)

## 快速答案
- **WMZ/WMF 可以转换为何种格式？** HTML、JPG、PNG 和 PDF 均得到完整支持。  
- **开发是否需要许可证？** 免费试用可用于测试；商业许可证可去除评估限制。  
- **需要哪个 Java 版本？** 推荐使用 Java 8 或更高版本。  
- **我可以只渲染特定页面吗？** 可以，在视图选项中指定页面范围。  
- **大文件的内存使用是否是问题？** 使用 try‑with‑resources 并仅渲染所需页面以保持低内存占用。

## 什么是 “convert WMZ to PDF”？

**Convert WMZ to PDF** 指将 WMZ 矢量文件的绘图指令嵌入 PDF 容器中，生成一种可在任何平台查看、可搜索、可打印的文档。转换会保留线条质量和形状，因此生成的 PDF 在任何设备上看起来都与原始图形完全一致。

## 为什么使用 GroupDocs Viewer for Java 转换矢量图形？

GroupDocs Viewer for Java 能以 **高保真** 处理 WMZ 和 WMF 的渲染，无论输出为 PDF、PNG 还是 HTML，都能保留矢量细节。该库可在任何带有 JDK 的平台上运行，无需原生 Windows 组件，并提供单调用 API，能够从单图标文件扩展到多页技术图纸。在基准测试中，它在标准的 4 核服务器上能够在 12 秒内处理 **超过 200 页的 WMZ 文件**。

## 前置条件

- **GroupDocs.Viewer for Java** – 核心渲染引擎。  
- Java Development Kit (JDK) 8 或更高版本。  
- IDE，如 IntelliJ IDEA 或 Eclipse（可选，但推荐）。  
- Maven（或 Gradle）用于依赖管理。  

熟悉 Java NIO (`java.nio.file.Path`) 和基本的文件 I/O 将有助于您顺利阅读示例。

## 设置 GroupDocs.Viewer for Java

`Viewer` 类是所有渲染操作的入口。它代表一个线程安全的引擎，可在多个转换之间复用。

将仓库和依赖添加到您的 `pom.xml`（或等效的 Gradle 文件）中。Maven 解析该构件后，您即可创建一个 `Viewer` 实例，用于每个转换步骤的复用。

> **许可证提示：** 使用免费试用进行评估，然后应用临时或购买的许可证以解锁全部功能。

## 实现指南

下面我们将演示四种转换场景——HTML、JPG、PNG 和 PDF。每个场景遵循相同的三步模式：

1. **定义输出目录**，用于保存渲染后的文件。  
2. **创建指向源 WMZ/WMF 文件的 `Viewer` 实例**。  
3. **配置特定格式的视图选项** 并调用 `view` 方法。

`view` 方法根据提供的选项执行渲染。

### 将 WMZ/WMF 渲染为 HTML

#### 概述
HTML 输出可让您将图形直接嵌入网页，所有资源（图像、CSS）均包含在单个文件中。

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
JPG 是一种广泛支持的栅格格式，适合快速预览或电子邮件附件。

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
PNG 支持透明度，非常适合需要与不同背景融合的图形。

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
PDF 提供一种跨平台、可搜索的文档，保留原始布局。

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

`PageStreamViewOptions` 允许将特定页面渲染为流。  
`PdfViewOptions` 配置 PDF 输出设置，如页面范围和 DPI。  
`FontSettings` 让您在源文档引用缺失字体时提供自定义字体。

| 问题 | 原因 | 解决方案 |
|-------|-------|----------|
| **OutOfMemoryError** 在大 WMZ 文件上 | Viewer 将整个文档加载到内存中 | 使用 `PageStreamViewOptions` 一次渲染单页，或增加 JVM 堆大小（`-Xmx`）。 |
| **Missing fonts** 在 PDF 中 | 源 WMZ 中未嵌入字体 | 在主机上安装所需字体，或使用 `FontSettings` 提供自定义字体。 |
| **Blank PNG output** | 输出路径不正确或写权限不足 | 确认 `outputDirectory` 存在且应用程序具有写入权限。 |
| **HTML resources not loading**（HTML 资源未加载） | 使用 `forExternalResources` 而未复制文件 | 使用 `forEmbeddedResources` 以获得自包含的 HTML 文件。 |

## 常见问答

**问：我可以使用相同的代码将 WMF 转换为 PNG 吗？**  
答：是的。PNG 示例适用于 WMZ 和 WMF 文件，只需将 `TestFiles.SAMPLE_WMZ` 替换为您的 WMF 源文件即可。

**问：是否可以仅转换部分页面？**  
答：当然。使用 `PdfViewOptions`（或其他格式对应的选项），并在渲染前调用 `setPageNumbers(List<Integer>)`。

**问：每种输出格式是否需要单独的许可证？**  
答：不需要。单一的 GroupDocs Viewer 许可证覆盖所有支持的格式，包括 HTML、JPG、PNG 和 PDF。

**问：“java convert vector graphics” 对性能有何影响？**  
答：矢量转栅格的转换耗费 CPU。对于大批量处理，考虑多线程并在文件之间复用单个 `Viewer` 实例。

**问：PDF 会保留矢量质量，还是会被栅格化？**  
答：在将 WMZ/WMF 转换为 PDF 时，GroupDocs Viewer 会在可能的情况下保留矢量指令，从而生成可缩放的 PDF。

## 结论

现在，您已经拥有使用 **GroupDocs Viewer for Java** 将 **convert WMZ to PDF** 以及其他常见格式的完整、可投入生产的指南。无论是构建实时提供图形的 Web 服务，还是将文档存档为 PDF 的工具，上述步骤都能帮助您快速、可靠地实现目标。根据项目需求，进一步探索 API 以自定义页面范围、DPI 设置或水印等功能。

---

**最后更新：** 2026-07-19  
**测试环境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs

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

## 相关教程

- [如何使用 GroupDocs.Viewer 在 Java 中将 OBJ 转换为 HTML、JPG、PNG 和 PDF](/viewer/java/export-conversion/master-obj-conversion-java-html-jpg-png-pdf/)
- [使用 GroupDocs.Viewer Java 将 IGS 转换为 PDF、HTML、JPG 和 PNG](/viewer/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/)
- [groupdocs viewer java：将文档转换为 PDF – 完整指南](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)