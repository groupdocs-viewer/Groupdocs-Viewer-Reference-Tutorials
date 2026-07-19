---
date: '2026-07-19'
description: 了解如何使用 GroupDocs.Viewer for Java 将 PST 转换为 HTML 以及 JPG、PNG、PDF 等其他格式。本指南涵盖所有步骤和所需配置。
keywords:
- convert pst to html
- convert pst to pdf
- java convert ost
- convert pst to png
- convert pst to jpg
lastmod: '2026-07-19'
og_description: 使用 GroupDocs.Viewer for Java 快速将 PST 转换为 HTML。通过本生产就绪指南，逐步学习如何导出为
  JPG、PNG 和 PDF。
og_image_alt: 'Developer guide: Convert PST to HTML, JPG, PNG, PDF using GroupDocs
  Viewer for Java'
og_title: 使用 GroupDocs.Viewer for Java 将 PST 转换为 HTML – Fast Email Export
schemas:
- author: GroupDocs
  dateModified: '2026-07-19'
  description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  headline: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert pst to html and other formats like JPG, PNG, PDF
    using GroupDocs.Viewer for Java. This guide covers all steps and configurations
    needed.
  name: Convert PST to HTML, JPG, PNG, PDF Using GroupDocs.Viewer for Java
  steps:
  - name: Set Up Output Directory
    text: Define a folder where the HTML pages will be written. GroupDocs creates
      a sub‑folder for each email to keep assets organized.
  - name: Configure Load Options
    text: '`LoadOptions` lets you specify password handling, resource‑loading timeouts,
      and selective page rendering. Setting a timeout of 30 seconds works well for
      most server environments.'
  - name: Define HTML View Options
    text: '`HtmlViewOptions` specifies the output folder, resource handling, and optional
      CSS settings for HTML conversion.'
  - name: Initialize Viewer and Render HTML
    text: Create a `Viewer` object, pass the PST file path, and call `view` with the
      `HtmlViewOptions`. The API automatically iterates through all messages inside
      the PST and generates a tidy HTML hierarchy.
  - name: Set Up Output Directory
    text: Create a dedicated folder for JPG snapshots; each email will become one
      or more image files depending on its length.
  - name: Configure Load Options
    text: The same `LoadOptions` used for HTML can be reused here, ensuring consistent
      password handling across formats.
  - name: Define JPG View Options
    text: '`JpgViewOptions` controls image resolution, quality, and output folder
      for JPEG conversion.'
  - name: Initialize Viewer and Render JPG
    text: Use `viewer.view(jpgOptions)` to generate high‑quality JPEG files ready
      for web preview.
  - name: Set Up Output Directory
    text: PNG output is useful when you need lossless quality for archiving or OCR
      processing.
  - name: Configure Load Options
    text: No additional settings are required beyond the password and timeout configuration.
  type: HowTo
- questions:
  - answer: Use `PdfViewOptions` as shown in the PDF rendering section; the rest of
      the code remains identical.
    question: How do I **convert pst to pdf** with the same code base?
  - answer: Yes, provide the password via `LoadOptions.setPassword("yourPassword")`
      before rendering.
    question: Can GroupDocs.Viewer handle encrypted PST files?
  - answer: PNG preserves lossless quality, ideal for screenshots, while JPG offers
      smaller file sizes for email previews.
    question: What is the difference between **java convert pst** to PNG vs JPG?
  - answer: Wrap the rendering logic in a loop that iterates over a directory of PST
      files; reuse the same `Viewer` configuration for each file.
    question: Is there a way to **how to convert pst** files in bulk?
  - answer: Yes, GroupDocs.Viewer streams data and can process files up to 2 GB without
      loading the entire archive into memory.
    question: Does the API support converting PST files larger than 1 GB?
  type: FAQPage
tags:
- convert pst
- GroupDocs.Viewer
- Java document processing
- email conversion
title: 使用 GroupDocs.Viewer for Java 将 PST 转换为 HTML、JPG、PNG、PDF
type: docs
url: /zh/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# 将 PST 转换为 HTML、JPG、PNG、PDF 使用 GroupDocs.Viewer for Java

您是否希望 **convert pst to html** 或其他格式如 JPG、PNG 或 PDF？借助强大的 GroupDocs.Viewer for Java 库，这项任务简单高效。在本教程中，您将学习如何将 Outlook PST/OST 文件渲染为适合网页的 HTML、图像文件或单个 PDF，使您的电子邮件存档易于共享和归档。

