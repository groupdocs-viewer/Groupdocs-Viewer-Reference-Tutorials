---
date: '2026-09-15'
description: 了解如何使用 GroupDocs.Viewer for Java 将 eml 转换为 html，并使用自定义 datetime 格式和 timezone
  offset——非常适合电子邮件归档和支持门户。
keywords:
- convert eml to html
- custom datetime format
- set timezone offset
- email rendering html
lastmod: '2026-09-15'
og_description: 使用 GroupDocs.Viewer for Java 将 eml 转换为 html，并使用自定义 datetime 格式和 timezone
  offset。请按照本分步指南实现精确的电子邮件渲染。
og_image_alt: Screenshot of GroupDocs.Viewer rendering an email to HTML with custom
  datetime in Java
og_title: 使用 GroupDocs.Viewer 在 Java 中将 eml 转换为 html 并自定义 datetime
schemas:
- author: GroupDocs
  dateModified: '2026-09-15'
  description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  headline: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  type: TechArticle
- description: Learn how to convert eml to html with a custom datetime format and
    timezone offset using GroupDocs.Viewer for Java—ideal for email archiving and
    support portals.
  name: Convert eml to html with custom datetime in java using GroupDocs.Viewer
  steps:
  - name: set up output directory and file path
    text: Define where the generated HTML will be saved. *Explanation:* `Path.of()`
      creates a reference to the folder where the HTML will be saved. `resolve()`
      appends the file name.
  - name: initialize viewer with email file
    text: Instantiate the `Viewer` class for the target EML file. *Explanation:* The
      `Viewer` instance points to the EML file you want to convert.
  - name: configure HtmlViewOptions
    text: Create an `HtmlViewOptions` object that bundles images and other resources
      directly into the HTML output. *Explanation:* `forEmbeddedResources()` bundles
      images and other resources directly into the HTML output.
  - name: set custom datetime format *(custom datetime java)*
    text: '`setDateTimeFormat` sets the date‑time pattern used when rendering email
      timestamps. Define the pattern that will be used for all timestamps in the rendered
      HTML. *Explanation:* This pattern displays the month, day, year, hour, minute,
      AM/PM marker, and the timezone offset (`zzz`).'
  - name: set timezone offset *(timezone offset java)*
    text: '`setTimeZoneOffset` specifies the time‑zone that will be applied to all
      email timestamps. Adjust timestamps to the desired time zone. *Explanation:*
      Adjusts the rendered timestamps to the desired time zone. Replace `"GMT+1"`
      with any valid zone identifier.'
  - name: render document
    text: Execute the conversion and produce the final HTML file. *Explanation:* Executes
      the conversion, producing an HTML file with your custom date‑time settings.
  type: HowTo
- questions:
  - answer: Attachments are automatically embedded when you use `HtmlViewOptions.forEmbeddedResources()`.
      You can also extract them via the Viewer API if you need separate files.
    question: How do I handle eml files with attachments?
  - answer: Yes, after rendering you can edit the generated HTML file or inject CSS
      programmatically before saving.
    question: Can I change the HTML template or add custom CSS?
  - answer: Wrap the rendering logic in a loop and reuse the same `HtmlViewOptions`
      instance for each file.
    question: Is it possible to render multiple eml files in a batch?
  - answer: GroupDocs.Viewer also supports MSG, PST, and other email containers—simply
      change the file extension in the `Viewer` constructor.
    question: What if I need to support other email formats like msg?
  - answer: Licensing is per deployment; consult the GroupDocs licensing guide for
      multi‑server scenarios.
    question: Do I need a separate license for each server?
  type: FAQPage
tags:
- convert eml
- GroupDocs Viewer
- java email conversion
- email to html
- custom datetime
title: 使用 GroupDocs.Viewer 在 Java 中将 eml 转换为 html 并自定义 datetime
type: docs
url: /zh/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 将 eml 转换为 html 并在 java 中使用 GroupDocs.Viewer 自定义日期时间

在现代的支持和归档系统中，**convert eml to html** 能够快速完成且保持精确时间戳是必备功能。本教程展示如何使用 GroupDocs.Viewer for Java 将 EML 邮件渲染为 HTML，应用 **custom datetime format**，并设置 **timezone offset**。完成后，您将拥有可重复使用的代码片段，能够为任何 **email to html conversion** 工作流生成准确、适合网页展示的邮件视图。

