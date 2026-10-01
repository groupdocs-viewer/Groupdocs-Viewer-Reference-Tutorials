---
date: '2026-09-30'
description: 了解如何在 Java 中使用 GroupDocs Viewer 将页面旋转 90 度，包括 setup、code 和 performance
  tips。
keywords:
- rotate page 90 degrees
- how to rotate pdf
- GroupDocs Viewer Java rotation
- Java document rendering
- PDF page transformation
lastmod: '2026-09-30'
og_description: 在 Java 中使用 GroupDocs Viewer 将页面旋转 90 度。Step‑by‑step guide、performance
  tips 和 real‑world use cases for developers。
og_image_alt: Illustration of rotating the first page of a document using GroupDocs
  Viewer for Java
og_title: 使用 GroupDocs Viewer for Java 将页面旋转 90 度
schemas:
- author: GroupDocs
  dateModified: '2026-09-30'
  description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  headline: Rotate page 90 degrees with GroupDocs Viewer for Java
  type: TechArticle
- description: Learn how to rotate page 90 degrees in Java using GroupDocs Viewer,
    including setup, code, and performance tips.
  name: Rotate page 90 degrees with GroupDocs Viewer for Java
  steps:
  - name: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
    text: '**Presentation adjustments** – Convert a portrait slide to landscape on
      the fly for better visual impact.'
  - name: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
    text: '**Bulk document correction** – Automate fixing of scanned PDFs that were
      captured sideways, saving hours of manual work.'
  - name: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
    text: '**Print‑ready output** – Ensure landscape graphics print correctly on portrait‑oriented
      paper without manual rotation in the printer driver.'
  type: HowTo
- questions:
  - answer: Yes—invoke `rotatePage()` for each page number you need to rotate, either
      in a loop or by chaining calls.
    question: Can I rotate multiple pages at once?
  - answer: Not directly. You would need to render the document again without the
      rotation options.
    question: Is there a way to undo the rotation after rendering?
  - answer: DOCX, PDF, PPTX, XLSX, and many other formats listed in the official documentation.
    question: Which file formats support page rotation in GroupDocs Viewer?
  - answer: Wrap the rotation logic in a loop that iterates over a collection of file
      paths, applying the same `rotatePage` configuration to each file.
    question: How can I rotate pages in a batch of documents automatically?
  - answer: Enclose the Viewer usage in a `try‑catch` block, log the exception details,
      and optionally continue processing the next file to avoid a single failure stopping
      the whole batch.
    question: What is the best practice for handling errors during rotation?
  type: FAQPage
tags:
- rotate page
- GroupDocs Viewer
- Java PDF processing
- document automation
title: 使用 GroupDocs Viewer for Java 将页面旋转 90 度
type: docs
url: /zh/java/advanced-rendering/rotate-first-page-document-groupdocs-viewer-java/
weight: 1
---


# 使用 GroupDocs Viewer for Java 将页面旋转 90 度

如果您需要在文档中**将页面旋转 90 度**——无论是 PDF、Word 文件还是电子表格——在 Java 中以编程方式完成此操作可以节省时间，消除手动错误，并且可以将此操作嵌入自动化流水线。在本高级指南中，您将学习如何使用 **GroupDocs Viewer for Java** 旋转任何受支持文档的首页，了解此功能在实际项目中的重要性，以及如何保持过程轻量且内存高效。

![使用 GroupDocs.Viewer for Java 旋转文档的首页](/viewer/advanced-rendering/rotate-the-first-page-of-a-document-java.png)

## 快速回答
- **rotate page 90 degrees** 是什么意思？它会将所选页面顺时针旋转四分之一圈。  
- **哪个库负责旋转？** GroupDocs Viewer for Java 提供 `rotatePage` 方法。  
- **我可以使用 Java 旋转 PDF 页面吗？** 是的——使用相同的 `rotatePage` 调用；它适用于 PDF、DOCX、XLSX 等。  
- **我需要许可证吗？** 免费试用可用于开发；生产环境需要付费许可证。  
- **该操作会占用大量内存吗？** 只要及时关闭 `Viewer` 实例即可；请参阅下面的性能提示。

