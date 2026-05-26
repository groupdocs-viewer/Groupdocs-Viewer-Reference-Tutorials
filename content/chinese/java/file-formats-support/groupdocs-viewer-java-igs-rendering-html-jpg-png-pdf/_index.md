---
date: '2026-02-23'
description: 了解如何使用 GroupDocs.Viewer for Java 将 IGS 转换为 PDF、HTML、JPG 和 PNG。请按照本分步指南，使用可直接运行的代码示例。
keywords:
- GroupDocs.Viewer Java
- Convert IGS Files
- Render IGS Documents
title: 使用 GroupDocs.Viewer Java 将 IGS 转换为 PDF、HTML、JPG 和 PNG
type: docs
url: /zh/java/file-formats-support/groupdocs-viewer-java-igs-rendering-html-jpg-png-pdf/
weight: 1
---

 inline.

Proceed to write final answer.# 使用 GroupDocs.Viewer Java 将 IGS 转换为 PDF、HTML、JPG 和 PNG

如果您需要在 Java 应用程序中直接 **convert IGS to PDF**（或转换为 HTML、JPG、PNG），您来对地方了。在本教程中，我们将一步步演示从库的配置到将 3‑D 模型渲染为适合您项目的格式的全部过程。您将了解为何 GroupDocs.Viewer 是实现快速、可靠转换的理想选择，并获取可以直接嵌入您解决方案的实用代码。

![Convert IGS Files to HTML, JPG, PNG, and PDF with GroupDocs.Viewer for Java](/viewer/file-formats-support/convert-igs-files-to-html-jpg-png-and-pdf-java.png)

## 快速答案
- **Can I convert IGS to PDF with Java?** 是的，使用 GroupDocs.Viewer 的 `PdfViewOptions`。
- **Which output formats are supported?** 支持 HTML、JPG、PNG 和 PDF。
- **Do I need a license for production?** 需要商业许可证；提供免费试用供测试使用。
- **What Java version is required?** 需要 JDK 8 或更高版本。
- **Is Maven the only way to add the library?** 不是，您也可以使用 Gradle 或手动引入 JAR 包。

## 什么是“convert IGS to PDF”？
将 IGS（用于 3‑D CAD 数据的中立文件格式）转换为 PDF，即把复杂的 3‑D 模型转化为静态、广泛可查看的文档。这对于向没有 CAD 工具的利益相关者共享设计非常有用。

## 为什么在 IGS 转换中使用 GroupDocs.Viewer？
- **Zero‑code CAD rendering** – 库自行处理 IGS 格式的解析工作。
- **Multiple output options** – 一次 API 调用即可生成 HTML、JPG、PNG 或 PDF。
- **Cross‑platform** – 在任何支持 Java 的操作系统上均可运行。
- **Performance‑focused** – 即使是大型装配体也能快速渲染。

## 前置条件
- **GroupDocs.Viewer for Java** ≥ 25.2  
- 已安装并在 IDE（IntelliJ IDEA、Eclipse、NetBeans 等）中配置 **JDK 8+**  
- 基本的 Maven 知识（可选但推荐）  

## 设置 GroupDocs.Viewer for Java

### Maven 依赖
在 `pom.xml` 中添加 GroupDocs 仓库和 Viewer 依赖：

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
GroupDocs.Viewer 提供：
- **Free trial** – 使用受限，适合快速测试。  
- **Temporary license** – 在短期评估期间提供完整功能。  
- **Commercial license** – 生产环境无限制使用。

### 基础 Viewer 初始化
下面的代码片段展示了如何创建指向您 IGS 文件的 `Viewer` 实例：

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
HTML 输出为您提供交互式、适合浏览器查看的 3‑D 模型视图。

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

**关键点：** `HtmlViewOptions.forEmbeddedResources()` 会将所有必需的资源（CSS、图片）直接嵌入 HTML 文件，使其可移植。

## 将 IGS 渲染为 JPG

### 如何将 IGS 转换为 JPG？
JPG 图像非常适合作为缩略图或快速预览。

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

您可以通过 `JpgViewOptions` 调整分辨率和压缩质量。

## 将 IGS 渲染为 PNG

### 如何将 IGS 转换为 PNG？
PNG 支持透明度，便于在不同背景上叠加模型。

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

尝试使用 `PngViewOptions` 来在文件大小和视觉保真度之间取得最佳平衡。

## 将 IGS 渲染为 PDF

### 如何将 IGS 转换为 PDF？
PDF 是共享详细设计文档的首选格式。本节直接对应主要关键词 **convert IGS to PDF**。

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

`PdfViewOptions` 让您可以控制页面布局、图像质量以及是否嵌入字体。

## 实际应用

- **Web portals** – 将 HTML 渲染的模型直接嵌入产品配置器。  
- **Marketing assets** – 为宣传册生成高分辨率的 JPG/PNG 图像。  
- **Technical documentation** – 在用户手册中加入 CAD 模型的 PDF 渲染。  
- **Quality assurance** – 为大量 IGS 文件自动生成缩略图。

## 常见问题与解决方案

| Issue | Solution |
|-------|----------|
| **Output folder not found** | Verify the path passed to `Path outputDirectory` and ensure the Java process has write permissions. |
| **Blank pages in PDF** | Make sure the IGS file is not corrupted; try opening it in a CAD viewer first. |
| **Slow rendering for large assemblies** | Increase JVM heap (`-Xmx2g` or more) and consider rendering page‑by‑page using `viewer.getPageCount()` if needed. |
| **Missing fonts in PDF** | Use `PdfViewOptions` to embed required fonts or install the missing fonts on the server. |

## 常见问答

**Q: Can I convert multiple IGS files in a single run?**  
A: 是的。遍历文件路径列表，对每个文件调用相应的 `view` 方法即可。

**Q: Is it possible to customize the PDF page size?**  
A: 当然。`PdfViewOptions` 提供 `setPageSize(PageSize.A4)` 等方法来自定义页面尺寸。

**Q: Do I need a separate license for each output format?**  
A: 不需要。单一的 GroupDocs.Viewer 许可证覆盖所有支持的格式。

**Q: How large can an IGS file be before performance degrades?**  
A: 该库可处理数百兆字节的文件，但对于非常大的模型可能需要分配更多的 JVM 内存。

**Q: Can I render only a specific view or orientation?**  
A: GroupDocs.Viewer 渲染默认视图。如需自定义方向，请在转换前使用 CAD 工具预处理 IGS 文件。

**Last Updated:** 2026-02-23  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs