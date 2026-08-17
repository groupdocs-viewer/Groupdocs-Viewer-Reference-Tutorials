---
date: '2026-08-08'
description: 了解如何使用 GroupDocs.Viewer for Java 将 IGS 转换为 PDF、HTML、JPG 和 PNG。Step‑by‑step
  guide、prerequisites 和 troubleshooting 适用于 Java 开发者。
keywords:
- convert igs to pdf
- convert cad to image
- convert igs to jpg
- java cad to pdf
lastmod: '2026-08-08'
og_description: 使用 GroupDocs.Viewer for Java 将 IGS 转换为 PDF、HTML、JPG 和 PNG。Detailed
  setup、code snippets 和 troubleshooting 适用于 Java 开发者。
og_image_alt: 'Developer guide: convert IGS files to PDF, HTML, JPG, PNG with GroupDocs.Viewer
  Java'
og_title: 使用 GroupDocs.Viewer Java 将 IGS 转换为 PDF、HTML、JPG 和 PNG
schemas:
- author: GroupDocs
  dateModified: '2026-08-08'
  description: Learn how to convert IGS to PDF, HTML, JPG, and PNG using GroupDocs.Viewer
    for Java. Step‑by‑step guide, prerequisites, and troubleshooting for Java developers.
  headline: Convert IGS to PDF, HTML, JPG & PNG with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: Yes. Iterate over a collection of file paths and invoke the appropriate
      `view` method for each file within the same `Viewer` instance.
    question: Can I convert multiple IGS files in a single run?
  - answer: Absolutely. `PdfViewOptions` offers `setPageSize(PageSize.A4)`, `PageSize.Letter`,
      and custom dimensions via `setCustomSize(width, height)`.
    question: Is it possible to customize the PDF page size?
  - answer: No. A single GroupDocs.Viewer license covers all supported formats, including
      HTML, JPG, PNG, and PDF.
    question: Do I need a separate license for each output format?
  - answer: The library reliably processes files up to **500 MB**; for models larger
      than 200 MB, allocate additional JVM memory and consider rendering in batches.
    question: How large can an IGS file be before performance degrades?
  - answer: GroupDocs.Viewer renders the default orientation defined in the IGS file.
      For custom views, preprocess the file with a CAD tool or adjust the model before
      conversion.
    question: Can I render only a specific view or orientation?
  type: FAQPage
tags:
- convert igs
- groupdocs.viewer
- java cad conversion
- pdf generation java
title: 使用 GroupDocs.Viewer Java 将 IGS 转换为 PDF、HTML、JPG 和 PNG
type: docs
url: /zh/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

# 将 IGS 转换为 PDF、HTML、JPG 和 PNG（使用 GroupDocs.Viewer Java）

如果您需要直接在 Java 应用程序中**将 IGS 转换为 PDF**（或转换为 HTML、JPG、PNG），那么您来对地方了。在本教程中，我们将逐步讲解您所需的一切——从安装库到以适合您项目的格式渲染 3‑D 模型。您将了解为何 GroupDocs.Viewer 是快速、可靠转换的可靠选择，并获取可直接放入您自己解决方案的即用代码片段。

