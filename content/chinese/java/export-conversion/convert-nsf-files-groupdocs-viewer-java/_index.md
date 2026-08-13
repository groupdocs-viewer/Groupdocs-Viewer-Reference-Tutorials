---
date: '2026-05-26'
description: 了解如何使用 GroupDocs.Viewer for Java 将 nsf 转换为 pdf 以及其他格式（HTML、JPG、PNG）。分步指南，附有最佳实践技巧。
keywords:
- convert nsf to pdf
- how to convert nsf
- java convert lotus notes
schemas:
- author: GroupDocs
  dateModified: '2026-05-26'
  description: Learn how to convert nsf to pdf and other formats (HTML, JPG, PNG)
    using GroupDocs.Viewer for Java. Step‑by‑step guide with best‑practice tips.
  headline: convert nsf to pdf with GroupDocs.Viewer for Java
  type: TechArticle
- description: Learn how to convert nsf to pdf and other formats (HTML, JPG, PNG)
    using GroupDocs.Viewer for Java. Step‑by‑step guide with best‑practice tips.
  name: convert nsf to pdf with GroupDocs.Viewer for Java
  steps:
  - name: '**Web‑Based Document Sharing:** Convert NSF to HTML for instant in‑browser
      viewing without installing Notes.'
    text: '**Web‑Based Document Sharing:** Convert NSF to HTML for instant in‑browser
      viewing without installing Notes.'
  - name: '**Image Archiving:** Store page‑by‑page JPG/PNG snapshots for thumbnail
      galleries or OCR pipelines.'
    text: '**Image Archiving:** Store page‑by‑page JPG/PNG snapshots for thumbnail
      galleries or OCR pipelines.'
  - name: '**Universal Access:** Use PDF conversion to provide a single, secure file
      that can be opened on any device, meeting compliance requirements.'
    text: '**Universal Access:** Use PDF conversion to provide a single, secure file
      that can be opened on any device, meeting compliance requirements.'
  type: HowTo
- questions:
  - answer: '`PdfViewOptions` preserves most annotations automatically; just render
      the document with these options and the resulting PDF mirrors the original layout.'
    question: How do I convert an NSF file to PDF without losing annotations?
  - answer: Yes. Provide credentials through `LoadOptions` before creating the `Viewer`
      instance.
    question: Can I convert password‑protected NSF files?
  - answer: JDK 11 or newer offers improved garbage collection and concurrency, which
      speeds up batch conversions.
    question: What Java version gives the best performance?
  - answer: Configure `JpgViewOptions.setResolution(int dpi)` or `PngViewOptions.setResolution(int
      dpi)` before calling `viewer.view(options)`.
    question: Is it possible to set a custom DPI for JPG/PNG output?
  - answer: Yes. Use the `Stream` overload of the view options to write the result
      straight to `HttpServletResponse.getOutputStream()`.
    question: Does GroupDocs.Viewer support streaming the output directly to an HTTP
      response?
  type: FAQPage
title: 使用 GroupDocs.Viewer for Java 将 nsf 转换为 pdf
type: docs
url: /zh/java/export-conversion/convert-nsf-files-groupdocs-viewer-java/
weight: 1
---

# 使用 GroupDocs.Viewer for Java 将 NSF 文件转换为多种格式

在本完整指南中，您将学习 **如何将 nsf 转换为 pdf**，以及使用 GroupDocs.Viewer for Java 将 NSF 文件渲染为 HTML、JPG 和 PNG。无论是需要归档 Lotus Notes 数据库、在浏览器中显示，还是生成图像预览，本教程都会一步步带您完成——从环境搭建到代码细节——让您在几分钟内实现转换。

![使用 GroupDocs.Viewer for Java 将 NSF 文件转换为 HTML、JPG、PNG 和 PDF](/viewer/export-conversion/convert-nsf-files-to-html-jpg-png-pdf-java.png)
[使用 GroupDocs.Viewer for Java 将 NSF 文件转换为 HTML、JPG、PNG 和 PDF](/viewer/export-conversion/convert-nsf-files-to-html-jpg-png-pdf-java.png)

## 快速答案
- **主要使用场景是什么？** 将 NSF 文件渲染为 PDF、HTML、JPG 或 PNG，以用于网页、归档或共享。  
- **哪个库负责转换？** GroupDocs.Viewer for Java。  
- **我需要许可证吗？** 提供免费试用版；生产环境需要完整许可证。  
- **需要哪个 Java 版本？** JDK 8 或更高版本。  
- **我可以批量处理多个 NSF 文件吗？** 可以——将渲染逻辑放入循环，并使用 try‑with‑resources 管理资源。

