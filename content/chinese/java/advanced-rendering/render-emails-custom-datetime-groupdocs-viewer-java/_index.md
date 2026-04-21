---
date: '2026-03-24'
description: 学习如何使用 GroupDocs.Viewer 在 Java 中将 EML 转换为 HTML，使用自定义日期时间格式并设置时区偏移。非常适用于电子邮件归档和支持系统。
keywords:
- render emails with custom datetime
- GroupDocs Viewer for Java
- email rendering HTML
title: 使用 GroupDocs.Viewer 在 Java 中将 EML 转换为 HTML 并自定义日期时间
type: docs
url: /zh/java/advanced-rendering/render-emails-custom-datetime-groupdocs-viewer-java/
weight: 1
---

# 使用 GroupDocs.Viewer 在 Java 中将 EML 转换为 HTML 并自定义日期时间

在当今快节奏的数字世界中，能够快速 **将 EML 转换为 HTML** 并以正确的日期时间呈现对于归档、支持门户和法律合规至关重要。本教程将指导您使用 GroupDocs.Viewer for Java 将电子邮件渲染为 HTML，同时应用 **自定义日期时间格式** 和 **时区偏移**。完成后，您将拥有一个可重复使用的解决方案，确保时间戳准确且易读，完美适用于任何 **email to HTML Java** 工作流。

![使用 GroupDocs.Viewer for Java 渲染带自定义日期时间的电子邮件](/viewer/advanced-rendering/render-emails-with-custom-datetime-java.png)

**您将学习**
- 如何在 Java 项目中设置 GroupDocs.Viewer  
- 如何将电子邮件渲染为带嵌入资源的 HTML  
- 如何 **自定义电子邮件的日期时间格式**（custom datetime java）  
- 如何 **设置时区偏移** 以获得正确的时间戳（timezone offset java）  

## 快速答案
- **GroupDocs.Viewer 能将 EML 转换为 HTML 吗？** 是的，它直接将 EML 文件渲染为 HTML。  
- **我需要许可证吗？** 免费试用可用于测试；生产环境需要付费许可证。  
- **需要哪个 Java 版本？** Java 8 或更高版本。  
- **如何更改显示的日期格式？** 使用 `options.getEmailOptions().setDateTimeFormat(...)`。  
- **我可以调整时区吗？** 可以，使用 `options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone(...))`。

## 什么是 “convert EML to HTML”？
将 EML 文件转换为 HTML 会将原始电子邮件（包括标题、正文和附件）转换为浏览器无需额外插件即可显示的网页友好格式。这使得在 Web 应用程序、归档或支持仪表板中嵌入电子邮件变得轻而易举。

## 为什么要使用 GroupDocs.Viewer 完成此任务？
- **零依赖渲染** – 无需 Outlook 或外部邮件解析器。  
- **内置对嵌入资源的支持**（图像、附件）。  
- **细粒度控制** 日期时间格式和时区处理。  

## 前置条件

- **GroupDocs.Viewer for Java** 版本 25.2 或更高。  
- **Java Development Kit (JDK)** 8+ 以及 IDE（IntelliJ IDEA、Eclipse 等）。  
- 基本的 Java 知识并熟悉 Maven。  

## 设置 GroupDocs.Viewer for Java

### Maven 配置
将 GroupDocs 仓库和依赖添加到您的 `pom.xml`：

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
先使用免费试用或请求临时许可证以进行扩展测试。生产环境请购买完整许可证。

### 基本初始化
```java
import com.groupdocs.viewer.Viewer;

// Initialize Viewer with the path to your document
try (Viewer viewer = new Viewer("path/to/your/document.eml")) {
    // Perform operations here
}
```

## 使用 Java 将 EML 转换为 HTML 并自定义日期时间

以下分步指南展示了如何在应用自定义日期时间格式和时区偏移的同时 **将 EML 转换为 HTML**。

### 步骤 1：设置输出目录和文件路径
```java
import java.nio.file.Path;

Path outputDirectory = Path.of("YOUR_OUTPUT_DIRECTORY");
Path filePath = outputDirectory.resolve("output.html");
```
*解释:* `Path.of()` 创建指向保存 HTML 的文件夹的引用。`resolve()` 添加文件名。

### 步骤 2：使用电子邮件文件初始化 Viewer
```java
import com.groupdocs.viewer.Viewer;

try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_EML")) {
    // Further configuration goes here
}
```
*解释:* `Viewer` 实例指向您想要转换的 EML 文件。

### 步骤 3：配置 HtmlViewOptions
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions options = HtmlViewOptions.forEmbeddedResources(filePath);
```
*解释:* `forEmbeddedResources()` 将图像和其他资源直接打包到 HTML 输出中。

### 步骤 4：设置自定义日期时间格式 *(custom datetime java)*
```java
options.getEmailOptions().setDateTimeFormat("MM d yyyy HH:mm tt zzz");
```
*解释:* 此模式显示月份、日期、年份、小时、分钟、上午/下午标记以及时区偏移 (`zzz`)。

### 步骤 5：设置时区偏移 *(timezone offset java)*
```java
import java.util.TimeZone;

options.getEmailOptions().setTimeZoneOffset(TimeZone.getTimeZone("GMT+1"));
```
*解释:* 将渲染的时间戳调整到所需时区。将 `"GMT+1"` 替换为任何有效的时区标识符。

### 如何在 Java 中调整电子邮件时区
如果您需要 **调整电子邮件时区**，不仅仅是简单的偏移——例如处理夏令时变化——可以使用区域 ID（如 `"Europe/Paris"` 或 `"America/New_York"`）从 `java.util.TimeZone` API 获取相应的 `TimeZone` 对象，并将其传递给 `setTimeZoneOffset`。这可确保电子邮件时间戳始终反映正确的当地时间。

### 步骤 6：渲染文档
```java
viewer.view(options);
```
*解释:* 执行转换，生成带有自定义日期时间设置的 HTML 文件。

## 故障排除技巧
- **FileNotFoundException:** 仔细检查 `Viewer` 和 `Path.of()` 中使用的路径。  
- **Incorrect timestamps:** 验证 `TimeZone` ID 是否与目标地区匹配。  
- **Missing images:** 确保使用了 `HtmlViewOptions.forEmbeddedResources()`；否则，外部资源可能未被包含。  

## 实际应用
1. **Email Archiving:** 将可搜索的电子邮件 HTML 快照存储用于合规。  
2. **Customer Support Portals:** 显示带有准确本地时间的来票。  
3. **Legal Documentation:** 生成符合标准时间戳的法庭可用电子邮件记录。  

## 性能考虑
- 在专用服务器上部署以进行批量转换。  
- 监控 Java 堆使用情况；如果遇到 `OutOfMemoryError`，请增加 `-Xmx`。  
- 当同一封电子邮件被重复请求时，缓存渲染后的 HTML。  

## 结论
您现在拥有一个完整的、可用于生产环境的方案，使用 GroupDocs.Viewer for Java **将 EML 转换为 HTML**，并自定义日期时间格式和时区偏移。这提升了可读性，确保时间戳的准确性，并能无缝融入归档或支持工作流。

**下一步：** 探索其他 Viewer 选项，如 CSS 样式、分页或 PDF 转换，以进一步满足您的需求。

## 常见问题

**问：如何处理带附件的 EML 文件？**  
A: 使用 `HtmlViewOptions.forEmbeddedResources()` 时，附件会自动嵌入。如有需要，也可以通过 Viewer API 提取它们。

**问：我可以更改 HTML 模板或添加自定义 CSS 吗？**  
A: 可以，渲染后您可以编辑生成的 HTML 文件，或在保存前以编程方式注入 CSS。

**问：是否可以批量渲染多个 EML 文件？**  
A: 将渲染逻辑放入循环中，并对每个文件复用同一个 `HtmlViewOptions` 实例。

**问：如果需要支持其他邮件格式，如 MSG，该怎么办？**  
A: GroupDocs.Viewer 也支持 MSG、PST 等邮件容器——只需在 `Viewer` 构造函数中更改文件扩展名即可。

**问：每台服务器是否需要单独的许可证？**  
A: 许可证按部署计费；请查阅 GroupDocs 许可证指南了解多服务器场景。

## 资源

- [文档](https://docs.groupdocs.com/viewer/java/)
- [API 参考](https://reference.groupdocs.com/viewer/java/)
- [下载](https://releases.groupdocs.com/viewer/java/)
- [购买](https://purchase.groupdocs.com/buy)
- [免费试用](https://releases.groupdocs.com/viewer/java/)
- [临时许可证](https://purchase.groupdocs.com/temporary-license/)
- [支持论坛](https://forum.groupdocs.com/c/viewer/9)

---

**最后更新：** 2026-03-24  
**测试环境：** GroupDocs.Viewer 25.2 (Java)  
**作者：** GroupDocs