![使用 GroupDocs.Viewer for Java 自定义日期时间渲染邮件](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

## 快速回答
- **Can GroupDocs.Viewer convert EML to HTML?** 是的 —— API 可以直接将 EML 文件渲染为 HTML，无需外部邮件客户端。  
- **Do I need a license for production?** 免费试用可用于测试；生产部署需要付费许可证。  
- **Which Java version is supported?** 完全支持 Java 8 或更高版本。  
- **How do I change the displayed date format?** 调用 `options.getEmailOptions().setDateTimeFormat("MMM dd, yyyy hh:mm a zzz")`。  
- **Can I adjust the time zone?** 可以，使用 `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"))`。

## 什么是 “convert eml to html”？
`Convert eml to html` 是将 EML 邮件文件转换为可在浏览器中渲染的 HTML 文档的过程。将 EML 文件转换为 HTML 会把原始邮件（包括标题、正文和附件）转化为浏览器无需额外插件即可显示的网页友好格式。这使得在 Web 应用、归档或支持仪表板中嵌入邮件变得轻而易举。

## 为什么在此任务中使用 GroupDocs.Viewer？
GroupDocs.Viewer 支持 **50+ 输入和输出格式**，包括 EML、MSG、PST 和 PDF，并且能够在不将整个文件加载到内存的情况下渲染数百页的邮件。其零依赖引擎消除了对 Outlook 或第三方解析器的需求，让您能够完全控制 **custom datetime format** 和 **timezone offset**，同时保持低资源消耗。

## 前置条件
- GroupDocs.Viewer for Java ≥ 25.2  
- JDK 8+ 和 Java IDE（IntelliJ IDEA、Eclipse、VS Code）  
- 用于依赖管理的 Maven  

## 设置 GroupDocs.Viewer for Java

### Maven 配置
将 GroupDocs 仓库和 Viewer 依赖添加到您的 `pom.xml` 文件中。

```xml
<repositories>
    <repository>
        <id>groupdocs-releases</id>
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
先使用免费试用或申请临时许可证进行扩展测试。生产环境请购买完整许可证。

### 基本初始化
创建指向您要转换的 EML 文件的 `Viewer` 实例。

```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## 将 eml 转换为 html 并在 java 中使用自定义日期时间

以下步骤将指导您在渲染 EML 文件为 HTML 时应用自定义日期时间格式和时区偏移。

### 步骤 1：设置输出目录和文件路径
定义生成的 HTML 将保存的位置。

```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*说明:* `Path.of()` 创建对保存 HTML 的文件夹的引用。`resolve()` 添加文件名。

### 步骤 2：使用电子邮件文件初始化 viewer
为目标 EML 文件实例化 `Viewer` 类。

```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*说明:* `Viewer` 实例指向您要转换的 EML 文件。

### 步骤 3：配置 HtmlViewOptions
创建一个 `HtmlViewOptions` 对象，将图像和其他资源直接捆绑到 HTML 输出中。

```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*说明:* `forEmbeddedResources()` 将图像和其他资源直接捆绑到 HTML 输出中。

### 步骤 4：设置自定义日期时间格式 *(custom datetime java)*
`setDateTimeFormat` 设置在渲染邮件时间戳时使用的日期时间模式。  
定义将在渲染的 HTML 中用于所有时间戳的模式。

```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*说明:* 此模式显示月份、日期、年份、小时、分钟、上午/下午标记以及时区偏移 (`zzz`)。

### 步骤 5：设置时区偏移 *(timezone offset java)*
`setTimeZoneOffset` 指定将应用于所有邮件时间戳的时区。  
将时间戳调整为所需的时区。

```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*说明:* 将渲染的时间戳调整为所需的时区。将 `"GMT+1"` 替换为任何有效的时区标识符。

### 如何在 java 中调整电子邮件时区
如果您需要 **adjust email timezone** 超出简单偏移（例如处理夏令时变化），可以使用区域 ID 如 `"Europe/Paris"` 或 `"America/New_York"` 从 `java.util.TimeZone` API 获取相应的 `TimeZone` 对象，并将其传递给 `setTimeZoneOffset`。这可确保邮件时间戳始终反映正确的当地时间。

### 步骤 6：渲染文档
执行转换并生成最终的 HTML 文件。

```java
viewer.view(options);
```
*说明:* 执行转换，生成带有自定义日期时间设置的 HTML 文件。

## 自定义日期时间格式如何影响渲染的 HTML？
自定义日期时间格式决定了每个邮件时间戳在生成的 HTML 中的显示方式，影响可读性和地区合规性。通过指定类似 `"MMM dd, yyyy hh:mm a zzz"` 的模式，您可以确保每个日期一致显示，包含月份缩写、日期、年份、小时、分钟、上午/下午标记以及明确的时区偏移，这对全球支持团队至关重要。

## GroupDocs.Viewer 支持哪些文件格式用于邮件渲染？
GroupDocs.Viewer 可以将 **EML、MSG、PST、MBOX 和 EMLX** 文件渲染为 HTML、PDF、PNG 和 JPEG。它支持超过 50 种文档和图像格式，使您能够在无需额外转换器的情况下将邮件转换为最常见的网页友好输出之一。

## 如何批量转换多个 eml 文件？
将所有 EML 文件放在同一目录中，使用 `for` 或 `foreach` 循环遍历每个文件，复用相同的 `HtmlViewOptions` 实例，并对每个文件调用 `viewer.view`。此方法可最小化对象创建开销并加快批量转换速度。

## 故障排除技巧
- **FileNotFoundException:** 验证 `Viewer` 和 `Path.of()` 中使用的路径。  
- **Incorrect timestamps:** 确保 `TimeZone` ID 与目标地区匹配。  
- **Missing images:** 确认已使用 `HtmlViewOptions.forEmbeddedResources()`；否则可能会遗漏外部资源。

## 实际应用
1. **Email archiving:** 将可搜索的 HTML 邮件快照存储用于合规审计。  
2. **Customer support portals:** 为全球代理展示带有准确本地时间的来票。  
3. **Legal documentation:** 生成符合法院要求的、带有标准化时间戳的邮件记录。

## 性能考虑
- 在专用服务器上部署以进行批量转换。  
- 监控 Java 堆使用情况；如果出现 `OutOfMemoryError`，请增加 `-Xmx`。  
- 当同一邮件被重复请求时缓存渲染的 HTML，以降低 CPU 负载。

## 结论
您现在拥有使用 GroupDocs.Viewer for Java 进行 **convert eml to html**、自定义日期时间格式和时区偏移的完整生产就绪方法。该解决方案提升了可读性，确保时间戳准确，并可无缝集成到归档、支持或法律工作流中。

**下一步:** 探索其他 Viewer 选项，如自定义 CSS 注入、分页或 PDF 转换，以进一步根据您的应用需求定制输出。

## 常见问题

**Q: 如何处理带有附件的 eml 文件？**  
A: 当使用 `HtmlViewOptions.forEmbeddedResources()` 时，附件会自动嵌入。若需要单独的文件，也可以通过 Viewer API 提取它们。

**Q: 我可以更改 HTML 模板或添加自定义 CSS 吗？**  
A: 可以，渲染后您可以编辑生成的 HTML 文件，或在保存前以编程方式注入 CSS。

**Q: 能否批量渲染多个 eml 文件？**  
A: 将渲染逻辑放入循环中，并为每个文件复用相同的 `HtmlViewOptions` 实例。

**Q: 如果需要支持其他邮件格式，如 msg，该怎么办？**  
A: GroupDocs.Viewer 也支持 MSG、PST 等邮件容器——只需在 `Viewer` 构造函数中更改文件扩展名即可。

**Q: 每台服务器是否需要单独的许可证？**  
A: 许可证按部署计费；有关多服务器场景，请参阅 GroupDocs 许可证指南。

## 资源
- [文档](https://docs.groupdocs.com/viewer/java/)
- [API 参考](https://reference.groupdocs.com/viewer/java/)
- [下载](https://releases.groupdocs.com/viewer/java/)
- [购买](https://purchase.groupdocs.com/buy)
- [免费试用](https://releases.groupdocs.com/viewer/java/)
- [临时许可证](https://purchase.groupdocs.com/temporary-license/)
- [支持论坛](https://forum.groupdocs.com/c/viewer/9)

---

**最后更新:** 2026-09-15  
**测试环境:** GroupDocs.Viewer 25.2 (Java)  
**作者:** GroupDocs

## 相关教程
- [将电子邮件转换为 HTML 并重命名字段 – GroupDocs Viewer Java](/viewer/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/)
- [java 将 msg 转换为 pdf – 使用 GroupDocs.Viewer 优化电子邮件到 PDF 的渲染](/viewer/java/performance-optimization/optimize-email-pdf-rendering-java-groupdocs-viewer-api/)
- [Groupdocs Viewer Java 响应式 HTML 渲染](/viewer/java/advanced-rendering/groupdocs-viewer-java-responsive-html-rendering/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}