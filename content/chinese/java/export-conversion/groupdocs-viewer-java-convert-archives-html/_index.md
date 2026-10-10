---
date: '2026-10-10'
description: 了解如何使用 GroupDocs.Viewer Java 将 zip 转换为 html，设置每页项目数，嵌入资源 html，并高效批量转换归档文件。
images:
- /java/export-conversion/groupdocs-viewer-java-convert-archives-html/og-image.png
keywords:
- how to convert zip
- convert archive to html
- java convert zip html
lastmod: '2026-10-10'
og_description: 了解如何使用 GroupDocs.Viewer Java 将 zip 转换为 html，嵌入资源，设置每页项目数，并批量处理归档文件，以实现快速、便携的网页预览。
og_image_alt: 'Developer guide: convert zip to HTML with GroupDocs.Viewer Java, showing
  pagination and embedded resources'
og_title: 使用 GroupDocs.Viewer Java 将 zip 转换为 HTML 并实现分页
schemas:
- author: GroupDocs
  dateModified: '2026-10-10'
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
title: 使用 GroupDocs.Viewer Java 将 zip 转换为 html 并设置每页项目数
type: docs
url: /zh/java/export-conversion/groupdocs-viewer-java-convert-archives-html/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 将 zip 转换为 html 并使用 GroupDocs.Viewer Java 设置每页项目数

在许多 Web 应用程序中，您需要直接在浏览器中显示 ZIP 或 RAR 存档的内容。**如何将 zip 文件**转换为 HTML 使用 GroupDocs.Viewer for Java 是一个常见需求，且该库允许您嵌入图像、CSS 和字体，从而得到一个单一的可移植页面。本教程将带您逐步了解所有内容——从 Maven 设置到多页渲染——并解释每个选项为何对性能和可用性至关重要。

![使用 GroupDocs.Viewer for Java 将存档转换为 HTML](/viewer/export-conversion/convert-archives-to-html-java.png)

## 快速答案
- **“set items per page” 控制什么？** 它决定了每个生成的 HTML 页面上显示多少个来自存档的文件或文件夹。  
- **我可以直接在 HTML 中嵌入图像和 CSS 吗？** 是的——使用 `forEmbeddedResources` 选项将资源嵌入 HTML。  
- **批量转换是否可行？** 当然可以；您可以遍历存档集合并使用相同的设置渲染每个存档。  
- **使用 GroupDocs.Viewer 是否需要 Maven？** 是的，按下面所示添加 `groupdocs-viewer` Maven 依赖。  
- **支持哪些输出格式？** 单页 HTML 和多页 HTML 均可用，且该库支持 50 多种输入存档类型。

## GroupDocs.Viewer 中的 “set items per page” 是什么？
它告诉查看器在生成多页文档时，每个 HTML 页面上应显示多少个存档条目（文件或文件夹）。调整此值有助于在大型存档中平衡页面大小和导航速度，通过限制每页加载的数据量并减少终端用户的渲染时间。

## 为什么要嵌入资源 html？
将资源（图像、CSS、字体）直接嵌入 HTML 文件会创建一个单一的可移植文档，无需外部文件即可打开。这对于电子邮件附件、离线查看或将输出嵌入其他网页非常理想。它还消除了管理外部资源路径的需求。

## 先决条件

- **必需的库：** 包括 GroupDocs.Viewer 版本 25.2 或更高。  
- **环境：** 已安装并配置 Java Development Kit（JDK）。  
- **知识：** 基本的 Java 和 Maven 依赖管理。  

## Maven GroupDocs Viewer 设置

将 GroupDocs 仓库和查看器依赖添加到您的 `pom.xml` 中：

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
GroupDocs.Viewer 提供 **免费试用链接**、临时许可证或完整购买选项。请选择最适合您项目时间表的方案。

## 基本初始化
`Viewer` 类是渲染文档和存档的入口点。完成 Maven 设置后，将查看器引入代码中：

```java
import com.groupdocs.viewer.Viewer;
// Your initialization code here
```

## 如何将存档渲染为单页 html
`HtmlViewOptions` 类定义了 HTML 输出的设置，例如嵌入资源。加载存档，配置 HTML 选项以嵌入资源，并将所有内容渲染到一个自包含页面中。这会生成一个包含所有文件、图像、CSS 和字体的单个 HTML 文件，适用于离线使用或电子邮件附件。

**直接答案：** 为 ZIP 文件创建 `Viewer` 实例，调用 `HtmlViewOptions.forEmbeddedResources()`，并执行 `viewer.view(documentPath, options)`。这会生成一个包含所有文件、图像、CSS 和字体的单个 HTML 文件，适用于离线使用或电子邮件附件。

### 步骤 1：定义输出目录
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### 步骤 2：设置单页输出的文件名
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result.html");
```

### 步骤 3：初始化查看器
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Further configuration steps follow
}
```

### 步骤 4：配置渲染选项（嵌入资源 html）
`HtmlViewOptions` 类定义了 HTML 输出的设置，例如嵌入资源。使用 `forEmbeddedResources()` 将所有内容打包成一个文件。

