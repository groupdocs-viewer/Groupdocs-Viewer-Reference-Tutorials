---
date: '2026-01-10'
description: 了解如何使用 GroupDocs.Viewer 在 Java 中将 EML 转换为 HTML，并自定义日期时间格式和设置时区偏移。非常适用于电子邮件归档和支持系统。
keywords:
- render emails with custom datetime
- GroupDocs Viewer for Java
- email rendering HTML
title: 使用 GroupDocs.Viewer 在 Java 中将 EML 转换为 HTML 并自定义日期时间
type: docs
url: /zh/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# 使用 GroupDocs.Viewer 将 EML 转换为 HTML 并自定义 Java 中的日期时间

## 介绍

在当今节奏快速的数字世界中，能够 **将 EML 转换为 HTML** 并以正确的日期时间展示方式快速完成转换，对于归档、支持门户和法律合规至关重要。本教程将指导您使用 GroupDocs.Viewer for Java 将电子邮件渲染为 HTML，同时应用 **自定义日期时间格式** 和 **时区偏移**。完成后，您将拥有一个可重复使用的解决方案，使时间戳保持准确且易读。

![使用 GroupDocs.Viewer for Java 渲染带自定义日期时间的电子邮件](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

**您将学习的内容**
- 如何在 Java 项目中设置 GroupDocs.Viewer  
- 如何将电子邮件渲染为带嵌入资源的 HTML  
- 如何 **自定义电子邮件的日期时间格式**（custom datetime format java）  
- 如何 **设置时区偏移** 以获得正确的时间戳（set timezone offset java）  

## 快速答案
- **GroupDocs.Viewer 能将 EML 转换为 HTML 吗？** 能，它可以直接将 EML 文件渲染为 HTML。  
- **需要许可证吗？** 免费试用可用于测试；生产环境需要付费许可证。  
- **需要哪个 Java 版本？** Java 8 或更高版本。  
- **如何更改显示的日期格式？** 使用 `options.getEmailOptions().setDateTimeFormat(...)`。  
- **可以调整时区吗？** 可以，使用 `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone(...))`。

## 什么是“convert EML to HTML”？
将 EML 文件转换为 HTML 会把原始电子邮件（包括标题、正文和附件）转换为浏览器无需额外插件即可显示的网页友好格式。这使得在 Web 应用、归档或支持仪表板中嵌入电子邮件变得非常简便。

## 为什么在此任务中使用 GroupDocs.Viewer？
- **零依赖渲染** – 无需 Outlook 或外部邮件解析器。  
- **内置对嵌入资源的支持**（图片、附件）。  
- **对日期时间格式和时区处理的细粒度控制**。  

## 前提条件

- **GroupDocs.Viewer for Java** 版本 25.2 或更高。  
- **Java Development Kit (JDK)** 8+ 以及 IDE（IntelliJ IDEA、Eclipse 等）。  
- 基本的 Java 知识并熟悉 Maven。

## 为 Java 设置 GroupDocs.Viewer

### Maven 配置
将 GroupDocs 仓库和依赖添加到您的 `pom.xml` 中：

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

### 许可证获取
先使用免费试用或申请临时许可证进行扩展测试。生产环境请购买正式许可证。

### 基本初始化
```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## 使用 Java 将 EML 转换为 HTML 并自定义日期时间

以下分步指南展示了如何在 **将 EML 转换为 HTML** 的同时应用自定义日期时间格式和时区偏移。

### 步骤 1：设置输出目录和文件路径
```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*说明：* `Path.of()` 用于创建保存 HTML 的文件夹引用。`resolve()` 会在其后追加文件名。

### 步骤 2：使用电子邮件文件初始化 Viewer
```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*说明：* `Viewer` 实例指向您想要转换的 EML 文件。

### 步骤 3：配置 HtmlViewOptions
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*说明：* `forEmbeddedResources()` 会将图像和其他资源直接嵌入到 HTML 输出中。

### 步骤 4：设置自定义日期时间格式 *(custom datetime format java)*
```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*说明：* 此模式会显示月份、日期、年份、小时、分钟、AM/PM 标记以及时区偏移 (`zzz`)。

### 步骤 5：设置时区偏移 *(set timezone offset java)*
```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*说明：* 将渲染的时间戳调整到所需时区。将 `"GMT+1"` 替换为任意有效的时区标识符。

### 步骤 6：渲染文档
```java
viewer.view(options);
```
*说明：* 执行转换，生成带有自定义日期时间设置的 HTML 文件。

## 故障排除技巧
- **FileNotFoundException：** 检查 `Viewer` 和 `Path.of()` 中使用的路径是否正确。  
- **时间戳不正确：** 确认 `TimeZone` ID 与目标地区匹配。  
- **图片缺失：** 确保使用了 `HtmlViewOptions.forEmbeddedResources()`；否则外部资源可能不会被包含。  

## 实际应用
1. **电子邮件归档：** 将可搜索的 HTML 快照存储用于合规。  
2. **客户支持门户：** 显示带有准确本地时间的来件工单。  
3. **法律文档：** 生成符合标准时间戳的法庭级电子邮件记录。  

## 性能考虑
- 在专用服务器上部署以处理批量转换。  
- 监控 Java 堆内存使用情况；如出现 `OutOfMemoryError`，请增加 `-Xmx` 参数。  
- 对相同邮件的重复请求，可缓存已渲染的 HTML。  

## 结论
现在，您已经掌握了一套完整的、可用于生产环境的 **将 EML 转换为 HTML** 方法，能够通过自定义日期时间格式和时区偏移提升可读性、确保时间戳准确，并轻松融入归档或支持工作流。

**后续步骤：** 探索 Viewer 的其他选项，如 CSS 样式、分页或 PDF 转换，以进一步定制输出以满足您的需求。

## 常见问题

**问：如何处理带附件的 EML 文件？**  
答：使用 `HtmlViewOptions.forEmbeddedResources()` 时，附件会自动嵌入。若需要，也可以通过 Viewer API 提取附件。

**问：可以更改 HTML 模板或添加自定义 CSS 吗？**  
答：可以，渲染后您可以编辑生成的 HTML 文件或在保存前以编程方式注入 CSS。

**问：是否可以批量渲染多个 EML 文件？**  
答：可以，将渲染逻辑放入循环中，并为每个文件复用同一个 `HtmlViewOptions` 实例。

**问：如果需要支持其他邮件格式如 MSG，怎么办？**  
答：GroupDocs.Viewer 同样支持 MSG、PST 等邮件容器，只需在 `Viewer` 构造函数中更改文件扩展名即可。

**问：每台服务器是否需要单独的许可证？**  
答：许可证按部署计费；多服务器场景请参考 GroupDocs 许可证指南。

## 资源

- [Documentation](https://docs.groupdocs.com/viewer/java/)
- [API Reference](https://reference.groupdocs.com/viewer/java/)
- [Download](https://releases.groupdocs.com/viewer/java/)
- [Purchase](https://purchase.groupdocs.com/buy)
- [Free Trial](https://releases.groupdocs.com/viewer/java/)
- [Temporary License](https://purchase.groupdocs.com/temporary-license/)
- [Support Forum](https://forum.groupdocs.com/c/viewer/9)

---

**最后更新：** 2026-01-10  
**测试环境：** GroupDocs.Viewer 25.2 (Java)  
**作者：** GroupDocs