## 什么是“convert nsf to pdf”？

将 NSF（Lotus Notes 数据库）文件转换为 PDF 可生成静态、通用可读的文档，保留原始布局、字体和图形，无需 Notes 客户端。该格式非常适合法律归档、安全分发和长期存储，因为 PDF 文件可在任何操作系统或设备上打开。

## 为什么将 NSF 转换为 PDF 及其他格式？

将 NSF 文件转换为 PDF、HTML、JPG 或 PNG 可实现跨平台访问，保持视觉保真度，并能够无缝集成到现代 Web 和移动应用中。PDF 保持精确的页面布局，HTML 提供即时的浏览器内预览，JPG/PNG 则提供高分辨率的图像快照，适用于缩略图或嵌入。

## 前置条件

在开始之前，请确保您拥有：

- **Java Development Kit (JDK) 8+** – 推荐使用 JDK 11 或更高版本，以获得更好的垃圾回收性能。  
- **Maven** – 用于依赖管理。  
- **GroupDocs.Viewer for Java** – 试用版或正式授权版。  
- 对 Java 文件 I/O 和 Maven 项目结构有基本了解。

## 设置 GroupDocs.Viewer for Java

### Maven 配置

在 `pom.xml` 中添加 GroupDocs.Viewer 依赖。这将自动拉取所有必需的二进制文件和传递依赖。

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

要解锁全部功能，您可以：

- **免费试用：** 在没有许可证密钥的情况下评估核心功能。  
- **临时许可证：** 申请限时密钥用于测试。  
- **正式购买：** 获取生产许可证，实现无限制使用。

### 基本初始化

`Viewer` 是将文档渲染为所需输出格式的核心类。请在 try‑with‑resources 块中使用许可证和文件路径初始化，以确保正确释放资源。

```java
import com.groupdocs.viewer.Viewer;

public class InitializeViewer {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF")) {
            // Viewer is ready for use.
        }
    }
}
```

## 如何将 NSF 转换为 PDF

要将 NSF 文档转换为 PDF，首先创建指向源文件的 `Viewer` 实例。然后配置 `PdfViewOptions`，定义页面尺寸、压缩级别以及是否嵌入字体等输出特性。最后调用 `viewer.view(pdfOptions)`，即可将整个文档渲染为单个 PDF 文件，准备分发。

`PdfViewOptions` 指定 PDF 特有的设置，如页面尺寸和压缩。

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result.pdf");
```
```java
import com.groupdocs.viewer.options.PdfViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);  // Convert to PDF.
}
```

## 将 NSF 渲染为 HTML

### 概述

将 NSF 文档转换为自包含的 HTML 页面，嵌入图像和 CSS，以实现准确的屏幕呈现。

### 步骤指南

#### 1. 设置输出目录和文件路径

定义保存 HTML 文件的文件夹。

```java
import java.nio.file.Path;
import java.nio.file.Paths;

Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("NSF_result.html");
```

#### 2. 配置加载选项

`LoadOptions` 允许您微调资源加载，例如为外部资产设置超时时间。

```java
import com.groupdocs.viewer.options.LoadOptions;

LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);  // Set timeout for loading resources.
```

#### 3. 初始化 Viewer 并渲染

`Viewer` 处理 NSF 并将 HTML 文件写入目标目录。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);  // Render the document to HTML.
}
```

## 将 NSF 渲染为 JPG

### 概述

从 NSF 文档的每一页生成高质量 JPG 图像，适用于预览或图像中心工作流的嵌入。

#### 1. 定义输出路径

