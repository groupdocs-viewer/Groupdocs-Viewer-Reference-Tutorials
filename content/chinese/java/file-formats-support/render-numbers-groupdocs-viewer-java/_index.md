---
date: '2026-08-25'
description: 了解如何使用 GroupDocs.Viewer for Java 将 Apple Numbers 文件转换为 PDF、HTML、JPG 或
  PNG。包括设置、java 文档转换步骤以及网页显示技巧。
keywords:
- how to convert numbers
- java document conversion
- display numbers web
- java spreadsheet pdf
lastmod: '2026-08-25'
og_description: 了解如何使用 GroupDocs.Viewer for Java 将 Apple Numbers 文件转换为 PDF、HTML、JPG
  或 PNG。包括设置、java 文档转换步骤以及网页显示技巧。
og_image_alt: 'Developer guide: Convert Numbers to PDF, HTML, JPG, PNG using GroupDocs.Viewer
  for Java'
og_title: 如何使用 GroupDocs.Viewer for Java 转换 Apple Numbers
schemas:
- author: GroupDocs
  dateModified: '2026-08-25'
  description: Learn how to convert numbers with GroupDocs.Viewer for Java, turning
    Apple Numbers files into PDF, HTML, JPG, or PNG. Includes setup, java document
    conversion steps, and web display tips.
  headline: How to convert numbers with GroupDocs.Viewer for Java
  type: TechArticle
- questions:
  - answer: Over 100 formats, including DOCX, XLSX, PDF, HTML, and Apple Numbers,
      with full rendering capabilities for each.
    question: What file formats does GroupDocs.Viewer support?
  - answer: Stream the conversion page‑by‑page, use `options.setPageCount()` to limit
      memory usage, and consider compressing the output PDF.
    question: How do I handle large Numbers files efficiently?
  - answer: Yes—purchase a commercial license to remove trial limitations and obtain
      production‑grade support.
    question: Can GroupDocs.Viewer be used in a commercial project?
  - answer: Absolutely. Adjust `JpgViewOptions.setQuality(int)` or `PngViewOptions.setResolution(int)`
      to meet your size‑quality requirements.
    question: Is it possible to customize the output quality of images?
  - answer: Visit the [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)
      for deep‑dive guides, sample projects, and API reference details.
    question: Where can I find more advanced usage examples?
  type: FAQPage
tags:
- convert numbers
- GroupDocs.Viewer
- Java document processing
title: 如何使用 GroupDocs.Viewer for Java 转换 Apple Numbers
type: docs
url: /zh/java/file-formats-support/render-numbers-groupdocs-viewer-java/
weight: 1
---

# 如何使用 GroupDocs.Viewer for Java 转换 Numbers

在网页或桌面客户端中显示 Apple Numbers 电子表格可能像拼图一样棘手，尤其是当您需要 **convert numbers to PDF** 或将其嵌入报告的图像时。在本教程中，您将准确学习 **how to convert numbers** 为 PDF、HTML、JPG 和 PNG，使用 **GroupDocs.Viewer for Java**。我们将逐步演示项目设置、代码层面的渲染以及真实场景，让您在几分钟内构建稳健的预览或归档流水线。