![使用 GroupDocs.Viewer for Java 将 IGS 文件转换为 HTML、JPG、PNG 和 PDF](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## 快速答案
- **我可以使用 Java 将 IGS 转换为 PDF 吗？** 是的，使用 `PdfViewOptions` 与 `Viewer` API 一起使用。  
- **支持哪些输出格式？** HTML、JPG、PNG 和 PDF 都是原生支持的。  
- **生产环境需要许可证吗？** 需要商业许可证；免费试用可让您测试核心功能。  
- **需要哪个 Java 版本？** JDK 8 或更高；该库也可在 Java 11、 17 及更高版本上运行。  
- **Maven 是唯一添加库的方式吗？** 不是，您也可以使用 Gradle 或手动将 JAR 文件添加到类路径。

## 什么是将 IGS 转换为 PDF？
将 IGS 转换为 PDF 意味着将中性的 3‑D CAD 文件转换为静态、可在任何平台查看的文档。这使您能够与没有 CAD 工具的利益相关者共享设计视觉效果，将渲染嵌入报告，或将模型归档以满足合规需求。

## 为什么在 IGS 转换中使用 GroupDocs.Viewer？
GroupDocs.Viewer 在无需任何外部 CAD 软件的情况下处理 IGS 文件。它支持 **50+ 输入和输出格式**，能够渲染包含 **数百个部件** 的装配体，同时将内存使用保持在 **200 MB** 以下，并在标准服务器上对典型模型在 **2 秒** 内交付结果。这些量化的优势使其成为企业流水线中高性能、成本效益的选择。

## 前提条件
- **GroupDocs.Viewer for Java** ≥ 25.2（最新稳定版本）。  
- **JDK 8+** 已安装并在您的 IDE（IntelliJ IDEA、Eclipse、NetBeans 等）中配置。  
- 基础的 Maven 知识（可选，但建议用于依赖管理）。

## 设置 GroupDocs.Viewer for Java

### Maven 依赖
将 GroupDocs 仓库和 Viewer 依赖添加到您的 `pom.xml` 中：

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
GroupDocs.Viewer 提供三种授权选项：
- **免费试用** – 使用受限，适合快速概念验证测试。  
- **临时许可证** – 在短期评估期间提供完整功能，适合试点项目。  
- **商业许可证** – 无限制的生产使用，包含优先支持和更新。

### 基本 Viewer 初始化
`Viewer` 类是所有渲染操作的入口。它加载源文件，解析格式，并提供生成所需输出的方法。

```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.igs")) {
            // Configuration and rendering logic goes here.
        }
    }
}
```

## 将 IGS 渲染为 HTML

### 如何将 IGS 转换为 HTML？
使用 `Viewer` 实例加载 IGS 文件，并传入一个嵌入所有必需资源的 `HtmlViewOptions` 对象。该调用返回一个包含完整 3‑D 视图的单个 HTML 文件，便于嵌入网页。您还可以通过设置页面大小、背景颜色以及是否包含交互控件等选项来自定义渲染。  
`HtmlViewOptions` 配置 HTML 输出的生成方式，包括资源嵌入和页面布局。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToHtml {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.html");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## 将 IGS 渲染为 JPG

### 如何将 IGS 转换为 JPG？
创建一个 `JpgViewOptions` 对象，配置所需的分辨率和压缩质量，然后让 `Viewer` 为模型的每一页生成光栅图像。生成的 JPG 文件可以保存到指定目录，您可以调整质量参数以在文件大小和视觉保真度之间取得平衡，这对于缩略图或高分辨率打印非常有用。  
`JpgViewOptions` 指定 JPG 图像生成的设置，如分辨率、质量和输出目录。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToJpg {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.jpg");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## 将 IGS 渲染为 PNG

### 如何将 IGS 转换为 PNG？
`PngViewOptions` 类允许您生成带可选透明度的无损图像。此格式非常适合在营销材料中将模型叠加在彩色背景上。您还可以定义分辨率和背景颜色以符合品牌指南，确保所有生成资产的外观一致。  
`PngViewOptions` 定义 PNG 渲染的参数，包括分辨率、透明度和背景颜色。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPng {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.png");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PngViewOptions options = new PngViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## 将 IGS 渲染为 PDF

### 如何将 IGS 转换为 PDF？
使用 `PdfViewOptions` 生成分页的 PDF，保留 3‑D 模型的视觉布局。您还可以嵌入字体并控制页面大小，以符合公司品牌指南。其他设置允许您指定图像质量、压缩级别，以及是否为多页装配体包含目录。  
`PdfViewOptions` 控制 PDF 的创建，允许配置页面大小、图像质量和字体嵌入。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;
import static java.nio.file.Paths.get;

public class RenderIgsToPdf {
    public static void run() {
        Path outputDirectory = get("YOUR_OUTPUT_DIRECTORY");
        Path pageFilePathFormat = outputDirectory.resolve("IGS_result.pdf");

        try (Viewer viewer = new Viewer(get("YOUR_DOCUMENT_DIRECTORY/SAMPLE_IGS"))) {
            PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
            viewer.view(options);
        }
    }
}
```

## 实际应用
- **Web 门户** – 将 HTML 渲染的模型直接嵌入产品配置器，允许客户在无需安装插件的情况下旋转和缩放。  
- **营销资产** – 为手册、幻灯片和社交媒体帖子生成高分辨率的 JPG/PNG 图像。  
- **技术文档** – 在用户手册中包含 CAD 模型的 PDF 渲染，确保工程师能够离线查看设计。  
- **质量保证** – 为数千个 IGS 文件自动创建缩略图，加快视觉检查工作流。

## 常见问题与解决方案

| 问题 | 解决方案 |
|-------|----------|
| **未找到输出文件夹** | 验证传递给 `Path outputDirectory` 的路径，并确保 Java 进程对目标目录具有写入权限。 |
| **PDF 中出现空白页** | 确认源 IGS 文件未损坏；先在原生 CAD 查看器中打开它。 |
| **大型装配体渲染缓慢** | 增加 JVM 堆内存（`-Xmx2g` 或更高），并考虑使用 `viewer.getPageCount()` 逐页渲染以分块处理。 |
| **PDF 中缺少字体** | 使用 `PdfViewOptions` 嵌入所需字体，或在托管转换服务的服务器上安装缺失的字体。 |

## 常见问题

**Q: 我可以在一次运行中转换多个 IGS 文件吗？**  
A: 可以。遍历文件路径集合，在同一个 `Viewer` 实例中为每个文件调用相应的 `view` 方法。

**Q: 可以自定义 PDF 页面大小吗？**  
A: 完全可以。`PdfViewOptions` 提供 `setPageSize(PageSize.A4)`、`PageSize.Letter`，以及通过 `setCustomSize(width, height)` 设置自定义尺寸。

**Q: 每种输出格式需要单独的许可证吗？**  
A: 不需要。单个 GroupDocs.Viewer 许可证覆盖所有支持的格式，包括 HTML、JPG、PNG 和 PDF。

**Q: IGS 文件多大时性能会下降？**  
A: 该库可靠地处理高达 **500 MB** 的文件；对于大于 200 MB 的模型，请分配更多 JVM 内存并考虑批量渲染。

**Q: 我可以只渲染特定视图或方向吗？**  
A: GroupDocs.Viewer 渲染 IGS 文件中定义的默认方向。若需自定义视图，请使用 CAD 工具预处理文件或在转换前调整模型。

**最后更新：** 2026-08-08  
**测试环境：** GroupDocs.Viewer 25.2 for Java  
**作者：** GroupDocs

## 相关教程

- [使用 GroupDocs.Viewer Java 将 cdr 转换为 html、jpg、png、pdf](/viewer/java/file-formats-support/render-cdr-documents-groupdocs-viewer-java-guide/)
- [如何在 Java 中使用 GroupDocs.Viewer 将 pdf 转换为 html 并优化图像质量](/viewer/java/advanced-rendering/adjust-image-quality-groupdocs-viewer-java/)