![使用 GroupDocs.Viewer for Java 将 PST/OST 转换为 HTML、JPG、PNG、PDF](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

[使用 GroupDocs.Viewer for Java 将 PST/OST 转换为 HTML、JPG、PNG、PDF](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**您将学习**
- 如何在 Maven 项目中设置 GroupDocs.Viewer for Java。  
- **java convert pst** 文件转换为 HTML、JPG、PNG 和 PDF 的逐步说明。  
- 优化性能的配置技巧以及常见陷阱。

## 快速答案
- **What library handles PST conversion?** GroupDocs.Viewer for Java.  
- **Can I convert PST to PDF directly?** Yes, using `PdfViewOptions`.  
- **Is a license required for production?** A valid GroupDocs license is needed.  
- **Which Java version is supported?** JDK 8 or higher.  
- **Do I need to extract attachments manually?** No, the viewer renders them automatically.

## 什么是 GroupDocs.Viewer for Java？
GroupDocs.Viewer for Java 是一个服务器端 API，能够加载超过 100 种文档和电子邮件格式，并将其渲染为 HTML、图像或 PDF 输出，无需外部软件。它可处理高达 2 GB 的 PST 文件，同时将内存使用保持在 200 MB 以下。

## 如何使用 GroupDocs.Viewer for Java 将 pst 转换为 html？
使用 `new Viewer("source.pst")` 加载 PST 文件，配置 `HtmlViewOptions` 指向输出文件夹，然后调用 `viewer.view(htmlOptions)`。API 会提取每封邮件，保留格式、附件和元数据，并为每条消息生成单独的 HTML 页面——全部在一次方法调用中完成。

### 为什么选择 GroupDocs.Viewer？
- **高保真渲染** – 99.9 % 的电子邮件内容（包括富文本正文、表格和嵌入图像）都能准确再现。  
- **多种输出格式** – 一次 API 调用即可生成 HTML、JPG、PNG 或 PDF，覆盖 50 多种导出选项。  
- **零外部依赖** – 无需 Outlook、Exchange Server 或第三方转换器；所有操作均在 Java 运行时内部完成。

## 前提条件

- **GroupDocs.Viewer for Java** – 版本 25.2 或更高。  
- **Java Development Kit (JDK)** – 8 或更新。  
- 用于依赖管理的 Maven。  
- 基本的 Java 知识并熟悉 Maven。

## 设置 GroupDocs.Viewer for Java

`Viewer` 是 GroupDocs.Viewer for Java 的核心类，用于加载文档并将其渲染为所选格式。将 GroupDocs 仓库和依赖添加到您的 `pom.xml`：

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

### 许可证获取
- **Free trial** – explore all features without cost.  
- **Temporary license** – extend evaluation time if needed.  
- **Full license** – required for production deployments.

### 基本初始化

`Viewer` 实例轻量，可在多个文件之间复用同一个实例，以最小化对象创建开销。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

public class PSTToHTML {
    public static void main(String[] args) {
        // Initialize Viewer with a sample PST file path
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST")) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources("output_directory/PST_result.html");
            viewer.view(options);
        }
    }
}
```

## 实施指南

以下章节将逐步演示如何将 PST/OST 文件渲染为每种支持的格式。

### 将 PST/OST 文档渲染为 HTML

#### 步骤 1：设置输出目录

定义一个文件夹用于写入 HTML 页面。GroupDocs 会为每封邮件创建子文件夹，以保持资源有序。

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### 步骤 2：配置加载选项

`LoadOptions` 允许您指定密码处理、资源加载超时以及选择性页面渲染。将超时设置为 30 秒在大多数服务器环境中表现良好。

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### 步骤 3：定义 HTML 视图选项

`HtmlViewOptions` 指定输出文件夹、资源处理方式以及可选的 CSS 设置，用于 HTML 转换。

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

#### 步骤 4：初始化 Viewer 并渲染 HTML

创建 `Viewer` 对象，传入 PST 文件路径，并使用 `HtmlViewOptions` 调用 `view`。API 会自动遍历 PST 中的所有消息并生成整洁的 HTML 层次结构。

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

### 将 PST/OST 文档渲染为 JPG

#### 步骤 1：设置输出目录

为 JPG 快照创建专用文件夹；每封邮件将根据其长度生成一个或多个图像文件。

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### 步骤 2：配置加载选项

可复用用于 HTML 的相同 `LoadOptions`，确保在不同格式之间保持一致的密码处理。

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### 步骤 3：定义 JPG 视图选项

`JpgViewOptions` 控制图像分辨率、质量以及 JPEG 转换的输出文件夹。

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### 步骤 4：初始化 Viewer 并渲染 JPG

使用 `viewer.view(jpgOptions)` 生成高质量 JPEG 文件，适合网页预览。

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

### 将 PST/OST 文档渲染为 PNG

#### 步骤 1：设置输出目录

PNG 输出在需要无损质量进行归档或 OCR 处理时非常有用。

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

#### 步骤 2：配置加载选项

除密码和超时配置外，无需额外设置。

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### 步骤 3：定义 PNG 视图选项

`PngViewOptions` 允许您设置透明背景并指定无损 PNG 图像的输出文件夹。

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### 步骤 4：初始化 Viewer 并渲染 PNG

实例化 `viewer.view(pngOptions)` 以生成每封邮件的 PNG 快照。

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### 将 PST/OST 文档渲染为 PDF

#### 步骤 1：设置输出目录

每个 PST 生成单个 PDF 文件，可简化法律审查工作流并降低存储开销。

CODE_BLOCK_PLACEHOLDER_14_END

#### 步骤 2：配置加载选项

转换为 PDF 时，您可能希望启用 `setEmbedFonts(true)`，以确保在任何机器上都能保持视觉一致性。

CODE_BLOCK_PLACEHOLDER_15_END

#### 步骤 3：定义 PDF 视图选项

`PdfViewOptions` 让您选择压缩级别、嵌入字体，并设置 PDF 转换的输出文件名。

CODE_BLOCK_PLACEHOLDER_16_END

#### 步骤 4：初始化 Viewer 并渲染 PDF

创建 `PdfViewOptions`，可选地选择压缩级别，然后调用 `viewer.view(pdfOptions)`。API 会将所有邮件合并为一个可搜索的 PDF 文档。

CODE_BLOCK_PLACEHOLDER_17_END

## 实际应用

- **电子邮件归档：** 将大型 PST 存档转换为可搜索的 HTML 或 PDF，以满足合规要求。  
- **文档管理系统：** 将转换后的文件存储在仅接受 PDF、PNG 或 JPG 的系统中。  
- **协作平台：** 在 Slack 或 Teams 中以图像形式共享转换后的邮件。  
- **法律审查：** 为法院提供 PDF 版的电子邮件证据。  
- **备份策略：** 为关键消息保留轻量级的 PNG 或 JPG 快照。

## 性能考虑

- **资源管理：** 处理多个文件时复用 `Viewer` 实例以降低开销。  
- **内存调优：** 根据服务器容量调整 `loadOptions.setResourceLoadingTimeout`。  
- **异步处理：** 将转换任务卸载到后台线程，以实现响应式 UI。  

## 常见问题

**Q: 我如何使用相同的代码库 **convert pst to pdf**？**  
A: 使用 `PdfViewOptions` 如 PDF 渲染章节所示；其余代码保持不变。

**Q: GroupDocs.Viewer 能处理加密的 PST 文件吗？**  
A: 可以，在渲染前通过 `LoadOptions.setPassword("yourPassword")` 提供密码。

**Q: **java convert pst** 转换为 PNG 与 JPG 有何区别？**  
A: PNG 保持无损质量，适合截图；JPG 文件更小，适用于邮件预览。

**Q: 是否有办法批量 **how to convert pst** 文件？**  
A: 将渲染逻辑放入循环中，遍历 PST 文件目录；对每个文件复用相同的 `Viewer` 配置。

**Q: API 是否支持转换大于 1 GB 的 PST 文件？**  
A: 支持，GroupDocs.Viewer 采用流式处理，可在不将整个存档加载到内存的情况下处理高达 2 GB 的文件。

## 结论

您现在拥有一份完整的、可投入生产的指南，使用 GroupDocs.Viewer for Java 将 **convert pst to html**、JPG、PNG 和 PDF。按照上述步骤，您可以将电子邮件转换集成到任何基于 Java 的工作流中，提高可访问性并满足合规要求。

---

**Last Updated:** 2026-07-19  
**Tested With:** GroupDocs.Viewer for Java 25.2  
**Author:** GroupDocs

## 相关教程

- [使用 GroupDocs.Viewer for Java 将 NSF 转换为 PDF、HTML、JPG、PNG](/viewer/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/)
- [convert odf html java – 使用 GroupDocs.Viewer for Java 将 ODF 转换为 HTML、JPG、PNG、PDF](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [如何使用 GroupDocs.Viewer for Java 将 DOCX 转换为 HTML：分步指南](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)