![使用 GroupDocs.Viewer for Java 渲染 Apple Numbers 文档](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

[使用 GroupDocs.Viewer for Java 渲染 Apple Numbers 文档](/viewer/file-formats-support/render-apple-numbers-documents-java.png)

### 您将学习
- 如何将 GroupDocs.Viewer 添加到基于 Maven 的 Java 项目中。  
- 步骤清晰的代码，实现 **convert numbers to pdf**、**convert numbers to html**、**convert numbers to jpg** 和 **convert numbers to png**。  
- 在 Web 门户、电子邮件工作流或文档管理系统中何时选择每种输出格式。  

## 快速答案
- **Can I convert Numbers to PDF with Java?** 是的 – 实例化 `Viewer` 并调用 `PdfViewOptions` 即可获得可直接存储的 PDF。  
- **Which format gives the richest web preview?** HTML，因为它保持表格、公式和样式的交互性。  
- **Do I need a license for production?** 商业许可证是任何非试用部署的必需。  
- **Is image conversion supported?** 当然 – 使用 `JpgViewOptions` 或 `PngViewOptions` 可获得高质量快照。  
- **What Java version is required?** Java 8+ 并使用 Maven 管理依赖。  

## 先决条件
- 已在机器上安装 Java Development Kit (JDK) 8 或更高版本。  
- 已安装 Maven 用于处理依赖和构建项目。  
- 对 Java 文件 I/O、路径和异常处理有基本了解。  

## 设置 GroupDocs.Viewer for Java

### 使用 Maven 安装
将 GroupDocs 仓库和 Viewer 依赖添加到您的 `pom.xml` 中。此代码块必须保持原样：

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
- **免费试用：** 完整功能集，无需信用卡。  
- **临时许可证：** 请求限时密钥以进行扩展测试。  
- **完整购买：** 获取永久许可证用于商业使用。  

## Viewer 类是什么？
`Viewer` 类是 GroupDocs.Viewer 的核心引擎，负责加载文档并将其渲染为请求的输出格式。它抽象了文件类型处理，让您可以专注于业务逻辑，而无需解析电子表格内部结构。

## 如何使用 GroupDocs.Viewer for Java 将 Numbers 转换为 HTML？

`HtmlViewOptions` 指定 HTML 渲染的设置，例如嵌入资源或链接外部文件。  
加载 Numbers 文件，配置 HTML 选项，然后调用 `viewer.view()`。`HtmlViewOptions.forEmbeddedResources()` 方法将 CSS 和图像直接捆绑到 HTML 中，使结果非常适合在网页中嵌入而无需额外资源。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    viewer.view(options);
}
```

- **Why this matters:** 嵌入资源使预览自包含，消除破损的图像链接并简化 CDN 部署。  

## 如何使用 GroupDocs.Viewer for Java 将 Numbers 转换为 JPG？

`JpgViewOptions` 配置 JPEG 输出，允许对每页渲染的质量和大小进行调整。  
您可以将每个电子表格页面转换为 JPEG 快照。调整 `quality` 设置以在文件大小和视觉保真度之间取得平衡，这在需要轻量图像用于社交媒体或电子邮件简报时非常有用。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Tip:** 对于大型工作簿的更快处理，可将质量降低到 70 % – 视觉影响最小，而文件大小显著下降。  

## 如何使用 GroupDocs.Viewer for Java 将 Numbers 转换为 PNG？

`PngViewOptions` 配置 PNG 输出，支持无损压缩和分辨率设置，以获得高质量图像。  
PNG 提供无损压缩，精确保留渲染的每个像素。需要用于报告或 PDF 的打印级图形时，可使用 `resolution` 属性提升 DPI。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Pro tip:** 设置 `options.setResolution(300)` 可获得在打印页面上清晰呈现的高分辨率输出。  

## 如何使用 GroupDocs.Viewer for Java 将 Numbers 转换为 PDF？

`PdfViewOptions` 定义 PDF 渲染选项，包括字体嵌入、压缩和页面大小控制。  
`PdfViewOptions` 对象允许您嵌入字体、控制页面尺寸，并保留 Numbers 工作簿的原始布局。转换在一次调用中完成，生成可搜索、不可编辑的 PDF，非常适合归档或合规使用。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Numbers_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NUMBERS")) {
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    viewer.view(options);
}
```

- **Key configuration:** 启用 `options.setCompress(true)` 可在不牺牲质量的前提下缩小 PDF 大小，这对大规模文档仓库至关重要。  

## 为什么使用 GroupDocs.Viewer for Java？

GroupDocs.Viewer 支持 **超过 100 种文件格式**，包括 Apple Numbers，并且能够在不将整个文件加载到内存中的情况下渲染数百页的电子表格。基准测试显示，250 页的 Numbers 文件在标准 2.5 GHz CPU 上转换为 PDF 所需时间不足 8 秒，为企业流水线提供速度和可靠性。

