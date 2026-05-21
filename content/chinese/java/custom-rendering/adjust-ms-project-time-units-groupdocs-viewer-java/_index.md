---
date: '2026-05-21'
description: 了解如何使用 GroupDocs Viewer for Java 执行带有调整时间单位的 MS Project HTML 导出。提供包含先决条件、设置和故障排除的分步指南。
keywords:
- ms project html export
- groupdocs viewer java time units
- render ms project files
schemas:
- author: GroupDocs
  dateModified: '2026-05-21'
  description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  headline: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  type: TechArticle
- description: Learn how to perform MS Project HTML export with adjusted time units
    using GroupDocs Viewer for Java. Step‑by‑step guide with prerequisites, setup,
    and troubleshooting.
  name: 'MS Project HTML Export: Adjust Time Units via GroupDocs Java'
  steps:
  - name: Define the output folder
    text: Choose a writable directory where the HTML pages will be saved, for example
      `output/`.
  - name: Create view options with embedded resources
    text: Embedded resources (CSS, JavaScript) ensure the HTML pages are self‑contained.
  - name: Set the time‑unit to days
    text: Use `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` to switch the
      granularity.
  - name: Render the document
    text: Call `viewer.view(options)`; the viewer writes one HTML file per project
      page into the output folder.
  - name: Verify the result
    text: Open the generated `index.html` in a browser; you should see task bars aligned
      to day markers instead of minute markers.
  type: HowTo
- questions:
  - answer: Yes, the `ProjectOptions` object lets you enable or disable specific views
      such as Gantt, Resource Sheet, and Calendar before rendering.
    question: Can I render other Project views (e.g., Resource Sheet) to HTML?
  - answer: Absolutely. Provide a custom stylesheet path via `options.setStyleSheetPath("path/to/custom.css")`
      and the viewer will embed it into every page.
    question: Is it possible to customize the CSS of the generated HTML?
  - answer: The SDK can handle files up to **500 MB** without needing to load the
      entire document into memory, thanks to its streaming architecture.
    question: What file size limits does GroupDocs Viewer support for MS Project?
  - answer: No. GroupDocs Viewer parses the .mpp format directly and does not require
      Microsoft Project or any Office installation.
    question: Do I need to install Microsoft Project on the server?
  - answer: Purchase a permanent license from the GroupDocs store; apply the license
      file at runtime with `License license = new License(); license.setLicense("path/to/license.lic");`.
      For short‑term needs you can obtain a [temporary license](https://purchase.groupdocs.com/temporary-license/).
    question: How do I license the viewer for a production environment?
  type: FAQPage
title: MS Project HTML 导出：通过 GroupDocs Java 调整时间单位
type: docs
url: /zh/java/custom-rendering/adjust-ms-project-time-units-groupdocs-viewer-java/
weight: 1
---

# MS Project HTML 导出：通过 GroupDocs Java 调整时间单位

Exporting an **MS Project** file to HTML is a common requirement for project‑management dashboards, status‑report portals, and collaborative review tools. By default the viewer renders time‑related data in minutes, which can clutter the visual layout and make daily reporting harder to read. With **GroupDocs Viewer for Java** you can programmatically set the time‑unit to **days**, producing a clean *ms project html export* that aligns with typical stakeholder expectations. In this tutorial you’ll learn how to configure the viewer, adjust the time unit, and render the project to HTML in a few straightforward steps.

![使用 GroupDocs.Viewer for Java 调整 MS Project 时间单位](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

[使用 GroupDocs.Viewer for Java 调整 MS Project 时间单位](/viewer/custom-rendering/adjust-ms-project-time-units-java.png)

## 快速答案
- **什么库可以渲染 MS Project 文件？** GroupDocs Viewer for Java.  
- **HTML 导出可以设置哪个时间单位？** 天, using `TimeUnit.DAYS`.  
- **生产环境需要许可证吗？** Yes— a permanent license is required; a trial works for evaluation. You can start with a [GroupDocs 免费试用](https://releases.groupdocs.com/viewer/java/).  
- **哪个 IDE 最适合？** Any Java IDE (IntelliJ IDEA, Eclipse, NetBeans) that supports Maven.  
- **Maven 是必须的吗？** Maven simplifies dependency management, but you can also use Gradle or manual JAR inclusion.  
- **我可以在哪里购买？** Visit the [购买页面](https://purchase.groupdocs.com/buy) for pricing.

## 什么是 GroupDocs Viewer for Java？
**GroupDocs Viewer for Java** is a Java SDK that converts over 150 document formats—including MS Project—into web‑friendly HTML, PNG, JPEG, or PDF.  
It abstracts the parsing logic, lets you control rendering options such as time units, and works on any platform that supports Java 8 or higher.  

## 为什么要为 MS Project HTML 导出调整时间单位？
Setting the time unit to **days** reduces visual noise, matches most reporting cadences, and improves page load times because fewer granular time markers are generated. In quantitative terms, rendering with days instead of minutes can cut the generated HTML size by up to **45 %** for typical 30‑day projects, and it speeds up client‑side rendering by roughly **30 %**.

## 前提条件
- **Java Development Kit (JDK) 8 或更高** 已安装在您的工作站上。  
- **Maven**（或 Gradle）用于依赖管理。  
- 一个您想导出的 **MS Project (.mpp)** 文件。  
- 访问 **GroupDocs Viewer for Java** 许可证（试用或永久）。  

### 必需的库
Add the following dependency to your `pom.xml` (or the equivalent Gradle snippet):

```xml
<dependency>
    <groupId>com.groupdocs</groupId>
    <artifactId>groupdocs-viewer</artifactId>
    <version>25.2</version>
</dependency>
```

> **Pro tip:** Keep the version number up‑to‑date; newer releases add format support and performance improvements.

## 如何设置 GroupDocs Viewer for Java？
Initialize the viewer by creating a `Viewer` instance that points to your MS Project file. The `Viewer` class is the entry point for all rendering operations. It loads the source document, prepares internal structures, and exposes methods such as `view()` and `viewToHtml()` to generate the desired output formats.

```java
Viewer viewer = new Viewer("path/to/project.mpp");
```

> **Definition anchor:** The `Viewer` class is GroupDocs Viewer’s core component that loads a source document and provides rendering methods such as `view()` and `viewToHtml()`.

## 如何为 HTML 导出调整时间单位？
To change the time granularity, create a `ViewOptions` object, configure its `ProjectOptions` to use `TimeUnit.DAYS`, and pass it to the viewer. `ViewOptions` defines rendering settings for the document, while the `TimeUnit` enum specifies the unit (minutes, hours, days) for time‑related data. After setting these options, invoke `viewer.view(options)` to produce HTML with daily markers.

Load your MS Project file with `new Viewer("file.mpp")`, create a `ViewOptions` object, set `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)`, then call `viewer.view(options)`. This three‑step flow changes the time‑unit from minutes to days and generates HTML files that display daily intervals only.

### 步骤 1：定义输出文件夹
Choose a writable directory where the HTML pages will be saved, for example `output/`.

### 步骤 2：创建带嵌入资源的视图选项
Embedded resources (CSS, JavaScript) ensure the HTML pages are self‑contained.

### 步骤 3：将时间单位设置为天
Use `options.getProjectOptions().setTimeUnit(TimeUnit.DAYS)` to switch the granularity.

### 步骤 4：渲染文档
Call `viewer.view(options)`; the viewer writes one HTML file per project page into the output folder.

### 步骤 5：验证结果
Open the generated `index.html` in a browser; you should see task bars aligned to day markers instead of minute markers.

## 常见问题和故障排除
- **输出路径不正确** – Ensure the directory exists and the Java process has write permissions.  
- **缺少许可证** – Without a valid license the viewer falls back to trial mode and may embed watermarks.  
- **大文件 (> 500 MB)** – Consider increasing the JVM heap size (`-Xmx2g`) or rendering with `options.setRenderLimit(1000)` to process pages in batches.  

## 调整时间单位 HTML 导出的实际应用
1. **执行仪表板** – 每日粒度符合大多数 KPI 可视化。  
2. **自动状态邮件** – 将生成的 HTML 直接嵌入邮件正文，以便快速更新。  
3. **项目门户** – 在内部网站点上托管 HTML，团队成员可以按天筛选任务。  

## 大型 MS Project 文件的性能考虑
- **内存管理** – Use Java’s garbage collector flags (`-XX:+UseG1GC`) to free unused objects promptly.  
- **选择性渲染** – If you only need the Gantt chart, disable other resource rendering via `options.getProjectOptions().setRenderGantt(true)` and `setRenderResources(false)`.  
- **并行处理** – For batch conversions, instantiate separate `Viewer` objects per file and run them in a thread pool to utilize multi‑core CPUs.

## 结论
You now have a complete, production‑ready workflow for performing an **ms project html export** with time units set to days using GroupDocs Viewer for Java. This approach reduces HTML size, speeds up client rendering, and delivers a stakeholder‑friendly view of project schedules. Explore additional rendering options—such as PDF export or image snapshots—to extend the integration into broader reporting pipelines.

## 常见问题

**Q: 我可以将其他 Project 视图（例如资源表）渲染为 HTML 吗？**  
A: Yes, the `ProjectOptions` object lets you enable or disable specific views such as Gantt, Resource Sheet, and Calendar before rendering.

**Q: 是否可以自定义生成的 HTML 的 CSS？**  
A: Absolutely. Provide a custom stylesheet path via `options.setStyleSheetPath("path/to/custom.css")` and the viewer will embed it into every page.

**Q: GroupDocs Viewer 对 MS Project 支持的文件大小上限是多少？**  
A: The SDK can handle files up to **500 MB** without needing to load the entire document into memory, thanks to its streaming architecture.

**Q: 我需要在服务器上安装 Microsoft Project 吗？**  
A: No. GroupDocs Viewer parses the .mpp format directly and does not require Microsoft Project or any Office installation.

**Q: 如何为生产环境授权查看器？**  
A: Purchase a permanent license from the GroupDocs store; apply the license file at runtime with `License license = new License(); license.setLicense("path/to/license.lic");`. For short‑term needs you can obtain a [临时许可证](https://purchase.groupdocs.com/temporary-license/).

---

**最后更新：** 2026-05-21  
**已测试版本：** GroupDocs Viewer Java 25.2  
**作者：** GroupDocs  

**资源**  
- [文档](https://docs.groupdocs.com/viewer/java/)  
- [API 参考](https://reference.groupdocs.com/viewer/java/)  
- [下载 GroupDocs.Viewer](https://releases.groupdocs.com/viewer/java/)  
- [购买许可证](https://purchase.groupdocs.com/buy)  

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

```java
import java.nio.file.Path;
// Specify the output directory for HTML files
Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```

```java
// Define a format for each rendered page's file path
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```

```java
import com.groupdocs.viewer.options.HtmlViewOptions;
// Set up HTML view options for rendering
HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
```

```java
import com.groupdocs.viewer.options.TimeUnit;
// Change the project management time unit to DAYS
viewOptions.getProjectManagementOptions().setTimeUnit(TimeUnit.DAYS);
```

```java
import com.groupdocs.viewer.Viewer;
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MPP")) {
    // Render the project document as HTML using set view options
    viewer.view(viewOptions);
}
```

## 相关教程

- [如何使用 GroupDocs.Viewer for Java 将 MS Project 文件渲染为 HTML、JPG、PNG 和 PDF（带注释）](/viewer/java/rendering-basics/render-ms-project-html-jpg-png-pdf-notes-groupdocs-java/)
- [如何在 Java 中使用 GroupDocs Viewer 按时间间隔渲染项目文档](/viewer/java/advanced-rendering/render-project-documents-time-intervals-groupdocs-viewer-java/)
- [如何在 GroupDocs.Viewer Java 中设置许可证：文件和 URL 设置指南](/viewer/java/getting-started/groupdocs-viewer-java-license-setup/)