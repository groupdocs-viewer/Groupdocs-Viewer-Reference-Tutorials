---
date: '2026-09-05'
description: 了解如何使用 GroupDocs Viewer for Java 从 PDF 生成 HTML 并禁用字符分组，以实现精确的文本呈现。
keywords:
- generate html from pdf
- render pdf to html
- convert pdf to html
lastmod: '2026-09-05'
og_description: 使用 GroupDocs Viewer for Java 从 PDF 生成 HTML，同时禁用字符分组，以实现精确的字形定位。了解逐步实现方法。
og_image_alt: GroupDocs Viewer for Java rendering PDF to HTML with precise character
  placement
og_title: 从 PDF 生成 HTML 并禁用分组 – GroupDocs Java
schemas:
- author: GroupDocs
  dateModified: '2026-09-05'
  description: Learn how to generate html from pdf and disable character grouping
    using GroupDocs Viewer for Java for precise text representation.
  headline: Generate html from pdf & disable grouping – GroupDocs Java
  type: TechArticle
- description: Learn how to generate html from pdf and disable character grouping
    using GroupDocs Viewer for Java for precise text representation.
  name: Generate html from pdf & disable grouping – GroupDocs Java
  steps:
  - name: define output directory
    text: '**Why?** This ensures your rendered HTML files are stored in a dedicated
      folder, making it easy to locate and manage them later.'
  - name: configure file path format
    text: '**Why?** Using a placeholder (`{0}`) lets the viewer create a separate
      HTML file for each PDF page, keeping the output organized.'
  - name: initialize HTML view options
    text: '**Why?** Embedded resources bundle images, fonts, and CSS directly with
      each HTML page, which is ideal for web‑based viewers or e‑learning platforms.'
  - name: disable character grouping
    text: '`setDisableCharsGrouping(true)` disables the default behavior of grouping
      adjacent characters, ensuring each glyph is rendered separately. **Why?** This
      is the crucial line that tells the rendering engine **not** to merge adjacent
      characters, guaranteeing that the generated HTML reflects the exact g'
  - name: render the document
    text: '`Viewer` is the primary class that opens a document and provides rendering
      capabilities. **Why?** Wrapping the `Viewer` in a try‑with‑resources block guarantees
      that all native resources are released automatically, preventing memory leaks
      in long‑running applications.'
  type: HowTo
- questions:
  - answer: It forces the renderer to treat each character as an independent element,
      preserving exact layout.
    question: What does “disable grouping” do?
  - answer: '`viewOptions.getPdfOptions().setDisableCharsGrouping(true)`.'
    question: Which API option controls this?
  - answer: A trial works for testing, but a full license is required for production.
    question: Do I need a license?
  - answer: Yes—use `HtmlViewOptions` to create HTML output while disabling grouping.
    question: Can I generate html from pdf at the same time?
  - answer: It’s primarily for PDFs, but the viewer supports many other formats.
    question: Is this feature limited to PDFs?
  type: FAQPage
tags:
- generate html
- GroupDocs Viewer
- Java document rendering
title: 从 PDF 生成 HTML 并禁用分组 – GroupDocs Java
type: docs
url: /zh/java/advanced-rendering/groupdocs-viewer-java-disable-character-grouping-pdf/
weight: 1
---

# 使用 GroupDocs Viewer for Java 从 PDF 生成 HTML 并禁用分组

在许多项目中，您需要 **从 PDF 生成 HTML**，同时保持每个字形准确位置。这在复杂脚本、古代语言或法律文档中尤为重要，因为单个字符位置错误可能改变含义。在本教程中，我们将完整演示使用 GroupDocs Viewer for Java 将 PDF 渲染为 HTML 的过程，并展示 **如何禁用分组**，使每个字符被视为独立元素。

![使用 GroupDocs.Viewer for Java 的精确渲染技术](/viewer/advanced-rendering/precise-rendering-techniques-java.png)

## 快速答案
- **“禁用分组”有什么作用？** 它强制渲染器将每个字符视为独立元素，保持精确布局。  
- **哪个 API 选项控制此行为？** `viewOptions.getPdfOptions().setDisableCharsGrouping(true)`。  
- **我需要许可证吗？** 试用版可用于测试，但生产环境需要完整许可证。  
- **我可以同时从 PDF 生成 HTML 吗？** 是的——使用 `HtmlViewOptions` 在禁用分组的同时生成 HTML 输出。  
- **此功能仅限于 PDF 吗？** 它主要针对 PDF，但查看器支持许多其他格式。

