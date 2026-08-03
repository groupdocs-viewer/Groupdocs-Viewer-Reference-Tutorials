---
date: '2026-08-03'
description: 了解如何使用 GroupDocs.Viewer Java 将 zip 转换为 html，设置 items per page，embed resources
  html，并高效 batch convert archives。
keywords:
- convert zip to html
- how to batch convert
- embed resources html
- batch convert archives
- how to convert archives
lastmod: '2026-08-03'
og_description: 了解如何使用 GroupDocs.Viewer Java 将 zip 转换为 html，设置 items per page，embed
  resources html，并高效 batch convert archives。遵循 step‑by‑step code 和 performance tips。
og_image_alt: 'Guide: convert zip to html with GroupDocs.Viewer Java, showing pagination
  and embedded resources'
og_title: 使用 GroupDocs.Viewer Java 将 zip 转换为 html 并设置 items per page
schemas:
- author: GroupDocs
  dateModified: '2026-08-03'
  description: Learn how to convert zip to html using GroupDocs.Viewer Java, set items
    per page, embed resources html, and batch convert archives efficiently.
  headline: Convert zip to html and set items per page with GroupDocs.Viewer Java
  type: TechArticle
- questions:
  - answer: GroupDocs.Viewer Java is a server‑side library that renders over 50 document
      and archive formats—including ZIP and RAR—into HTML, PDF, or image files without
      requiring external applications.
    question: What is GroupDocs.Viewer Java?
  - answer: Visit the [free trial link](https://releases.groupdocs.com/viewer/java/)
      to download and test.
    question: How can I obtain a free trial of GroupDocs.Viewer?
  - answer: Yes, the viewer supports PDFs, Word, Excel, PowerPoint, and 35+ additional
      formats.
    question: Can I convert other document types besides archives?
  - answer: Reduce the number of items per page, enable streaming, or process archives
      in smaller batches to improve speed.
    question: What should I do if rendering is slow?
  - answer: Reach out via the [support forum](https://forum.groupdocs.com/c/viewer/9).
    question: Where can I get help or support?
  type: FAQPage
tags:
- convert zip
- GroupDocs.Viewer
- Java archive conversion
- html rendering
- batch conversion
title: 使用 GroupDocs.Viewer Java 将 zip 转换为 html 并设置 items per page
type: docs
url: /zh/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

# 将 zip 转换为 html 并使用 GroupDocs.Viewer Java 设置每页项目数

在许多 Web 应用程序中，您需要直接在浏览器中显示 ZIP 或 RAR 存档的内容。使用 GroupDocs.Viewer for Java，您可以在一步完成 **convert zip to html**，控制每页显示的存档条目数量，嵌入所有支持的图像和 CSS，甚至批量处理数十个存档。本教程将带您完整了解工作流，从 Maven 设置到多页渲染，并解释每个设置对性能和可用性的影响。

![Convert Archives to HTML with GroupDocs.Viewer for Java](/viewer/export-conversion/convert-archives-to-html-java.png)

## 快速答案
- **“set items per page” 控制什么？** 它决定每个生成的 HTML 页面上显示多少个来自存档的文件或文件夹。  
- **我可以直接在 HTML 中嵌入图像和 CSS 吗？** 可以 — 使用 `forEmbeddedResources` 选项将资源嵌入 HTML。  
- **批量转换可能吗？** 完全可以；您可以遍历存档集合，并使用相同的设置渲染每个存档。  
- **使用 GroupDocs.Viewer 是否需要 Maven？** 是的，按如下所示添加 `groupdocs-viewer` Maven 依赖。  
- **支持哪些输出格式？** 单页 HTML 和多页 HTML 均可用，且库支持 50 多种输入存档类型。

## “set items per page” 在 GroupDocs.Viewer 中是什么？
**set items per page** 设置属于存档渲染选项。它告诉查看器在生成多页 HTML 文档时，每个 HTML 页面上应显示多少个存档条目（文件或文件夹）。调整此值有助于在页面大小和导航速度之间取得平衡，尤其是对于大型存档。

## 为什么嵌入资源 html？
将资源（图像、CSS、字体）直接嵌入 HTML 文件内部，可创建单一可移植的文档，无需外部文件即可打开。这对于电子邮件附件、离线查看或将输出嵌入其他网页非常理想。这种方式还简化了部署，因为无需管理外部资源路径。

## 前提条件

- **Required libraries:** 包含 GroupDocs.Viewer 版本 25.2 或更高。  
- **Environment:** 已安装并配置 Java Development Kit (JDK)。  
- **Knowledge:** 基本的 Java 和 Maven 依赖管理。  

## Maven GroupDocs Viewer 设置

Add the GroupDocs repository and the viewer dependency to your `pom.xml`:

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
GroupDocs.Viewer 提供 **free trial link**、临时许可证或完整购买选项。请选择适合您项目时间表的方案。

### 基本初始化
After the Maven setup, bring the viewer into your code:

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## 如何将存档渲染为单页 html
Viewer 是用于加载文档或存档进行渲染的核心类。

要生成包含整个存档的单个 HTML 文件，需为 ZIP 文件创建 `Viewer` 实例，并使用 `HtmlViewOptions.forEmbeddedResources()` 嵌入所有图像、CSS 和字体。使用这些选项渲染存档会生成一个自包含的页面，适用于电子邮件或离线使用。

### 步骤 1：定义输出目录
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### 步骤 2：设置单页输出的文件名
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### 步骤 3：初始化 Viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### 步骤 4：配置渲染选项（嵌入资源 html）
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### 步骤 5：渲染为单页
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## 如何将存档渲染为多页 html 并设置每页项目数
`HtmlViewOptions` 配置查看器渲染 HTML 输出的方式，包括分页和资源嵌入。

要将存档拆分为多个页面，创建 `HtmlViewOptions.forEmbeddedResources()` 并使用 `options.setItemsPerPage(20)` 设置所需的页面大小。查看器将生成多个 HTML 文件，每个文件显示最多指定数量的条目，这可提升大型存档的导航体验并确保更快的加载速度。

### 步骤 1：复用输出目录
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### 步骤 2：定义多页的文件名格式
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### 步骤 3：再次初始化 Viewer
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### 步骤 4：配置多页选项（嵌入资源 html）
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### 步骤 5：设置每页项目数（操作中的主要关键字）
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## 实际应用

- **Document management systems:** 添加存档预览功能，无需安装额外的查看器。  
- **Web portals:** 为用户提供快速、无需下载的方式来浏览打包的文档。  
- **Collaboration tools:** 让团队直接在浏览器中检查共享的存档。  

## 性能考虑

- **Resource management:** 通过流式处理存档保持低内存使用；查看器可处理高达 500 MB 的存档，而无需将整个文件加载到内存中。  
- **Batch convert archives:** 循环遍历存档文件列表并调用相同的渲染逻辑，以最大化吞吐量。  
- **Caching strategy:** 如果同一存档被频繁访问，将渲染后的 HTML 存入缓存，可将重复处理时间降低最多 70 %。  

## 常见问题

**Q: 什么是 GroupDocs.Viewer Java？**  
A: GroupDocs.Viewer Java 是一个服务器端库，可将 50 多种文档和存档格式（包括 ZIP 和 RAR）渲染为 HTML、PDF 或图像文件，无需外部应用程序。

**Q: 如何获取 GroupDocs.Viewer 的免费试用？**  
A: 访问 [free trial link](https://releases.groupdocs.com/viewer/java/) 下载并测试。

**Q: 我可以转换除存档之外的其他文档类型吗？**  
A: 可以，查看器支持 PDF、Word、Excel、PowerPoint 以及另外 35 种以上的格式。

**Q: 如果渲染速度慢该怎么办？**  
A: 减少每页项目数，启用流式处理，或将存档分成更小的批次处理以提升速度。

**Q: 我在哪里可以获得帮助或支持？**  
A: 通过 [support forum](https://forum.groupdocs.com/c/viewer/9) 联系我们。

**Q: 是否可以直接在 HTML 中嵌入 CSS 和图像？**  
A: 完全可以 — 如示例所示，使用 `HtmlViewOptions.forEmbeddedResources`。

**Q: 如何批量转换一个存档文件夹？**  
A: 使用 `for` 循环遍历每个文件，对每次迭代应用相同的 `Viewer` 和 `HtmlViewOptions` 配置。

## 资源

- **Documentation:** 通过 [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/) 深入了解功能。  
- **API reference:** 在 [GroupDocs API](https://reference.groupdocs.com/viewer/java/) 查看完整 API。  
- **Download:** 从 [download page](https://releases.groupdocs.com/viewer/java/) 获取最新二进制文件。  
- **Purchase and licensing:** 在 [purchase page](https://purchase.groupdocs.com/buy) 查看选项。  
- **Support and community:** 加入 [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9) 讨论。

---

**最后更新：** 2026-08-03  
**测试环境：** GroupDocs.Viewer 25.2  
**作者：** GroupDocs

## 相关教程

- [如何使用 GroupDocs.Viewer 将 zip 转换为 HTML 并在 Java 中渲染 zip 文件夹](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [使用 GroupDocs.Viewer Java 将 zip 转换为 pdf - 自定义文件名](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [使用 GroupDocs.Viewer for Java 将 DOCX 转换为 HTML 的分步指南](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)