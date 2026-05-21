---
date: '2026-02-21'
description: 学习如何使用 GroupDocs Viewer Maven 在 Java 中将 txt 文件转换为 html、jpg、png 和 pdf。包括
  txt 转 pdf 的 Java 步骤以及多页 html 的 Java 步骤。
keywords:
- GroupDocs.Viewer for Java
- convert TXT to HTML
- render TXT as JPG/PNG
title: groupdocs viewer maven：将 TXT 转换为 HTML、JPG、PNG、PDF
type: docs
url: /zh/java/export-conversion/groupdocs-viewer-java-txt-conversion-guide/
weight: 1
---

 we keep them.

Now produce final answer.# groupdocs viewer maven: 使用 GroupDocs.Viewer for Java 将 TXT 文件转换为 HTML、JPG、PNG 和 PDF

在现代 Java 应用程序中，**groupdocs viewer maven** 使将纯文本（TXT）文档转换为网页就绪的 HTML、高分辨率图像或可移植的 PDF 文件变得简单直观。无论您是在构建文档门户、归档服务还是预览功能，使用 GroupDocs.Viewer 转换 TXT 文件都能为您节省时间并消除自定义解析器的需求。在本指南中，我们将完整演示设置过程，并展示如何 **convert txt files java** 转换为 HTML（单页和多页）、JPG、PNG 和 PDF。

![使用 GroupDocs.Viewer for Java 将 TXT 文件转换为 HTML、JPG、PNG 和 PDF](/viewer/export-conversion/convert-txt-files-to-html-jpg-png-and-pdf-java.png)

## 快速答案
- **Which Maven artifact do I need?** `com.groupdocs:groupdocs-viewer` (see Maven snippet below).  
- **Can I render multi‑page HTML?** Yes – use `HtmlViewOptions.forEmbeddedResources` without the single‑page flag.  
- **Is a license required for production?** A trial works for evaluation; a permanent license is needed for commercial use.  
- **What Java version is supported?** Java 8 or newer (Java 11+ recommended).  
- **Do I need additional libraries for image output?** No, the Viewer library includes JPG and PNG support out‑of‑the‑box.

## 什么是 groupdocs viewer maven？
**groupdocs viewer maven** 是 GroupDocs.Viewer for Java 库的基于 Maven 的分发方式。它提供了一个简洁的 API，能够将超过 100 种文档格式（包括纯文本）渲染为 HTML、图像或 PDF，而无需 Microsoft Office 或其他第三方工具。

## 为什么要 convert txt files java？
- **跨平台预览** – HTML 和图像可以在浏览器或移动应用中显示。  
- **标准化归档** – PDF 保留格式，且可在任何设备上阅读。  
- **自动化友好** – 可将转换集成到批处理作业、云服务或 CI 流水线中。  

## 前提条件

- **GroupDocs.Viewer for Java** 版本 25.2 或更高（通过 Maven 获取）。  
- JDK 8 +（推荐使用 Java 11 +）。  
- IntelliJ IDEA、Eclipse 或 NetBeans 等 IDE。  
- 基本的 Java 与 Maven 知识。  

## 设置 GroupDocs.Viewer for Java

将仓库和依赖添加到您的 `pom.xml`：

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

### 获取许可证的步骤
- Start with a **free trial** or obtain a **temporary license** to explore the full capabilities.  
- For production, purchase a license through the official [purchase page](https://purchase.groupdocs.com/buy)。  

### 基本初始化和设置
1. Add the Maven dependency shown above.  
2. Ensure your JDK and IDE are correctly configured.  

现在让我们深入具体的转换场景。

## 实现指南

### 功能 1：将 TXT 渲染为多页 HTML *(multi page html java)*

#### 概述
此示例将 TXT 文档转换为 **多页 HTML** 文件，保持换行跨多个网页。

**Import Required Libraries**

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**Set Up Paths and Viewer**

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // Configure options for rendering with embedded resources
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    
    // Render the document to HTML using these options
    viewer.view(options);
}
```

*Explanation:* `HtmlViewOptions.forEmbeddedResources` 将 CSS、字体和图像直接打包进 HTML 输出，使其可移植。

### 功能 2：将 TXT 渲染为单页 HTML *(convert txt to html java)*

#### 概述
将整个文本文件压缩为单个 HTML 页面——适合快速预览。

**Import Required Libraries**

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.HtmlViewOptions;
```