## 什么是“rotate page 90 degrees”？
将页面旋转 90 度会将页面从纵向重新定向为横向（或反之），而不改变底层内容。这对于演示、仅横向打印的图形或纠正横向扫描的文档非常有用。旋转在渲染时应用，原始文件保持不变。

## 为什么使用 GroupDocs Viewer for Java 以编程方式旋转页面？
GroupDocs Viewer 支持 **50+ 输入和输出格式**——包括 PDF、DOCX、PPTX、XLSX 以及多种图像类型——因此您可以在无需外部转换器的情况下渲染任何文档。API 流畅、线程安全，并可在任何 Java 8+ 运行时上运行，是企业级自动化的可靠选择，能够一致地处理数十种文件类型。

## 前提条件

- GroupDocs Viewer for Java（最新版本）
- JDK 8 或更高版本
- Maven（或 Gradle）用于依赖管理
- IDE，例如 IntelliJ IDEA 或 Eclipse
- 对 Java I/O 有基本了解

## 设置 GroupDocs.Viewer for Java

将 GroupDocs 仓库和依赖添加到您的 `pom.xml`。此代码片段与原教程保持一致：

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
- **免费试用** – 从 GroupDocs 网站下载。  
- **临时许可证** – 如果需要延长评估期，请申请。  
- **正式许可证** – 购买用于生产部署。

### 基本 Viewer 初始化
`Viewer` 类是加载文档并公开渲染和转换方法的入口点。保持代码完全如示：

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with your document path
try (Viewer viewer = new Viewer("path/to/your/document.docx")) {
    // Perform operations...
}
```

## 如何使用 GroupDocs Viewer 在 Java 中旋转 PDF 页面
使用 `Viewer` 加载目标文件，指定页码，然后调用 `rotatePage`。该方法适用于 PDF、DOCX、PPTX、XLSX 以及库支持的任何其他格式。旋转后，您可以将文档渲染为新的 PDF，或直接流式传输给客户端，确保原始文件保持不变。

## 步骤实现：将首页旋转 90 度

### 1. 导入所需的包
`PdfViewOptions` 告诉 Viewer 输出 PDF 文件，而 `Rotation` 枚举定义旋转角度。这两个类均位于 `com.groupdocs.viewer.options` 包中。

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
import com.groupdocs.viewer.options.Rotation;
```

### 2. 定义输出位置并创建 Viewer
将占位符路径替换为实际目录。`Viewer` 构造函数接受指向源文档的 `File` 对象。

```java
import java.nio.file.Path;

public class RotateSpecificPage {
    public static void run() {
        Path outputDirectory = YOUR_OUTPUT_DIRECTORY.resolve("RotateSpecificPage");
        Path outputFilePath = outputDirectory.resolve("output.pdf");

        try (Viewer viewer = new Viewer(YOUR_DOCUMENT_DIRECTORY.resolve("Sample.docx"))) {
            // Proceed with the rotation steps below...
        }
    }
}
```

### 3. 配置 PDF 视图选项并应用旋转
`rotatePage(int, Rotation)` 方法接受 **基于 1 的** 页码索引和 `Rotation` 枚举值。本例使用 `Rotation.ON_90_DEGREE` 将首页顺时针旋转。

```java
PdfViewOptions viewOptions = new PdfViewOptions(outputFilePath);

// Specify which page to rotate (1 for first page) and the rotation angle
viewOptions.rotatePage(1, Rotation.ON_90_DEGREE);
```

### 4. 渲染文档
调用配置好的 `view` 方法将旋转后的 PDF 写入输出文件夹。

```java
viewer.view(viewOptions);
```