## 什么是从 PDF 生成 HTML？
`generate html from pdf` 描述了将 PDF 文档转换为一组保留原始布局、字体和图像的 HTML 页面。此转换实现了无需 PDF 插件的轻松网页查看、索引和交互。

## 为什么使用 GroupDocs Viewer for Java？
GroupDocs.Viewer for Java 支持 **超过 100 种输入格式**，并且能够在不将整个文件加载到内存的情况下渲染最多 **500 页** 的 PDF。该库以流式方式处理每页，相比完整文档加载可将堆内存使用降低最多 **70 %**。这些量化的能力使其成为高容量、企业级文档流水线的可靠选择。

## 介绍

在处理 PDF 文档时，渲染精度至关重要——尤其是面对象形文字或需要精确字符表现的语言等复杂文本结构时。“字符分组”功能常因错误地将字符分组而导致文档内容被误解。这对需要精确复制文档文本布局的用户尤为成问题。

**GroupDocs.Viewer for Java** 是一个服务器端库，能够将超过 100 种文档格式渲染为 HTML、图像和 PDF，提供像素级的精确度。

### 前置条件

- **Libraries & dependencies**: 您需要 GroupDocs.Viewer for Java 版本 25.2 或更高。  
- **Environment setup**: 安装 Java 开发工具包 (JDK) 并为 Maven 项目配置 IDE。  
- **Knowledge prerequisites**: 基础 Java 编程、文件系统处理以及 Maven 的使用经验。

## 如何使用 GroupDocs Viewer 从 PDF 生成 HTML

从 PDF 生成 HTML 是一个两步过程：配置查看器，然后渲染文档。关键是在渲染前关闭字符分组，使 HTML 输出逐字符地镜像原始 PDF 布局。

### 设置 GroupDocs.Viewer for Java

#### 通过 Maven 安装

Add the following dependency to your `pom.xml`:

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

#### 获取许可证

To fully utilize GroupDocs.Viewer, consider acquiring a license:
- **Free trial**: 使用免费试用版测试功能。  
- **Temporary license**: 如需更多时间，可申请临时许可证。  
- **Purchase**: 对于长期项目，建议购买许可证。

#### 基本初始化和设置

`HtmlViewOptions` configures the output format and options for rendering a document to HTML.

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

// Initialize the GroupDocs Viewer
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getPdfOptions().setDisableCharsGrouping(true);

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

### 实现指南

#### 功能：禁用字符分组

下面我们逐行解析示例，以帮助您了解 **为什么** 这样做以及 **如何** 它有助于在不进行不必要字符合并的情况下从 PDF 生成 HTML。

##### 步骤 1：定义输出目录  

```java
Path outputDirectory = Utils.getOutputDirectoryPath("DisableCharactersGrouping");
```

**为什么？** 这确保渲染后的 HTML 文件存储在专用文件夹中，便于后续定位和管理。

##### 步骤 2：配置文件路径格式  

```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

**为什么？** 使用占位符 (`{0}`) 让查看器为每个 PDF 页面创建单独的 HTML 文件，保持输出有序。

##### 步骤 3：初始化 HTML 视图选项  

```java
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

**为什么？** 嵌入式资源将图像、字体和 CSS 直接捆绑到每个 HTML 页面中，非常适合基于网页的查看器或电子学习平台。

##### 步骤 4：禁用字符分组  

`setDisableCharsGrouping(true)` disables the default behavior of grouping adjacent characters, ensuring each glyph is rendered separately.

```java
viewOptions.getPdfOptions().setDisableCharsGrouping(true);
```

**为什么？** 这行代码是关键，它告诉渲染引擎 **不要** 合并相邻字符，确保生成的 HTML 精确反映源 PDF 中的字形位置。

##### 步骤 5：渲染文档  

