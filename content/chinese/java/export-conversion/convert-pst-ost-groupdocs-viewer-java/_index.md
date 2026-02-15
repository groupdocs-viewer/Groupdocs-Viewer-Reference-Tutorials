---
date: '2026-02-15'
description: 了解如何使用 GroupDocs.Viewer for Java 将 pst 转换为 html 以及 JPG、PNG、PDF 等其他格式。本指南涵盖所有必要的步骤和配置。
keywords:
- convert PST/OST
- GroupDocs.Viewer for Java
- render documents
title: 使用 GroupDocs.Viewer for Java 将 PST 转换为 HTML、JPG、PNG、PDF
type: docs
url: /zh/java/export-conversion/convert-pst-ost-groupdocs-viewer-java/
weight: 1
---

# 使用 GroupDocs.Viewer for Java 将 PST 转换为 HTML、JPG、PNG、PDF

您是否想要 **convert pst to html** 或其他格式如 JPG、PNG、PDF？借助强大的 GroupDocs.Viewer for Java 库，这项任务变得简单高效。在本教程中，您将学习如何将 Outlook PST/OST 文件渲染为适合网页的 HTML、图像文件或单个 PDF，使您的邮件存档易于共享和归档。

![使用 GroupDocs.Viewer for Java 将 PST/OST 转换为 HTML、JPG、PNG、PDF](/viewer/export-conversion/convert-pst-ost-to-html-jpg-png-pdf.png)

**您将学习的内容**
- 如何在 Maven 项目中设置 GroupDocs.Viewer for Java。  
- 逐步说明如何 **java convert pst** 文件转换为 HTML、JPG、PNG 和 PDF。  
- 优化性能和常见陷阱的配置技巧。

## 快速答案
- **What library handles PST conversion?** GroupDocs.Viewer for Java。  
- **Can I convert PST to PDF directly?** Yes, using `PdfViewOptions`。  
- **Is a license required for production?** A valid GroupDocs license is needed。  
- **Which Java version is supported?** JDK 8 or higher。  
- **Do I need to extract attachments manually?** No, the viewer renders them automatically。

## 如何使用 GroupDocs.Viewer for Java 将 pst 转换为 html
下面先简要概述转换流程，然后再深入代码示例。

### 为什么选择 GroupDocs.Viewer？
- **High fidelity** 渲染邮件正文、附件和格式。  
- **Multiple output formats**（HTML、JPG、PNG、PDF）只需一个 API。  
- **No external dependencies** – 所有功能均在您的 Java 应用内部运行。

## 前置条件

- **GroupDocs.Viewer for Java** – 版本 25.2 或更高。  
- **Java Development Kit (JDK)** – 8 或更新。  
- Maven 用于依赖管理。  
- 基础的 Java 知识并熟悉 Maven。

## 设置 GroupDocs.Viewer for Java

在 `pom.xml` 中添加 GroupDocs 仓库和依赖：

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
- **Free trial** – 免费试用全部功能。  
- **Temporary license** – 如有需要可延长评估时间。  
- **Full license** – 生产环境部署必需。

### 基本初始化

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

## 实现指南

以下章节将逐步演示如何将 PST/OST 文件渲染为各支持的格式。

### 将 PST/OST 文档渲染为 HTML

#### 步骤 1：设置输出目录

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.html");
```

#### 步骤 2：配置加载选项

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### 步骤 3：初始化 Viewer 并渲染 HTML

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
    viewer.view(options);
}
```

### 将 PST/OST 文档渲染为 JPG

#### 步骤 1：设置输出目录

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.jpg");
```

#### 步骤 2：配置加载选项

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### 步骤 3：初始化 Viewer 并渲染 JPG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    JpgViewOptions options = new JpgViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### 将 PST/OST 文档渲染为 PNG

#### 步骤 1：设置输出目录

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result_{0}.png");
```

#### 步骤 2：配置加载选项

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### 步骤 3：初始化 Viewer 并渲染 PNG

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PngViewOptions options = new PngViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

### 将 PST/OST 文档渲染为 PDF

#### 步骤 1：设置输出目录

```java
Path outputDirectory = Paths.get("YOUR_OUTPUT_DIRECTORY");
Path pageFilePathFormat = outputDirectory.resolve("PST_result.pdf");
```

#### 步骤 2：配置加载选项

```java
LoadOptions loadOptions = new LoadOptions();
loadOptions.setResourceLoadingTimeout(100);
```

#### 步骤 3：初始化 Viewer 并渲染 PDF

```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_PST", loadOptions)) {
    PdfViewOptions options = new PdfViewOptions(pageFilePathFormat);
    viewer.view(options);
}
```

## 实际应用场景

- **邮件归档**：将大型 PST 存档转换为可搜索的 HTML 或 PDF，以满足合规要求。  
- **文档管理系统**：将转换后的文件存入仅接受 PDF、PNG 或 JPG 的系统。  
- **协作平台**：在 Slack 或 Teams 中以图片形式共享转换后的邮件。  
- **法律审查**：向法院提供 PDF 版的邮件证据。  
- **备份策略**：为关键邮件保留轻量级的 PNG 或 JPG 快照。

## 性能考虑

- **资源管理**：在处理多个文件时复用 `Viewer` 实例以降低开销。  
- **内存调优**：根据服务器容量调整 `loadOptions.setResourceLoadingTimeout`。  
- **异步处理**：将转换任务放入后台线程，以保持 UI 响应。

## 常见问题

**Q: How do I **convert pst to pdf** with the same code base?**  
A: Use `PdfViewOptions` as shown in the PDF rendering section; the rest of the code remains identical.

**Q: Can GroupDocs.Viewer handle encrypted PST files?**  
A: Yes, provide the password via `LoadOptions.setPassword("yourPassword")` before rendering.

**Q: What is the difference between **java convert pst** to PNG vs JPG?**  
A: PNG preserves lossless quality, ideal for screenshots, while JPG offers smaller file sizes for email previews.

**Q: Is there a way to **how to convert pst** files in bulk?**  
A: Wrap the rendering logic in a loop that iterates over a directory of PST files; reuse the same `Viewer` configuration for each file.

## 结论

现在，您已经拥有使用 GroupDocs.Viewer for Java 将 **convert pst to html**、JPG、PNG 和 PDF 的完整、可投入生产的指南。按照上述步骤，您可以将邮件转换集成到任何基于 Java 的工作流中，提升可访问性并满足合规需求。

---

**最后更新：** 2026-02-15  
**测试环境：** GroupDocs.Viewer for Java 25.2  
**作者：** GroupDocs