```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### 步骤 5：渲染为单页
```java
options.setRenderToSinglePage(true);
viewer.view(options);
```

## 如何将存档渲染为多页 html 并设置每页项目数
`HtmlViewOptions` 类同样支持分页。通过调用 `options.setItemsPerPage(N)`，您指示查看器将存档拆分为多个 HTML 文件，每个文件显示最多 **N** 条目。这种方法在保持每页轻量的同时，提高了大型存档的导航速度。

**直接答案：** 使用 `HtmlViewOptions.forEmbeddedResources()`，调用 `options.setItemsPerPage(N)`，并渲染存档。查看器将生成多个 HTML 文件——每页一个——每个文件包含最多 **N** 条目，从而加快大存档的导航速度。

### 步骤 1：复用输出目录
```java
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

### 步骤 2：定义多页的文件名格式
```java
Path pageFilePathFormat = outputDirectory.resolve("RAR_result_page_{0}.html");
```

### 步骤 3：再次初始化查看器
```java
try (Viewer viewer = new Viewer(TestFiles.SAMPLE_RAR_WITH_FOLDERS)) {
    // Continue with multi‑page configuration
}
```

### 步骤 4：配置多页选项（嵌入资源 html）
```java
HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

### 步骤 5：设置每页项目数（操作中的主要关键词）
```java
options.getArchiveOptions().setItemsPerPage(10); // Default is 16
viewer.view(options);
```

## 实际应用

- **文档管理系统：** 在无需安装额外查看器的情况下添加存档预览功能。  
- **Web 门户：** 为用户提供快速、无需下载的方式来浏览打包的文档。  
- **协作工具：** 让团队直接在浏览器中检查共享的存档。  

## 性能考虑因素

- **资源管理：** 通过流式处理存档来保持低内存使用；查看器可处理高达 500 MB 的存档，而无需将整个文件加载到内存中。  
- **批量转换存档：** 遍历存档文件列表并调用相同的渲染逻辑，以最大化吞吐量。  
- **缓存策略：** 如果同一存档被频繁访问，将渲染后的 HTML 存入缓存，可将重复处理时间降低至 70 %。  

## 常见问题

**Q: 什么是 GroupDocs.Viewer Java？**  
A: GroupDocs.Viewer Java 是一个服务器端库，可将 50 多种文档和存档格式（包括 ZIP 和 RAR）渲染为 HTML、PDF 或图像文件，无需外部应用程序。

**Q: 如何获取 GroupDocs.Viewer 的免费试用？**  
A: 访问 [free trial link](https://releases.groupdocs.com/viewer/java/) 下载并测试。

**Q: 我可以转换除存档之外的其他文档类型吗？**  
A: 是的，查看器支持 PDF、Word、Excel、PowerPoint 以及另外 35 种以上的格式。

**Q: 如果渲染速度慢该怎么办？**  
A: 减少每页项目数，启用流式处理，或将存档分成更小的批次处理以提升速度。

**Q: 我在哪里可以获得帮助或支持？**  
A: 通过 [support forum](https://forum.groupdocs.com/c/viewer/9) 联系我们。

**Q: 是否可以直接在 HTML 中嵌入 CSS 和图像？**  
A: 完全可以——如示例所示，使用 `HtmlViewOptions.forEmbeddedResources`。

**Q: 如何批量转换文件夹中的存档？**  
A: 使用 `for` 循环遍历每个文件，对每次迭代应用相同的 `Viewer` 和 `HtmlViewOptions` 配置。

**Q: 我可以在哪里与其他用户讨论问题？**  
A: 访问 [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9) 进行社区讨论。

## 资源

- **文档：** 深入了解功能，请参阅 [GroupDocs documentation](https://docs.groupdocs.com/viewer/java/)。  
- **API 参考：** 在 [GroupDocs API](https://reference.groupdocs.com/viewer/java/) 查看完整 API。  
- **下载：** 从 [download page](https://releases.groupdocs.com/viewer/java/) 获取最新二进制文件。  
- **购买和许可：** 在 [purchase page](https://purchase.groupdocs.com/buy) 查看选项。  
- **支持与社区：** 在 [support forum](https://forum.groupdocs.com/c/viewer/9) 加入讨论。  
- **GroupDocs 论坛：** 访问 [GroupDocs forum](https://forum.groupdocs.com/c/viewer/9) 获取社区帮助。

---

**最后更新：** 2026-10-10  
**测试版本：** GroupDocs.Viewer 25.2  
**作者：** GroupDocs

## 相关教程

- [如何使用 GroupDocs.Viewer 将 zip 转换为 HTML 并在 Java 中渲染 zip 文件夹](/viewer/java/advanced-rendering/render-archive-folders-groupdocs-viewer-java/)
- [使用 GroupDocs.Viewer Java 将 zip 转换为 pdf - 自定义文件名](/viewer/java/advanced-rendering/groupdocs-viewer-java-custom-filenames-rendering-archives/)
- [如何使用 GroupDocs.Viewer for Java 将 DOCX 转换为 HTML：分步指南](/viewer/java/export-conversion/convert-docx-to-html-groupdocs-viewer-java/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}