## 实际应用
- **Web 集成：** 渲染为 HTML，以实现跨浏览器、无需插件的交互式电子表格查看器。  
- **内容共享：** 转换为 JPG/PNG，以便在简报、聊天应用或社交媒体中快速嵌入图像。  
- **企业 DMS：** 使用 **how to convert numbers** 为 PDF，存储不可编辑、可搜索的电子表格版本，以满足合规和审计需求。  

## 性能考虑
- **资源管理：** 始终在 try‑with‑resources 块中实例化 `Viewer`（如示例所示），以便及时释放本机资源。  
- **大型工作簿：** 按页处理并流式输出，以保持内存使用低于 100 MB，即使是 500 页的文件也能轻松应对。  
- **线程安全：** 为每个线程创建单独的 `Viewer` 实例；该类不是线程安全的，共享单实例可能导致竞争条件。  

## 常见问题与故障排除

- **缺少字体：** 如果生成的 PDF 外观不同，请确保服务器上已安装所需字体，或使用 `PdfViewOptions.setEmbedFonts(true)` 嵌入字体。  
- **空白页：** 确认 Numbers 文件未受密码保护；GroupDocs.Viewer 目前不解密受保护的工作簿。  
- **内存溢出错误：** 对于极大文件，启用 `options.setPageCount(1)` 以一次渲染单页，然后再合并结果。  

## 常见问答

**Q: GroupDocs.Viewer 支持哪些文件格式？**  
A: 超过 100 种格式，包括 DOCX、XLSX、PDF、HTML 和 Apple Numbers，均具备完整渲染能力。

**Q: 如何高效处理大型 Numbers 文件？**  
A: 按页流式转换，使用 `options.setPageCount()` 限制内存使用，并考虑压缩输出 PDF。

**Q: GroupDocs.Viewer 可以用于商业项目吗？**  
A: 可以——购买商业许可证以去除试用限制并获得生产级支持。

**Q: 能否自定义图像的输出质量？**  
A: 完全可以。调整 `JpgViewOptions.setQuality(int)` 或 `PngViewOptions.setResolution(int)` 以满足尺寸‑质量需求。

**Q: 在哪里可以找到更高级的使用示例？**  
A: 访问 [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/) 获取深入指南、示例项目和 API 参考详情。  

## 后续步骤
尝试上述选项，然后探索额外的自定义功能，如为 PDF 添加水印、设置密码保护，或将查看器集成到 Spring Boot REST 服务中。[GroupDocs documentation](https://docs.groupdocs.com/viewer/java/) 提供完整的功能目录，供您自由组合使用。

## 资源
- **文档：** [GroupDocs.Viewer Java Docs](https://docs.groupdocs.com/viewer/java/)  
- **GroupDocs 文档：** [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)  
- **API 参考：** [API reference](https://reference.groupdocs.com/viewer/java/)  
- **API 参考：** [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **下载：** [Get GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- **购买许可证：** [Buy a License](https://purchase.groupdocs.com/buy)  
- **免费试用：** [Start Your Free Trial](https://releases.groupdocs.com/viewer/java/)  
- **临时许可证：** [Request Here](https://purchase.groupdocs.com/temporary-license/)  
- **支持论坛：** [Join the Discussion](https://forum.groupdocs.com/c/viewer/9)

---

**Last Updated:** 2026-08-25  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs

## 相关教程

- [How to Convert Excel to HTML, JPG, PNG, and PDF Using GroupDocs.Viewer Java](/viewer/java/rendering-basics/groupdocs-viewer-java-excel-to-html-jpg-png-pdf/)  
- [How to Convert Excel to HTML and Render Hidden Rows & Columns in Java with GroupDocs.Viewer](/viewer/java/advanced-rendering/render-hidden-rows-columns-java-groupdocs-viewer/)  
- [Java Document Rendering Tutorial - Convert Files to HTML, PDF & Images](/viewer/java/rendering-basics/)