#### 工作原理
- **PdfViewOptions** 指示 Viewer 生成 PDF 输出文件。  
- **rotatePage(int, Rotation)** 仅旋转指定页面，其他页面保持不变。  
- 该方法支持三个旋转常量：`ON_90_DEGREE`、`ON_180_DEGREE` 和 `ON_270_DEGREE`。

## 常见问题及解决方案
| 症状 | 可能原因 | 解决方案 |
|---------|--------------|-----|
| **FileNotFoundException** | 路径不正确或文件夹缺失 | 确认 `YOUR_OUTPUT_DIRECTORY` 和 `YOUR_DOCUMENT_DIRECTORY` 存在且可读。 |
| **Unsupported file format** | 尝试旋转 Viewer 不支持的格式 | 查看 [GroupDocs Viewer supported formats] 页面。 |
| **No rotation visible** | 使用了错误的页码（基于 0） | 请记住 `rotatePage` 使用 **1‑based** 索引。 |
| **Out‑of‑memory errors on large docs** | 在单线程中渲染大量大型文件 | 顺序处理文档或使用并发受限的线程池。 |

## 实际应用

1. **演示调整** – 将纵向幻灯片即时转换为横向，以获得更好的视觉效果。  
2. **批量文档校正** – 自动修复横向扫描的 PDF，节省数小时人工工作。  
3. **打印就绪输出** – 确保横向图形在纵向纸张上正确打印，无需在打印机驱动中手动旋转。

## 性能提示

- **及时关闭资源** – `try‑with‑resources` 块会自动释放 `Viewer`，释放内存。  
- **批处理** – 每个线程复用单个 `Viewer` 实例以降低初始化开销。  
- **监控内存** – 对于大于 100 MB 的文档，将输出流式写入磁盘而不是全部保存在内存中；GroupDocs Viewer 可在低于 250 MB RAM 的情况下处理 200 MB 文件。

## 常见问题

**Q: 我可以一次旋转多个页面吗？**  
A: 可以——对每个需要旋转的页码调用 `rotatePage()`，可以在循环中或通过链式调用实现。

**Q: 渲染后有办法撤销旋转吗？**  
A: 不能直接撤销。需要在不使用旋转选项的情况下重新渲染文档。

**Q: 哪些文件格式在 GroupDocs Viewer 中支持页面旋转？**  
A: DOCX、PDF、PPTX、XLSX 等，更多格式请参阅官方文档。

**Q: 如何在一批文档中自动旋转页面？**  
A: 将旋转逻辑封装在循环中，遍历文件路径集合，对每个文件应用相同的 `rotatePage` 配置。

**Q: 处理旋转期间错误的最佳实践是什么？**  
A: 将 Viewer 的使用放在 `try‑catch` 块中，记录异常细节，并可选择继续处理下一个文件，以防单个失败导致整个批次中止。

## 资源

- **文档**: [GroupDocs Viewer Java Documentation](https://docs.groupdocs.com/viewer/java/)  
- **API 参考**: [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/)  
- **下载**: [Get GroupDocs Viewer for Java](https://releases.groupdocs.com/viewer/java/)  
- **购买**: [Buy a License](https://purchase.groupdocs.com/buy)  
- **免费试用**: [Try Free](https://releases.groupdocs.com/viewer/java/)  
- **临时许可证**: [Request Temporary License](https://purchase.groupdocs.com/temporary-license/)  
- **支持**: [GroupDocs Forum](https://forum.groupdocs.com/c/viewer/9)

---

**最后更新：** 2026-09-30  
**测试环境：** GroupDocs Viewer 25.2 for Java  
**作者：** GroupDocs

## 相关教程

- [如何使用 GroupDocs.Viewer for Java 旋转特定 PDF 页面](/viewer/java/advanced-rendering/rotate-pdf-pages-groupdocs-viewer-java/)
- [在 Java 中从 URL 加载文档 – GroupDocs.Viewer 教程](/viewer/java/document-loading/)
- [Groupdocs Viewer Java 文档视图](/viewer/java/advanced-rendering/groupdocs-viewer-java-document-views/)