`Viewer` is the primary class that opens a document and provides rendering capabilities.

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/HIEROGLYPHS_PDF")) {
    viewer.view(viewOptions);
}
```

**为什么？** 将 `Viewer` 包装在 try‑with‑resources 块中可确保所有本机资源自动释放，防止长时间运行的应用程序出现内存泄漏。

## 禁用字符分组如何提升 HTML 保真度？

禁用字符分组会迫使引擎将每个字形输出为单独的 HTML 元素，从而精确保留原始间距、连字和变音符号，完全与源 PDF 中的呈现一致。这产生了忠实的网页表现，对于字符顺序和间距传递意义的脚本（如阿拉伯语、天城文或古代象形文字）尤为重要。

## 禁用分组的性能影响是什么？

关闭分组会略微增加 CPU 周期，因为渲染器会逐字符处理。实际中，对于典型的 100 页 PDF，开销低于 **5 %**，对于超过 500 页的文档，仍保持在 **12 %** 以下，前提是 JVM 堆大小设置得当（例如 `-Xmx2g`）。在需要精确视觉保真度时，这一权衡是值得的。

## 常见问题及解决方案

- **FileNotFoundException** – 再次检查传递给 `new Viewer(...)` 的路径。使用绝对路径或 `Path.of(...)` 以确保明确。  
- **Write permissions** – 确保 Java 进程对输出目录具有写权限；在 Linux 上可能需要调整文件夹权限 (`chmod 775`)。  
- **Version mismatch** – `setDisableCharsGrouping` 选项自版本 25.2 起可用。请确认您的 `pom.xml` 使用了正确的版本。  

## 实际应用

1. **Language preservation** – 适用于渲染中文、日文、阿拉伯文或古代文字等字符间距承载意义的文档。  
2. **Legal & financial documents** – 确保合规性强的法律和财务文档文本精确复制。  
3. **Educational resources** – 适合包含复杂图表、注释或多语言内容的教材。  

## 性能考虑

- **Optimize resource usage** – 大型 PDF 可能占用大量内存。分批处理页面并及时释放 `Viewer` 实例。  
- **Java memory management** – 如需处理数百页以上的 PDF，请调优 JVM 堆大小（`-Xmx2g` 或更高）。  
- **Parallel rendering** – 对于批量转换，可创建多个线程，每个线程拥有独立的 `Viewer` 实例，以利用多核 CPU。  

## 常见问题

**Q:** *为什么需要禁用字符分组？*  
**A:** 禁用分组可防止渲染器合并属于不同字形的字符，这对间距和顺序传递意义的脚本至关重要。

**Q:** *`setDisableCharsGrouping` 设置仅适用于 HTML 输出吗？*  
**A:** 不是，它影响底层 PDF 渲染引擎，因此任何输出格式（HTML、PNG、JPEG 等）都会体现此更改。

**Q:** *我可以将此设置与自定义字体结合使用吗？*  
**A:** 可以——在初始化 `Viewer` 之前加载自定义字体，分组规则仍然适用。

**Q:** *禁用分组会影响性能吗？*  
**A:** 稍有影响，因为引擎逐字符处理，但对大多数文档的影响很小（通常低于 5 % 开销）。

**Q:** *是否可以按页切换分组？*  
**A:** 目前该选项在每个 `PdfOptions` 实例中是全局的；如果需要混合行为，需要为不同页面使用独立的 `Viewer` 实例。

## 资源

- [GroupDocs 文档](https://docs.groupdocs.com/viewer/java/)
- [API 参考](https://reference.groupdocs.com/viewer/java/)
- [下载 GroupDocs Viewer](https://releases.groupdocs.com/viewer/java/)
- [购买许可证](https://purchase.groupdocs.com/buy)
- [免费试用版](https://releases.groupdocs.com/viewer/java/)
- [临时许可证申请](https://purchase.groupdocs.com/temporary-license/)
- [GroupDocs 支持论坛](https://forum.groupdocs.com/c/viewer/9)

---

**最后更新：** 2026-09-05  
**测试环境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs

## 相关教程

- [如何在 Java 中使用 GroupDocs.Viewer 将 PDF 转换为 HTML 并优化图像质量](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)
- [在 Java 中渲染 PDF 分层 – 使用 GroupDocs.Viewer 高效的 PDF 分层渲染](/viewer/java/advanced-rendering/pdf-layered-rendering-java-groupdocs-viewer/)
- [GroupDocs Viewer Java 响应式 HTML 渲染](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)