---
date: '2026-03-24'
description: 了解如何使用 GroupDocs Viewer for Java 将电子邮件转换为 HTML 并重命名电子邮件字段。本指南展示了使用自定义标题将电子邮件渲染为
  HTML。
keywords:
- rename email fields Java
- render emails HTML GroupDocs Viewer
- customize email metadata Java
title: 将电子邮件转换为HTML并重命名字段 – GroupDocs Viewer Java
type: docs
url: /zh/java/advanced-rendering/rename-email-fields-html-groupdocs-viewer-java/
weight: 1
---

# 将电子邮件转换为 HTML 并重命名字段 – GroupDocs Viewer Java

如果您需要 **convert email to HTML** 并为电子邮件标题提供自定义外观，您来对地方了。 在本教程中，我们将逐步演示如何重命名电子邮件字段、**convert email to HTML**，以及使用 GroupDocs.Viewer for Java 自定义电子邮件标题。 完成后，您将获得一个干净的 HTML 表示，其中包含您偏好的标题名称，使输出更易阅读并可集成到您的应用程序中。

![在将电子邮件转换为 HTML 时重命名电子邮件字段 - 使用 GroupDocs.Viewer for Java](/viewer/advanced-rendering/rename-email-fields-when-converting-emails-to-html-java.png)

### 您将学习
- 如何使用 GroupDocs.Viewer for Java 将 **convert email to HTML**。  
- 将 **rename email fields**（如 “From”、 “To”、 “Sent”、 “Subject”）的技术。  
- 设置 Maven 和许可证的最佳实践。  
- 实际场景中 **customizing email headers** 能带来价值。

## 快速答案
- **“convert email to HTML” 是什么意思？** 它表示将电子邮件文件（MSG/EML）渲染为可在网页上显示的 HTML 文档。  
- **哪个库负责转换？** GroupDocs.Viewer for Java (v25.2+)。  
- **我需要许可证吗？** 试用版可用于评估；生产环境需要完整许可证。  
- **我可以更改任何标题名称吗？** 可以，任何标准电子邮件标题都可以通过 `fieldTextMap` 重新映射。  
- **输出是 HTML 还是嵌入资源？** 您可以选择嵌入资源，以获得单个自包含文件。

## 在 GroupDocs.Viewer 中，“convert email to HTML” 是什么？
将电子邮件转换为 HTML 意味着获取原始电子邮件文件并生成一个显示邮件正文及其元数据的 HTML 页面。当您同时 **rename email fields** 时，默认标签（例如 “From”）会被自定义文本（例如 “Sender”）替换，这有助于匹配企业术语或提升 UI 一致性。

## 为什么要将电子邮件转换为 HTML 并重命名电子邮件字段？
- **Consistent branding:** 将输出与组织的语言保持一致。  
- **Improved searchability:** 在归档系统中，定制的标题可以更有效地被索引。  
- **Better UI integration:** 定制 HTML 片段，使其无缝集成到网页门户或支持仪表板中。

## 前提条件

### 必需的库、版本和依赖项
- **GroupDocs.Viewer for Java** – 版本 25.2 或更高。  
- **Java Development Kit (JDK)** – 版本 8+。

### 环境设置要求
- **Maven** 用于依赖管理。  
- IDE 如 IntelliJ IDEA、Eclipse 或 VS Code。

### 知识前提
基础的 Java 和 Maven 知识将帮助您快速跟随教程。

## 设置 GroupDocs.Viewer for Java

### Maven 配置
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

### 获取许可证步骤
- **Free Trial:** 从 [GroupDocs Releases](https://releases.groupdocs.com/viewer/java/) 下载免费试用版。  
- **Temporary License:** 在 [GroupDocs Temporary License](https://purchase.groupdocs.com/temporary-license/) 获取临时许可证，以无限制地探索全部功能。  
- **Purchase:** 若需持续使用，请通过 [GroupDocs Purchase](https://purchase.groupdocs.com/buy) 购买许可证。

### 基本初始化和设置
```java
import com.groupdocs.viewer.Viewer;

public class ViewerSetup {
    public static void main(String[] args) {
        try (Viewer viewer = new Viewer("path/to/your/document.msg")) {
            // Perform operations here
        }
    }
}
```
将文件路径调整为指向您的 `.msg` 文件。

## 如何将电子邮件转换为 HTML 并重命名字段 – 步骤详解

### 1. 设置输出目录路径
```java
import java.nio.file.Path;

Path outputDirectory = Utils.getOutputDirectoryPath("YOUR_OUTPUT_DIRECTORY");
```
*将 `"YOUR_OUTPUT_DIRECTORY"` 替换为您希望保存 HTML 文件的文件夹。*

### 2. 定义页面文件路径格式
```java
Path pageFilePathFormat = outputDirectory.resolve("page_{0}.html");
```
*渲染时，`{0}` 将被页面编号替换。*

### 3. 创建电子邮件字段到新名称的映射
```java
import com.groupdocs.viewer.options.Field;
import java.util.HashMap;
import java.util.Map;

Map<Field, String> fieldTextMap = new HashMap<>();
fieldTextMap.put(Field.FROM, "Sender");
fieldTextMap.put(Field.TO, "Receiver");
fieldTextMap.put(Field.SENT, "Date");
fieldTextMap.put(Field.SUBJECT, "Topic");
```
*此处将默认标签更改为自定义标签。*

### 4. 配置 HTML 视图选项
```java
import com.groupdocs.viewer.options.HtmlViewOptions;

HtmlViewOptions viewOptions = HtmlViewOptions.forEmbeddedResources(pageFilePathFormat);
viewOptions.getEmailOptions().setFieldTextMap(fieldTextMap);
```
*`forEmbeddedResources` 将 CSS/JS 打包到 HTML 中，而 `setFieldTextMap` 应用自定义标题名称。*

### 5. 将电子邮件渲染为 HTML
```java
try (Viewer viewer = new Viewer("YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG")) {
    viewer.view(viewOptions);
}
```
*将 `"YOUR_DOCUMENT_DIRECTORY/SAMPLE_MSG"` 替换为实际的 MSG 文件路径。*

#### 故障排除提示
- 确认输出目录可写。  
- 确保输入的 MSG 文件存在且路径正确。  
- 使用与 Maven 中声明的相同的 GroupDocs.Viewer 版本（25.2）。

## 实际应用
1. **Custom Email Reports:** 将电子邮件标题与企业术语对齐，以获得更清晰的报告。  
2. **Email Archiving Systems:** 通过使用标准化的标题名称提升可搜索性。  
3. **Customer Support Platforms:** 使用个性化的标题标签呈现工单，以提升客服体验。

## 性能考虑
- 使用 try‑with‑resources 释放 `Viewer` 对象，以快速回收内存。  
- 对大批量进行性能分析，必要时考虑使用并行流处理电子邮件。

## 结论
您现在了解了如何使用 GroupDocs.Viewer for Java **convert email to HTML**、**rename email fields** 和 **customize email headers**。此技术让您完全掌控 HTML 输出中电子邮件元数据的呈现方式。

### 下一步
- 尝试更多字段映射（例如 CC、BCC）。  
- 探索其他渲染格式，如 PDF 或 PNG。  
- 访问 [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) 获取更深入的 API 见解。

## 常见问题

**Q: 此方法是否适用于其他电子邮件格式，如 EML？**  
A: 是的，GroupDocs.Viewer 支持 MSG 和 EML 文件；相同的字段映射逻辑适用。

**Q: 我可以输出不包含嵌入资源的 HTML 吗？**  
A: 如果您更喜欢使用独立的 CSS/JS 文件，可以使用 `HtmlViewOptions.forExternalResources(...)`。

**Q: 测试使用的 GroupDocs.Viewer 版本是什么？**  
A: 代码已在 GroupDocs.Viewer **25.2** 上测试。

**Q: 能否更改自定义标题的字体或样式？**  
A: 渲染后可通过 CSS 应用样式，或使用 `HtmlViewOptions.getResourcesPath()` 注入自定义 CSS。

**Q: 如何以编程方式获取生成的 HTML 文件路径？**  
A: 文件路径遵循 `pageFilePathFormat` 中定义的模式；您可以使用 `String.format` 并传入页码来构建它。

## 资源
- **Documentation:** 完整指南可在 [GroupDocs Documentation](https://docs.groupdocs.com/viewer/java/) 查看。  
- **API Reference:** 详细的 API 信息可在 [GroupDocs API Reference](https://reference.groupdocs.com/viewer/java/) 找到。  
- **Download GroupDocs.Viewer:** 可通过 [Downloads Page](https://releases.groupdocs.com/viewer/java/) 获取最新版本。

---

**最后更新：** 2026-03-24  
**测试版本：** GroupDocs.Viewer 25.2  
**作者：** GroupDocs