**Set Up Paths and Viewer**

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result_single_page.html");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_2_TXT")) {
    // Configure options for rendering with embedded resources
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFileFullPath);
    
    // Set the option to render as a single page HTML
    options.setRenderToSinglePage(true);
    
    // Render the document using these options
    viewer.view(options);
}
```

*Explanation:* `setRenderToSinglePage(true)` 将所有页面合并为一个 HTML 文件。

### 功能 3：将 TXT 渲染为 JPG

#### 概述
将 TXT 文件转换为高质量 JPEG 图像，适用于只能接受图像的平台。

**Import Required Libraries**

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.JpgViewOptions;
```

**Set Up Paths and Viewer**

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.jpg");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // Configure options for rendering to a JPEG image
    JpgViewOptions options = new JpgViewOptions(pageFileFullPath);
    
    // Render the document as a JPG using these options
    viewer.view(options);
}
```

*Explanation:* `JpgViewOptions` 让您可以控制图像质量、DPI 和输出路径。

### 功能 4：将 TXT 渲染为 PNG

#### 概述
从文本文件生成无损 PNG 图像——在需要清晰、可缩放的图形时非常理想。

**Import Required Libraries**

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PngViewOptions;
```

**Set Up Paths and Viewer**

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.png");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // Configure options for rendering to a PNG image
    PngViewOptions options = new PngViewOptions(pageFileFullPath);
    
    // Render the document as a PNG using these options
    viewer.view(options);
}
```

*Explanation:* PNG 提供无损压缩，保持原始文本的精确外观。

### 功能 5：将 TXT 渲染为 PDF *(txt to pdf java / convert txt to pdf java)*

#### 概述
从 TXT 文档创建 PDF 文件——适用于归档、打印或发送给客户。

**Import Required Libraries**

```java
import com.groupdocs.viewer.Viewer;
import com.groupdocs.viewer.options.PdfViewOptions;
```

**Set Up Paths and Viewer**

```java
Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path pageFileFullPath = outputDirectory.resolve("Txt_result.pdf");

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_TXT")) {
    // Configure options for rendering to a PDF
    PdfViewOptions options = new PdfViewOptions(pageFileFullPath);
    
    // Render the document as a PDF using these options
    viewer.view(options);
}
```

*Explanation:* `PdfViewOptions` 自动处理页面布局、字体和资源嵌入。

## 实际应用

1. **文档管理系统：** 自动将遗留的 TXT 文档转换为 HTML，以供内网门户使用。  
2. **出版平台：** 将作者提交的 TXT 手稿转换为 HTML，实现与 CMS 的无缝集成。  
3. **归档解决方案：** 将旧文本文件保存为 PDF 或 PNG，以实现长期存储。  
4. **云存储集成：** 实时转换并将渲染后的文件存入 AWS S3、Azure Blob 或 Google Cloud。  

## 常见问题及解决方案

| 问题 | 原因 | 解决方案 |
|------|------|----------|
| **输出为空白** | 文件路径错误或缺少读取权限。 | Verify `YOUR_DOCUMENT_DIRECTORY` points to the actual TXT file and that the process has read rights. |
| **图像质量低** | 默认 DPI 较低。 | Use `JpgViewOptions.setResolution(int dpi)` or `PngViewOptions.setResolution(int dpi)` to increase DPI (e.g., 300). |
| **HTML 包含损坏的链接** | 资源未嵌入。 | Use `HtmlViewOptions.forEmbeddedResources` or provide a custom resource folder. |
| **许可证异常** | 未设置有效许可证。 | Load your license file with `License license = new License(); license.setLicense("path/to/license.file");` before creating the `Viewer`. |

## 常见问答

**Q: Can I convert large TXT files (hundreds of MB) with GroupDocs.Viewer?**  
A: Yes. The library streams the source file, but you may want to increase the JVM heap size for very large documents.

**Q: Do I need additional dependencies to generate JPG or PNG?**  
A: No. The Viewer package includes all required image processing libraries.

**Q: Is it possible to customize the PDF page size?**  
A: Absolutely. Use `PdfViewOptions.setPageSize(PageSize.A4)` or any other `PageSize` before rendering.

**Q: How do I handle password‑protected TXT files?**  
A: TXT files do not support passwords. If the file is encrypted, decrypt it first before passing it to the Viewer.

**Q: Can I run this conversion in a Docker container?**  
A: Yes. Just include the JDK, copy your `pom.xml` with the GroupDocs dependency, and run the Java application inside the container.

---

**Last Updated:** 2026-02-21  
**Tested With:** GroupDocs.Viewer 25.2 for Java  
**Author:** GroupDocs