指定类似 `output_page_{0}.jpg` 的命名模式，其中 `{0}` 为页码。

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result_{0}.jpg");
```

#### 2. 配置并渲染

`JpgViewOptions` 定义 JPEG 图像输出的设置，包括分辨率和质量。创建 `JpgViewOptions`，设置所需 DPI，然后调用 `viewer.view(options)`。

```java
import com.groupdocs.viewer.options.JpgViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);  // Render to JPG.
}
```

## 将 NSF 渲染为 PNG

### 概述

生成无损 PNG 图像，保留原始 NSF 页面中的每一个细节。

#### 1. 设置输出路径

使用模板如 `nsf_page_{0}.png` 实现自动分页。

```java
Path pageFilePathFormat = outputDirectory.resolve("NSF_result_{0}.png");
```

#### 2. 渲染文档

`PngViewOptions` 配置 PNG 输出参数，如分辨率和色深。配置 `PngViewOptions`（例如 `setResolution(300)`），随后渲染。

```java
import com.groupdocs.viewer.options.PngViewOptions;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_NSF", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);  // Convert to PNG.
}
```

## 实际应用

1. **基于 Web 的文档共享：** 将 NSF 转换为 HTML，实现无需安装 Notes 的即时浏览器预览。  
2. **图像归档：** 将页面逐页的 JPG/PNG 快照存储用于缩略图库或 OCR 流程。  
3. **通用访问：** 使用 PDF 转换提供单一安全文件，可在任何设备上打开，满足合规要求。

## 性能考虑

- **资源加载：** 根据网络延迟调整 `setResourceLoadingTimeout`，避免卡顿。  
- **内存管理：** 对 `Viewer` 实例使用 try‑with‑resources，可自动释放本机资源。  
- **批量处理：** 对大批量文件，可顺序或并行流处理，监控堆内存使用，确保不超出 JVM 限制。

## 常见问题解答

**转换 NSF 文档的最佳格式是什么？**  
- 取决于下游使用场景：Web 门户使用 HTML，通用分发使用 PDF，图像工作流使用 JPG/PNG。

**如何高效处理大型 NSF 文件？**  
- 调整 `LoadOptions`（如增大 `setResourceLoadingTimeout`），将文件分批处理，并在可能的情况下复用单个 `Viewer` 实例。

**我可以自定义图像格式的输出质量吗？**  
- 可以。在渲染前通过 `JpgViewOptions` 或 `PngViewOptions` 设置 DPI、压缩级别和色深。

**如果转换失败，我该怎么办？**  
- 检查文件路径，确认 NSF 文件未损坏，并查阅 GroupDocs.Viewer 日志获取详细错误码。升级到最新库版本通常能解决兼容性问题。

**是否支持批量转换？**  
- 完全支持。将渲染逻辑放入 `for` 循环或 Java Stream，即可自动处理多个 NSF 文件。

## 常见问答

**如何在不丢失注释的情况下将 NSF 文件转换为 PDF？**  
A: `PdfViewOptions` 会自动保留大多数注释；只需使用这些选项渲染，生成的 PDF 将忠实呈现原始布局。

**我可以转换受密码保护的 NSF 文件吗？**  
A: 可以。在创建 `Viewer` 实例之前，通过 `LoadOptions` 提供凭证即可。

**哪个 Java 版本性能最佳？**  
A: JDK 11 或更高版本提供改进的垃圾回收和并发机制，可加速批量转换。

**是否可以为 JPG/PNG 输出设置自定义 DPI？**  
A: 在调用 `viewer.view(options)` 前，使用 `JpgViewOptions.setResolution(int dpi)` 或 `PngViewOptions.setResolution(int dpi)` 进行配置。

**GroupDocs.Viewer 是否支持将输出直接流式传输到 HTTP 响应？**  
A: 支持。使用视图选项的 `Stream` 重载，将结果直接写入 `HttpServletResponse.getOutputStream()`。

## 结论

您现在已经掌握了使用 GroupDocs.Viewer for Java **convert nsf to pdf** 并将 NSF 文件渲染为 HTML、JPG、PNG 的完整路线图。按照上述步骤，您可以在任何 Java 应用中集成强大的文档转换功能，实现批量作业，并以最适合用户需求的格式交付内容。进一步探索 Viewer 的水印、自定义字体和多页处理等功能，以进一步丰富您的解决方案。

---

**Last Updated:** 2026-05-26  
**Tested With:** GroupDocs.Viewer 25.2  
**Author:** GroupDocs

## 相关教程

- [groupdocs viewer java：将文档转换为 PDF – 完整指南](/viewer/java/export-conversion/convert-documents-pdf-groupdocs-viewer-java/)
- [convert odf html java – 使用 GroupDocs.Viewer for Java 将 ODF 转换为 HTML、JPG、PNG、PDF](/viewer/java/export-conversion/convert-odf-documents-groupdocs-viewer-java/)
- [使用 GroupDocs.Viewer for Java 将 PST 转换为 HTML、JPG、PNG、PDF](/viewer/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/)